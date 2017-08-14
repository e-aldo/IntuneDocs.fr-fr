---
title: Application | Microsoft Docs
description: "Rubrique de référence sur la catégorie Application de collections d’entités dans l’API d’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e12792445b36ba6657cbe6b2f6c924f6d97fe3c
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2017
---
# <a name="reference-for-application-entities"></a>Informations de référence sur les entités d’application

La catégorie **Application** contient des entités pour appareils mobiles qui font le suivi d’informations, notamment les suivantes :

  -  Versions d’une application
  -  Source d’installation d’une application
  -  Type de développeur à l’origine d’une application
  -  Types de logiciels gérés pour une application, par exemple **sidecar** ou **desktop**
  -  État du programme d’achat en volume (VPP) d’une application

## <a name="apprevision"></a>AppRevision

L’entité **AppRevision** répertorie toutes les versions des applications.

| Propriété  | Description | Exemple |
|---------|------------|--------|
| AppKey |Identificateur unique de l’application |123 |
| ApplicationId |Identificateur unique de l’application (semblable à AppKey, mais il s’agit d’une clé naturelle) |b66bc706-ffff-7437-0340-032819502773 |
| Révision |Version mentionnée par l’administrateur durant le chargement du binaire |2 |
| Titre |Titre de l’application |Excel |
| Éditeur |Éditeur de l’application |Microsoft |
| UploadState |État de chargement de l’application |1 |
| AppTypeKey |Référence à AppType décrite dans la section suivante | |
| VppProgramTypeKey |Référence à VppProgramType décrite ci-dessous | |
| CreationTime |Heure de création de cette révision |11/23/2016 12:00:00 AM |
| ModifiedTime |Heure du dernier changement apporté à cette révision |11/23/2016 12:00:00 AM |
| Size |Taille du binaire | |
| StartDateInclusiveUTC |Date et heure UTC de création de la révision de cette application dans l’entrepôt de données |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |Date et heure UTC correspondant au moment auquel cette révision d’application est devenue obsolète |11/23/2016 12:00:00 AM |
| IsCurrent |Indique si cette version de l’application est active ou non dans l’entrepôt de données |Vrai/Faux |
| RowLastModifiedDateTimeUTC |Date et heure UTC de la dernière modification de cette version d’application dans l’entrepôt de données |11/23/2016 12:00:00 AM |

## <a name="appinstallertypes"></a>AppInstallerTypes

L’entité **AppInstallerTypes** répertorie la source d’installation d’une application.

| Propriété  | Description |
|---------|------------|
| AppTypeID |ID du type |
| AppTypeKey |Clé de substitution pour la clé |
| AppTypeName |Type d’application |

## <a name="example"></a>Exemple

| AppTypeID  | Nom | Description |
|---------|------------|--------|
| 0 |Application de l’Android Store |Application de l’Android Store |
| 1 |Application métier Android |Application métier Android |
| 2 |Application de l’Android Store gérée (GAM) |Application de l’Android Store activée pour la gestion |
| 3 |Application de l’App Store iOS |Application de l’App Store iOS |
| 4 |Application métier iOS |Application métier iOS |
| 5 |Application de l’App Store iOS gérée (GAM ?) |Application de l’App Store iOS activée pour la gestion |
| 6 |Office 365 Pro Plus Suite |Office 365 Pro Plus Suite pour Windows 10 |
| 7 |Application web |Application web |
| 8 |Application du Windows Phone 8.1 Store |Application du Windows Phone 8.1 Store |
| 9 |Application du Windows Store |Application du Windows Store |
| 10 |Applications métier Windows |Application métier AppX Windows |
| 11 |Windows Mobile MSI |Application métier MSI |
| 12 |Application métier Windows Phone |Application métier Windows Phone |

## <a name="applicationtypes"></a>ApplicationTypes

L’entité **ApplicationTypes** répertorie les types possibles pour une application.

| Propriété  | Description |
|---------|------------|
| ApplicationTypeID |ID du type |
| ApplicationTypeKey |Clé de substitution pour la clé |
| ApplicationTypeName |Type d’application |

## <a name="example"></a>Exemple

| ApplicationTypeID  | Nom | Description |
|---------|------------|--------|
| 0 |InHouse |Application développée en interne |
| 1 |DeepLink |Lien vers une application dans un App Store |
| 2 |WebLink |Lien vers l’application web |

## <a name="managedsoftwaretypes"></a>ManagedSoftwareTypes

L’entité **ManagedSoftwareTypes** répertorie les types de logiciels gérés possibles pour une application.

| Propriété  | Description |
|---------|------------|
| SoftwareTypeID |ID du type |
| SoftwareTypeKey |Clé de substitution pour la clé |
| SoftwareTypeName |Type de logiciel |

## <a name="example"></a>Exemple

| SoftwareTypeID  | Nom | Description |
|---------|------------|--------|
| 0 |Bureau |Application de bureau |
| 2 |Mise à jour |Mise à jour de fenêtre |
| 5 |SideCarAgent | |
| 1 |Mobile |Application mobile |
| 3 |WebLink |Lien web |
| 4 |VppDeepLink |Lien vers une application dans l’App Store qui fait partie d’un Programme d’achat en volume (VPP) |

## <a name="vppprogramtypes"></a>VppProgramTypes

L’entité **VppProgramTypes** répertorie les types de VPP possibles pour une application.

| Propriété  | Description |
|---------|------------|
| VppProgramTypeID |ID du type |
| VppProgramTypeKey |Clé de substitution pour la clé |
| VppProgramTypeName |Type de programme VPP |

## <a name="example"></a>Exemple

| VppProgramID  | Nom | Description |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |Programme VPP Microsoft |
| 00000000-0000-0000-0000-000000000000 |Pas encore disponible |Valeur par défaut : aucun VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |Programme VPP Apple |