---
title: "Facteurs de migration spécifiques à prendre en compte"
description: "Cet article détaille diverses considérations spécifiques de la migration que les clients doivent prendre en compte avant de démarrer une campagne de migration."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Facteurs de migration spécifiques à prendre en compte

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Selon l’environnement de fournisseur de GPM existant, certaines remarques spécifiques de la migration peuvent être applicables.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Réinitialisation des paramètres d’origine pour le programme Apple DEP (Device Enrollment Program)

Le programme Apple DEP définit des configurations d’appareil qui ne peuvent pas être supprimées par l’utilisateur final. Pour conserver les fonctionnalités de gestion avancée du programme DEP, vous devez réinitialiser les paramètres d’origine sur l’appareil, afin de rétablir l’état prêt à l’emploi, pour pouvoir l’inscrire auprès de Microsoft Intune.

Pour continuer à utiliser DEP pour gérer les appareils dans Intune, [configurez l’inscription des appareils iOS avec le programme d’inscription des appareils](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Étapes suivantes 

[Phase 2 : Campagne de migration](migration-guide-campaign.md)
