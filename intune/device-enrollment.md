---
title: "Qu’est-ce que l’inscription des appareils Microsoft Intune ?"
titlesuffix: Microsoft Intune
description: "En savoir plus sur l’inscription pour les appareils iOS, Android et Windows."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9f49178a2d8e8a73a693ed2f374b86b8e702680f
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="what-is-device-enrollment"></a>Qu’est-ce que l’inscription d’appareils ?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune vous permet de gérer les appareils et les applications des membres de votre personnel, et comment ils accèdent aux données de votre entreprise. Pour utiliser cette gestion des appareils mobiles (MDM), les appareils doivent d’abord être inscrits auprès du service Intune. Quand un appareil est inscrit, il reçoit un certificat MDM. Ce certificat est utilisé pour communiquer avec le service Intune.

Comme vous pouvez le voir dans les tableaux suivants, il existe plusieurs méthodes pour inscrire les appareils des membres de votre personnel. Chaque méthode dépend de la propriété de l’appareil (personnel ou d’entreprise), du type d’appareil (iOS, Windows, Android) et des exigences de gestion (réinitialisations, affinité, verrouillage).

## <a name="ios-enrollment-methods"></a>Méthodes d’inscription iOS

| **Méthode** |  **Réinitialisation requise** |    [**Affinité utilisateur**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Verrouillé** | **Détails** |
|:---:|:---:|:---:|:---:|:---:|
| | Les appareils sont réinitialisés aux paramètres d’usine lors de l’inscription. |  Associe chaque appareil à un utilisateur.| Les utilisateurs ne peuvent pas désinscrire les appareils.  | |
|**[BYOD](#bring-your-own-device)** | Non|   Oui |   Non | [Plus d’informations](./apple-mdm-push-certificate-get.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#device-enrollment-manager)**| Non |Non |Non  | [Plus d’informations](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Oui |   Facultatif |  Facultatif|[Plus d’informations](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Oui |   Facultatif |  Non| [Plus d’informations](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Non |    Non  | Non|[Plus d’informations](./apple-configurator-direct-enroll-ios.md)|

## <a name="macos-enrollment-methods"></a>Méthodes d’inscription macOS

| **Méthode** |  **Réinitialisation requise** |  **Affinité utilisateur** | **Verrouillé** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Non| Oui | Non | [Plus d’informations](./macos-enroll.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#device-enrollment-manager)**| Non |Non |Non  | [Plus d’informations](./device-enrollment-manager-enroll.md)|


## <a name="windows-enrollment-methods"></a>Méthodes d’inscription de Windows

| **Méthode** |  **Réinitialisation requise** |    **Affinité utilisateur**   |   **Verrouillé** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Non |  Oui |   Non | [Plus d’informations](windows-enroll.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#device-enrollment-manager)**| Non |Non |Non  |[Plus d’informations](device-enrollment-manager-enroll.md)|
|**Inscription automatique** | Non |Oui |Non | [Plus d’informations](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Inscription en bloc** |Non |Non |Non | [Plus d’informations](./windows-bulk-enroll.md) |

## <a name="android-enrollment-methods"></a>Méthodes d’inscription d’Android

| **Méthode** |  **Réinitialisation requise** |    **Affinité utilisateur**   |   **Verrouillé** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Non|   Oui |   Non | [Plus d’informations](./android-enroll.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#device-enrollment-manager)**| Non |Non |Non  |[Plus d’informations](./device-enrollment-manager-enroll.md)|
|**Android for Work**| Non | Oui | Non| [Plus d’informations](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="bring-your-own-device"></a>(Apportez votre propre appareil)
Les appareils BYOD incluent les téléphones, les tablettes et les PC personnels. Les utilisateurs installent et exécutent l’application Portail d’entreprise pour inscrire des appareils BYOD. Ce programme permet aux utilisateurs d’accéder aux ressources de l’entreprise, comme la messagerie électronique.

## <a name="corporate-owned-device"></a>Appareil d’entreprise
Les appareils d’entreprise incluent les téléphones, les tablettes et les PC appartenant à l’organisation et distribués aux employés. L’inscription des appareils d’entreprise prend en charge des scénarios comme l’inscription automatique, les appareils partagés ou les exigences d’inscription pré-autorisée. Une méthode courante pour inscrire des appareils d’entreprise est l’utilisation du gestionnaire de l’inscription d’appareil par un administrateur ou un responsable. Vous pouvez inscrire des appareils iOS directement via les outils du Programme d’inscription des appareils fournis par Apple. Les appareils avec un numéro IMEI peuvent également être identifiés et référencés comme appartenant à l’entreprise.

### <a name="device-enrollment-manager"></a>Gestionnaire d'inscription d'appareils
Le gestionnaire d’inscription d’appareil est un compte d’utilisateur spécial permettant d’inscrire et de gérer plusieurs appareils d’entreprise. Les responsables peuvent installer le Portail d’entreprise et inscrire de nombreux appareils sans utilisateur. En savoir plus sur le [gestionnaire d’inscription d’appareil](./device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Programme d'inscription d'appareils Apple
Le programme d’inscription d’appareils Apple (ou DEP) vous permet de créer et déployer une stratégie « à distance » sur des appareils iOS achetés et gérés avec DEP. L’appareil est inscrit quand l’utilisateur le démarre pour la première fois et exécute l’Assistant d’installation iOS. Cette méthode prend en charge le mode iOS supervisé, qui permet la configuration d’un appareil avec des fonctionnalités spécifiques.

Pour en savoir plus sur l’inscription DEP iOS :

- [Choisir comment inscrire des appareils iOS](ios-enroll.md)
- [Inscrire des appareils iOS à l’aide du programme d’inscription d’appareils](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB-SA
Les administrateurs utilisent Apple Configurator, via un port USB, pour préparer manuellement chaque appareil d’entreprise à l’inscription à l’aide de l’Assistant Configuration. Ils créent un profil d’inscription et l’exportent vers Apple Configurator. Lorsque les utilisateurs reçoivent leurs appareils, ils sont invités à exécuter l’Assistant Configuration pour inscrire leurs appareils. Cette méthode prend en charge le mode **iOS supervisé**, qui active les fonctionnalités suivantes :
  - Inscription verrouillée
  - Mode plein écran et autres configurations et restrictions avancées

Découvrez l’inscription d’Apple Configurator iOS avec l’Assistant Configuration :

- [Choisir la méthode d’inscription des appareils iOS](enrollment-method-choose-ios.md)
- [Inscrire des appareils iOS avec Configurator et l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Pour les inscriptions directes, l’administrateur doit inscrire manuellement chaque appareil en créant une stratégie d’inscription et en l’exportant vers Apple Configurator. Les appareils d’entreprise connectés par USB sont inscrits directement et aucune réinitialisation aux paramètres d’usine n’est nécessaire. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ou la gestion des applications mobiles.

Pour en savoir plus sur l’inscription d’appareils iOS, consultez :

- [Choisir la méthode d’inscription des appareils iOS](enrollment-method-choose-ios.md)
- [Inscrire des appareils iOS avec Apple Configurator et l’inscription directe](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud. Plus d’informations seront bientôt disponibles.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Nettoyage de l’appareil mobile après expiration du certificat MDM

Le certificat MDM est renouvelé automatiquement lorsque les appareils mobiles communiquent avec le service Intune. Si des appareils mobiles sont réinitialisés ou ne parviennent pas à communiquer avec le service Intune pendant un certain temps, le certificat MDM n’est pas renouvelé. L’appareil est supprimé du portail Azure 180 jours après l’expiration du certificat MDM.
