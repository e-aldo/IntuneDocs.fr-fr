---
title: Paramètres personnalisés dans Microsoft Intune pour les appareils exécutant Windows Phone 8.1
titleSuffix: ''
description: Découvrez les paramètres que vous pouvez utiliser dans un profil personnalisé Windows Phone 8.1.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83c123f3752680dbc7faca76aa525a0f035831d7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-phone-81"></a>Paramètres d’appareil personnalisés dans Microsoft Intune pour les appareils exécutant Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Utilisez le profil **Personnalisé** Windows Phone 8.1 de Microsoft Intune pour affecter les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Windows Phone 8.1. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres qui ne sont pas configurables avec d’autres stratégies Intune.

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a>Paramètres de stratégie personnalisés pour les appareils Windows Phone 8.1

1. Suivez les instructions figurant dans [Configuration de paramètres d'appareil personnalisés dans Microsoft Intune](custom-settings-configure.md) pour commencer.
2. Dans le volet **Paramètres OMA-URI personnalisés**, choisissez **Ajouter** pour ajouter un ou plusieurs paramètres OMA-URI.
3. Dans le volet **Ajouter une ligne**, configurez les valeurs suivantes pour chaque paramètre :
    - **Nom** : affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.
    - **Description** - Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.
    - **OMA-URI** : spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Type de données** : sélectionnez le type de données pour lequel spécifier ce paramètre OMA-URI. Choisissez parmi **Chaîne**, **Chaîne (XML)**, **Date et heure**, **Entier**, **Virgule flottante**, **Booléen** et **Base64**.
    - **Valeur** : entrez la valeur ou le fichier à associer à l’identificateur OMA-URI que vous avez entré.

4. Cliquez sur **OK** lorsque vous avez terminé, puis continuez à ajouter d’autres paramètres si nécessaire.
