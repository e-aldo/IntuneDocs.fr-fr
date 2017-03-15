---
title: "Ajouter des identificateurs IMEI à Intune"
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment ajouter des identificateurs d’entreprise (numéros IMEI) à Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: d8cb15d1b8c1c100f15084e43d2c3c4633fd64b5
ms.openlocfilehash: f12d538b1f4cd327b893d234f2b558185cdd9d85
ms.lasthandoff: 03/09/2017

---

# <a name="add-corporate-identifiers"></a>Ajouter des identificateurs d’entreprise

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vous pouvez créer une liste de numéros International Mobile Equipment Identity (IMEI) afin d’identifier les appareils d’entreprise. Ces appareils peuvent être inscrits ou non, et avoir un état « Inscrit » ou « Non contacté ». « Non contacté » signifie que l’appareil ne se connectera jamais au service Intune.

Pour créer la liste, préparez une liste à deux colonnes de valeurs séparées par des virgules (.csv), sans en-tête. Ajoutez l’identificateur IMEI dans la colonne de gauche et les détails dans la colonne de droite. Le maximum actuel de la liste est de 500 lignes.

Dans un éditeur de texte, la liste .csv ressemble à ceci :

01 234567 890123,détails de l’appareil</br>
02 234567 890123,Détails sur l'appareil

**Pour ajouter une liste .csv d’identificateurs d’entreprise**

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **inscrire des appareils**, puis choisissez **Identificateurs d’appareil d’entreprise**.

3. Si vous importez un fichier avec de nouvelles informations pour remplacer celles existantes, sélectionnez **Remplacer les informations des identificateurs existants** pour que les nouveaux détails remplacent les informations existantes.

4. Accédez au fichier CSV d’IMEI, puis sélectionnez **Ajouter**.

> [!IMPORTANT]
> Certains appareils Android ont plusieurs numéros IMEI. Intune inventorie un seul numéro IMEI par appareil. Si vous importez un numéro IMEI mais qu’il ne s’agit pas de celui inventorié par Intune, l’appareil est classé comme appareil personnel plutôt que comme appareil d’entreprise. Si vous importez plusieurs numéros IMEI pour un appareil, les numéros non inventoriés affichent **Inconnu** comme état de l’inscription.

**Pour supprimer une liste .csv d’identificateurs d’entreprise**

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **inscrire des appareils**, puis choisissez **Identificateurs d’appareil d’entreprise**.

3. Choisissez **Supprimer**.

