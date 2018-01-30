---
title: "Configurer les paramètres de restriction d’appareil Intune"
titleSuffix: Azure portal
description: "Découvrez comment utiliser Intune pour configurer des paramètres et des fonctionnalités sur les appareils que vous gérez."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cd21d6e87dfa142fe9e3ef4d9bbbc0be87eca9b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Guide pratique pour configurer des paramètres de restriction d’appareils dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les restrictions de l’appareil vous permettent de contrôler un large éventail de paramètres et de fonctionnalités que vous gérez dans diverses catégories, dont la sécurité, le navigateur, le matériel et les paramètres de partage de données. Par exemple, vous pouvez créer un profil de restriction de l’appareil qui empêche les utilisateurs d’appareils iOS d’accéder à l’appareil photo.

Utilisez les informations de cette rubrique pour apprendre les notions de base sur la configuration de profils de restriction de l’appareil, puis lisez les autres rubriques pour chaque plateforme pour en savoir plus sur les caractéristiques des appareils.

Pour créer un profil d’appareil contenant des paramètres de restriction d’appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
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
    - [Paramètres Android](device-restrictions-android.md)
    - [Paramètres iOS](device-restrictions-ios.md)
    - [Paramètres macOS](device-restrictions-macos.md)
    - [Paramètres Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Paramètres Windows 10](device-restrictions-windows-10.md)
    - [Paramètres Windows 10 Collaboration](device-restrictions-windows-10-teams.md)
    - [Paramètres Android for Work](device-restrictions-android-for-work.md)
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->