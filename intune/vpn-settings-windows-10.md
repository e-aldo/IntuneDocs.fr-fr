---
title: Afficher les paramètres VPN dans Microsoft Intune - Azure | Microsoft Docs
description: Découvrez les paramètres VPN disponibles dans Microsoft Intune, à quoi ils servent et ce qu’ils font, notamment les règles de trafic, l’accès conditionnel et les paramètres DNS et de proxy pour les appareils Windows 10 et les appareils Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 9464b73acc43b9625560156617359c374d7100fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Découvrir les paramètres VPN dans Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Vous pouvez configurer des connexions VPN avec Intune. Cet article décrit ces paramètres, les règles de trafic, l’accès conditionnel, ainsi que les paramètres DNS et de proxy.

Ces paramètres s’appliquent aux :

- Appareils exécutant Windows 10
- Appareils exécutant Windows Holographic for Business

Selon les paramètres que vous choisissez, toutes les valeurs ne sont pas nécessairement configurables.

## <a name="base-vpn-settings"></a>Paramètres VPN de base

- **Nom de connexion** : entrez un nom pour cette connexion. Les utilisateurs finaux voient ce nom quand ils recherchent dans leur appareil la liste des connexions VPN disponibles.
- **Serveurs** : ajoutez un ou plusieurs serveurs VPN auxquels les appareils se connectent.
  - **Ajouter** : ouvre **Ajouter une ligne** où vous entrez les informations suivantes :
    - **Description** : entrez un nom descriptif pour le serveur, comme **Serveur VPN Contoso**.
    - **Adresse IP ou nom de domaine complet** : entrez l’adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent, comme **192.168.1.1** ou **vpn.contoso.com**.
    - **Serveur par défaut** : active ce serveur comme serveur par défaut que les appareils utilisent pour établir la connexion. Ne définissez qu’un seul serveur par défaut.
  - **Importer** : accédez à un fichier séparé par des virgules contenant une liste de serveurs au format description, adresse IP ou nom de domaine complet, serveur par défaut. Choisissez **OK** pour importer ces serveurs dans la liste **Serveurs**.
  - **Exporter** : exporte la liste des serveurs dans un fichier de valeurs séparées par des virgules (csv).

**Type de connexion** : sélectionnez le type de connexion VPN dans la liste de fournisseurs suivante :

- **Automatique**
- **Check Point Capsule VPN**
- **Citrix VPN** (VPN Citrix)
- **SonicWALL Mobile Connect**
- **Client F5 Edge**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Groupe de connexion ou domaine** (SonicWALL Mobile Connect uniquement) : cette propriété ne peut pas être définie dans le profil VPN. À la place, Mobile Connect analyse cette valeur lorsque le nom d’utilisateur et le domaine sont entrés dans les formats `username@domain` ou `DOMAIN\username`.

**XML personnalisé**/**EAP XML** : entrez des commandes XML personnalisées qui configurent la connexion VPN.

**Exemple pour Pulse Secure :**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Exemple pour CheckPoint Mobile VPN :**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Exemple pour SonicWALL Mobile Connect :**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Exemple pour Client F5 Edge :**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Pour plus d’informations sur l’écriture des commandes XML personnalisées, consultez la documentation du VPN de chaque fabricant.

Pour plus d’informations sur la création de code XML EAP personnalisé, consultez [Configuration EAP](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Tunneling fractionné** : **activez**ou **désactivez** cette option pour laisser les appareils décider quelle connexion utiliser en fonction du trafic. Par exemple, un utilisateur dans un hôtel utilise la connexion VPN pour accéder à ses fichiers de travail, mais utilise le réseau standard de l’hôtel pour surfer sur Internet.
- **Fractionner les itinéraires de tunneling pour cette connexion VPN** : ajoutez des itinéraires facultatifs pour les fournisseurs VPN tiers. Entrez un préfixe de destination et une taille de préfixe pour chacun.

## <a name="apps-and-traffic-rules"></a>Règles de trafic et d’application

**Limiter la connexion VPN à ces applications** : activez cette option si vous souhaitez que seules certaines applications utilisent la connexion VPN.
**Applications associées** : entrez une liste d’applications qui utilisent automatiquement la connexion VPN. Le type d'application détermine l'identificateur de l'application. Pour une application universelle, entrez le nom de famille du package. Pour une application de bureau, indiquez le chemin de l’application.

>[!IMPORTANT]
>Nous vous recommandons de sécuriser toutes les listes d’applications créées pour des VPN par application. Si un utilisateur non autorisé modifie cette liste et que vous l’importez dans la liste d’applications du VPN par application, vous autorisez alors potentiellement un accès VPN à des applications qui ne doivent pas y avoir accès. Pour sécuriser les listes d’applications, vous avez la possibilité d’utiliser une liste de contrôle d’accès (liste ACL).

**Règles de trafic réseau pour cette connexion VPN** : sélectionnez les protocoles, les ports locaux/distants et les plages d’adresses à activer pour la connexion VPN. Si vous ne créez pas de règle de trafic réseau, tous les protocoles, les ports et les plages d’adresses sont alors activés. Une fois qu’une règle est créée, la connexion VPN utilise uniquement les protocoles, les ports et les plages d’adresses que vous entrez dans cette règle.

## <a name="conditional-access"></a>Accès conditionnel

**Accès conditionnel pour cette connexion VPN** : active le flux de conformité des appareils à partir du client. Quand cette option est activée, le client VPN tente de communiquer avec Azure Active Directory pour obtenir un certificat à utiliser pour l’authentification. Le VPN doit être configuré pour utiliser l’authentification par certificat, et le serveur VPN doit approuver le serveur retourné par Azure Active Directory.

**Authentification unique avec certificat de remplacement** : pour la conformité des appareils, utilisez un certificat autre que le certificat d’authentification VPN pour l’authentification Kerberos. Entrez le certificat avec les paramètres suivants :

- **Utilisation améliorée de la clé** : nom de l’utilisation améliorée de la clé
- **Identificateur d’objet** : identificateur d’objet pour l’utilisation améliorée de la clé
- **Hachage de l’émetteur** : empreinte numérique du certificat SSO

## <a name="dns-settings"></a>Paramètres DNS

**Noms et serveurs DNS pour cette connexion VPN** : sélectionnez les serveurs DNS utilisés par la connexion VPN quand celle-ci est établie.
Pour chaque serveur, entrez :
- **Nom DNS**
- **Serveur DNS**
- **Proxy**

## <a name="proxy-settings"></a>Paramètres du proxy

- **Détecter automatiquement les paramètres du proxy** : si votre serveur VPN requiert un serveur proxy pour la connexion, indiquez si vous souhaitez que les appareils détectent automatiquement les paramètres de connexion.
- **Script de configuration automatique** : utilisez un fichier de configuration pour configurer le serveur proxy. Entrez l’**URL du serveur Proxy**, comme `http://proxy.contoso.com`, qui contient le fichier de configuration.
- **Utiliser un serveur proxy** : activez cette option pour entrer manuellement les paramètres du serveur proxy.
  - **Adresse** : entrez l’adresse du serveur proxy (comme une adresse IP).
  - **Numéro de port** : entrez le numéro de port associé au serveur proxy.
- **Contourner le proxy pour les adresses locales** : si votre serveur VPN requiert un serveur proxy pour la connexion, sélectionnez ce paramètre si vous ne souhaitez pas utiliser le serveur proxy pour les adresses locales que vous entrez.
