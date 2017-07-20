---
title: "Restrictions d'appareil Intune pour Windows 10 Collaboration"
titleSuffix: Intune on Azure
description: "Découvrez les restrictions d’appareils disponibles pour les appareils Windows 10 Collaboration."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e7e6e5093b09d7a221083cd36a8d3e5ecbbb8c2
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Windows 10 Collaboration dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

- **Sortir l'écran du mode veille quand une personne est dans la pièce** - Permet à l’appareil de sortir automatiquement quand son capteur détecte la présence d’une personne dans la pièce.
- **Code confidentiel pour la projection sans fil** - Indique si vous devez entrer un code confidentiel avant de pouvoir utiliser les fonctionnalités de projection sans fil de l’appareil.
- **Projection sans fil Miracast** - Si vous voulez que l’appareil Windows 10 Collaboration utilise des appareils activés pour Miracast pour la projection, sélectionnez cette option.
- **Informations sur la réunion affichées sur l’écran d’accueil** - Activez cette option pour choisir les informations qui s’affichent sur la vignette Réunions de l’écran d’accueil. Vous pouvez :
    - **Afficher uniquement l’organisateur et l’heure**
    - **Afficher l’organisateur, l’heure et l’objet (objet masqué pour les réunions privées)**
- **URL de l'image d'arrière-plan de l'écran d'accueil** - Activez ce paramètre pour afficher un arrière-plan personnalisé sur l’écran **Bienvenue** des appareils Windows 10 Collaboration à partir de l’URL que vous spécifiez.<br>L’image doit être au format PNG et l’URL doit commencer par **https://**.
- **Fenêtre de maintenance pour les mises à jour** - Configure la fenêtre quand des mises à jour peuvent avoir lieu sur l’appareil. Vous pouvez configurer l’heure de début de la fenêtre et la durée (de 1 à 5 heures).
- **Azure Operational Insights** - Azure Operational Insights, qui fait partie de la suite Microsoft Operations Manager, collecte, stocke et analyse les données des fichiers journaux provenant d’appareils Windows 10 Collaboration.<br>Pour vous connecter à Azure Operational insights, vous devez spécifier un **ID d’espace de travail** et une **Clé d’espace de travail**.

## <a name="next-steps"></a>Étapes suivantes

Aidez-vous des informations contenues dans le [Guide pratique pour configurer des paramètres de restriction d’appareils](device-restrictions-configure.md) pour enregistrer et affecter le profil à des utilisateurs et appareils.
