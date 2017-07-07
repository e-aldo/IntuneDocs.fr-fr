---
title: "Paramètres de la stratégie de configuration Windows Collaboration"
description: "Utilisez la **stratégie de configuration générale de Windows 10 Collaboration** Microsoft Intune pour configurer les paramètres des appareils Windows 10 Collaboration inscrits, comme Microsoft Surface Hub."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e0f0ea969ed78f2daf482438b056c8b4eb1a316
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie de configuration Windows Collaboration dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez la **stratégie de configuration générale de Windows 10 Collaboration** Microsoft Intune pour configurer les paramètres des appareils Windows 10 Collaboration inscrits, comme Microsoft Surface Hub.

|Nom du paramètre|Détails|
|----------------|-----------|
|**Autoriser l’écran à sortir de veille automatiquement quand une personne se trouve dans la pièce**|Permet à l’appareil de sortir automatiquement quand son capteur détecte la présence d’une personne dans la pièce.|
|**Exiger un code PIN pour la projection sans fil**|Indique si vous devez entrer un code confidentiel avant de pouvoir utiliser les fonctionnalités de projection sans fil de l’appareil.|
|**Définir une fenêtre de maintenance pour les mises à jour de l’appareil**|Configure la fenêtre quand des mises à jour peuvent avoir lieu sur l’appareil. Vous pouvez configurer l’heure de début de la fenêtre et la durée (de 1 à 5 heures).|
|**Activer Azure Operational Insights**|Azure Operational Insights, qui fait partie de la suite Microsoft Operations Manager, collecte, stocke et analyse les données des fichiers journaux provenant d’appareils Windows 10 Collaboration.<br /><br />Pour vous connecter à Azure Operational insights, vous devez spécifier un **ID d’espace de travail** et une **Clé d’espace de travail**.|
|**Activer la projection sans fil Miracast**|Activez cette option si vous voulez que l’appareil Windows 10 Collaboration utilise des appareils activés pour Miracast pour la projection.<br /><br />Si vous activez cette option, dans **Choisir un canal Miracast**, sélectionnez le canal Miracast utilisé pour projeter le contenu.|
|**Choisir les informations relatives à la réunion affichées sur l’écran d’accueil**|Si vous activez cette option, vous pouvez choisir les informations qui sont affichées sur la vignette **Réunions** de l’écran **Accueil**. Vous pouvez :<br /><br />-   **Afficher uniquement l’organisateur et l’heure**<br />-   **Afficher l’organisateur, l’heure et l’objet (objet masqué pour les réunions privées)**|
|**URL de l’image d’arrière-plan de l’écran de verrouillage**|Activez ce paramètre pour afficher un arrière-plan personnalisé sur l’écran **Bienvenue** des appareils Windows 10 Collaboration à partir de l’URL que vous spécifiez.<br /><br />L’image doit être au format PNG et l’URL doit commencer par **https://**.|


### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

