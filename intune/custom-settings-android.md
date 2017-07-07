---
title: "Paramètres personnalisés Intune pour les appareils Android"
titleSuffix: Intune on Azure
description: "Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 014e59c017eac0d54a632e545692e1a1a8053164
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Paramètres personnalisés pour les appareils Android dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez le profil Microsoft Intune Android **personnalisé** pour affecter les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres Android qui ne sont pas configurables avec des stratégies Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Paramètres de profil personnalisés pour les appareils Android

1. Suivez les instructions figurant dans le [Guide pratique pour configurer des paramètres d’appareils personnalisés](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Sur le panneau **Modifier une ligne**, configurez les valeurs suivantes pour chaque paramètre :
    - **Nom** : affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** : entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.
    - **Type de données** : sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne**, **Chaîne (XML)**, **Date et heure**, **Entier**, **Virgule flottante** ou **Booléen**.
    - **OMA-URI** : spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Valeur** : entrez la valeur à associer à l’identificateur OMA-URI que vous avez entré.
4. Cliquez sur **OK** lorsque vous avez terminé, puis continuez à ajouter d’autres paramètres si nécessaire.
