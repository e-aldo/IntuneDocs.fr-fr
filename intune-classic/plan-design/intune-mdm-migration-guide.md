---
title: "Guide de migration de la gestion des appareils mobiles (MDM) Intune | Microsoft Docs"
description: "Ce guide présente aux clients des informations détaillées sur la migration des appareils depuis un fournisseur MDM tiers vers Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: cce6d997c1aad73819b8cfcf31a1505f0ce75923
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-migration-guide"></a>Guide de migration Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Image du guide de migration de MDM Intune](../media/MDM-migration-guide-art.PNG)

Pour réussir votre migration vers Intune, vous devez d’abord élaborer un plan robuste prenant en compte l’environnement MDM actuel, les objectifs commerciaux et les critères techniques. En outre, vous devez déterminer les parties prenantes qui prendront en charge et participeront à votre plan de migration.

Ce guide a pour objectif de vous présenter des informations détaillées sur la migration des appareils depuis un fournisseur MDM tiers vers Intune.

## <a name="whats-included-in-this-guide"></a>Que contient ce guide ?

Ce guide présente deux phases comprenant des tâches, des stratégies et des conseils tactiques destinés à faciliter le processus de migration de bout en bout vers la gestion MDM Intune.

-   [Phase 1 : Préparer Intune pour la gestion des appareils mobiles] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Évaluer les besoins concernant la migration de MDM](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Configuration de base](/intune-classic/plan-design/migration-phase1-basic-setup)

    -   [Configurer les stratégies de gestion des appareils mobiles et des applications](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Configurer des stratégies de protection d’applications] (/intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Facteurs de migration spécifiques à prendre en compte](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

-   [Phase 2 : Campagne de migration](/intune-classic/plan-design/migration-phase2-migration-campaign)

    -   [Plan de communication](/intune-classic/plan-design/migration-phase2-communication-plan)

    -   [Encourager l’adoption par les utilisateurs finaux avec l’accès conditionnel](/intune-classic/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Cycle de migration classique](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)
        -   [Surveillance de la migration](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Tâches de post-migration](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Hypothèses

-   Vous avez déjà évalué Intune dans un environnement de preuve de concept et avez décidé de l’utiliser comme solution MDM dans votre organisation.

-   Vous êtes déjà familiarisé avec Intune et ses fonctionnalités. 

> [!NOTE]
> Consultez le [guide d’évaluation Intune](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune) si vous souhaitez vous familiariser avec Intune avant de procéder à la migration.

## <a name="before-you-begin"></a>Avant de commencer

Il est important de savoir que votre nouveau déploiement Microsoft Intune peut être différent de l’ancien déploiement MDM. Contrairement aux services MDM traditionnels, Intune se concentre sur le contrôle d’accès basé sur les identités. Pour cette raison, il ne nécessite aucune appliance de proxy réseau pour contrôler l’accès aux données de l’entreprise depuis des appareils mobiles situés en dehors du périmètre réseau de l’organisation. Microsoft propose des solutions permettant de sécuriser les services de données dans le cloud lui-même, via une suite de services cloud étroitement intégrés, regroupés au sein de l’offre Enterprise Client + Security.

-   Consultez les [utilisations courantes d’Intune](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Étapes suivantes

[Phase 1 : Préparer Intune pour la gestion des appareils mobiles] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

