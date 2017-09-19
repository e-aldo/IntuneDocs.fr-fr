---
title: "Configurer les paramètres de fonctionnalités d’appareil Intune"
titleSuffix: Azure portal
description: "Découvrez comment utiliser Intune pour configurer les fonctionnalités sur les appareils que vous gérez."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4a2723bfc0adecd9b6265b4af43e6fe185882b5e
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Comment configurer les paramètres de fonctionnalités d’appareil dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les restrictions d’appareil vous permettent de contrôler les fonctionnalités sur les appareils iOS et MacOS comme AirPrint, les notifications et les configurations d’appareils partagés.

Utilisez les informations de cette rubrique pour apprendre les notions de base sur la configuration des profils de fonctionnalités d’appareil, puis lisez les autres rubriques pour chaque plateforme afin d’en savoir plus sur les caractéristiques spécifiques à chaque appareil.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Création d’un profil d'appareil contenant des paramètres de restriction d'appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **nom** et une **description** pour le profil de fonctionnalités de l’appareil.
5. Dans la liste déroulante **Plate-forme**, sélectionnez la plate-forme d’appareil à laquelle vous souhaitez appliquer les paramètres. Actuellement, vous pouvez choisir une des plateformes suivantes pour les fonctionnalités de l’appareil :
    - **iOS**
    - **MacOS**
6. Dans la liste déroulante **Type de profil**, choisissez **Fonctionnalités de l’appareil**. 
7. Selon la plateforme que vous choisissez, les paramètres que vous pouvez configurer diffèrent. Accédez à l’une des rubriques suivantes pour obtenir les paramètres détaillés pour chaque plateforme :
    - [Paramètres Intune AirPrint pour appareils iOS et Mac OS](air-print-settings-ios-macos.md)
    - [Paramètres Intune AirPlay pour appareils iOS](airplay-settings-ios.md)
    - [Paramètres de disposition de l’écran d’accueil Intune pour les appareils iOS](home-screen-settings-ios.md)
    - [Paramètres de notification des applications Intune pour les appareils iOS](app-notification-settings-ios.md)
    - [Paramètres de configuration des appareils Intune partagés pour iOS](shared-device-settings-ios.md)
    - [Paramètres de filtrage de contenu web Intune pour les appareils iOS](web-content-filter-settings-ios.md)

8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).



