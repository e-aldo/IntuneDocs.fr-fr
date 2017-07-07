---
title: "Encourager l’adoption par les utilisateurs finaux avec l’accès conditionnel"
description: "Cet article fournit des informations sur la façon de tirer parti de l’accès conditionnel pour permettre l’inscription d’appareils auprès de Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Encourager l’adoption par les utilisateurs finaux avec l’accès conditionnel

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

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

-   En savoir plus sur l'[accès conditionnel](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Liste de tâches relatives à l’accès conditionnel

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Tâche 1 : Définir la façon dont vous allez implémenter l’accès conditionnel

[Utilisations courantes de l’accès conditionnel](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>Tâche 2 : Configuration de l’accès conditionnel Intune

Choisissez l'une des options suivantes :

-   [Configuration de l’accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Installer le connecteur Exchange local avec Intune](/intune/exchange-connector-install)

-   [Configurer les stratégies d’accès conditionnel basé sur l’application pour Exchange Online](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Configurer des stratégies d’accès conditionnel basé sur l’application pour SharePoint Online](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Bloquer les applications qui n’utilisent pas l’authentification moderne (ADAL)](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Étapes suivantes

[Cycle de migration classique](migration-guide-cycle.md)
