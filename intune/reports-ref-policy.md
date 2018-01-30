---
title: "Stratégie | Microsoft Docs"
description: "Rubrique de référence sur la catégorie Stratégie de collections d’entités dans l’API d’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4b3178b8469b5c92e4124ab00f9a635e63568d77
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="reference-for-policy-entities"></a>Informations de référence sur les entités de stratégie

La catégorie **Stratégie** contient des entités pour appareils mobiles qui font le suivi d’informations, notamment les suivantes :

  -  Inventaire des profils de configuration d’appareil, des profils de configuration d’application et des stratégies de conformité  
  -  Nombre d’appareils, par jour, dans un état de réussite, d’attente, d’échec ou d’erreur  
  -  Nombre d’appareils, par jour, dans un état de réussite, d’attente, d’échec ou d’erreur  
  -  Nombre cumulé d’appareils dans un état de réussite, d’attente, d’échec ou d’erreur  

## <a name="policy"></a>Stratégie

L’entité **Policy** répertorie les profils de configuration d’appareil, les profils de configuration d’application et les profils de conformité. Vous pouvez affecter les stratégies à un groupe de votre entreprise à l’aide de la gestion des appareils mobiles (MDM).

| Propriété  | Description | Exemple |
|---------|------------|--------|
| PolicyKey |Clé unique représentant la stratégie dans l’entrepôt de données. |123 |
| PolicyId |Identificateur unique de la stratégie dans l’entrepôt de données. |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Nom de la stratégie. |« Ligne de base Windows 10 » |
| PolicyVersion |Version de la stratégie. Quand la stratégie est modifiée ou changée, une version plus récente est créée. |1, 2, 3 |
| IsDeleted |Indique si l’enregistrement de stratégie a été mis à jour.  <br>True : la stratégie a un nouvel enregistrement avec des champs mis à jour. <br>False : dernier enregistrement de la stratégie. |Vrai/Faux |
| StartDateInclusiveUTC |Date et heure UTC de création de la stratégie dans l’entrepôt de données. |11/23/2016 12:00:00 AM |
| DeletedDateUTC |Date et heure UTC de l’affectation de la valeur True à IsDeleted. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Date et heure UTC de la dernière modification de la stratégie dans l’entrepôt de données. |11/23/2016 12:00:00 AM |

## <a name="policytype"></a>PolicyType

L’entité **PolicyType** répertorie les types de profils de configuration d’appareil, de profils de configuration d’application et de profils de conformité. Vous pouvez affecter les stratégies à un groupe de votre entreprise à l’aide de la gestion des appareils mobiles (MDM).

| Propriété  | Description | Exemple |
|---------|------------|--------|
| PolicyTypeId |Identificateur unique de la stratégie dans le système source. |123 |
| PolicyTypeKey |Identificateur unique de la stratégie dans l’entrepôt de données. |1 |
| PolicyTypeName |Nom du type de stratégie |Stratégie de conformité Windows 10. |

## <a name="deviceconfiguration"></a>DeviceConfiguration

L’entité **DeviceConfigurationProfileDeviceActivity** répertorie le nombre d’appareils, par jour, dans un état de réussite, d’attente, d’échec ou d’erreur. Le nombre reflète les profils de configuration d’appareil affectés à l’entité. Par exemple, si toutes les stratégies affectées à un appareil sont dans un état de réussite, le compteur de réussite augmente d’une unité pour ce jour-là. Si deux profils sont affectés à un appareil, l’un dans un état de réussite et l’autre dans un état d’erreur, l’entité incrémente le compteur de réussite et affecte à l’appareil un état d’erreur. L’entité répertorie le nombre d’appareils dans chaque état pour un jour donné au cours des 30 derniers jours.

| Propriété  | Description | Exemple |
|---------|------------|--------|
| DateKey |Clé de date qui indique quand l’enregistrement du profil de configuration d’appareil est enregistré dans l’entrepôt de données. |20160703 |
| En attente |Nombre d’appareils uniques en état d’attente. |123 |
| Réussi |Nombre d’appareils uniques en état de réussite. |12 |
| Erreur |Nombre d’appareils uniques en état d’erreur. |10 |
| Échec |Nombre d’appareils uniques en état d’échec. |2 |

## <a name="userconfiguration"></a>UserConfiguration

L’entité **UserConfigurationProfileDeviceActivity** répertorie le nombre d’utilisateurs, par jour, dans un état de réussite, d’attente, d’échec ou d’erreur. Le nombre reflète les profils de configuration d’appareil affectés à l’entité. Par exemple, si toutes les stratégies affectées à un utilisateur sont dans un état de réussite, le compteur de réussite augmente d’une unité pour ce jour-là. Si deux profils sont affectés à un utilisateur, l’un dans un état de réussite et l’autre dans un état d’erreur, nous comptons l’utilisateur comme étant dans un état d’erreur.  L’entité **UserConfigurationProfileDeviceActivity** répertorie le nombre d’utilisateurs dans chaque état pour un jour donné au cours des 30 derniers jours.

| Propriété  | Description | Exemple |
|---------|------------|--------|
| DateKey |Clé de date qui indique quand l’enregistrement du profil de configuration d’appareil est enregistré dans l’entrepôt de données. |20160703 |
| En attente |Nombre d’utilisateurs uniques en état d’attente. |123 |
| Réussi |Nombre d’utilisateurs uniques en état de réussite. |12 |
| Erreur |Nombre d’utilisateurs uniques en état d’erreur. |10 |
| Échec |Nombre d’utilisateurs uniques en état d’échec. |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

L’entité **PolicyTypeActivity** répertorie le nombre cumulé d’appareils dans un état de réussite, d’attente, d’échec ou d’erreur. Elle répertorie ces états, par jour, par rapport à un profil de configuration d’appareil, un profil de configuration d’application ou une stratégie de conformité.

| Propriété  | Description | Exemple |
|---------|------------|--------|
| DateKey |Clé de date qui indique quand l’enregistrement du profil de configuration d’appareil est enregistré dans l’entrepôt de données. |20160703 |
| PolicyKey |Clé de stratégie pouvant être jointe à la stratégie pour obtenir le nom de la stratégie. |Ligne de base Windows 10 |
| PolicyTypeKey |Type de clé de stratégie pouvant être joint au type de stratégie pour obtenir le nom du type de la stratégie. |Stratégie de conformité Windows 10 |
| En attente |Nombre d’appareils uniques en état d’attente. |123 |
| Réussi |Nombre d’appareils uniques en état de réussite. |12 |
| Erreur |Nombre d’appareils uniques en état d’erreur. |10 |
| Fail- |Nombre d’appareils uniques en état d’échec. |2 |