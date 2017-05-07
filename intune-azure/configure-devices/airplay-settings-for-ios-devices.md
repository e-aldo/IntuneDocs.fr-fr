---
title: "Paramètres Intune AirPlay pour appareils iOS"
titleSuffix: Intune Azure preview
description: "Découvrez comment utiliser Intune pour connecter automatiquement des appareils iOS à des appareils compatibles AirPlay."
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
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: f1f7aa6a0b441b51f20d104c4353a1542a9e01ad
ms.lasthandoff: 04/19/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Paramètres Intune AirPlay pour appareils iOS

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez ces paramètres pour vous aider à connecter des appareils iOS que vous gérez à des appareils compatibles AirPlay (tels que des téléviseurs Apple) de votre réseau.
Avec cette fonctionnalité, vous pouvez :

- **Configurer une liste d’appareils et de mots de passe** : configurez des appareils avec le nom et le mot de passe des appareils AirPlay pour leur permettre de se connecter automatiquement dès lors qu’ils se trouvent à portée. Si vous spécifiez un mot de passe, les utilisateurs finaux n’auront pas à le fournir lors de leur connexion.
- **Configurer des destinations autorisées** : configurez une liste d’appareils AirPlay (par ID d’appareil). Les utilisateurs finaux ne pourront voir et se connecter qu’aux appareils répertoriés (pour les appareils supervisés uniquement).

## <a name="get-started"></a>Prise en main

1. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **AirPlay**.
2. Dans le panneau **AirPlay**, choisissez une ou des opérations suivantes :

## <a name="configure-a-device-and-password-list"></a>Configurer une liste d’appareils et de mots de passe

1. Dans le panneau **Mots de passe**, entrez le **nom de l’appareil** et le **mot de passe** d’un appareil Airplay, par exemple **Contoso Apple TV**.
2. Après avoir entré les détails de l’appareil, cliquez sur **Ajouter**. L’appareil s’affiche dans la liste **Nom de l’appareil**.
3. Continuez à ajouter des appareils. Quand vous avez terminé, cliquez sur **OK**.


## <a name="configure-allowed-destinations"></a>Configurer des destinations autorisées

1. Dans le panneau **Allowed destinations (supervised only)* (Destinations autorisées (mode supervisé uniquement)), entrez **l’ID d’appareil** d’un appareil Airplay, par exemple 52:46:CD:51:83:4 C.
2. Après avoir entré l’ID de l’appareil, cliquez sur **Ajouter**. L’ID s’affiche dans la liste **ID d’appareil**.
3. Continuez à ajouter des appareils. Quand vous avez terminé, cliquez sur **OK**.

Vous pouvez également importer des appareils et des mots de passe, ainsi que des destinations autorisées, à partir d’un fichier csv.



