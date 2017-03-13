---
title: "Paramètres de VPN Intune pour les appareils Android"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres Windows Intune que vous pouvez utiliser pour configurer des connexions VPN sur les appareils Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 5ecbeb43e05887dc4cadbe110e3f97bd15363073
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Paramètres VPN pour les appareils Android dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Selon les paramètres que vous choisissez, toutes les valeurs dans la liste ci-dessous ne peuvent pas nécessairement être configurées.

**Nom de connexion** : saisissez un nom pour cette connexion. Les utilisateurs finaux voient ce nom lorsqu’ils consultent leur appareil pour obtenir la liste des connexions VPN disponibles.
- **Adresse IP ou nom de domaine complet** : fournissez l'adresse IP ou le nom de domaine complet du serveur VPN auquel les appareils se connectent. Exemples : **192.168.1.1**, **vpn.contoso.com**.
- **Méthode d’authentification** : choisissez la façon dont les appareils s’authentifient auprès du serveur VPN à partir de :
    - **Certificats** : sélectionnez un profil de certificat SCEP ou PKCS que vous avez créé précédemment pour authentifier la connexion. Pour plus d’informations sur les profils de certificat, consultez [Guide pratique pour configurer des certificats](how-to-configure-certificates.md).
    - **Nom d’utilisateur et mot de passe** : les utilisateurs finaux doivent fournir un nom d’utilisateur et un mot de passe pour se connecter au serveur VPN.
- **Type de connexion** : sélectionnez le type de connexion VPN à partir de la liste de fournisseurs suivante :
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **Client F5 Edge**
    - **Pulse Secure**
    - **Citrix**

- **Empreinte digitale** (VPN Check Point Capsule uniquement) : spécifiez une chaîne (par exemple « Code d’empreinte digitale Contoso ») qui sera utilisée pour vérifier que le serveur VPN est digne de confiance. Une empreinte digitale peut être envoyée au client pour que celui-ci sache qu’il peut approuver n’importe quel serveur présentant cette même empreinte lors de la connexion. Si l’appareil n’a pas encore l’empreinte digitale, il invite l’utilisateur à approuver le serveur VPN auquel il se connecte en affichant l’empreinte digitale (l’utilisateur vérifie l’empreinte manuellement et choisit Approuver pour se connecter).
- **Entrer les paires clé / valeur pour les attributs de Citrix VPN** (Citrix uniquement) : entrez les paires de clé / valeur fournies par Citrix pour configurer les propriétés de la connexion VPN.

