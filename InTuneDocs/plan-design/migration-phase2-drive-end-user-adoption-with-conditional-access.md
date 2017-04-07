---
title: "Encourager l’adoption par les utilisateurs finaux avec l’accès conditionnel | Microsoft Docs"
description: "Cet article fournit des informations sur la façon de tirer parti de l’accès conditionnel pour permettre l’inscription d’appareils auprès de Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 26d11bc64802005bcce8cc1962d531af6ffe5cd5
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Phase 2 : Encourager l’adoption par les utilisateurs finaux avec l’accès conditionnel

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

En activant les fonctionnalités d’accès conditionnel avec Intune (par exemple, le blocage des e-mails sur les appareils non inscrits), vous pouvez favoriser l’inscription des appareils et leur mise en conformité. Toutefois, ce n’est pas nécessaire pour assurer la réussite de la migration. En effet, ce sont les objectifs relatifs à l’adoption et les exigences en matière de sécurité qui déterminent sa réussite.

## <a name="migration-campaign-with-conditional-access"></a>Campagne de migration avec accès conditionnel

Voici une méthode d’amélioration classique des campagnes de migration avec accès conditionnel :

1.  Définissez les règles d’accès conditionnel à appliquer pour tous les utilisateurs, mais excluez spécifiquement ceux qui doivent effectuer la migration depuis l’ancien fournisseur de GPM. Vous pouvez créer un groupe d’utilisateurs Azure AD, qui rassemble tous les utilisateurs exclus avec accès conditionnel.

2.  Au fur et à mesure que ces utilisateurs effectuent cette migration, retirez-les du groupe d’exclusion avec accès conditionnel.

3.  Une fois la migration terminée, configurez toutes les stratégies d’accès conditionnel de manière à appliquer un blocage par défaut, sauf si Intune autorise l’accès.

### <a name="advantages"></a>Avantages

-   Propose un contrôle d’accès pour les nouveaux comptes d’utilisateur, ou ceux qui n’ont pas été gérés par la précédente solution.

-   Propose aux utilisateurs une période de grâce pour la migration depuis la solution précédente.

-   Minimise les pertes de productivité.

### <a name="disadvantages"></a>Inconvénients

-   Les utilisateurs de la solution précédente avaient la possibilité d’accéder aux ressources à l’aide d’appareils non gérés, jusqu’à ce que l’accès conditionnel soit activé sur leurs appareils.

> [!TIP] 
> Il s’agit d’une approche parmi d’autres. Vous pouvez choisir un processus plus simple, qui diffère tout accès conditionnel jusqu’à la fin de chaque phase de l’inscription, ou mettre en place un procédé plus strict, qui applique l’accès conditionnel dès le départ et requiert une conformité complète pour tout accès.

-   En savoir plus sur l'[accès conditionnel](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access).

## <a name="task-list-for-conditional-access"></a>Liste de tâches relatives à l’accès conditionnel

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Tâche 1 : Préparation à l’implémentation de l’accès conditionnel dans Intune

-   Découvrez comment [configurer l’accès conditionnel](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-setup-intune-conditional-access"></a>Tâche 2 : Configuration de l’accès conditionnel dans Intune

Choisissez l’un des types de stratégie d’accès conditionnel suivants pour en savoir plus :

-   [Exchange Online et nouvel Exchange Online Dedicated](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Exchange local et Exchange Online Dedicated hérité](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype Entreprise Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Exemples de scénarios d’accès aux e-mails](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Étapes suivantes

[Phase 2 : Cycle de migration classique](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)

