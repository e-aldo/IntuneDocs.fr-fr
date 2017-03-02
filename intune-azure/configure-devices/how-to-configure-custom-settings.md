---
title: "Guide pratique pour configurer des paramètres d’appareils personnalisés Intune | Préversion Intune Azure | Microsoft Docs"
description: "Préversion Intune Azure : Découvrez comment utiliser Intune pour configurer des paramètres personnalisés sur les appareils que vous gérez."
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
ms.openlocfilehash: d9da3f1c2ccade5391e2e874336802602a016700
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Guide pratique pour configurer des paramètres d’appareils personnalisés dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Quand utiliser des paramètres personnalisés

Les paramètres d’appareils personnalisés peuvent être utiles lorsque les paramètres que vous voulez configurer ne sont pas intégrés à Intune, ni disponibles à partir d’autres profils d’appareils.
Les paramètres personnalisés sont configurés différemment pour chaque plateforme. Par exemple, avec les appareils Android et Windows, vous pouvez spécifier des valeurs OMA-URI (Open Mobile Alliance Uniform Resource Identifier) pour contrôler les fonctionnalités sur les appareils. Pour les appareils Apple, vous pouvez importer un fichier que vous avez créé dans l’outil [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Utilisez les informations de cette rubrique pour apprendre les notions de base sur la configuration de profils avec des paramètres personnalisés, puis lisez les autres rubriques pour chaque plateforme pour en savoir plus sur les caractéristiques des appareils.

## <a name="create-a-device-profile-containing-custom-settings"></a>Créer un profil d’appareil contenant des paramètres personnalisés

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, saisissez un **Nom** et une **Description** pour le profil personnalisé.
5. À partir de la liste déroulante **Plateforme**, sélectionnez la plateforme de l’appareil auquel vous souhaitez appliquer les paramètres personnalisés. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres personnalisés :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Personnalisé**.
7. Selon la plateforme que vous choisissez, les paramètres que vous pouvez configurer diffèrent. Accédez à l’une des rubriques suivantes pour obtenir les paramètres détaillés pour chaque plateforme :
    - [Paramètres Android](custom-for-android.md)
    - [Paramètres iOS](custom-for-ios.md)
    - [Paramètres macOS](custom-for-macos.md)
    - [Paramètres Windows Phone 8.1](custom-for-windows-phone-8-1.md)
    - [Paramètres Windows 10](custom-for-windows-10.md)
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareils](how-to-assign-device-profiles.md).


