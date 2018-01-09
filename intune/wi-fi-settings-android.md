---
title: "Paramètres Wi-Fi Intune pour les appareils Android"
titleSuffix: Azure portal
description: "Découvrez-en davantage sur la configuration des paramètres de connexion Wi-Fi sur les appareils Android et Android for Work."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36690343efc8c632a6b0e4326125ed85d93ed600
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/30/2017
---
# <a name="wi-fi-settings-for-android-and-android-for-work-devices-in-microsoft-intune"></a>Paramètres Wi-Fi pour les appareils Android et Android for Work dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Paramètres Wi-Fi pour les profils de base et d’entreprise

Les paramètres Wi-Fi suivants sont disponibles pour les appareils Android et Android for Work :

- **Nom du réseau** : saisissez un nom pour cette connexion Wi-Fi. Il s'agit du nom que voient les utilisateurs lorsqu’ils parcourent la liste des connexions disponibles sur leurs appareils.
- **SSID** : identificateur SSID. Il s’agit du nom réel du réseau sans fil auquel les appareils se connectent. Toutefois, les utilisateurs voient uniquement le nom de réseau créé ci-dessus lorsqu’ils choisissent la connexion.
- **Se connecter automatiquement** : l’appareil se connecte chaque fois qu’il se trouve dans la portée de ce réseau.
- **Réseau masqué** : empêche ce réseau de s’afficher dans la liste des réseaux disponibles sur l’appareil.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>Paramètres Wi-Fi pour les profils d’entreprise uniquement

- **Type EAP** : choisissez le type de protocole EAP (Extensible Authentication Protocol) utilisé pour authentifier les connexions sans fil sécurisées :
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Options supplémentaires lorsque vous choisissez un type EAP

#### <a name="server-trust"></a>Approbation du serveur



|Nom du paramètre|Autres informations|À effectuer quand :|
|-------------|---------------|-----------|
|**Noms de serveurs de certificats**|Spécifiez un ou plusieurs noms communs utilisés dans les certificats émis par votre autorité de certification de confiance. Si vous fournissez ces informations, vous pouvez ignorer la boîte de dialogue d’approbation dynamique qui s’affiche sur les appareils des utilisateurs finaux lorsqu’ils se connectent à ce réseau Wi-Fi.|Le Type EAP est **EAP-TLS** ou **EAP-TTLS**|
|**Certificat racine pour la validation du serveur**|Choisissez le profil de certificat racine approuvé utilisé pour authentifier la connexion. |Le type EAP est **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Confidentialité de l’identité (identité externe)**|Spécifiez le texte envoyé en réponse à une demande d'identité EAP. Ce texte peut être n'importe quelle valeur. Lors de l'authentification, cette identité anonyme est envoyée en premier, suivie de l'identification réelle adressée dans un tunnel sécurisé.|Le type EAP est **PEAP**|


#### <a name="client-authentication"></a>Authentification du client


|Nom du paramètre|Autres informations|À effectuer quand :|
|----------|--------------|----------|
|**Certificat client pour l'authentification du client (certificat d'identité)**|Choisissez le profil de certificat SCEP ou PKCS utilisé pour authentifier la connexion.|Le type EAP est **EAP-TLS**|
|**Méthodes d’authentification**|Sélectionnez la méthode d'authentification de la connexion :<br>- **Certificats** pour sélectionner le certificat d’identité client SCEP ou PKCS présenté au serveur.<br><br>- **Nom d’utilisateur et mot de passe** pour spécifier une autre méthode d’authentification. <br><br>Si vous avez sélectionné **Nom d’utilisateur et mot de passe**, configurez :<br><br>-  **Méthode non EAP (identité interne)**, puis sélectionnez la méthode d’authentification de la connexion :<br>- **Aucun**<br>- **Mot de passe non chiffré (PAP)**<br>- **Protocole CHAP (Challenge Handshake Authentication Protocol)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP Version 2 (MS-CHAP v2)**<br>Les options disponibles dépendent du type EAP sélectionné.<br><br>**et**<br><br>- **Confidentialité de l'identité (identité externe)** : spécifiez le texte envoyé en réponse à une demande d'identité EAP. Ce texte peut être n'importe quelle valeur. Lors de l'authentification, cette identité anonyme est envoyée en premier, suivie de l'identification réelle adressée dans un tunnel sécurisé.|Le type EAP est **EAP-TTLS** ou **PEAP**|
