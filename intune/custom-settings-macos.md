---
title: "Paramètres personnalisés Intune pour les appareils macOS"
titleSuffix: Azure portal
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé macOS."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d52b6aac830ff01ee5c05ebc51f923102bf3eef2
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Paramètres personnalisés pour les appareils Mac OS dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez le profil personnalisé Mac OS de Microsoft Intune pour affecter les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) sur des appareils Mac OS. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans un profil personnalisé macOS Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité vous permet d’affecter des paramètres Mac OS qui ne sont pas configurables avec d’autres types de profils Intune.


1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Créer un profil**, spécifiez les valeurs suivantes :

- **Nom du profil de configuration personnalisé** : entrez le nom de la stratégie tel qu’il sera affiché sur l’appareil et dans l'état Intune.
- **Fichier du profil de configuration** : accédez au profil de configuration que vous avez créé à l’aide de l’outil Apple Configurator.
Vérifiez que les paramètres que vous exportez à partir de l’outil Apple Configurator sont compatibles avec la version de Mac OS sur les appareils auxquels vous affectez la stratégie personnalisée Mac OS. Pour en savoir plus sur la résolution des paramètres incompatibles, recherchez l’élément **Configuration Profile Reference** et **Mobile Device Management Protocol Reference** sur le site web [Apple Developer](https://developer.apple.com/).

Le fichier importé s’affichera dans la zone **Contenu du fichier** du panneau.
