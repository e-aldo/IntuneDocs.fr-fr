---
title: Utiliser des paramètres d’appareil personnalisés dans Microsoft Intune - Azure | Microsoft Docs
description: Ajouter ou créer un profil afin d’utiliser des paramètres personnalisés pour des appareils iOS, Android et Windows à l’aide de Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce7c263435f92a041b93dc5d34ffa912c6fa87fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31021878"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Créer un profil avec des paramètres personnalisés dans Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune n’a peut-être pas tous les paramètres intégrés dont vous avez besoin. Ou vous pouvez vouloir utiliser un paramètre disponible dans d’autres profils d’appareils. Pour ajouter ces paramètres, créez un profil d’appareil et configurez le profil avec des paramètres d’appareil personnalisés.

Cet article décrit les étapes de base permettant de créer un profil avec des paramètres personnalisés. Il contient également des liens qui vous permettront d’aller plus loin dans la création de paramètres personnalisés avec les différentes plateformes.

## <a name="custom-settings-on-different-platforms"></a>Paramètres personnalisés sur différentes plateformes
Les paramètres personnalisés sont configurés différemment pour chaque plateforme. Par exemple, pour contrôler les fonctionnalités sur des appareils Android et Windows, vous pouvez entrer des valeurs OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Pour les appareils Apple, vous pouvez importer un fichier que vous avez créé dans l’outil [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## <a name="create-the-profile"></a>Créer le profil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Configuration de l’appareil**, **Profils**, puis **Créer un profil**.
4. Entrez un **Nom** et une **Description** pour le profil personnalisé.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme de l’appareil auquel appliquer les paramètres personnalisés. Vous pouvez choisir l’une des plateformes suivantes :

    - **Android**
    - **Android for Work**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**

6. Dans la liste déroulante **Type de profil**, choisissez **Personnalisé**.
7. Les paramètres que vous pouvez configurer diffèrent en fonction de la plateforme choisie. Les liens suivants fournissent plus d’informations sur les paramètres personnalisés pour chaque plateforme :

    - [Paramètres Android](custom-settings-android.md)
    - [Paramètres iOS](custom-settings-ios.md)
    - [Paramètres macOS](custom-settings-macos.md)
    - [Paramètres Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Paramètres Windows 10](custom-settings-windows-10.md)
    - [Paramètres Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Paramètres Android for Work](custom-settings-android-for-work.md)

8. Quand vous avez terminé, sélectionnez **Créer**.

Le profil est créé et apparaît dans la liste des profils. Pour attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).
