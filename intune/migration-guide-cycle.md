---
title: "Fonctionnement d’un cycle de migration Intune classique"
description: "Cet article explique le fonctionnement d’un cycle de migration Intune. Il fournit des exemples illustrant le traitement de cycles de migration par le client."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70aa7155e050450a2d786a1f16e42ce2a3c77f9e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="typical-migration-cycle"></a>Cycle de migration classique

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Il arrive souvent qu’une organisation débute une migration Intune avec un pilote de petite taille, en ciblant un sous-ensemble des utilisateurs au sein du service informatique. En outre, il se peut que votre organisation doive aborder certains facteurs, à savoir la volonté d’évolution du groupe, le nombre d’utilisateurs, la complexité, les exigences, l’emplacement et les risques métiers, pour identifier la plage de migration la plus adaptée.

Voici un exemple de planification de vos groupes cibles :

  | **Groupes ciblés par la migration** | **Période 1** | **Période 2** | **Période 3** | **Période 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Service informatique pilote de taille restreinte (50 utilisateurs) | Annoncer le plan | Demander aux utilisateurs de s’inscrire | Définir une échéance | Appliquer un accès conditionnel |  |                                                        
| Service informatique pilote de taille étendue (200 utilisateurs) |  | Annoncer le plan | Demander aux utilisateurs de s’inscrire | Définir une échéance | Appliquer un accès conditionnel | 
| Phase de migration 1 : Utilisateurs technophiles (2 000) |  |  | Annoncer le plan | Demander aux utilisateurs de s’inscrire | Définir une échéance | 
| Phase de migration 2 : Est des États-Unis |  |  |  | Annoncer le plan | Demander aux utilisateurs de s’inscrire | 
| Toutes les régions |  |  |  |  | Annoncer le plan | 

## <a name="customer-migration-case-study"></a>Étude de cas client

### <a name="adatum-corporation"></a>Adatum Corporation

- Découvrez comment [Adatum Corporation a effectué la migration de ces systèmes depuis un fournisseur tiers de gestion des périphériques mobiles vers Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Surveillance de la migration

Microsoft Intune propose plusieurs méthodes permettant de surveiller la migration :

1.  Vues de groupes d’utilisateurs Intune

2.  Ensembles de rapports intégrés

3.  Alertes générées dans la console

Vous devez effectuer le suivi du nombre d’utilisateurs ayant inscrit des appareils après chaque phase, afin de pouvoir :

-   évaluer l’efficacité de votre plan de communication ;

-   estimer l’impact d’une stratégie d’accès conditionnel.


## <a name="post-migration"></a>Post-migration

Vous devez mettre hors service le fournisseur de gestion des appareils mobiles précédent et annuler l’abonnement à partir du service après la migration vers Intune. En outre, vous devrez supprimer toute exigence inutile concernant l’infrastructure, en suivant les instructions du fournisseur de gestion des périphériques mobiles.
