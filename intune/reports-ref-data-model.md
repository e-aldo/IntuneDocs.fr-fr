---
title: "Modèle de données de l’entrepôt de données | Microsoft Docs"
description: "L’entrepôt de données Intune échantillonne quotidiennement les données pour vous offrir un historique de votre environnement mobile en constante évolution."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9257af29c65dbe27667738abc8ee06203177124f
ms.sourcegitcommit: b8ef9d8387b4d9b2ea4e6ce937635304771e6532
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2017
---
# <a name="data-warehouse-data-model"></a>Modèle de données de l’entrepôt de données

L’entrepôt de données Intune échantillonne quotidiennement les données pour vous offrir un historique de votre environnement mobile en constante évolution.

Les données extraites de votre locataire sont ajoutées dans un entrepôt de données. L’entrepôt est un ensemble d’entités et de relations qui sont utiles pour répondre aux questions que vous souhaitez poser. Par exemple, vous pouvez passer en revue le nombre d’installations quotidiennes d’une application Android développée en interne au cours de la semaine dernière pour déterminer si les installations sont à la hausse. La structure de l’entrepôt de données vous permet d’obtenir des insights sur votre environnement mobile. Des outils analytiques comme Microsoft Power BI peuvent ensuite utiliser le modèle de données de l’entrepôt de données pour créer des visualisations et des tableaux de bord dynamiques.

La structure de l’entrepôt de données Intune repose sur un modèle de schéma en étoile. Un schéma en étoile organise des faits par rapport à la dimension temps. Dans le contexte du modèle, un *fait* est une mesure quantitative comme le nombre d’appareils, le nombre d’applications ou l’heure de l’inscription. Dans le même contexte, une *dimension* est un jeu de catégories et de leurs relations hiérarchiques. Par exemple, les jours sont regroupés en mois et les mois en années. Optimisé pour la flexibilité et l’analyse des données, un modèle de schéma en étoile vous permet de créer les rapports nécessaires pour comprendre l’évolution de votre environnement mobile.

L’entrepôt de données expose les données dans les catégories principales suivantes :
  -  Applications protégées par App Protection et utilisation
  -  Appareils inscrits, propriétés et inventaire
  -  Inventaire des applications et des logiciels
  -  Configuration des appareils et stratégies de conformité

**Jeux d’entités du modèle de données**

Les jeux d’entités sont des collections nommées d’entités dans le modèle de données. Ces jeux contiennent des entités qui définissent les données collectées dans le modèle. Chaque jeu d’entités fournit un point d’accès au modèle de données de l’entrepôt de données. Pour plus d’informations, cliquez sur les catégories d’entités suivantes :

  -  [Date](reports-ref-date.md)
  -  [Utilisateur](reports-ref-user.md)
  -  [Gestion des applications mobiles (GAM)](reports-ref-mobile-app-management.md)
  -  [Appareils](reports-ref-devices.md)
  -  [Application](reports-ref-application.md)
  -  [Stratégie](reports-ref-policy.md)

<!-- ## Data Model relationships

For more information on the relationships in the data model, see [Relationships of Entities](reports-api-entity-relationships.md). -->