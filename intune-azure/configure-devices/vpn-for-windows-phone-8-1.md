---
title: "Paramètres de VPN Intune pour les appareils Windows Phone 8.1"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres Windows Intune que vous pouvez utiliser pour configurer des connexions VPN sur les appareils Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 2fe54f4d97c28825f06d40ec47a8a9dc40da2554
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Paramètres VPN pour les appareils Windows Phone 8.1 dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Selon les paramètres que vous choisissez, toutes les valeurs dans la liste ci-dessous ne peuvent pas nécessairement être configurées.

## <a name="base-vpn-settings"></a>Paramètres VPN de base

- **Appliquer tous les paramètres à Windows Phone 8.1 uniquement** : il s’agit d’un paramètre que vous pouvez configurer dans le portail Intune classique. Dans le portail Azure, ce paramètre ne peut pas être modifié. Si la valeur est définie sur **Configuré**, les paramètres seront uniquement appliqués aux appareils Windows Phone 8.1. Si la valeur est **Non configuré**, ces paramètres s’appliqueront également aux appareils Windows 10 Mobile.
- **Nom de connexion** : saisissez un nom pour cette connexion. Les utilisateurs finaux voient ce nom lorsqu’ils consultent leur appareil pour obtenir la liste des connexions VPN disponibles.
- **Méthode d’authentification** : choisissez la façon dont les appareils s’authentifient auprès du serveur VPN à partir de :
    - **Certificats** : sous **Certificat d’authentification**, choisissez le profil de certificat SCEP ou PKCS que vous avez créé précédemment pour authentifier la connexion. Pour plus d’informations sur les profils de certificat, consultez [Guide pratique pour configurer des certificats](how-to-configure-certificates.md).
    - **Nom d’utilisateur et mot de passe** : les utilisateurs finaux doivent fournir un nom d’utilisateur et un mot de passe pour se connecter au serveur VPN.
- **Serveurs** : ajoutez un ou plusieurs serveurs VPN auxquels les appareils se connectent.
    - **Ajouter** : ouvre le panneau **Ajouter une ligne** dans lequel vous pouvez spécifier les informations suivantes :
        - **Description** : spécifiez un nom descriptif pour le serveur, comme **Serveur VPN Contoso**.
        - **Adresse IP ou nom de domaine complet** : fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. Exemples : **192.168.1.1**, **vpn.contoso.com**.
        - **Serveur par défaut** : active ce serveur comme serveur par défaut que les appareils utiliseront pour établir la connexion. Veillez à ne définir qu’un seul serveur par défaut.
    - **Importer** : accédez à un fichier qui contient une liste séparée par des virgules de serveurs au format description, adresse IP ou nom de domaine complet, serveur par défaut. Choisissez **OK** pour les importer dans la liste **Serveurs**.
    - **Exporter** : exporte la liste des serveurs dans un fichier de valeurs séparées par des virgules (csv).

- **Contourner le VPN sur le réseau Wi-Fi d'entreprise** : activez cette option pour indiquer que la connexion VPN n’est pas utilisée quand l’appareil est connecté au réseau Wi-Fi d’entreprise.
- **Contourner le VPN sur le réseau Wi-Fi domestique** : sélectionnez cette option pour indiquer que la connexion VPN n’est pas utilisée quand l’appareil est connecté à un réseau Wi-Fi domestique.

- **Type de connexion** : sélectionnez le type de connexion VPN à partir de la liste de fournisseurs suivante :
    - **Check Point Capsule VPN**
    - **Dell SonicWALL Mobile Connect**
    - **Client F5 Edge**
    - **Pulse Secure**

- **Groupe de connexion ou domaine** (Dell SonicWALL Mobile Connect uniquement) : spécifiez le nom du groupe de connexion ou domaine auquel vous souhaitez vous connecter.
- **Rôle** (Pulse Secure uniquement) : spécifiez le nom du rôle d'utilisateur qui a accès à cette connexion. Un rôle d’utilisateur définit des options et des paramètres personnels, et active ou désactive certaines fonctionnalités d’accès.
- **Domaine** (Pusle Secure uniquement) : spécifiez le nom du domaine d'authentification que vous souhaitez utiliser. Un domaine d’authentification est un regroupement de ressources d’authentification qu’utilise le type de connexion Pulse Secure.

- **Liste de recherche de suffixes DNS** - **Ajouter** un ou plusieurs suffixes DNS. Chaque suffixe DNS que vous spécifiez sera recherché lors de la connexion à un site web en utilisant un nom court. Par exemple, spécifiez les suffixes DNS **domain1.contoso.com** et **domain2.contoso.com**, accédez à l'URL **http://mywebsite**, et les URL **http://mywebsite.domain1.contoso.com** et **http://mywebsite.domain2.contoso.com** seront recherchées.

- **XML personnalisé** : spécifiez des commandes XML personnalisées qui configurent la connexion VPN.

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

- **Tunneling fractionné** - **Activez** ou **Désactivez** cette option qui permet aux appareils de décider de la connexion à utiliser en fonction du trafic. Par exemple, un utilisateur dans un hôtel utilisera la connexion VPN pour accéder aux fichiers de travail, mais utilisera le réseau standard de l’hôtel pour la navigation web ordinaire.




## <a name="proxy-settings"></a>Paramètres du proxy

- **Détecter automatiquement les paramètres du proxy** : si votre serveur VPN nécessite un serveur proxy pour la connexion, spécifiez si vous souhaitez que les appareils détectent automatiquement les paramètres de connexion. Pour plus d'informations, consultez la documentation de Windows Server.
- **Script de configuration automatique** : utilisez un fichier de configuration pour configurer le serveur proxy. Saisissez **l’URL du serveur proxy** (par exemple **http://proxy.contoso.com**) qui contient le fichier de configuration.
- **Utiliser un serveur proxy** : activez cette option si vous souhaitez saisir manuellement les paramètres du serveur proxy.
    - **Adresse** : saisissez l’adresse du serveur proxy (comme une adresse IP).
    - **Numéro de port** : saisissez le numéro de port associé au serveur proxy.
- **Contourner le proxy pour les adresses locales** : si votre serveur VPN nécessite un serveur proxy pour la connexion, sélectionnez cette option si vous ne souhaitez pas utiliser le serveur proxy pour les adresses locales que vous spécifiez. Pour plus d'informations, consultez la documentation de Windows Server.

