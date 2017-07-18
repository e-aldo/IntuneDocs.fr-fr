---
title: "Ajouter des identificateurs IMEI à Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment ajouter des identificateurs d’entreprise (numéros IMEI) à Microsoft Intune. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57ab3b79ad53a4b195fac426d211a114f054602f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="add-corporate-identifiers"></a>Ajouter des identificateurs d’entreprise

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur informatique, vous pouvez créer et importer un fichier de valeurs séparées par des virgules (.csv) qui répertorie les numéros International Mobile Equipment Identity (IMEI) ou les numéros de série afin d’identifier les appareils d’entreprise. Vous pouvez déclarer le numéro de série uniquement pour les appareils iOS et Android. Chaque numéro IMEI ou numéro de série peut contenir des détails spécifiés dans la liste pour des raisons administratives.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Découvrez comment trouver un numéro de série d’appareil Apple](https://support.apple.com/HT204308).
[Découvrez comment trouver votre numéro de série d’appareil Android](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Ajouter des identificateurs d’entreprise
Pour créer la liste, préparez une liste à deux colonnes de valeurs séparées par des virgules (.csv), sans en-tête. Ajoutez les numéros de série ou IMEI dans la colonne de gauche, et les détails dans la colonne de droite. Vous ne pouvez importer qu’un seul type d’ID, numéro IMEI ou numéro de série dans un fichier .csv. Les détails sont limités à 128 caractères et sont réservés à des fins d’administration. Les détails ne sont pas affichés sur l’appareil. La limite actuelle est de 500 lignes par fichier .csv.

**Chargez un fichier .csv qui contient les numéros de série** : créez une liste de valeurs séparées par des virgules (.csv) de deux colonnes sans en-tête, limitée à 5 000 appareils ou à 5 Mo par fichier .csv.

|||
|-|-|
|&lt;ID 1&gt;|&lt;Détails de l’appareil 1&gt;|
|&lt;ID 2&gt;|&lt;Détails de l’appareil 2&gt;|

Dans un éditeur de texte, ce fichier .csv s'affiche comme suit :

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Certains appareils Android ont plusieurs numéros IMEI. Intune ne lit qu’un seul numéro IMEI par appareil inscrit. Si vous importez un numéro IMEI mais qu’il ne s’agit pas de celui inventorié par Intune, l’appareil est classé comme appareil personnel plutôt que comme appareil d’entreprise. Si vous importez plusieurs numéros IMEI pour un appareil, les numéros non inventoriés affichent **Inconnu** comme état de l’inscription.

**Pour ajouter une liste .csv d’identificateurs d’entreprise**

1. Dans le portail Intune, choisissez **Inscription de l’appareil** > **Restrictions d’inscription**, choisissez **Identificateurs d’appareil d’entreprise**, puis cliquez sur **Ajouter**.

 ![Capture d’écran de l’espace de travail d’identificateurs d’appareils d’entreprise avec le bouton Ajouter mis en surbrillance.](./media/add-corp-id.png)

2. Dans le panneau **Ajouter des identificateurs**, spécifiez le type d’identificateur, **IMEI** ou **Série**. Vous pouvez spécifier si les numéros précédemment importés doivent **Remplacer les informations des identificateurs existants**.

3. Cliquez sur l’icône du dossier et spécifiez le chemin de la liste que vous voulez importer. Accédez au fichier .csv, puis sélectionnez **Ajouter**. Vous pouvez cliquer sur **Actualiser** pour afficher les nouveaux identificateurs d’appareils.

Une fois importés, ces appareils peuvent ou non être inscrits et afficher l’état **Inscrit** ou **N’a pas contacté**. **N’a pas contacté** signifie que l’appareil n’a jamais communiqué avec le service Intune.

## <a name="delete--corporate-identifiers"></a>Supprimer des identificateurs d’entreprise

1. Dans le portail Intune, choisissez **Inscription de l’appareil** > **Restrictions d’inscription**, choisissez **Identificateurs d’appareil d’entreprise**, puis cliquez sur **Supprimer**.

3. Dans le panneau **Supprimer des identificateurs**, accédez au fichier .csv des identificateurs d’appareils à supprimer, puis cliquez sur **Supprimer**.

## <a name="imei-specifications"></a>Spécifications IMEI
Pour obtenir des spécifications détaillées sur les IMEI (International Mobile Equipment Identifiers), consultez [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).
