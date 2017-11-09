---
title: "Association appareil-utilisateur - Entrepôt de données Intune | Microsoft Docs"
description: "Liste des modifications dans l’API de l’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2017
---
# <a name="user-device-association"></a>Association appareil-utilisateur

L’entité **UserDeviceAssociation** contient les associations appareil-utilisateur dans votre organisation.

| Nom               | Description                                                                                      | Exemple                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Identificateur unique de l’utilisateur dans l’entrepôt de données. (Clé de substitution).                              | 123                    |
| DeviceKey          | Identificateur unique de l’appareil dans l’entrepôt de données.                                            | 123                    |
| CreatedDateTimeUTC | Date et heure auxquelles l’association appareil-utilisateur a été créée. Utilise le format UTC.                                | 11/23/2016 12:00:00 AM |
| IsDeleted          | Indique que l’utilisateur a désinscrit cet appareil et que l’association n’est plus d’actualité. | Vrai/Faux             |
| EndedDateTimeUTC   | Date et heure UTC à laquelle IsDeleted est passé à **True**.                                              | 23/06/2017 00:00:00 |
