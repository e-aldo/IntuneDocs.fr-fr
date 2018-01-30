---
title: "Paramètres personnalisés Intune pour les appareils iOS"
titleSuffix: Azure portal
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 761b19de8442e88717a5dcd52f7f0375bace91da
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Paramètres personnalisés Microsoft Intune pour les appareils iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez le profil personnalisé iOS de Microsoft Intune pour affecter les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) sur des appareils iOS. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans un profil personnalisé iOS Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité vous permet d’affecter des paramètres iOS qui ne sont pas configurables avec d’autres types de profils Intune.


1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Créer un profil**, spécifiez les valeurs suivantes :

- **Nom du profil de configuration personnalisé** : entrez le nom de la stratégie tel qu’il sera affiché sur l’appareil et dans l'état Intune.
- **Fichier du profil de configuration** : accédez au profil de configuration que vous avez créé à l’aide de l’outil Apple Configurator.
Vérifiez que les paramètres que vous exportez à partir de l’outil Apple Configurator sont compatibles avec la version d’iOS sur les appareils auxquels vous affectez la stratégie personnalisée iOS. Pour en savoir plus sur la résolution des paramètres incompatibles, recherchez l’élément **Configuration Profile Reference** et **Mobile Device Management Protocol Reference** sur le site web [Apple Developer](https://developer.apple.com/).

Le fichier importé s’affichera dans la zone **Contenu du fichier** du panneau.
