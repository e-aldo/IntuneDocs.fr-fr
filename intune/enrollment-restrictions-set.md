---
title: "Définir des restrictions d’inscription dans Intune"
titlesuffix: Azure portal
description: "Restriction de l’inscription par la plateforme et définition d’une limite d’inscriptions d’appareils dans Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 06c0c58992a2119aff7fd5be54ae90be886d2a53
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="set-enrollment-restrictions"></a>Définir des restrictions d’inscription

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur Intune, vous pouvez déterminer les appareils qui peuvent s’inscrire à la gestion avec Intune. Utilisez le portail Azure pour définir les restrictions suivantes pour l’inscription d’appareils :

- Nombre maximal d’appareils inscrits
- Plateformes d’appareils qui peuvent s’inscrire :
  - Android
  - iOS
  - macOS
  - Windows
- Version du système d’exploitation de la plateforme (iOS et Android uniquement)
  - Version minimale
  - Version maximale
- Restreindre les appareils personnels (iOS, Android, macOS uniquement)

>[!NOTE]
>Les restrictions d’inscription ne sont pas des fonctionnalités de sécurité. Des appareils compromis peuvent falsifier leur caractère. Ces restrictions représentent une barrière de meilleur effort pour les utilisateurs non malveillants.

## <a name="set-device-type-restrictions"></a>Définition des restrictions de type d'appareil
Les restrictions d’inscription par défaut s’appliquent à l’ensemble des utilisateurs et des inscriptions sans utilisateur.
1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Choisissez **Inscription de l’appareil** > **Restrictions d’inscription**.
4. Sous **Restrictions d’inscription** > **Restrictions de type d’appareil**, sélectionnez **Par défaut**.
5. Sous **Tous les utilisateurs**, sélectionnez **Plateformes**. Choisissez **Autoriser** ou **Bloquer** pour chaque plateforme :
  - **Android**
  - **iOS**
  - **MacOS**
  - **Windows**

  Cliquez sur **Enregistrer**.
6. Sous **Tous les utilisateurs**, sélectionnez **Configurations de plateforme**, puis les configurations suivantes. Pour chaque plateforme autorisée, vous pouvez configurer les options suivantes :
  - **Versions** : spécifiez les versions **Min** et **Max** du système d’exploitation de la plateforme pour les appareils Android et iOS. Les versions du système d’exploitation ne s’appliquent pas aux appareils inscrits par le biais du Programme d’inscription des appareils, d’Apple School Manager ou de l’application Apple Configurator.
  - **Propriété personnelle** : indiquez s’il convient **d’autoriser** ou de **bloquer** les appareils Android, iOS et macOS.
  ![Capture d’écran de l’espace de travail de restrictions sur les appareils avec les configurations de plateforme d’appareils par défaut indiquant les paramètres de propriété personnelle configurés.](media/device-restrictions-platform-configurations.png)
  Cliquez sur **Enregistrer**.

>[!NOTE]
>Si vous bloquez l’inscription des appareils Android personnels, les appareils Android for Work personnels peuvent quand même être inscrits.

## <a name="set-device-limit-restrictions"></a>Définition des restrictions de limite d'appareil
Les restrictions d’inscription par défaut s’appliquent à tous les utilisateurs.
1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Choisissez **Inscription de l’appareil** > **Restrictions d’inscription**.
4. Dans le portail Azure, choisissez **Inscription de l’appareil**, puis **Restrictions d’inscription**.
5. Choisissez **Restrictions d’inscription** > **Restrictions de limite d’appareils**.
6. Sous **Tous les utilisateurs**, sélectionnez **Limite d’appareils**. Spécifiez le nombre maximal d’appareils inscrits par utilisateur.  
![Capture d’écran du panneau des restrictions de limite d’appareils avec les restrictions de limite d’appareils.](./media/device-restrictions-limit.png)

  Cliquez sur **Enregistrer**.
