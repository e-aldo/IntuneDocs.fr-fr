---
title: "Démarrer une campagne de migration Intune | Microsoft Docs"
description: "Cet article fournit des conseils sur la méthode à suivre pour démarrer une campagne de migration."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e98730105044d2147d9be37002fc20ec2de8eb0e
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-migration-campaign"></a>Phase 2 : Campagne de migration

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Les organisations doivent choisir l’approche de migration qui convient le mieux à leurs besoins et ajuster leurs stratégies d’implémentation en fonction de leurs besoins spécifiques. Les autres sections de ce guide fournissent les outils vous permettant d’atteindre votre objectif, à savoir l’inscription des appareils des utilisateurs auprès de Microsoft Intune.

## <a name="keys-to-a-successful-migration"></a>Garantir la réussite de la migration

Lorsque vous effectuez la migration depuis un fournisseur GPM tiers vers Intune, vous devez tenir compte des facteurs suivants :

-   Une bonne communication est essentielle pour minimiser les temps d’arrêt des utilisateurs finaux et optimiser leur taux de satisfaction.

-   Veillez à proposer des instructions de migration spécifiques et concrètes.

-   Tous les appareils gérés doivent être désinscrits de votre fournisseur GPM existant avant l’inscription auprès de Microsoft Intune.

-   Fournissez aux utilisateurs finaux les instructions du fournisseur existant concernant la désinscription de leurs appareils.

-   Utilisez une approche progressive. Commencez par un petit groupe d’utilisateurs pilotes, puis ajoutez des groupes supplémentaires de manière incrémentielle, jusqu’au niveau de déploiement à grande échelle.

-   Surveillez la charge du support technique et vérifiez que chaque inscription a abouti. Consacrez un certain temps à l’évaluation des critères de réussite pour chaque groupe avant de passer à la migration du groupe suivant. Votre déploiement pilote doit vérifier les points suivants :

    -   Les taux de réussite et d’échec des inscriptions sont inclus dans les plages prévues.

    -   Productivité des utilisateurs :

        -   Les ressources d’entreprise telles que le VPN, le Wi-Fi, la messagerie et les certificats fonctionnent correctement.

        -   Les applications configurées sont accessibles.

    -   Sécurité des données :

        -   Création de rapports sur la conformité

        -   Application d’une protection aux applications mobiles

-   Lorsque vous êtes satisfait de la première phase de migration, répétez le cycle de migration (décrit sous Cycle de migration classique) pour la phase suivante.

-   Répétez chaque cycle progressif jusqu’à ce que tous les utilisateurs soient migrés vers Intune.

-   Assurez-vous que l’équipe du support technique est prête à prendre en charge les utilisateurs finaux à toutes les étapes de la campagne de migration. Exécutez une migration volontaire, afin de pouvoir estimer la charge de travail liée aux appels de support.

-   Ne définissez aucune échéance tant que le support technique n’a pas pu gérer tous les utilisateurs restants.

> [!IMPORTANT] 
> Ne configurez pas Intune et votre solution GPM tierce de façon à appliquer des contrôles d’accès aux ressources telles que Microsoft Exchange ou SharePoint Online. En outre, les appareils doivent uniquement être inscrits auprès d’une solution à la fois.

## <a name="next-steps"></a>Étapes suivantes

[Phase 2 : Plan de communication](/intune-classic/plan-design/migration-phase2-communication-plan)

