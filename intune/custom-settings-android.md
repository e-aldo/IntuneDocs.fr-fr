---
title: "Paramètres personnalisés Intune pour les appareils Android"
titleSuffix: Azure portal
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Android."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b1ccb3b0b7b2ce024ff6a09d7f9d8366896fb67
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Paramètres personnalisés pour les appareils Android dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez le profil Microsoft Intune Android **personnalisé** pour affecter les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres Android suivants qui ne sont pas configurables avec des stratégies Intune :

- [Utiliser un profil d’appareil personnalisé Microsoft Intune pour créer un profil Wi-Fi avec une clé prépartagée](/intune/wi-fi-profile-shared-key)
- [Utiliser un profil personnalisé Microsoft Intune pour créer un profil VPN par application pour les appareils Android](/intune/android-pulse-secure-per-app-vpn)
- [Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung Knox Standard dans Microsoft Intune](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Seuls les paramètres répertoriés ci-dessus peuvent être configurés par ce type de profil. Les appareils Android n’exposent pas une liste complète des paramètres OMA-URI que vous pouvez configurer. Si vous voulez que d’autres paramètres soient ajoutés, demandez-le sur le [site Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Paramètres de profil personnalisés pour les appareils Android

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Sur le panneau **Modifier une ligne**, configurez les valeurs suivantes pour chaque paramètre :
    - **Nom** : affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** : entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.
    - **Type de données** : sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne**, **Chaîne (XML)**, **Date et heure**, **Entier**, **Virgule flottante** ou **Booléen**.
    - **OMA-URI** : spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Valeur** : entrez la valeur à associer à l’identificateur OMA-URI que vous avez entré.
4. Cliquez sur **OK** lorsque vous avez terminé, puis continuez à ajouter d’autres paramètres si nécessaire.

## <a name="next-steps"></a>Étapes suivantes

Une fois les paramètres définis, le profil est créé et s’affiche dans le panneau de la liste des profils. Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).




