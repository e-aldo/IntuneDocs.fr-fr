---
title: "Configurer les paramètres des fonctionnalités d’appareil Microsoft Intune"
titleSuffix: 
description: "Découvrez comment utiliser Microsoft Intune pour configurer les fonctionnalités sur les appareils que vous gérez."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Configurer les paramètres de fonctionnalités d’appareil dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les fonctionnalités de l’appareil vous permettent de contrôler les fonctionnalités iOS et MacOS comme AirPrint, les notifications et les configurations d’appareils partagés.

Utilisez les informations de cet article pour apprendre les notions de base sur la configuration des profils de fonctionnalités d’appareil, puis lisez d’autres articles pour chaque plateforme afin d’explorer les caractéristiques spécifiques aux appareils.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Créer un profil d’appareil contenant des paramètres de fonctionnalités d’appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans la page **Intune**, choisissez **Configuration de l’appareil**.
2. Dans la page **Configuration de l’appareil**, sous la section **Gérer**, choisissez **Profils**.
3. Dans la page des profils, choisissez **Créer un profil**.
4. Dans la page **Créer un profil**, entrez un **nom** et une **description** pour le profil de fonctionnalités de l’appareil.
5. Dans la liste déroulante **Plate-forme**, sélectionnez la plate-forme d’appareil à laquelle vous souhaitez appliquer les paramètres. Actuellement, vous pouvez choisir une des plateformes suivantes pour les fonctionnalités de l’appareil :
    - **iOS**
    - **MacOS**
6. Dans la liste déroulante **Type de profil**, choisissez **Fonctionnalités de l’appareil**. 
7. Selon la plateforme que vous choisissez, les paramètres que vous pouvez configurer diffèrent. Accédez à l’un des articles suivants pour obtenir les paramètres détaillés pour chaque plateforme :
    - [Paramètres Intune AirPrint pour appareils iOS et Mac OS](air-print-settings-ios-macos.md)
    - [Paramètres Intune AirPlay pour appareils iOS](airplay-settings-ios.md)
    - [Paramètres de disposition de l’écran d’accueil Intune pour les appareils iOS](home-screen-settings-ios.md)
    - [Paramètres de notification des applications Intune pour les appareils iOS](app-notification-settings-ios.md)
    - [Paramètres de configuration des appareils Intune partagés pour iOS](shared-device-settings-ios.md)
    - [Configurer Intune pour l’authentification unique des appareils iOS](sso-ios.md)
    - [Paramètres de filtrage de contenu web Intune pour les appareils iOS](web-content-filter-settings-ios.md)

8. Une fois terminé, sélectionnez **OK**, revenez à la page **Créer un profil**, puis choisissez **Créer**.

Le profil est créé et apparaît dans la page de la liste des profils.
## <a name="next-steps"></a>Étapes suivantes

Si vous souhaitez affecter ce profil à des groupes, consultez [Guide pratique pour affecter des profils d’appareil](device-profile-assign.md).



