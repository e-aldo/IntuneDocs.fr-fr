---
title:
- Valider la configuration de votre gestion des applications mobiles | Microsoft Intune
description: "Cette rubrique décrit comment tester et valider la configuration et le bon fonctionnement de votre stratégie de gestion des applications mobiles."
keywords: 
author: karthikaraman
manager: angerobe
ms.date: 08/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
translationtype: Human Translation
ms.sourcegitcommit: 0736b5f24065f55d8fbd312395e4bb7226ebf619
ms.openlocfilehash: 5b6253d3d4c969b6947d83b5c8695a484f8c1d27


---

# Validation de la configuration de la gestion des applications mobiles

Cette rubrique fournit des informations sur la manière de vérifier s’il existe des problèmes après avoir configuré la gestion des applications mobiles. Ces instructions s’appliquent aux stratégies de gestion des applications mobiles dans le portail Azure.

### Recherche de symptômes
Les utilisateurs ont peu de chances de signaler des problèmes étant donné que la gestion des applications mobiles est un outil de protection des données. En cas de problème avec la configuration de la gestion des applications mobiles, l’utilisateur dispose d’un accès illimité, comme il en disposerait sans la gestion des applications mobiles, et il n’aura pas conscience de l’existence d’un problème. C’est pourquoi nous vous recommandons de valider la configuration de votre gestion des applications mobiles en pilotant vos stratégies de gestion des applications mobiles avec un petit groupe d’utilisateurs à même d’en tester délibérément les restrictions.


### Les points à vérifier

Si les tests montrent que le comportement de votre stratégie de gestion des applications mobiles n’est pas conforme à ce qui est prévu, nous vous recommandons de vérifier les points suivants :

- Les utilisateurs disposent-ils d’une licence pour la gestion des applications mobiles ?
- Les utilisateurs disposent-ils d’une licence pour O365 ?
- Quel est l’état de chacune des applications de gestion des applications mobiles des utilisateurs ? Les états possibles des applications sont **Archivé** et **Non archivé**.

#### État de la gestion des applications mobiles de l’utilisateur
1. Dans le portail Azure, choisissez **Gestion des applications mobiles Intune** > **Paramètres** > **Gestion des applications** > **Tous les paramètres** > **Rapports d’application par utilisateur** > **Utilisateurs**.

2. Choisissez un utilisateur dans la liste ou recherchez et sélectionnez un utilisateur, puis choisissez **Sélectionner un utilisateur**. En haut de la colonne **Rapports d’application**, vous voyez si l’utilisateur a une licence pour la gestion des applications mobiles. En dessous, vous voyez si l’utilisateur a une licence pour O365 et l’état de l’application pour tous les appareils de l’utilisateur est indiqué.

![État de l’application pour la gestion des applications mobiles](..\media\ts-mam-user-apps.png) 

### Procédure à suivre
Voici les actions à exécuter selon l’état de l’utilisateur :

- Si l’utilisateur n’a pas de licence pour la gestion des applications mobiles, attribuez une licence Intune à l’utilisateur comme décrit dans [Gérer les licences Intune](..\get-started\start-with-a-paid-subscription-to-microsoft-intune).
- Si l’utilisateur n’a pas de licence pour O365, obtenez-en une pour lui.
- Si l’état de l’application de l’utilisateur est **Non archivé**, vérifiez si vous avez correctement configuré une stratégie de gestion des applications mobiles pour cette application.
- Vérifiez que ces conditions sont appliquées à tous les utilisateurs auxquels vous voulez appliquer des stratégies de gestion des applications mobiles.

### Voir aussi
[Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Protéger les données d’application à l’aide des stratégies de gestion des applications mobiles avec Microsoft Intune](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)



<!--HONumber=Oct16_HO1-->


