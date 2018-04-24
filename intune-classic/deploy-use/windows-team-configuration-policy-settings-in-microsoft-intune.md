---
title: Paramètres de la stratégie de configuration Windows Collaboration
description: Utilisez la **stratégie de configuration générale de Windows 10 Collaboration** Microsoft Intune pour configurer les paramètres des appareils Windows 10 Collaboration inscrits, comme Microsoft Surface Hub.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70b1091cd58439b7d42eab1a612b0b63ca39103d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie de configuration Windows Collaboration dans Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Utilisez la **stratégie de configuration générale de Windows 10 Collaboration** Microsoft Intune pour configurer les paramètres des appareils Windows 10 Collaboration inscrits, comme Microsoft Surface Hub.


|                                  Nom du paramètre                                   |                                                                                                                                                                Détails                                                                                                                                                                |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <strong>Autoriser l’écran à sortir de veille automatiquement quand une personne se trouve dans la pièce</strong>   |                                                                                                                         Permet à l’appareil de sortir automatiquement quand son capteur détecte la présence d’une personne dans la pièce.                                                                                                                          |
|              <strong>Exiger un code PIN pour la projection sans fil</strong>               |                                                                                                             Indique si vous devez entrer un code confidentiel avant de pouvoir utiliser les fonctionnalités de projection sans fil de l’appareil.                                                                                                             |
|          <strong>Définir une fenêtre de maintenance pour les mises à jour de l’appareil</strong>           |                                                                                          Configure la fenêtre quand des mises à jour peuvent avoir lieu sur l’appareil. Vous pouvez configurer l’heure de début de la fenêtre et la durée (de 1 à 5 heures).                                                                                           |
|               <strong>Activer Azure Operational Insights</strong>                |                  Azure Operational Insights, qui fait partie de la suite Microsoft Operations Manager, collecte, stocke et analyse les données des fichiers journaux provenant d’appareils Windows 10 Collaboration.<br /><br />Pour vous connecter à Azure Operational insights, vous devez spécifier un <strong>ID d’espace de travail</strong> et une <strong>Clé d’espace de travail</strong>.                   |
|              <strong>Activer la projection sans fil Miracast</strong>               |                                          Activez cette option si vous voulez que l’appareil Windows 10 Collaboration utilise des appareils activés pour Miracast pour la projection.<br /><br />Si vous activez cette option, dans <strong>Choisir un canal Miracast</strong>, sélectionnez le canal Miracast utilisé pour projeter le contenu.                                           |
| <strong>Choisir les informations relatives à la réunion affichées sur l’écran d’accueil</strong> | Si vous activez cette option, vous pouvez choisir les informations qui sont affichées sur la vignette <strong>Réunions</strong> de l’écran <strong>Accueil</strong>. Vous pouvez :<br /><br />-   <strong>Afficher uniquement l’organisateur et l’heure</strong><br />-   <strong>Afficher l’organisateur, l’heure et l’objet (objet masqué pour les réunions privées)</strong> |
|                <strong>URL de l’image d’arrière-plan de l’écran de verrouillage</strong>                 |                                           Activez ce paramètre pour afficher un arrière-plan personnalisé sur l’écran <strong>Bienvenue</strong> des appareils Windows 10 Collaboration à partir de l’URL que vous spécifiez.<br /><br />L’image doit être au format PNG et l’URL doit commencer par <strong>https://</strong>.                                            |

### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

