---
title: "Ajout d’identificateurs IMEI à Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment ajouter des identificateurs d’entreprise (numéros IMEI) à Microsoft Intune. "
keywords: 
author: staciebarker
ms.author: stabark
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: e134a6e3ff143dacce1d70ef0ab44ade0722ed57

---

# <a name="add-corporate-identifiers"></a>Ajouter des identificateurs d’entreprise

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vous pouvez créer une liste de numéros International Mobile Equipment Identity (IMEI) afin d’identifier les appareils d’entreprise. Ces appareils peuvent être inscrits ou non, et avoir un état « Inscrit » ou « Non contacté ». « Non contacté » signifie que l’appareil ne se connectera jamais au service Intune.

Pour créer la liste, préparez une liste à deux colonnes de valeurs séparées par des virgules (.csv), sans en-tête. Ajoutez l’identificateur IMEI dans la colonne de gauche et les détails dans la colonne de droite. Le maximum actuel de la liste est de 500 lignes.

Dans un éditeur de texte, la liste .csv ressemble à ceci :

01 234567 890123,détails de l’appareil</br>
02 234567 890123,Détails sur l'appareil

**Pour ajouter une liste .csv d’identificateurs d’entreprise**

1. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**.

2. Dans le panneau Intune, choisissez **inscrire des appareils**, puis choisissez **Identificateurs d’appareil d’entreprise**.

3. Si vous importez un fichier avec de nouvelles informations pour remplacer celles existantes, sélectionnez **Remplacer les informations des identificateurs existants** pour que les nouveaux détails remplacent les informations existantes.

4. Accédez au fichier CSV d’IMEI, puis sélectionnez **Ajouter**.

**Pour supprimer une liste .csv d’identificateurs d’entreprise**

1. Dans le panneau Intune, choisissez **inscrire des appareils**, puis choisissez **Identificateurs d’appareil d’entreprise**.

2. Choisissez **Supprimer**.



<!--HONumber=Feb17_HO1-->


