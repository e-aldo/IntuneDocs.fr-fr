---
title: "Paramètres personnalisés d’Intune pour les appareils Windows Phone 8.1 | Préversion Intune Azure | Microsoft Docs"
description: "Préversion Intune Azure : Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows Phone 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: ab1ad9852b8f9145f405bb71cf52bfcb00e078f6
ms.lasthandoff: 02/16/2017


---

# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a>Paramètres personnalisés pour les appareils Windows Phone 8.1 dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez le profil **Personnalisé** Microsoft Intune Windows Phone 8.1 pour déployer les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Windows Phone 8.1. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres qui ne sont pas configurables avec d’autres stratégies Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Paramètres de stratégie personnalisés pour les appareils Windows Phone 8.1

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](how-to-configure-custom-settings.md) pour commencer.
2. Dans le panneau **Créer un profil**, choisissez **Paramètres** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Sur le panneau **Ajouter une ligne**, configurez les valeurs suivantes pour chaque paramètre :
    - **Nom** - Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** - Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.
    - **OMA-URI** - Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Type de données** - Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne**, **Date et heure**, **Entier**, **Virgule flottante** ou **Booléen**.
    - **Valeur** - Entrez la valeur à associer à l’identificateur OMA-URI que vous avez entré.

4. Cliquez sur **OK** lorsque vous avez terminé, puis continuez à ajouter d’autres paramètres si nécessaire.

