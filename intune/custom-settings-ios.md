---
title: "Paramètres personnalisés dans Microsoft Intune pour les appareils exécutant iOS"
titleSuffix: Azure portal
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 40e34a2e22c9349cad63d813b892863e0e8a2933
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Paramètres d’appareil personnalisés dans Microsoft Intune pour les appareils exécutant iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez le profil personnalisé iOS de Microsoft Intune pour affecter les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) sur des appareils iOS. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans un profil personnalisé iOS Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité vous permet d’affecter des paramètres iOS qui ne sont pas configurables avec d’autres types de profils Intune.


1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
2. Dans le volet **Profil de configuration personnalisée**, configurez chacun des paramètres suivants :

- **Nom du profil de configuration personnalisé** : entrez le nom de la stratégie tel qu’affiché sur l’appareil et dans l’état Intune.
- **Fichier du profil de configuration** : accédez au profil de configuration que vous avez créé à l’aide de l’outil Apple Configurator.
Vérifiez que les paramètres que vous exportez à partir de l’outil Apple Configurator sont compatibles avec la version d’iOS sur les appareils auxquels vous affectez la stratégie personnalisée iOS. Pour en savoir plus sur la résolution des paramètres incompatibles, recherchez l’élément **Configuration Profile Reference** et **Mobile Device Management Protocol Reference** sur le site web [Apple Developer](https://developer.apple.com/).

Le fichier importé s’affiche dans la zone **Contenu du fichier** du volet.
