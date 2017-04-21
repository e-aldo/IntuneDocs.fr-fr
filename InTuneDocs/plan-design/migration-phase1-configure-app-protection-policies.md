---
title: "Configurer des stratégies de protection des applications pendant une migration Intune | Microsoft Docs"
description: "Cet article décrit les étapes nécessaires pour configurer des stratégies de protection des applications lors d’une migration Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: f30ab8799b2e049372139c7f9ee7213547736bb0
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>Phase 1 : Configurer des stratégies de protection des applications (facultatif)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Les stratégies de protection des applications vous permettent de chiffrer des applications, de définir un code confidentiel lors de l’accès à l’application, d’empêcher les applications de s’exécuter sur des périphériques jailbreakés ou rootés, etc. Si l’appareil d’un utilisateur est perdu ou volé, vous pouvez choisir d’effacer à distance les données de l’entreprise sans modifier les données personnelles, via l’application de stratégies de protection des applications mobiles.

Les stratégies de protection des applications mettent en œuvre des mécanismes de sécurité au niveau de l’application. Vous n’avez pas besoin d’inscrire l’appareil. Elles peuvent être utilisées sur les appareils, qu’ils soient ou non inscrits auprès d’Intune. Par ailleurs, vous pouvez les exécuter sur des appareils inscrits auprès d’un fournisseur de gestion des périphériques mobiles (GPM) tiers.

## <a name="app-protection-policies-with-lob-apps"></a>Stratégies de protection des applications et applications métiers

Vous pouvez également étendre les stratégies de protection des applications à vos applications métiers en tirant parti du [Kit de développement logiciel (SDK) des applications Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) ou de l’outil de création de package de restrictions d’application Microsoft Intune App Wrapping Tool, pour [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) et [Android](https://www.microsoft.com/download/details.aspx?id=47267).

## <a name="how-do-app-protection-policies-help-during-migration"></a>De quelle manière les stratégies de protection des applications facilitent-elles la migration ?

Pour pouvoir effectuer la migration, vous devez supprimer l’inscription des appareils auprès de l’ancien fournisseur de gestion des périphériques mobiles (GPM), puis inscrire ces dernières auprès de Microsoft Intune. Cette opération nécessite une planification précise. Invitez les utilisateurs finaux à désinscrire leurs appareils et à les inscrire immédiatement auprès de Microsoft Intune. Toutefois, il se peut que certains utilisateurs, dont les appareils ne sont pas gérés par l’ancien fournisseur, n’effectuent pas immédiatement la migration vers Intune.

Pendant cet intervalle, votre organisation risque d’être plus vulnérable au vol d’appareils et à la perte de données d’entreprise si l’accès aux ressources reste autorisé. Or, s’il ne l’est pas, il se peut que la productivité des utilisateurs en souffre.

Intune propose différents mécanismes de protection des données d’entreprise lors de la migration, afin que ces données restent sécurisées si aucune gestion des appareils n’est mise en place.

Lorsque vous désactivez l’accès conditionnel au sein du fournisseur GPM de départ, les utilisateurs restent productifs lors de leur intégration dans Intune.

## <a name="task-list-for-app-protection-policies"></a>Liste des tâches associées aux stratégies de protection des applications

-   Tâche 1 : Procédez aux [préparatifs avant la configuration de stratégies de protection des applications](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

-   Tâche 2 : Découvrez comment [créer et déployer des stratégies de protection des applications avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="next-steps"></a>Étapes suivantes 

[Phase 1 : Facteurs de migration spécifiques à prendre en compte](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

