---
title: "Paramètres VPN Intune pour les appareils Windows 10"
titlesuffix: Azure portal
description: "Découvrez les paramètres Intune que vous pouvez utiliser pour configurer des connexions VPN sur les appareils Windows 10."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 54ff681c96dc01587cd9a2770dacc5bb9a54d134
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2017
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Paramètres VPN pour les appareils Windows 10 dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Selon les paramètres que vous choisissez, toutes les valeurs dans la liste ci-dessous ne peuvent pas nécessairement être configurées.


## <a name="base-vpn-settings"></a>Paramètres VPN de base


- **Nom de connexion** : saisissez un nom pour cette connexion. Les utilisateurs finaux voient ce nom lorsqu’ils consultent leur appareil pour obtenir la liste des connexions VPN disponibles.
- **Serveurs** : ajoutez un ou plusieurs serveurs VPN auxquels les appareils se connectent.
    - **Ajouter** : ouvre le panneau **Ajouter une ligne** dans lequel vous pouvez spécifier les informations suivantes :
        - **Description** : spécifiez un nom descriptif pour le serveur, comme **Serveur VPN Contoso**.
        - **Adresse IP ou nom de domaine complet** : fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. Exemples : **192.168.1.1**, **vpn.contoso.com**.
        - **Serveur par défaut** : active ce serveur comme serveur par défaut que les appareils utiliseront pour établir la connexion. Veillez à ne définir qu’un seul serveur par défaut.
    - **Importer** : accédez à un fichier qui contient une liste séparée par des virgules de serveurs au format description, adresse IP ou nom de domaine complet, serveur par défaut. Choisissez **OK** pour les importer dans la liste **Serveurs**.
    - **Exporter** : exporte la liste des serveurs dans un fichier de valeurs séparées par des virgules (csv).

**Type de connexion** : sélectionnez le type de connexion VPN à partir de la liste de fournisseurs suivante :
- **Automatique**
- **Check Point Capsule VPN**
- **Citrix VPN** (VPN Citrix)
- **Dell SonicWALL Mobile Connect**
- **Client F5 Edge**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**


**Groupe de connexion ou domaine** (Dell SonicWALL Mobile Connect uniquement) : spécifiez le nom du groupe de connexion ou domaine auquel vous souhaitez vous connecter.

**XML personnalisé**/**EAP XML** : spécifiez des commandes XML personnalisées qui configurent la connexion VPN.

**Exemple pour Pulse Secure :**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Exemple pour CheckPoint Mobile VPN :**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Exemple pour Dell SonicWALL Mobile Connect :**

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Exemple pour Client F5 Edge :**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Pour plus d’informations sur l’écriture des commandes XML personnalisées, reportez-vous à la documentation du VPN de chaque fabricant.

**Tunneling fractionné** - **Activez** ou **Désactivez** cette option qui permet aux appareils de décider de la connexion à utiliser en fonction du trafic. Par exemple, un utilisateur dans un hôtel utilisera la connexion VPN pour accéder aux fichiers de travail, mais utilisera le réseau standard de l’hôtel pour la navigation web ordinaire.
- **Fractionner les itinéraires de tunneling pour cette connexion VPN** : ajoutez éventuellement des itinéraires pour les fournisseurs de VPN tiers. Spécifiez un préfixe de destination et une taille de préfixe pour chacun.

## <a name="apps-and-traffic-rules"></a>Règles de trafic et d’application

**Limiter la connexion VPN à ces applications** : activez cette option si vous souhaitez seules les applications que vous spécifiez puissent utiliser la connexion VPN.
**Applications associées** : vous pouvez fournir une liste d'applications qui utiliseront automatiquement la connexion VPN. Le type d'application détermine l'identificateur de l'application. Pour une application universelle, indiquez le nom de famille du package. Pour une application de bureau, indiquez le chemin de l’application.

>[!IMPORTANT]
>Nous vous recommandons de sécuriser toutes les listes d’applications que vous compilez pour les utiliser dans la configuration d’un VPN par application. Si un utilisateur non autorisé modifie votre liste et que vous l’importez dans la liste des applications du VPN par application, vous autorisez potentiellement un accès VPN à des applications qui ne doivent pas y avoir accès. Pour sécuriser les listes d’applications, vous avez la possibilité d’utiliser une liste de contrôle d’accès (liste ACL).

**Règles de trafic réseau pour cette connexion VPN** : sélectionnez les protocoles, les ports locaux/distants et les plages d’adresses à activer pour la connexion VPN. Si vous ne créez pas de règle de trafic réseau, tous les protocoles, les ports et les plages d’adresses sont activés. Une fois qu’une règle est créée, la connexion VPN utilise uniquement les protocoles, les ports et les plages d’adresses que vous spécifiez dans cette règle.


## <a name="conditional-access"></a>Accès conditionnel

**Accès conditionnel pour cette connexion VPN** : Active le flux de conformité des appareils à partir du client. Quand cette option est activée, le client VPN tente de communiquer avec Azure Active Directory pour obtenir un certificat à utiliser pour l’authentification. Le VPN doit être configuré pour utiliser l’authentification par certificat, et le serveur VPN doit approuver le serveur retourné par Azure Active Directory.

**Authentification unique avec certificat de remplacement** : Pour la conformité des appareils, utilisez un certificat autre que le certificat d’authentification VPN pour l’authentification Kerberos. Spécifiez le certificat avec les paramètres suivants : 

- **Utilisation améliorée de la clé** : Nom de l’utilisation améliorée de la clé.
- **Identificateur d’objet** : Identificateur d’objet pour l’utilisation améliorée de la clé.
- **Hachage de l’émetteur** : Empreinte numérique du certificat SSO.

## <a name="dns-settings"></a>Paramètres DNS

**Noms et serveurs DNS pour cette connexion VPN** : sélectionnez les serveurs DNS qu’utilisera la connexion VPN quand celle-ci sera établie.
Pour chaque serveur. spécifiez :
- **Nom DNS**
- **Serveur DNS**
- **Proxy**

## <a name="proxy-settings"></a>Paramètres du proxy

- **Détecter automatiquement les paramètres du proxy** : si votre serveur VPN nécessite un serveur proxy pour la connexion, spécifiez si vous souhaitez que les appareils détectent automatiquement les paramètres de connexion. Pour plus d'informations, consultez la documentation de Windows Server.
- **Script de configuration automatique** : utilisez un fichier de configuration pour configurer le serveur proxy. Saisissez **l’URL du serveur proxy** (par exemple **http://proxy.contoso.com**) qui contient le fichier de configuration.
- **Utiliser un serveur proxy** : activez cette option si vous souhaitez saisir manuellement les paramètres du serveur proxy.
    - **Adresse** : saisissez l’adresse du serveur proxy (comme une adresse IP).
    - **Numéro de port** : saisissez le numéro de port associé au serveur proxy.
- **Contourner le proxy pour les adresses locales** : si votre serveur VPN nécessite un serveur proxy pour la connexion, sélectionnez cette option si vous ne souhaitez pas utiliser le serveur proxy pour les adresses locales que vous spécifiez. Pour plus d'informations, consultez la documentation de Windows Server.
