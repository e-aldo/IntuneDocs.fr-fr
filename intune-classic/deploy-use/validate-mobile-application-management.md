---
title: Valider la configuration GAM (Gestion des applications mobiles)
description: "Cette rubrique décrit comment tester et valider la configuration et le bon fonctionnement de votre stratégie de gestion des applications mobiles."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
ms.custom: intune-classic
ms.openlocfilehash: 1e22be7b238cce195ee88c938b1cca009c0b21d3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="validating-your-mobile-application-management-setup"></a>Validation de la configuration de la gestion des applications mobiles

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique fournit des informations sur la manière de vérifier s’il existe des problèmes après avoir configuré la gestion des applications mobiles. Ces instructions s’appliquent aux stratégies de gestion des applications mobiles dans le portail Azure.

### <a name="checking-for-symptoms"></a>Recherche de symptômes
Les utilisateurs ont peu de chances de signaler des problèmes étant donné que la gestion des applications mobiles est un outil de protection des données. En cas de problème avec la configuration de la gestion des applications mobiles, l’utilisateur dispose d’un accès illimité, comme il en disposerait sans la gestion des applications mobiles, et il n’aura pas conscience de l’existence d’un problème. C’est pourquoi nous vous recommandons de valider la configuration de votre gestion des applications mobiles en pilotant vos stratégies de gestion des applications mobiles avec un petit groupe d’utilisateurs à même d’en tester délibérément les restrictions.


### <a name="what-to-check"></a>Les points à vérifier

Si les tests montrent que le comportement de votre stratégie de gestion des applications mobiles n’est pas conforme à ce qui est prévu, nous vous recommandons de vérifier les points suivants :

- Les utilisateurs disposent-ils d’une licence pour la gestion des applications mobiles ?
- Les utilisateurs disposent-ils d’une licence pour O365 ?
- Quel est l’état de chacune des applications de gestion des applications mobiles des utilisateurs ? Les états possibles des applications sont **Archivé** et **Non archivé**.

#### <a name="user-mam-status"></a>État de la gestion des applications mobiles de l’utilisateur
1. Dans le portail Azure, choisissez **Gestion des applications mobiles Intune** > **Paramètres** > **Gestion des applications** > **Tous les paramètres** > **Rapports d’application par utilisateur** > **Utilisateurs**.

2. Choisissez un utilisateur dans la liste ou recherchez et sélectionnez un utilisateur, puis choisissez **Sélectionner un utilisateur**. En haut de la colonne **Rapports d’application**, vous voyez si l’utilisateur a une licence pour la gestion des applications mobiles. En dessous, vous voyez si l’utilisateur a une licence pour O365 et l’état de l’application pour tous les appareils de l’utilisateur est indiqué.

![État de l’application pour la gestion des applications mobiles](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a>Procédure à suivre
Voici les actions à exécuter selon l’état de l’utilisateur :

- Si l’utilisateur n’a pas de licence pour la gestion des applications mobiles, attribuez une licence Intune à l’utilisateur comme décrit dans [Gérer les licences Intune](/intune/setup-steps).
- Si l’utilisateur n’a pas de licence pour O365, obtenez-en une pour lui.
- Si l’état de l’application de l’utilisateur est **Non archivé**, vérifiez si vous avez correctement configuré une stratégie de gestion des applications mobiles pour cette application.
- Vérifiez que ces conditions sont appliquées à tous les utilisateurs auxquels vous voulez appliquer des stratégies de gestion des applications mobiles.

### <a name="see-also"></a>Voir aussi
[Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[Protéger les données d’application à l’aide des stratégies de gestion des applications mobiles avec Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
