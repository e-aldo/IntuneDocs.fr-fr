---
title: "Paramètres VPN Intune pour les appareils macOS"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : découvrez les paramètres Intune que vous pouvez utiliser pour configurer des connexions VPN sur les appareils Mac OS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 068dcd5209ff1cc2b2799919fe38bdfbf809423a
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Paramètres VPN pour les appareils Mac OS dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Selon les paramètres que vous choisissez, toutes les valeurs dans la liste ci-dessous ne peuvent pas nécessairement être configurées.

## <a name="base-vpn-settings"></a>**Paramètres VPN de base**

**Nom de connexion** : saisissez un nom pour cette connexion. Les utilisateurs finaux voient ce nom lorsqu’ils consultent leur appareil pour obtenir la liste des connexions VPN disponibles.
- **Adresse IP ou nom de domaine complet** : fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. Exemples : **192.168.1.1**, **vpn.contoso.com**.
- **Méthode d’authentification** : choisissez la façon dont les appareils s’authentifient auprès du serveur VPN à partir de :
    - **Certificats** : sous **Certificat d’authentification**, choisissez le profil de certificat SCEP ou PKCS que vous avez créé précédemment pour authentifier la connexion. Pour plus d’informations sur les profils de certificat, consultez [Guide pratique pour configurer des certificats](how-to-configure-certificates.md).
    - **Nom d’utilisateur et mot de passe** : les utilisateurs finaux doivent fournir un nom d’utilisateur et un mot de passe pour se connecter au serveur VPN.
- **Type de connexion** : sélectionnez le type de connexion VPN à partir de la liste de fournisseurs suivante :
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **Client F5 Edge**
    - **Pulse Secure**
    - **VPN personnalisé**
- **Tunneling fractionné** - **Activez** ou **Désactivez** cette option qui permet aux appareils de décider de la connexion à utiliser en fonction du trafic. Par exemple, un utilisateur dans un hôtel utilisera la connexion VPN pour accéder aux fichiers de travail, mais utilisera le réseau standard de l’hôtel pour la navigation web ordinaire.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or Mac OS X app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you deploy the software. For more information, see [How to deploy and monitor apps](/intune-azure/manage-apps/deploy-apps). --->

## <a name="custom-vpn-settings"></a>Paramètres VPN personnalisés

Si vous avez sélectionné **VPN personnalisé**, configurez ces paramètres supplémentaires :

- **Identificateur VPN** : il s’agit d’un identificateur pour l’application VPN que vous utilisez, et qui est fourni par votre fournisseur VPN.
- **Entrez les paires clé-valeur pour les attributs du VPN personnalisé** Ajoutez ou importez des **Clés** et **Valeurs** pour personnaliser votre connexion VPN. Là encore, ces valeurs sont généralement fournies par votre fournisseur de VPN.


## <a name="proxy-settings"></a>Paramètres du proxy

- **Script de configuration automatique** : utilisez un fichier de configuration pour configurer le serveur proxy. Saisissez **l’URL du serveur proxy** (par exemple **http://proxy.contoso.com**) qui contient le fichier de configuration.
- **Adresse** : saisissez l’adresse du serveur proxy (comme une adresse IP).
- **Numéro de port** : saisissez le numéro de port associé au serveur proxy.

