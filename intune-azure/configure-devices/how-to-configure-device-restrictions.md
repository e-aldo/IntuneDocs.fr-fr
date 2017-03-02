---
title: "Configurer les paramètres de restriction de l’appareil Intune | Préversion Intune Azure | Microsoft Docs"
description: "Préversion Intune Azure : Découvrez comment utiliser Intune pour configurer des paramètres et des fonctionnalités sur les appareils que vous gérez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: c6293e9c669266203705a8fe06c323869dc7881f
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Guide pratique pour configurer des paramètres de restriction d’appareils dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Les restrictions de l’appareil vous permettent de contrôler un large éventail de paramètres et de fonctionnalités que vous gérez dans diverses catégories, dont la sécurité, le navigateur, le matériel et les paramètres de partage de données. Par exemple, vous pouvez créer un profil de restriction de l’appareil qui empêche les utilisateurs d’appareils iOS d’accéder à l’appareil photo.

Utilisez les informations de cette rubrique pour apprendre les notions de base sur la configuration de profils de restriction de l’appareil, puis lisez les autres rubriques pour chaque plateforme pour en savoir plus sur les caractéristiques des appareils.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Créer un profil d’appareil contenant des paramètres de restriction de l’appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de restriction de l’appareil.
5. À partir de la liste déroulante **Plateforme**, sélectionnez la plateforme de l’appareil auquel vous souhaitez appliquer les paramètres personnalisés. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres de restriction de l’appareil :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Restrictions de l’appareil**. Si vous souhaitez créer un profil de restrictions de l’appareil pour les appareils Windows 10 Collaboration comme un appareil Surface Hub, choisissez **Restrictions de l’appareil (Windows 10 Collaboration)**.
7. Selon la plateforme que vous choisissez, les paramètres que vous pouvez configurer diffèrent. Accédez à l’une des rubriques suivantes pour obtenir les paramètres détaillés pour chaque plateforme :
    - [Paramètres Android](device-restrictions-for-android.md)
    - [Paramètres iOS](device-restrictions-for-ios.md)
    - [Paramètres macOS](device-restrictions-for-macos.md)
    - [Paramètres Windows Phone 8.1](device-restrictions-for-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-for-windows-8-1.md)
    - [Paramètres Windows 10](device-restrictions-for-windows-10.md)
    - [Paramètres Windows 10 Collaboration](device-restrictions-for-windows-10-team.md)
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](how-to-assign-device-profiles.md).

## <a name="example-of-device-restriction-settings"></a>Exemple de paramètres de restriction de l’appareil

Dans cet exemple de haut niveau, vous allez créer une stratégie de restriction de l’appareil qui bloque l’utilisation de l’application d’appareil photo intégrée sur les appareils Android.

![Comment désactiver l’appareil photo sur les appareils Android](./media/disable-android-camera.png)


