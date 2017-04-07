---
title: "Configuration de base Microsoft Intune | Microsoft Docs"
description: "L’objectif de cet article est de décrire les étapes à suivre pour configurer Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: b01b68b7587cb91f24285cdffafeab43296886e6
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-basic-setup"></a>Phase 1 : Configuration de base

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Une fois l’environnement évalué, il est temps de configurer Intune.

## <a name="external-dependencies-for-an-intune-deployment"></a>Dépendances externes d’un déploiement Intune

### <a name="identity"></a>Fournisseur

Intune requiert l’utilisation d’Azure Active Directory (Azure AD) en tant que fournisseur de groupes d’utilisateurs et d’identités.

-   En savoir plus sur les [conditions requises pour les identités](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   En savoir plus sur les [conditions requises pour la synchronisation d’annuaires](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   En savoir plus sur [les conditions requises pour l’authentification multifacteur](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   En savoir plus sur la [planification de vos groupes d’utilisateurs et d'appareils](https://docs.microsoft.com/intune/deploy-use/plan-your-user-and-device-groups).

-   En savoir plus la [création de groupes d’utilisateurs et d'appareils](https://docs.microsoft.com/en-us/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

Si votre organisation utilise déjà Office 365, il est important qu'Intune utilise le même environnement Azure Active Directory.

### <a name="pki-optional"></a>Infrastructure PKI (facultatif)

Si vous comptez utiliser l’authentification basée sur un certificat pour valider des profils VPN, Wi-Fi ou de courrier électronique avec Intune, veillez à mettre en place une [infrastructure PKI](https://docs.microsoft.com/intune/deploy-use/secure-resource-access-with-certificate-profiles) prise en charge, prête à créer et à déployer des profils de certificat.

Pour en savoir plus sur la configuration des certificats dans Intune, consultez les documents indiqués ci-dessous.

-   [Configurer l’infrastructure de certificats pour SCEP](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-scep).

-   [Configurer l’infrastructure de certificat pour PFX](https://docs.microsoft.com/intune/deploy-use/configure-certificate-infrastructure-for-pfx).

-   [Configurer les profils de certificats Intune] (file:///C:/intune/deploy-use/https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles).

-   [Comment configurer les stratégies d’accès aux ressources](https://docs.microsoft.com/intune/deploy-use/enable-access-to-company-resources-with-microsoft-intune).

## <a name="task-list-for-an-intune-setup"></a>Liste des tâches de configuration de Microsoft Intune

### <a name="task-1-intune-subscription"></a>Tâche 1 : Abonnement Intune

Avant de pouvoir migrer vers Intune, vous devez créer un abonnement Intune.

-   Vous pouvez consulter [cette page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), qui fournit des instructions sur les opérations suivantes :

    -   Création d’un abonnement Intune lié à un nouveau locataire AAD

    -   Liaison de l’abonnement Intune via la connexion à un locataire AAD existant

### <a name="task-2-assign-intune-user-licenses"></a>Tâche 2 : Affecter des licences utilisateur Intune

-   Découvrez comment [affecter des licences utilisateur Intune](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4).

-   Si vous avez créé un locataire Azure Active Directory, découvrez comment [générer des utilisateurs ou synchroniser un utilisateur à partir de votre instance Active Directory locale.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Tâche 3 : Définir l’autorité de gestion des périphériques mobiles sur Intune

Vous pouvez gérer Intune via le portail Azure ou la console Configuration Manager Current Branch. Nous vous recommandons de gérer ce logiciel via le [portail Azure](https://portal.azure.com), sauf si vous souhaitez l’intégrer dans un déploiement Configuration Manager Current Branch.

Définissez l’autorité de gestion des périphériques mobiles (GPM) sur **Intune** pour activer le portail Intune Azure. Grâce à l’utilisation d’une autre autorité de gestion des périphériques mobiles (GPM), Intune peut transférer l’administration de ces données à d’autres consoles de gestion Microsoft. Cependant, ces cas sont rares.

> [!IMPORTANT]
> Si vous transférez la fonction d’administration des appareils mobiles à Intune pour la première fois, vous devez définir l’autorité GPM sur Intune.

-   Découvrez comment [définir l’autorité de gestion des appareils mobiles](https://docs.microsoft.com/intune/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).

## <a name="next-step"></a>Étape suivante

[Phase 1 : Configurer les stratégies de gestion des appareils et des applications](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

