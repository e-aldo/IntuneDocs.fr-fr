---
title: "Restrictions d’appareils Intune pour Windows 10 Collaboration | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : en savoir plus sur les restrictions d’appareils disponibles pour les appareils Windows 10 Collaboration."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 342681922944fd1ea4be6aa4ddcb0725f6cfd42b


---

# <a name="windows-10-team-device-restriction-settings-in-intune-azure-preview"></a>Paramètres de restriction des appareils Windows 10 Collaboration dans la version préliminaire d'Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

- **Sortir l'écran du mode veille quand une personne est dans la pièce** - Permet à l’appareil de sortir automatiquement quand son capteur détecte la présence d’une personne dans la pièce.
- **Code confidentiel pour la projection sans fil** - Indique si vous devez entrer un code confidentiel avant de pouvoir utiliser les fonctionnalités de projection sans fil de l’appareil.
- **Projection sans fil Miracast** - Activez cette option si vous voulez que l’appareil Windows 10 Collaboration utilise des appareils activés pour Miracast pour la projection.
- **Informations sur la réunion affichées sur l’écran d’accueil** - Si vous activez cette option, vous pouvez choisir les informations qui sont affichées sur la vignette Réunions de l’écran d’accueil. Vous pouvez :
    - **Afficher uniquement l’organisateur et l’heure**
    - **Afficher l’organisateur, l’heure et l’objet (objet masqué pour les réunions privées)**
- **URL de l'image d'arrière-plan de l'écran d'accueil** - Activez ce paramètre pour afficher un arrière-plan personnalisé sur l’écran **Bienvenue** des appareils Windows 10 Collaboration à partir de l’URL que vous spécifiez.<br>L’image doit être au format PNG et l’URL doit commencer par **https://**.
- **Fenêtre de maintenance pour les mises à jour** - Configure la fenêtre quand des mises à jour peuvent avoir lieu sur l’appareil. Vous pouvez configurer l’heure de début de la fenêtre et la durée (de 1 à 5 heures).
- **Azure Operational Insights** - Azure Operational Insights, qui fait partie de la suite Microsoft Operations Manager, collecte, stocke et analyse les données des fichiers journaux provenant d’appareils Windows 10 Collaboration.<br>Pour vous connecter à Azure Operational insights, vous devez spécifier un **ID d’espace de travail** et une **Clé d’espace de travail**.



<!--HONumber=Feb17_HO1-->


