---
title: Paramètres personnalisés dans Microsoft Intune pour les appareils exécutant iOS
titleSuffix: ''
description: Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé iOS dans Microsoft Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3c92b8816dd6c5afd96cb8853b6d251ff5befaf4
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2018
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
