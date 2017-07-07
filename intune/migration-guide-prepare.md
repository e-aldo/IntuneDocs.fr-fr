---
title: "Préparation de Microsoft Intune à la gestion des appareils mobiles"
description: "Cet article vise à aider les lecteurs à évaluer leurs exigences commerciales et techniques avant de migrer vers Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 65e3bb4b6a4e6e8dcfa1dd16738ae47758f4fb9b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>Phase 1 : Préparation de Microsoft Intune à la gestion des périphériques mobiles (GPM)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Avant d’étudier plus en détail la configuration de Microsoft Intune, passons en revue les exigences de la gestion de périphériques mobiles de votre organisation. Il peut être utile d’exécuter des rapports d’utilisateurs actifs dans votre fournisseur de gestion des périphériques mobiles en cours pour identifier les groupes d’utilisateurs critiques, puis de commencer à répondre aux questions de la section [Évaluation des exigences en matière de GPM](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>Évaluation des exigences en matière de GPM

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Quels appareils devez-vous prendre en charge ?

-   Quelles [plates-formes](/intune-classic/get-started/supported-mobile-devices-and-computers) devez-vous prendre en charge ?

-   Les appareils à gérer appartiennent-ils à l’entreprise ou sont-ils de type BYOD ?

-   Quel est le type de connectivité utilisé ? Wi-Fi, cellulaire ou VPN ?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Quelles opérations vos utilisateurs doivent-ils exécuter sur les appareils gérés ?

-   Devez-vous configurer des applications pour vos utilisateurs finaux ?

-   Utilisez-vous des applications cœur de métier personnalisées ? Avez-vous uniquement besoin d’applications de magasin publiques ?

-   Devez-vous configurer des comptes de messagerie ?

### <a name="what-kinds-of-users"></a>Quels sont les types d’utilisateurs ?

-   Combien de personnes utiliseront un seul appareil ?

-   De quelles conditions d’utilisation avez-vous besoin ?

    -   Veillez à faire appel au service juridique aussitôt que possible.

    -   Quelle est la localisation requise ?

-   Les utilisateurs sont-ils familiarisés avec la technologie et l’informatique en général ?

### <a name="what-is-your-device-security-policy"></a>Quelle stratégie de sécurité des appareils mobiles comptez-vous appliquer ?

-   Devez-vous appliquer un chiffrement au niveau des appareils ?

-   Quelle est la longueur des phrases et codes secrets des appareils ?

-   Devez-vous désactiver des fonctionnalités de l’appareil, ou imposer des restrictions à certains comportements des appareils ?

    -   Vous pouvez contrôler différents paramètres spécifiques de la plateforme grâce aux profils de configuration des appareils, par exemple la désactivation de l’appareil photo ou le verrouillage du mode d’application unique.
<br></br>
-   Quels types d’authentification devez-vous prendre en charge ?

    -   Si vous devez mettre en place l’authentification basée sur les certificats, quels sont les types de certificats à configurer ?

        -   Intune peut configurer des certificats avec des profils d’accès aux ressources pour les appareils inscrits.
<br></br>
    -   Quel type d’infrastructure à clé publique (PKI) devez-vous prendre en charge ?
<br></br>
-   Devez-vous prendre en charge un réseau privé virtuel (VPN) au niveau des appareils ou des applications ?

    -   Intune peut configurer des configurations VPN pour les fournisseurs VPN tiers.
<br></br>
-   Est-il possible de mettre en place des exceptions temporaires concernant certaines exigences, afin d’éviter les temps d’arrêt ? Ou les appareils dotés d’un accès doivent-ils toujours se conformer aux exigences en termes de sécurité ?

## <a name="additional-information"></a>Informations supplémentaires

-   Pour obtenir des exemples plus détaillés, consultez ces [études de cas](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune), qui proviennent de différents secteurs professionnels, afin de savoir de quelle manière les organisations ont pu évaluer leurs besoins en matière de GPM.

## <a name="next-steps"></a>Étapes suivantes

[Configuration de base](migration-guide-setup.md)
