---
title: Configurer les paramètres Wi-Fi dans Microsoft Intune pour les appareils exécutant Android
titleSuffix: ''
description: Découvrez les paramètres de configuration Wi-Fi Intune sur les appareils exécutant Android.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0157815322488525a4ce7a3d6d2c90cbb8d3ff2a
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905663"
---
# <a name="configure-wi-fi-settings-in-microsoft-intune-for-devices-running-android-android-work-profiles-and-android-kiosk-devices"></a>Configurer les paramètres Wi-Fi dans Microsoft Intune pour les appareils exécutant Android, pour les profils professionnels Android et pour les appareils Android en mode kiosque

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cet article décrit les paramètres Wi-Fi que vous pouvez configurer dans Microsoft Intune pour les appareils exécutant Android et Profils professionnels Android.

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>Paramètres Wi-Fi pour les profils de base et d’entreprise

Les paramètres Wi-Fi suivants sont disponibles pour les appareils Android et avec profil professionnel Android :

- **Nom du réseau** : saisissez un nom pour cette connexion Wi-Fi. Il s’agit du nom que voient les utilisateurs quand ils parcourent la liste des connexions disponibles sur leurs appareils.
- **SSID** : identificateur SSID. Il s’agit du nom réel du réseau sans fil auquel les appareils se connectent. Toutefois, les utilisateurs voient uniquement le nom de réseau que vous avez configuré quand ils choisissent la connexion.
- **Se connecter automatiquement** : l’appareil se connecte chaque fois qu’il se trouve dans la portée de ce réseau.
- **Réseau masqué** : empêche ce réseau de s’afficher dans la liste des réseaux disponibles sur l’appareil.

## <a name="wi-fi-settings-available-for-enterprise-kiosk-profiles"></a>Paramètres Wi-Fi disponibles pour les profils de kiosque Entreprise
- **Type de Wi-Fi** : ces paramètres de type de Wi-Fi sont disponibles seulement quand vous choisissez **Type de profil** > **Propriétaire de l’appareil uniquement** > **Wi-Fi**.
    - **Ouvrir (pas d’authentification)**
    - **Clé WEP prépartagée** : vous devez fournir le mot de passe dans la zone **Clé prépartagée**.
    - **Clé WPA prépartagée** : vous devez fournir le mot de passe dans la zone **Clé prépartagée**.

## <a name="wi-fi-settings-for-android-legacy-and-android-work-profiles-only"></a>Paramètres Wi-Fi uniquement pour les versions antérieures d’Android et les profils professionnels Android

- **Type EAP** : choisissez le type de protocole EAP (Extensible Authentication Protocol) utilisé pour authentifier les connexions sans fil sécurisées :
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Options supplémentaires lorsque vous choisissez un type EAP

#### <a name="server-trust"></a>Approbation du serveur



|Nom du paramètre|Plus d’informations|À effectuer quand :|
|-------------|---------------|-----------|
|**Noms de serveurs de certificats**|Spécifiez un ou plusieurs noms communs utilisés dans les certificats émis par votre autorité de certification de confiance. Si vous fournissez ces informations, vous pouvez ignorer la boîte de dialogue d’approbation dynamique qui s’affiche sur les appareils des utilisateurs quand ils se connectent à ce réseau Wi-Fi.|Le Type EAP est **EAP-TLS** ou **EAP-TTLS**|
|**Certificat racine pour la validation du serveur**|Choisissez le profil de certificat racine approuvé utilisé pour authentifier la connexion. |Le type EAP est **EAP-TLS**, **EAP-TTLS** ou **PEAP**|
|**Confidentialité de l’identité (identité externe)**|Spécifiez le texte envoyé en réponse à une demande d'identité EAP. Ce texte peut être n'importe quelle valeur. Lors de l'authentification, cette identité anonyme est envoyée en premier, suivie de l'identification réelle adressée dans un tunnel sécurisé.|Le type EAP est **PEAP**|


#### <a name="client-authentication"></a>Authentification du client


|                                     Nom du paramètre                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Plus d’informations                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                            À effectuer quand :                            |
|--------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Certificat client pour l'authentification du client (certificat d'identité)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       Choisissez le profil de certificat SCEP ou PKCS utilisé pour authentifier la connexion.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |              Le type EAP est <strong>EAP-TLS</strong>              |
|                        <strong>Méthodes d’authentification</strong>                        | Sélectionnez la méthode d'authentification de la connexion :<br>- <strong>Certificats</strong> pour sélectionner le certificat d’identité client SCEP ou PKCS présenté au serveur.<br><br>- <strong>Nom d’utilisateur et mot de passe</strong> pour spécifier une autre méthode d’authentification. <br><br>Si vous avez sélectionné <strong>Nom d’utilisateur et mot de passe</strong>, configurez :<br><br>-  <strong>Méthode non-EAP (identité interne)</strong>, puis sélectionnez la méthode d’authentification de la connexion :<br>- <strong>Aucun</strong><br>- <strong>Mot de passe non chiffré (PAP)</strong><br>- <strong>Protocole CHAP (Challenge Handshake Authentication Protocol)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP Version 2 (MS-CHAP v2)</strong><br>Les options disponibles dépendent du type EAP sélectionné.<br><br><strong>et</strong><br><br>- <strong>Confidentialité de l'identité (identité externe)</strong> : spécifiez le texte envoyé en réponse à une demande d'identité EAP. Ce texte peut être n'importe quelle valeur. Lors de l'authentification, cette identité anonyme est envoyée en premier, suivie de l'identification réelle adressée dans un tunnel sécurisé. | Le type EAP est <strong>EAP-TTLS</strong> ou <strong>PEAP</strong> |

