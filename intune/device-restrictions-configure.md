---
title: "Configurer les paramètres de restriction des appareils dans Microsoft Intune"
titleSuffix: 
description: "Découvrez comment utiliser Microsoft Intune pour configurer les paramètres et les fonctionnalités des appareils que vous gérez."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c5ccb928b8ff3f9cebbd6f51d99cddd1f36fb074
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Guide pratique pour configurer des paramètres de restriction d’appareils dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les restrictions de l’appareil vous permettent de contrôler un large éventail de paramètres et de fonctionnalités que vous gérez dans diverses catégories comme :
- Sécurité
- Navigateur
- Matériel
- Paramètres de partage des données

Par exemple, vous pouvez créer un profil de restriction de l’appareil qui empêche les utilisateurs d’appareils iOS d’accéder à l’appareil photo.

Découvrez les principes de base des profils de restriction, puis lisez d’autres articles décrivant les spécificités des appareils sur chaque plateforme.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Créer un profil d’appareil contenant des paramètres de restriction de l’appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans la page **Intune**, choisissez **Configuration de l’appareil**.
2. Dans la page **Configuration de l’appareil**, sous la section **Gérer**, choisissez **Profils**.
3. Dans la page **Profils**, choisissez **Créer un profil**.
4. Dans la page **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de restriction d’appareil.
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
    - [Paramètres Windows Holographic for Business](device-restrictions-windows-holographic.md)
    - [Paramètres Android for Work](device-restrictions-android-for-work.md)
8. Quand vous avez terminé, revenez à la page **Créer un profil**, puis cliquez sur **Créer**.

Le profil est créé et apparaît dans la page de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
