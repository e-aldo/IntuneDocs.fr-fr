---
title: "Guide de migration de la gestion des périphériques mobiles (GPM) - Microsoft Intune | Microsoft Docs"
description: "Ce guide présente aux clients des informations détaillées sur la migration des appareils depuis un fournisseur GPM tiers vers Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Guide de migration Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Image relative au guide de migration GPM Intune](../media/MDM-migration-guide-art.PNG)

Pour garantir la réussite de votre migration vers Intune, vous devez d’abord élaborer un plan robuste, qui inclue l’environnement GPM actuel, les objectifs commerciaux et les besoins techniques à prendre en compte. En outre, vous devez déterminer les parties prenantes qui prendront en charge et participeront à votre plan de migration.

Ce guide a pour objectif de vous présenter des informations détaillées sur la migration des appareils depuis un fournisseur GPM tiers vers Intune.

## <a name="whats-included-in-this-guide"></a>Qu’est-ce qui est inclus dans ce guide ?

Ce guide comprend deux phases, qui incluent des tâches, des stratégies et des conseils tactiques destinés à faciliter le processus de migration de bout en bout vers la fonction GPM de Microsoft Intune.

-   [Phase 1 : Préparation de Microsoft Intune à la gestion des périphériques mobiles (GPM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Évaluer les besoins concernant la migration de la fonction GPM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Configuration de base](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Configurer les stratégies de gestion des appareils mobiles et des applications](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Configurer des stratégies de protection des applications (facultatif)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Facteurs de migration spécifiques à prendre en compte](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [Phase 2 : Campagne de migration](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [Plan de communication](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [Encourager l’adoption par les utilisateurs finaux avec l’accès conditionnel](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Cycle de migration classique](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [Surveillance de la migration](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Tâches de post-migration](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Hypothèses

-   Vous avez déjà évalué Intune dans un environnement de preuve de concept et avez décidé de l’utiliser comme solution de gestion des périphériques mobiles (GPM) dans votre organisation.

-   Vous êtes déjà familiarisé avec Intune et ses fonctionnalités. 

> [!NOTE]
> Consultez le [guide d’évaluation Intune](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune) si vous souhaitez vous familiariser avec Intune avant de procéder à la migration.

## <a name="before-you-begin"></a>Avant de commencer

Il est important de savoir que votre nouveau déploiement Microsoft Intune peut être différent de l’ancien déploiement GPM. Contrairement aux services GPM traditionnels, Intune se concentre sur le contrôle d’accès basé sur les identités. Pour cette raison, il ne nécessite aucune appliance de proxy réseau pour contrôler l’accès aux données de l’entreprise depuis des appareils mobiles situés en dehors du périmètre réseau de l’organisation. Microsoft propose des solutions permettant de sécuriser les services de données dans le cloud lui-même, via une suite de services cloud étroitement intégrés, regroupés au sein de l’offre Enterprise Client + Security.

-   Parcourez les [méthodes d’utilisation de Microsoft Intune les plus fréquentes](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune) et entamez la compilation des réponses aux questions dans l’étape [Évaluer les besoins concernant la migration de la fonction GPM de la phase 1](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Étapes suivantes

[Phase 1 : Préparation de Microsoft Intune à la gestion des périphériques mobiles (GPM)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

