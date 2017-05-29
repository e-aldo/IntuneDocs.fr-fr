---
title: "Paramètres Intune AirPrint pour appareils iOS et Mac OS"
titleSuffix: Intune Azure preview
description: "Intune Azure en version préliminaire : découvrez comment utiliser Intune pour connecter automatiquement des appareils iOS et Mac OS à des imprimantes compatibles AirPrint."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55486693e2f5678ceeb20dd3a0ef3c52553871d2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="airprint-settings-for-ios-and-macos-devices"></a>Paramètres AirPrint pour appareils iOS et Mac OS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Utilisez ces paramètres pour configurer les appareils iOS ou Mac OS afin qu’ils se connectent automatiquement aux imprimantes compatibles AirPrint sur votre réseau. Vous aurez besoin de l’adresse IP et du chemin d’accès de la ressource de vos imprimantes pour continuer.

## <a name="find-airprint-printer-information"></a>Rechercher les informations relatives à l’imprimante AirPrint

Utilisez cette procédure pour ajouter des informations AirPrint à la charge utile AirPrint afin que les utilisateurs d’appareils iOS puissent effectuer des impressions sur des imprimantes AirPrint connues.

1. Sur un Mac connecté au même réseau local (sous-réseau) que les imprimantes Airprint, ouvrez le Terminal (à partir de **/Applications/Utilities**)
2. Dans le Terminal, tapez **ippfind**, puis appuyez sur Entrée.
3. Notez toutes les informations sur l’imprimante retournées par la commande, par exemple : **ipp://myprinter.local.:631/ipp/port1**. La première partie des informations correspond au nom de votre imprimante, la dernière partie au chemin d’accès de la ressource.
4. Dans le Terminal, tapez **ping myprinter.local**, puis appuyez sur Entrée.
5. Notez l’adresse IP renvoyée par la commande, par exemple **PING myprinter.local (10.50.25.21)**.
6. Enfin, utilisez l’adresse IP et le chemin d’accès de la ressource contenus dans les paramètres de la charge utile AirPrint. Une adresse IP peut être, par exemple, **10.50.25.21**, et un chemin de ressource **/ipp port1**.

## <a name="configure-an-airprint-profile"></a>Configurer un profil AirPrint

1. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **AirPrint**.
2. Dans le panneau **AirPrint**, pour ajouter une destination AirPrint, entrez son **adresse IP** et le **chemin d’accès de la ressource**, puis cliquez sur **Ajouter**.
3. Continuez à ajouter autant de destinations que nécessaire. Quand vous avez terminé, cliquez sur **OK**.

Vous pouvez également importer une liste d’imprimantes à partir d’un fichier .csv, ou encore exporter la liste.

