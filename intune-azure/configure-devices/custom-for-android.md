---
title: "Paramètres personnalisés d’Intune pour les appareils Android | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5ab494a3dd1e1bdea9703ab314574b192c5208ee
ms.openlocfilehash: 3a80a69a27b540b66fb96e098c0b0f66a0854297


---

# <a name="custom-settings-for-android-devices-in-intune-azure-preview"></a>Paramètres personnalisés pour les appareils Android dans la version préliminaire d'Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez le profil Microsoft Intune Android **personnalisé** pour déployer les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Android qui ne sont pas configurables avec des stratégies Intune.

## <a name="custom-profile-settings-for-android-devices"></a>Paramètres de profil personnalisés pour les appareils Android

1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](how-to-configure-custom-settings.md) pour commencer.
2. Dans le panneau **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Sur le panneau **Modifier une ligne**, configurez les valeurs suivantes pour chaque paramètre :
    - **Nom** : affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** : entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.
    - **Type de données** : sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne**, **Chaîne (XML)**, **Date et heure**, **Entier**, **Virgule flottante** ou **Booléen**.
    - **OMA-URI** : spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Valeur** : entrez la valeur à associer à l’identificateur OMA-URI que vous avez entré.
4. Cliquez sur **OK** lorsque vous avez terminé, puis continuez à ajouter d’autres paramètres si nécessaire.



<!--HONumber=Feb17_HO1-->


