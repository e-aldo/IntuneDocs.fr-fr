---
title: "Définir des restrictions d’inscription dans Intune"
titleSuffix: Intune on Azure
description: "Restriction de l’inscription par la plateforme et définition d’une limite d’inscriptions d’appareils dans Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2017
---
# <a name="set-enrollment-restrictions"></a>Définir des restrictions d’inscription

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur Intune, vous pouvez déterminer les appareils qui peuvent s’inscrire à la gestion avec Intune. Utilisez le portail Intune afin de définir les restrictions suivantes pour l’inscription d’appareils :

- Nombre maximal d’appareils inscrits
- Plateformes d’appareils qui peuvent s’inscrire :
  - Android
  - iOS
  - macOS
  - Windows
- Appareils personnels (iOS et Android uniquement)

>[!NOTE]
>Les restrictions d’inscription ne sont pas une fonctionnalité de sécurité. Des appareils compromis peuvent falsifier leur caractère. Ces restrictions représentent une barrière de meilleur effort pour les utilisateurs non malveillants.

## <a name="set-device-type-restrictions"></a>Définition des restrictions de type d'appareil
Les restrictions d’inscription par défaut s’appliquent à tous les utilisateurs auxquels des restrictions d’inscription de priorité plus élevée ne sont pas affectées.  
1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis **Restrictions d’inscription**.
![Capture d’écran de l’espace de travail de restrictions sur les appareils avec les restrictions de type d’appareil par défaut et les restrictions de limite d’appareils.](media/device-restrictions-set-default.png)
2. Sous **Restrictions d’inscription** > **Restrictions de type d’appareil**, sélectionnez **Par défaut**.
3. Sous **Tous les utilisateurs**, sélectionnez **Plateformes**. Choisissez **Autoriser** ou **Bloquer** pour chaque plateforme :
  - **Android**
  - **iOS**
  - **MacOS**
  - **Windows**

  Cliquez sur **Enregistrer**.
4. Sous **Tous les utilisateurs**, sélectionnez **Configurations de plateforme**, puis les configurations suivantes :
  - **Personally Owned** (Propriété personnelle) : indiquez s’il convient **d’autoriser** ou de **bloquer** les appareils Android et iOS.
  ![Capture d’écran de l’espace de travail de restrictions sur les appareils avec les configurations de plateforme d’appareils par défaut indiquant les paramètres de propriété personnelle configurés.](media/device-restrictions-platform-configurations.png)
  Cliquez sur **Enregistrer**.

>[!NOTE]
>Si vous empêchez des appareils Android personnels de s’inscrire, les appareils Android for Work peuvent toujours être inscrits.

## <a name="set-device-limit-restrictions"></a>Définition des restrictions de limite d'appareil
Les restrictions d’inscription par défaut s’appliquent à tous les utilisateurs auxquels des restrictions d’inscription de priorité plus élevée ne sont pas affectées.  
1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis **Restrictions d’inscription**.
2. Choisissez **Restrictions d’inscription** > **Restrictions de limite d’appareils**.
3. Sous **Tous les utilisateurs**, sélectionnez **Limite d’appareils**. Spécifiez le nombre maximal d’appareils inscrits par utilisateur.  
![Capture d’écran du panneau des restrictions de limite d’appareils avec les restrictions de limite d’appareils.](./media/device-restrictions-limit.png)

  Cliquez sur **Enregistrer**.
