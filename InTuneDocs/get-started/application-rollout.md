---
title: "Déploiement d’application | Microsoft Intune"
description: "Recommandations pour un déploiement échelonné d’applications dans Microsoft Intune."
keywords: 
author: Nbigman
ms.author: nbigman
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8921043334630bbd2955c0423ca9cd1b76c27758
ms.openlocfilehash: aea7c235ad643a2a03ac7b3ea68c6b8c717bcd48


---

# Déploiement d’application
Cette rubrique fournit des recommandations spécifiques pour un déploiement échelonné d’applications dans Microsoft Intune. Pour obtenir des informations générales sur les phases de déploiement, consultez [Phases de déploiement Microsoft Intune](rollout-phases-for-microsoft-intune-deployment.md).

### Phases de déploiement d’application
Les étapes de déploiement d’application sont les suivantes :

-   Définition de la portée du projet

-   Preuve de concept

-   Pilote

-   Déploiement en entreprise

-   Opérations et maintenance

## Portée du projet
Considérez les points suivants :

-   La tâche utilisateur que l’application est censée activer.

-   L’adéquation de l’application pour vos utilisateurs et leurs appareils (tous les systèmes d’exploitation susceptibles d’être utilisés).

-   Vérifiez que le programme d’installation de l’application que vous avez choisie est pris en charge par la distribution d’application Intune, comme décrit dans [Ajouter des applications avec Microsoft Intune](/intune/deploy-use/add-apps).

-   Vérifiez que les éléments prérequis pour la distribution d’application sont installés. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md).--->

-   Vérifiez que le type d’application est pris en charge par Intune.

-   Vérifiez que vous disposez d’un espace de stockage cloud suffisant pour charger l’application. Vous trouverez des instructions pour l’achat de stockage supplémentaire dans [Ajouter des applications avec Microsoft Intune](/intune/deploy-use/add-apps).

> [!NOTE]           
> Vous pouvez télécharger ce [modèle de planification pour les applications mobiles](https://gallery.technet.microsoft.com/Mobile-app-planning-18689d59) pour faciliter votre processus de déploiement.

## Preuve de concept
Durant la phase de preuve de concept, vous devez tester votre déploiement d’application dans un environnement de laboratoire sur des appareils et des utilisateurs que vous avez configurés strictement à des fins de test.

-   Faites participer votre personnel de support technique à cette phase pour qu’il connaisse les problèmes qui peuvent survenir pendant le déploiement pilote et de production. Vous trouverez des informations de dépannage dans [Résoudre les problèmes de déploiement d’applications dans Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   À ce stade du processus, vous devez développer des plans de communication pour les utilisateurs pilotes et de production. Au minimum, le plan doit préciser quelle application est déployée, comment et quand les utilisateurs l’obtiendront, l’objectif professionnel du déploiement, et que faire si les utilisateurs rencontrent des problèmes (à la fois des informations d’auto-assistance et comment contacter le support technique).

## Pilote
Pendant la phase pilote, vous allez déployer l’application vers un petit groupe test d’utilisateurs et d’appareils. Considérez les points suivants :

-   Vérifiez que le groupe test est représentatif des utilisateurs et des appareils qui utiliseront l’application après le déploiement en production.

-   Formez le personnel de support technique concernant le déploiement d’application et vérifiez qu’il est prêt à aider les utilisateurs du groupe test.

-   Choisissez des utilisateurs de test qui soumettront l’application à une utilisation classique et qui signaleront à coup sûr tout problème aux administrateurs du pilote.

-   Activez votre plan de communication pour les utilisateurs pilotes.

## Déploiement en entreprise

-   Utilisez les résultats du pilote pour ajuster votre déploiement en entreprise.

-   Informez le support technique du planning de déploiement d’application. Mettez en place des mécanismes permettant de répondre aux demandes d’aide et d’ajuster le déploiement si nécessaire.

-   Préparez-vous à dépanner le déploiement en cas de problème.

-   Activez votre plan de communication pour les utilisateurs de production.

-   Utilisez une approche progressive pour déployer l’application, en ajoutant des groupes de façon incrémentielle pour vous assurer que le déploiement se déroule sans heurts.

## Opérations et maintenance
**Opérations :** surveillez votre console Intune pour identifier immédiatement les alertes et les problèmes liés aux appareils ou aux utilisateurs, et pour vous assurer que la distribution de l’application fonctionne conformément à votre conception.

**Support technique :** vérifiez que votre personnel de support technique a connaissance des éventuels changements de disponibilité de l’application pouvant entraîner des demandes de support.

### Voir aussi
[Déployer des applications](/intune/deploy-use/deploy-apps)

[Résoudre les problèmes de déploiement d’applications dans Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)



<!--HONumber=Oct16_HO4-->


