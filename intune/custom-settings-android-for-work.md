---
title: Paramètres de profil Intune personnalisés pour Android for Work
titlesuffix: Microsoft Intune
description: Découvrez comment créer des paramètres de profil Intune personnalisés Microsoft Intune pour les appareils Android for Work.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d7d1512514465b618435b8e699c581534384d2c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>Créer des paramètres de profil Intune personnalisés pour les appareils Android for Work

Utilisez la stratégie de configuration personnalisée Android for Work d’Intune pour affecter les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android for Work. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres Android qui ne sont pas configurables avec des stratégies Intune. Intune prend en charge un nombre limité de stratégies personnalisées Android à l’heure actuelle. Consultez les exemples de cette rubrique pour savoir quelles stratégies vous pouvez configurer.

## <a name="create-a-custom-profile"></a>Créer un profil personnalisé

1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](custom-settings-configure.md) pour commencer.
2. Dans le panneau **Paramètres OMA-URI personnalisés**, cliquez sur **Ajouter** pour ajouter un nouveau paramètre.
3. Dans le panneau **Ajouter une ligne**, configurez les éléments suivants :
    - **Nom** : entrez un nom unique pour les paramètres personnalisés d’Android for Work pour pouvoir l’identifier dans le portail Azure.
    - **Description** : fournissez une description générale de la stratégie personnalisée Android et d’autres informations pertinentes pour mieux la localiser.
    - **OMA-URI** : entrez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Type de données** : sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez entre **Chaîne**, **Chaîne (fichier XML)**, **Date et heure**, **Entier**, **Virgule flottante**, **Booléen** ou **Base64 (fichier)**.
    - **Valeur** : spécifiez la valeur à associer à l’identificateur OMA-URI spécifié précédemment. La méthode que vous utilisez pour renseigner cette valeur varie en fonction du type de données que vous avez sélectionné. Par exemple, si vous avez choisi **Date et heure**, vous devez sélectionner la valeur à partir d’un sélecteur de dates.
4. Lorsque vous avez terminé, cliquez sur OK pour revenir aux **Paramètres OMA-URI personnalisés**, puis ajoutez davantage de paramètres ou cliquez sur **Créer** pour créer le profil personnalisé.


## <a name="example"></a>Exemple

Dans cet exemple, vous allez créer un profil personnalisé que vous pourrez utiliser pour spécifier si les actions Copier et Coller entre applications professionnelles et personnelles sont ou non autorisées sur les appareils Android for Work gérés.

1. Utilisez la procédure de cette rubrique pour créer un profil personnalisé pour les appareils Android for Work à l’aide des valeurs suivantes :
    - **Nom** : entrez « Bloquer la fonction copier/coller » ou le texte de votre choix.
    - **Description** : entrez « Bloquer la fonction copier/coller entre les applications professionnelles et personnelles » ou le texte de votre choix.
    - **OMA-URI** : entrez **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Type de données** : sélectionnez **Booléen** pour indiquer que la valeur de cette OMA-URI est soit **True** soit **False**.
    - **Valeur** : sélectionnez **True**.
2. Vous devez retrouver un paramètre similaire à cette image.
![Bloquer la fonction copier/coller pour Android for Work.](./media/custom-policy-afw-copy-paste.png)
3. À présent, lorsque vous attribuez ce profil personnalisé aux appareils Android for Work que vous gérez, la fonction copier/coller sera bloquée entre les applications du profil professionnel et du profil personnel.