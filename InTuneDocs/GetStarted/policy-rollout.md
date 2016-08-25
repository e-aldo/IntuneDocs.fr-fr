---
title: "Déploiement de stratégies | Microsoft Intune"
description: "Recommandations pour un déploiement échelonné de stratégies Microsoft Intune."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 0c23fdd5f5e6bc1b50dda56fe2135e8cc24b5e26


---

# Déploiement de stratégies
Cette rubrique fournit des recommandations spécifiques pour un déploiement échelonné de stratégies dans Microsoft Intune. Cette approche est valable pour les premières stratégies que vous appliquez dans un nouveau déploiement Intune ou pour des stratégies que vous ajoutez à un déploiement existant.

Pour obtenir des informations générales sur les phases de déploiement, consultez [Phases de déploiement Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Phases de déploiement d’une stratégie
Les phases de déploiement d’une stratégie sont :

-   Définition de la portée du projet

-   Preuve de concept

-   Pilote

-   Déploiement en entreprise

-   Opérations et maintenance

## Définition de la portée du projet
Définition l’étendue de votre déploiement de stratégie Intune :

-   Pour une nouvelle implémentation, vous devrez définir l’ensemble des comportements d’appareil et les exigences de sécurité que vous souhaitez créer avec votre stratégie.

-   Décidez quels utilisateurs et quels appareils seront impactés par ces stratégies.

-   Concevez vos groupes d’utilisateurs et d’appareils afin d’appliquer les nouvelles stratégies de manière appropriée.

-   Déterminez s’il existe des limitations ou des exigences associées à chaque système d’exploitation qui affecteront les intentions de votre stratégie.

-   Tenez compte des caractéristiques de conception de stratégie telles que le type de stratégie et le modèle à utiliser.

-   Que vous lanciez votre premier jeu de stratégies ou ajoutiez de nouvelles stratégies à un jeu existant, vous devez tenir compte des interactions entre les différentes stratégies et du comportement éventuel de l’appareil. Des problèmes liés aux interactions entre les stratégies et des conflits peuvent être détectés dans la phase pilote. Mais l’exécution du pilote sera d’autant plus simple que ces conflits sont reconnus tôt dans le processus de planification.

## Preuve de concept
Durant la phase de preuve de concept, vous devez tester votre déploiement de stratégie dans un environnement de laboratoire sur des appareils et des utilisateurs que vous avez configurés strictement à des fins de test.

-   Faites participer votre personnel de support technique à cette phase pour qu’il connaisse les problèmes qui peuvent survenir pendant le déploiement pilote et de production. Vous trouverez des informations de dépannage dans [Résoudre les problèmes de stratégie dans Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).

-   À ce stade du processus, vous devez développer des plans de communication pour les utilisateurs pilotes et de production. Au minimum, le plan doit préciser quel appareil est modifié et quand, l’objectif métier du déploiement, et que faire si les utilisateurs ou le personnel informatique rencontrent des problèmes (à la fois des informations d’auto-assistance et de contact du support technique).

## Pilote
Pendant la phase pilote, vous allez déployer la stratégie dans un petit groupe test d’utilisateurs et d’appareils. Vous devez tenir compte de certains points pour le pilote de la stratégie dans Intune :

-   Le groupe de test doit être représentatif du groupe auquel la stratégie sera appliquée lors du déploiement en production.

-   Formez le personnel de support technique quant aux modifications des stratégies et vérifiez qu’il est prêt à aider les utilisateurs du groupe test.

-   Activez votre plan de communication pour les utilisateurs du pilote.

-   Le pilote peut être d’abord exécuté en mode isolé, où l’appareil n’est pas soumis à d’autres stratégies qui peuvent provoquer des conflits et un comportement inattendu.

-   Le test final doit prendre en compte la nouvelle stratégie et toutes les stratégies existantes qui seront appliquées au même appareil.

## Déploiement en entreprise

-   Selon les résultats du pilote, ajustez votre stratégie planifiée pour corriger les conflits de stratégie et les comportements imprévus.

-   Informez le support technique du planning de déploiement en entreprise. Mettez en place des mécanismes permettant de répondre aux demandes d’aide et d’ajuster le déploiement si nécessaire.

-   Préparez-vous à dépanner la stratégie en cas de problème.

-   Activez votre plan de communication pour les utilisateurs de l’environnement de production.

-   Appliquez les stratégies de façon incrémentielle à des groupes supplémentaires pour surveiller l’état de la stratégie dans les appareils concernés et suivre les demandes d’assistance qui peuvent être liées à la nouvelle stratégie.

## Opérations et maintenance
**Opérations :** surveillez votre console Intune pour identifier les alertes et les problèmes liés aux appareils ou aux utilisateurs, et vérifiez que les stratégies s’exécutent comme prévu.

**Support technique :** assurez-vous que votre support technique est informé de chaque modification apportée aux stratégies qui affecte l’expérience utilisateur, car il pourrait en résulter des demandes d’assistance.


### Voir aussi
[Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Résoudre les problèmes de stratégie dans Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)



<!--HONumber=Jul16_HO4-->


