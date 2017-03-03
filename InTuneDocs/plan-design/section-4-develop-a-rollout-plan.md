---
title: "Déterminer les groupes et délais ciblés du déploiement Intune | Microsoft Docs"
description: "Cet article permet de déterminer les groupes et les délais ciblés par un déploiement dans le cadre d&quot;une implémentation de cloud Microsoft Intune uniquement."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 36530602813467c184b4f262719a56cedbaa2ba9


---

# <a name="develop-an-intune-rollout-plan"></a>Développer un plan de déploiement Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Cette section vous aidera à déterminer les groupes organisationnels qui seront ciblés par votre déploiement Intune, le délai de déploiement pour chaque groupe et les approches d’inscription qui seront utilisées.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Déterminer les groupes et délais ciblés du déploiement Intune

Il est important d’identifier d’abord les groupes ciblés par votre déploiement Intune. Les groupes ciblés ont déjà été abordés dans la section d'identification des scénarios de cas d'utilisation Intune de ce guide.

Ensuite, vous devez déterminer le délai de ciblage de chaque groupe pour le déploiement Intune. Cette opération nécessite généralement une discussion avec l’équipe de déploiement Intune et les groupes ciblés afin de déterminer le délai de déploiement le plus approprié pour chaque groupe.

Pour déterminer ce délai, l’équipe de déploiement Intune peut, par exemple, discuter des facteurs tels que la disposition du groupe face à d'éventuelles modifications, le nombre d’utilisateurs et d'appareils, les types de plateformes d’appareils, les exigences, l'emplacement géographique et les risques commerciaux.

Les organisations choisissent généralement de démarrer le déploiement Intune avec un pilote initial, en ciblant un petit groupe d’utilisateurs au sein du service informatique. Le pilote peut ensuite être étendu afin d'inclure un ensemble plus large d’utilisateurs et la participation d’autres groupes de l’organisation. Une fois ce pilote correctement défini, les organisations sont prêtes à commencer un déploiement de production complet, en ciblant le reste des groupes de l’organisation. Vous trouverez ci-dessous différents exemples de groupes et de phases de déploiement :

-   **Pilote :** la première phase de déploiement doit représenter des utilisateurs pilotes. Les utilisateurs pilotes doivent comprendre qu’ils sont les premiers utilisateurs d'une nouvelle solution et être prêts à fournir des commentaires afin d'améliorer la configuration, la documentation, les notifications et ouvrir ainsi la voie à tous les autres utilisateurs dans les phases de déploiement ultérieures. Ces utilisateurs ne doivent pas être des cadres ou des VIP.

-   **Services :** chaque service peut être une phase de déploiement. Dans ce scénario, vous allez cibler un service complet. Dans ce type de déploiement, chaque phase utilisera probablement l’appareil mobile de la même manière et accédera aux mêmes applications. Les utilisateurs adoptent également sans doute les mêmes types de stratégies.

-   **Géographie :** ce type de déploiement couvre tous les utilisateurs d’une zone géographique spécifique, qu'il s'agisse des mêmes continent, pays, région ou bâtiment de la société. Ce type de déploiement par phases permet de se concentrer sur un emplacement spécifique d’utilisateurs. Il favorise également une approche de type [gant blanc](#user-assisted-enrollment) car le nombre d’emplacements de déploiement Intune simultanés est réduit. Étant donné qu’il est probable que différents services ou cas d’utilisation se trouvent au même endroit, différents cas d’utilisation peuvent être déployés en même temps.

-   **Plateforme :** ce type de déploiement consiste à déployer simultanément des plateformes similaires. Exemple : tous les appareils iOS le premier mois, puis les appareils Android, suivis des appareils Windows. Ce type de déploiement par phases simplifie le support technique. Le support technique ne gère qu'une seule plate-forme à la fois.

Voici un exemple de plan de déploiement Intune incluant des groupes et des délais ciblés :

| **Phases de déploiement** | **Juillet** | **Août** | **Septembre** | **Octobre** |
|:---:|:---:|:---:|:---:|:---:|
| Pilote limité | Informatique (50 utilisateurs) |  |  |  |                                                         
| Pilote développé | Informatique (200 utilisateurs), cadres informatiques (10 utilisateurs) |  |  |  |                                                         
| Phase 1 du déploiement de production |  | Ventes et marketing (2000 utilisateurs) |  |  |
| Phase 2 du déploiement de production |  |  | Vente au détail (1 000 utilisateurs) |  |
| Phase 3 du déploiement de production |  |  |  | Ressources humaines (50 utilisateurs), finances (40 utilisateurs), cadres (30 utilisateurs) |

## <a name="determine-the-intune-enrollment-approach"></a>Déterminer l’approche d’inscription Intune

Maintenant que vous avez déterminé les groupes et les délais ciblés pour votre déploiement Intune, l’étape suivante consiste à choisir l’approche d’inscription Intune la plus appropriée pour chaque groupe. Il existe différentes approches de déploiement que les organisations peuvent utiliser pour leur déploiement Intune. Les approches d’inscription courantes incluent le libre-service pour l'utilisateur, l'inscription avec assistance de l’utilisateur et le salon informatique.

### <a name="user-self-service"></a>Libre-service pour utilisateur

Avec cette approche, l’utilisateur est responsable de l’inscription de ses propres appareils, généralement en suivant les instructions d’inscription fournies par son service informatique. Cette approche est plus couramment utilisée dans des organisations et elle est plus évolutive que l’inscription avec assistance de l'utilisateur.

### <a name="user-assisted-enrollment"></a>Inscription avec assistance de l'utilisateur

Il s'agit ici d'une approche « gant blanc », dans laquelle un membre de l'équipe informatique peut assister l’utilisateur tout au long du processus d’inscription, en personne ou via Skype. Cette approche est généralement utilisée avec les cadres et autres groupes qui peuvent nécessiter une assistance plus poussée pendant le processus d’inscription.

### <a name="it-tech-fair"></a>Salon informatique

Une autre option d’inscription de l'utilisateur Intune consiste à organiser un salon informatique. Au cours de cet événement, le service informatique installe un stand d'assistance pour l'inscription Intune d’inscription où les utilisateurs peuvent recevoir des informations sur l’inscription à Intune, poser des questions et obtenir de l’aide sur le processus d’inscription. Cette option peut être utile à la fois pour le service informatique et l’utilisateur, en particulier au cours des premières phases de déploiement Intune.

Voici un exemple de plan de déploiement Intune avec des groupes, des délais et des approches d'inscription ciblés :

| **Phases de déploiement** | **Juillet** | **Août** | **Septembre** | **Octobre** |
|:---:|:---:|:---:|:---:|:---:|
| Pilote limité |  |  |  |  |                                                         
| Libre-service | Informatique |  |  |  |
| Pilote développé |  |  |  |  |                                                         
| Libre-service | Informatique |  |  |  |
| Gant blanc | Cadres informatiques |  |  |  |
| Phase 1 du déploiement de production |  | Ventes, marketing |  |  |
| Libre-service |  | Ventes et marketing |  |  |
| Phase 2 du déploiement de production |  |  | Commerce |  |
| Libre-service |  |  |  |  |
| Phase 3 du déploiement de production |  |  | Commerce |  |
| Libre-service |  |  |  | Ressources humaines, finances |
| Gant blanc |  |  |  | Cadres |

## <a name="next-section"></a>Section suivante

La section suivante fournit des conseils sur [le développement d'un plan de communication de déploiement Intune](section-5-develop-a-rollout-communication-plan.md).



<!--HONumber=Dec16_HO5-->


