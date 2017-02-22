---
title: "Paramètres VPN d’Intune pour les appareils iOS | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : en savoir plus sur les paramètres Windows Intune que vous pouvez utiliser pour configurer des connexions VPN sur des appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: 23322313bfedb089f2665f53795996a26efe40e0


---

# <a name="vpn-settings-for-ios-devices-in-intune-azure-preview"></a>Paramètres VPN pour les appareils iOS dans la version préliminaire d'Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Selon les paramètres que vous choisissez, toutes les valeurs dans la liste ci-dessous ne peuvent pas nécessairement être configurées.

## <a name="base-vpn-settings"></a>Paramètres VPN de base


**Nom de connexion** : saisissez un nom pour cette connexion. Les utilisateurs finaux voient ce nom lorsqu’ils consultent leur appareil pour obtenir la liste des connexions VPN disponibles.
- **Adresse IP ou nom de domaine complet** : fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. Exemples : **192.168.1.1**, **vpn.contoso.com**.
- **Méthode d’authentification** : choisissez la façon dont les appareils s’authentifient auprès du serveur VPN à partir de :
    - **Certificats** : sous **Certificat d’authentification**, choisissez le profil de certificat SCEP ou PKCS que vous avez créé précédemment pour authentifier la connexion. Pour plus d’informations sur les profils de certificat, consultez [Guide pratique de configuration des certificats](how-to-configure-certificates.md).
    - **Nom d’utilisateur et mot de passe** : les utilisateurs finaux doivent fournir un nom d’utilisateur et un mot de passe pour se connecter au serveur VPN.
- **Type de connexion** : sélectionnez le type de connexion VPN à partir de la liste de fournisseurs suivante :
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **Client F5 Edge**
    - **Pulse Secure**
    - **Cisco (IPSec)**
    - **Citrix**
    - **VPN personnalisé**
- **Tunneling fractionné** - **Activez** ou **Désactivez** cette option qui permet aux appareils de décider de la connexion à utiliser en fonction du trafic. Par exemple, un utilisateur dans un hôtel utilisera la connexion VPN pour accéder aux fichiers de travail, mais utilisera le réseau standard de l’hôtel pour la navigation web ordinaire.


## <a name="custom-vpn-settings"></a>Paramètres VPN personnalisés

Si vous avez sélectionné **VPN personnalisé** comme type de connexion, configurez ces paramètres supplémentaires :

- **Identificateur VPN** : il s’agit d’un identificateur pour l’application VPN que vous utilisez, et qui est fourni par votre fournisseur VPN.
- **Entrez les paires clé-valeur pour les attributs du VPN personnalisé** Ajoutez ou importez des **Clés** et **Valeurs** pour personnaliser votre connexion VPN. Là encore, ces valeurs sont généralement fournies par votre fournisseur de VPN.

## <a name="apps-per-app-vpn-settings"></a>Paramètres des applications (VPN par application)

- **VPN par application** : activez cette option si vous souhaitez utiliser des URL qui activeront la connexion VPN lorsqu’elles sont consultées à partir du navigateur Safari. Pour ce faire, vous devez avoir sélectionné **Certificats** comme méthode d’authentification dans les paramètres VPN de base.
- **URL qui activeront la connexion VPN en utilisant le navigateur Safari** : cliquez sur Ajouter pour ajouter une ou plusieurs URL de site web. Lorsque ces URL sont visitées, la connexion VPN est activée.

- **Règles à la demande** : vous pouvez configurer des règles conditionnelles qui contrôlent l’activation de la connexion VPN. Par exemple, vous pouvez créer une condition dans laquelle la connexion VPN est utilisée uniquement lorsqu’un appareil n’est pas connecté à un des réseaux Wi-Fi de votre société. Sinon, vous pouvez créer une condition dans laquelle la connexion VPN n’est pas lancée si un appareil ne peut pas accéder à un domaine de recherche DNS que vous spécifiez.

    - **Domaines de recherche DNS ou SSID** : indiquez si cette condition utilisera les **SSID** de réseau sans fil, ou les **domaines de recherche DNS**. Cliquez sur Ajouter pour configurer un ou plusieurs SSID ou domaines de recherche.
    - **Sonde de chaîne d’URL** (facultatif) : fournissez une URL que la règle utilise comme test. Si l’appareil sur lequel ce profil est installé peut accéder à cette URL sans redirection, la connexion VPN est initiée et l’appareil se connecte à l’URL cible. L’utilisateur ne voit pas le site de la sonde de chaîne d’URL. Par exemple, une sonde de chaîne d’URL peut être l’adresse d’un serveur web d’audit qui vérifie la compatibilité de l’appareil avant la connexion du VPN. Autre exemple, l’URL teste la capacité du VPN à se connecter à un site avant de connecter l’appareil à l’URL cible via le VPN.
    - **Action du domaine** : vous pouvez choisir une des options suivantes :
        - Se connecter si nécessaire : 
        - Ne jamais se connecter : 
    - **Action** : choisissez l’une des options suivantes :
        - Se connecter - 
        - Évaluer la connexion : 
        - Ignorer - 
        - Se déconnecter - 


## <a name="proxy-settings"></a>Paramètres du proxy

- **Script de configuration automatique** : utilisez un fichier de configuration pour configurer le serveur proxy. Saisissez **l’URL du serveur proxy** (par exemple **http://proxy.contoso.com**) qui contient le fichier de configuration.
- **Adresse** : saisissez l’adresse du serveur proxy (comme une adresse IP).
- **Numéro de port** : saisissez le numéro de port associé au serveur proxy.



<!--HONumber=Feb17_HO2-->


