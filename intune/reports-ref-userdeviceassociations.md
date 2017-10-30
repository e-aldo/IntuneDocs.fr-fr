---
title: Association appareil-utilisateur | Microsoft Docs
description: "Rubrique de référence pour la catégorie Association appareil-utilisateur de collection d’entités dans l’API d’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Informations de référence sur l’entité Association appareil-utilisateur

La catégorie **Association appareil-utilisateur** contient l’entité **Association appareil-utilisateur** utilisée pour définir les associations des appareils dans l’organisation.

**Association appareil-utilisateur**

L’entité **Association appareil-utilisateur** représente les associations des appareils définies dans l’organisation.

| Nom               | Description                                                                                      | Exemple                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Identificateur unique de l’utilisateur dans l’entrepôt de données (clé de substitution).                             | 123                    |
| DeviceKey          | Identificateur unique de l’appareil dans l’entrepôt de données.                                           | 123                    |
| CreatedDateTimeUTC | Date et heure UTC à laquelle l’association appareil-utilisateur a été créée.                               | 11/23/2016 12:00:00 AM |
| IsDeleted          | Indique que l’utilisateur a désinscrit cet appareil et que l’association n’est plus d’actualité. | True                   |
| EndedDateTimeUTC   | Date et heure UTC à laquelle IsDeleted est passé à **True**.                                         | 23/06/2017 00:00:00 |