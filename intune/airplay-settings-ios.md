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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ad2f20603261ec0eac4156facd3fd23b2982f517
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-airplay-settings-for-ios-devices"></a>Paramètres Intune AirPlay pour appareils iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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



