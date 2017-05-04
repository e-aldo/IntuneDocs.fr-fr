---
title: "Ajouter des identificateurs IMEI à Intune"
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment ajouter des identificateurs d’entreprise (numéros IMEI) à Microsoft Intune. "
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 15415f9f31d520d66257df3a7e134e4b1de8467c
ms.openlocfilehash: 8c9e6b39ee01697d993e5738ec35e8a64fc8e236
ms.lasthandoff: 04/07/2017

---

# <a name="add-corporate-identifiers"></a>Ajouter des identificateurs d’entreprise

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

En tant qu’administrateur informatique, vous pouvez créer et importer un fichier de valeurs séparées par des virgules (.csv) qui répertorie les numéros International Mobile Equipment Identity (IMEI) afin d’identifier les appareils d’entreprise. Chaque numéro IMEI peut contenir des détails spécifiés dans la liste pour des raisons administratives.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

## <a name="add-corporate-identifiers"></a>Ajouter des identificateurs d’entreprise
Pour créer la liste, préparez une liste à deux colonnes de valeurs séparées par des virgules (.csv), sans en-tête. Ajoutez l’identificateur IMEI dans la colonne de gauche et les détails dans la colonne de droite. Les détails sont limités à 128 caractères et sont réservés à des fins d’administration. Les détails ne sont pas affichés sur l’appareil. La limite actuelle est de 500 lignes par fichier .csv.

**Chargez un fichier .csv qui contient les numéros de série** : créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5 000 appareils ou à 5 Mo par fichier .csv. 

|||
|-|-|
|&lt;IMEI 1&gt;|&lt;Détails de l’appareil 1&gt;|
|&lt;IMEI 2&gt;|&lt;Détails de l’appareil 2&gt;|

Dans un éditeur de texte, ce fichier .csv s'affiche comme suit :

```
01234567890123,device details
02234567890123,device details
```


> [!IMPORTANT]
> Certains appareils Android ont plusieurs numéros IMEI. Intune inventorie un seul numéro IMEI par appareil. Si vous importez un numéro IMEI mais qu’il ne s’agit pas de celui inventorié par Intune, l’appareil est classé comme appareil personnel plutôt que comme appareil d’entreprise. Si vous importez plusieurs numéros IMEI pour un appareil, les numéros non inventoriés affichent **Inconnu** comme état de l’inscription.

**Pour ajouter une liste .csv d’identificateurs d’entreprise**

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscription de l’appareil** > **Restrictions d’inscription**, choisissez **Identificateurs d’appareil d’entreprise**, puis cliquez sur **Ajouter**.

3. Dans le panneau **Ajouter des identificateurs**, spécifiez le type d’identificateur **IMEI**. Vous pouvez spécifier si les numéros précédemment importés doivent **Remplacer les informations des identificateurs existants**.  

4. Cliquez sur l’icône du dossier et spécifiez le chemin de la liste que vous voulez importer. Accédez au fichier CSV d’IMEI, puis sélectionnez **Ajouter**.

Une fois importés, ces appareils peuvent ou non être inscrits et afficher l’état **Inscrit** ou **N’a pas contacté**. **N’a pas contacté** signifie que l’appareil n’a jamais communiqué avec le service Intune.

## <a name="delete--corporate-identifiers"></a>Supprimer des identificateurs d’entreprise

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscription de l’appareil** > **Restrictions d’inscription**, choisissez **Identificateurs d’appareil d’entreprise**, puis cliquez sur **Supprimer**.

3. Dans le panneau **Supprimer des identificateurs**, accédez au fichier .csv des identificateurs d’appareils à supprimer, puis cliquez sur **Supprimer**.

## <a name="imei-specifications"></a>Spécifications IMEI
Pour obtenir des spécifications détaillées sur les IMEI (International Mobile Equipment Identifiers), consultez [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

