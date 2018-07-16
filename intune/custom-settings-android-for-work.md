---
title: Paramètres de profil personnalisé Intune pour les profils professionnels Android
titlesuffix: Microsoft Intune
description: Découvrez comment créer des paramètres de profil personnalisé Microsoft Intune pour les appareils avec profil professionnel Android.
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
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905289"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Créer des paramètres de profil personnalisé Intune pour les appareils avec profil professionnel Android

Utilisez la stratégie de configuration personnalisée de profil professionnel Android d’Intune pour affecter des paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils avec profil professionnel Android. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres Android qui ne sont pas configurables avec des stratégies Intune. Intune prend en charge un nombre limité de stratégies personnalisées Android à l’heure actuelle. Consultez les exemples de cet article pour savoir quelles stratégies vous pouvez configurer.

## <a name="create-a-custom-profile"></a>Créer un profil personnalisé

1. Suivez les instructions figurant dans le [Guide pratique pour la configuration des paramètres d’appareils personnalisés](custom-settings-configure.md) pour commencer. Pour **Plateforme** choisissez **Android Entreprise** et pour **Type de profil**, choisissez **Personnalisé**.
2. Dans le panneau **Paramètres OMA-URI personnalisés**, cliquez sur **Ajouter** pour ajouter un nouveau paramètre.
3. Dans le panneau **Ajouter une ligne**, configurez les éléments suivants :
    - **Nom** : entrez un nom unique pour les paramètres personnalisés de profil professionnel Android pour pouvoir l’identifier dans le portail Azure.
    - **Description** : fournissez une description générale de la stratégie personnalisée Android et d’autres informations pertinentes pour mieux la localiser.
    - **OMA-URI** : entrez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.
    - **Type de données** : sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez entre **Chaîne**, **Chaîne (fichier XML)**, **Date et heure**, **Entier**, **Virgule flottante**, **Booléen** ou **Base64 (fichier)**.
    - **Valeur** : spécifiez la valeur à associer à l’identificateur OMA-URI spécifié précédemment. La méthode que vous utilisez pour renseigner cette valeur varie en fonction du type de données que vous avez sélectionné. Par exemple, si vous avez choisi **Date et heure**, vous devez sélectionner la valeur à partir d’un sélecteur de dates.
4. Lorsque vous avez terminé, cliquez sur OK pour revenir aux **Paramètres OMA-URI personnalisés**, puis ajoutez davantage de paramètres ou cliquez sur **Créer** pour créer le profil personnalisé.


## <a name="example"></a>Exemple

Dans cet exemple, vous créez un profil personnalisé que vous pouvez utiliser pour spécifier si les actions de copier et coller entre applications professionnelles et personnelles sont ou non autorisées sur les appareils avec profil professionnel Android.

1. Utilisez la procédure de cet article pour créer un profil personnalisé pour les appareils avec profil professionnel Android en utilisant les valeurs suivantes :
    - **Nom** : entrez « Bloquer la fonction copier/coller » ou le texte de votre choix.
    - **Description** : entrez « Bloquer la fonction copier/coller entre les applications professionnelles et personnelles » ou le texte de votre choix.
    - **OMA-URI** : entrez **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Type de données** : sélectionnez **Booléen** pour indiquer que la valeur de cette OMA-URI est soit **True** soit **False**.
    - **Valeur** : sélectionnez **True**.
2. Vous devez retrouver un paramètre similaire à cette image.
![Bloquer la fonction copier/coller pour un profil professionnel Android.](./media/custom-policy-afw-copy-paste.png)
3. Désormais, quand vous attribuez ce profil personnalisé à des appareils avec profil professionnel Android que vous gérez, la fonction copier/coller sera bloquée entre les applications du profil professionnel et du profil personnel.