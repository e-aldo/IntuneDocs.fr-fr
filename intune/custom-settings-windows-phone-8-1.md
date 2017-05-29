---
title: "Paramètres personnalisés Intune pour les appareils Windows Phone 8.1"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 646d0ec4274e068487ad9546ff0b5dabfc815e46
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Paramètres personnalisés pour les appareils Windows Phone 8.1 dans Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Utilisez le profil **Personnalisé** Windows Phone 8.1 de Microsoft Intune pour affecter les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Windows Phone 8.1. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres qui ne sont pas configurables avec d’autres stratégies Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Paramètres de stratégie personnalisés pour les appareils Windows Phone 8.1

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Sur le panneau **Ajouter une ligne**, configurez les valeurs suivantes pour chaque paramètre :
    - **Nom** - Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** - Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.
    - **OMA-URI** - Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Type de données** - Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne**, **Date et heure**, **Entier**, **Virgule flottante** ou **Booléen**.
    - **Valeur** - Entrez la valeur à associer à l’identificateur OMA-URI que vous avez entré.

4. Cliquez sur **OK** lorsque vous avez terminé, puis continuez à ajouter d’autres paramètres si nécessaire.

