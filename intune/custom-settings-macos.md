---
title: Paramètres personnalisés dans Microsoft Intune pour les appareils exécutant macOS
titleSuffix: ''
description: Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé macOS dans Microsoft Intune.
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
ms.openlocfilehash: 66a935b96b802a05831118cd9dc0adbc62bb4bae
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-macos"></a>Paramètres d’appareil personnalisés dans Microsoft Intune pour les appareils exécutant macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Utilisez le profil personnalisé Mac OS de Microsoft Intune pour affecter les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) sur des appareils Mac OS. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans un profil personnalisé macOS Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité vous permet d’affecter des paramètres Mac OS qui ne sont pas configurables avec d’autres types de profils Intune.


1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
2. Dans le volet **Profil de configuration personnalisée**, configurez chacun des paramètres suivants :

- **Nom du profil de configuration personnalisé** : entrez le nom de la stratégie tel qu’affiché sur l’appareil et dans l’état Intune.
- **Fichier du profil de configuration** : accédez au profil de configuration que vous avez créé à l’aide de l’outil Apple Configurator.
Vérifiez que les paramètres que vous exportez à partir de l’outil Apple Configurator sont compatibles avec la version de Mac OS sur les appareils auxquels vous affectez la stratégie personnalisée Mac OS. Pour en savoir plus sur la résolution des paramètres incompatibles, recherchez l’élément **Configuration Profile Reference** et **Mobile Device Management Protocol Reference** sur le site web [Apple Developer](https://developer.apple.com/).

Le fichier importé s’affiche dans la zone **Contenu du fichier** du volet.
