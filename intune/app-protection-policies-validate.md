---
title: "Valider vos stratégies de protection des applications"
titleSuffix: Intune Azure preview
description: "Intune Azure (préversion) : cette rubrique décrit comment tester et valider la configuration et le bon fonctionnement de votre stratégie de protection d’application."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 26e191965eff482cf97b920e028cdf60d1881d32
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-validate-your-app-protection-policy-setup"></a>Guide pratique de validation de votre configuration de stratégie de protection d’application

[!INCLUDE[azure_preview](./includes/azure_preview.md)]


Cette rubrique fournit des informations sur la manière de vérifier s’il existe des problèmes après avoir configuré une stratégie de protection d’application. Ces instructions s’appliquent aux stratégies de protection des applications dans la **préversion** du portail Azure.

### <a name="checking-for-symptoms"></a>Recherche de symptômes
Les utilisateurs ont peu de chances de signaler des problèmes étant donné que la protection d’application est un outil de protection des données. En cas de problème avec la configuration de la protection d’application, l’utilisateur dispose d’un accès illimité, comme il en disposerait sans la protection d’application, et il n’aura pas conscience de l’existence d’un problème. C’est pourquoi nous vous recommandons de valider la configuration de votre protection d’application en pilotant vos stratégies de protection d’application avec un petit groupe d’utilisateurs à même d’en tester délibérément les restrictions.


### <a name="what-to-check"></a>Les points à vérifier

Si les tests montrent que le comportement de votre stratégie de protection d’application n’est pas conforme à ce qui est prévu, nous vous recommandons de vérifier les points suivants :

- Les utilisateurs disposent-ils d’une licence pour la protection d’application ?
- Les utilisateurs disposent-ils d’une licence pour O365 ?
- L’état de chacune des applications de protection d’application des utilisateurs. Les états possibles des applications sont **Archivé** et **Non archivé**.

#### <a name="user-app-protection-status"></a>État de protection d’application utilisateur
1. Dans le portail Azure, choisissez **Gérer les applications** > **Surveillance** >  **État d’utilisateur de protection d’application** > **Utilisateurs**.

2. Choisissez un utilisateur dans la liste ou recherchez et sélectionnez un utilisateur, puis choisissez **Sélectionner un utilisateur**. En haut de la colonne **Rapports d’application**, vous voyez si l’utilisateur a une licence pour la protection d’application. En dessous, vous voyez si l’utilisateur a une licence pour O365 et l’état de l’application pour tous les appareils de l’utilisateur est indiqué.



### <a name="what-to-do"></a>Procédure à suivre
Voici les actions à exécuter selon l’état de l’utilisateur :

- Si l’utilisateur n’est pas autorisé pour la protection d’application, attribuez une licence Intune à l’utilisateur.
- Si l’utilisateur n’a pas de licence pour O365, obtenez-en une pour lui.
- Si l’état de l’application de l’utilisateur est **Non archivé**, vérifiez si vous avez correctement configuré une stratégie de protection d’application pour cette application.
- Vérifiez que ces conditions sont appliquées à tous les utilisateurs auxquels vous voulez appliquer des stratégies de protection d’application.

### <a name="see-also"></a>Voir aussi

[Qu’est ce qu’une stratégie de protection d’application Intune ?](app-protection-policies.md)

