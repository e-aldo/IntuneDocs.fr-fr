---
title: "Supprimer les données d’entreprise d’appareils avec Intune"
titleSuffix: Intune on Azure
description: "Apprenez à supprimer uniquement les données d’entreprise des appareils que vous gérez avec Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Supprimer les données d’entreprise des appareils gérés par Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Supprimer les données d’entreprise** supprime uniquement les données d’entreprise des appareils gérés par Intune. Cela ne supprime pas les données personnelles de l’appareil. L’appareil ne sera plus géré par Intune et ne sera plus en mesure d’accéder aux ressources d’entreprise (non pris en charge pour les appareils Windows joints à Azure Active Directory).

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, puis choisissez l’action à distance d’appareil **Supprimer les données d’entreprise**.

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.
