---
title: "Ajouter des identificateurs d’entreprise à Intune"
titlesuffix: Azure portal
description: "Découvrez comment ajouter des identificateurs d’entreprise (méthode d’inscription, numéros IMEI et numéros de série) à Microsoft Intune. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 82b839943d21cd44c1be457cc8436928f41fe73c
ms.sourcegitcommit: b6a2d55d9c4e3248ff7ef738393f458f1978de44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2017
---
# <a name="identify-devices-as-corporate-owned"></a>Identifier les appareils comme appartenant à l’entreprise

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur Intune, vous pouvez identifier les appareils comme étant propriété de l’entreprise, ce qui en permet une gestion et une identification plus précises. Intune peut effectuer d’autres tâches d’administration et collecter des informations supplémentaires, comme le numéro de téléphone complet et un inventaire des applications des appareils d’entreprise. Vous pouvez également définir des restrictions au niveau des appareils pour bloquer l’inscription des appareils qui n’appartiennent pas à l’entreprise.

Un appareil est identifié comme étant détenu par l’entreprise si l’une des conditions suivantes est vérifiée :

- Appareil inscrit avec un compte de [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md) (toutes les plateformes)
- Appareil inscrit avec le [programme d’inscription des appareils](device-enrollment-program-enroll-ios.md) Apple, [Apple School Manager](apple-school-manager-set-up-ios.md) ou [Apple Configurator](apple-configurator-enroll-ios.md) (iOS uniquement)
- [Appareil identifiés comme appartenant à l’entreprise avant l’inscription](#identify-corporate-owned-devices-with-imei-or-serial-number) avec un numéro IMEI (International Mobile Equipment Identifier) (pour toutes les plateformes avec des numéros IMEI) ou un numéro de série (iOS et Android)
- Appareil inscrit dans Azure Active Directory ou Enterprise Mobility + Security comme appareil Windows 10 Entreprise
- Propriétés de l’appareil spécifiant [l’entreprise comme propriétaire de l’appareil](#change-device-ownership)

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identifier des appareils d’entreprise à l’aide de leur numéro IMEI ou de leur numéro de série

Les administrateurs Intune peuvent créer et importer un fichier de valeurs séparées par des virgules (.csv) qui répertorie les numéros de série ou les numéros IMEI. Intune utilise ces identificateurs pour spécifier l’entreprise comme propriétaire des appareils lors de l’inscription de l’appareil. Vous pouvez déclarer des numéros IMEI pour toutes les plateformes prises en charge. Vous pouvez déclarer un numéro de série seulement pour les appareils iOS, macOS et Android. Chaque numéro IMEI ou numéro de série peut contenir des détails spécifiés dans la liste pour des raisons administratives.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Découvrez comment trouver un numéro de série d’appareil Apple](https://support.apple.com/HT204308).<br>
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
> Certains appareils Android ont plusieurs numéros IMEI. Intune ne lit qu’un seul numéro IMEI par appareil inscrit. Si vous importez un numéro IMEI, mais qu’il ne s’agit pas du numéro IMEI inventorié par Intune, l’appareil est classé comme appareil personnel plutôt que comme appareil d’entreprise. Si vous importez plusieurs numéros IMEI pour un appareil, les numéros non inventoriés présentent l’état d’inscription **Inconnu**.<br>
>Notez également que les numéros de série Android ne sont pas nécessairement uniques ou présents. Vérifiez auprès du fournisseur de votre appareil si le numéro de série est un ID d’appareil fiable.
>Les numéros de série signalés à Intune par l’appareil peuvent ne pas correspondre à l’ID affiché dans les menus Paramètres/À propos d’Android de l’appareil. Vérifiez le type de numéro de série signalé par le fabricant de l’appareil.

### <a name="add-a-csv-list-of-corporate-identifiers"></a>Ajouter une liste .csv d’identificateurs d’entreprise

1. Dans Intune, dans le portail Azure, choisissez **Inscription de l’appareil** > **Identificateurs d’appareil d’entreprise**, puis cliquez sur **Ajouter**.

 ![Capture d’écran de l’espace de travail d’identificateurs d’appareils d’entreprise avec le bouton Ajouter mis en surbrillance.](./media/add-corp-id.png)

2. Dans le panneau **Ajouter des identificateurs**, spécifiez le type d’identificateur : **IMEI** ou **Série**. Vous pouvez spécifier si les numéros précédemment importés doivent **Remplacer les informations des identificateurs existants**.

3. Cliquez sur l’icône du dossier et spécifiez le chemin de la liste que vous voulez importer. Accédez au fichier .csv, puis sélectionnez **Ajouter**. Vous pouvez cliquer sur **Actualiser** pour afficher les nouveaux identificateurs d’appareils.

Les appareils importés ne sont pas nécessairement inscrits. Les appareils peuvent avoir l’état **Inscrit** ou l’état **Non contacté**. **N’a pas contacté** signifie que l’appareil n’a jamais communiqué avec le service Intune.

### <a name="delete-corporate-identifiers"></a>Supprimer des identificateurs d’entreprise

1. Dans Intune, dans le portail Azure, choisissez **Inscription de l’appareil** > **Identificateurs d’appareil d’entreprise**.
2. Sélectionnez les identificateurs d’appareil que vous voulez supprimer, puis choisissez **Supprimer**.
3. Confirmez la suppression.

La suppression d’un identificateur d’entreprise pour un appareil inscrit ne change pas la propriété de l’appareil. Pour changer la propriété d’un appareil, accédez à **Appareils** > **Tous les appareils**, sélectionnez l’appareil, choisissez **Propriétés** et changez la **Propriété de l’appareil**.

### <a name="imei-specifications"></a>Spécifications IMEI
Pour obtenir des spécifications détaillées sur les IMEI (International Mobile Equipment Identifiers), consultez [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Changer la propriété des appareils

Les propriétés des appareils affichent **Propriété** pour chaque enregistrement d’appareil dans Intune. En tant qu’administrateur, vous pouvez spécifier des appareils comme étant **Personnel** ou d’**Entreprise**.

**Pour changer la propriété d’un appareil :**
1. Dans Intune, dans le portail Azure, accédez à **Appareils** > **Tous les appareils**, puis choisissez l’appareil.
3. Choisissez **Propriétés**.
4. Spécifiez pour **Propriété de l’appareil** l’option **Personnel** ou **Entreprise**.

  ![Capture d’écran des propriétés de l’appareil montrant la catégorie Appareil et les options Propriété de l’appareil.](./media/device-properties.png)
