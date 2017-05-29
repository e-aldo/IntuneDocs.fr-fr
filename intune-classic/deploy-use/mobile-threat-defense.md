---
title: Protection contre les menaces mobiles Intune | Microsoft Docs
description: "Protégez l’accès aux ressources d’entreprise en fonction du risque évalué pour l’appareil."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 56cd18e1a5556178d951ec47c6e894d8fc2e6f86
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-mobile-threat-defense-connectors"></a>Connecteurs de protection contre les menaces mobiles Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les connecteurs de protection contre les menaces mobiles Intune vous permettent de tirer parti de votre fournisseur de protection contre les menaces mobiles choisi comme source d’informations pour vos stratégies de conformité et vos règles d’accès conditionnel. Cela permet aux administrateurs informatiques d’ajouter une couche de protection à leurs ressources d’entreprise Exchange et Sharepoint, en particulier contre les appareils mobiles compromis.

## <a name="what-problem-does-this-solve"></a>Quel problème cette fonctionnalité résout-elle ?

Les entreprises doivent protéger leurs données sensibles contre diverses menaces émergentes, notamment les menaces ciblant le matériel, les applications et le réseau, ainsi que les vulnérabilités du système d’exploitation.
Historiquement, les entreprises ont été proactives en matière de protection des PC contre les attaques, tandis que les appareils mobiles restent non contrôlés et non protégés. Les plateformes mobiles offrent maintenant une protection intégrée grâce notamment à l’isolation d’application et à la vérification des applications des App Store, mais elles restent vulnérables aux attaques sophistiquées. Aujourd'hui, de plus en plus d’employés utilisent des appareils pour travailler et ils ont besoin d’accéder à des informations sensibles. Les appareils doivent être protégés contre des attaques de plus en plus sophistiquées.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Comment les connecteurs de protection contre les menaces mobiles Intune fonctionnent-ils ?

Le connecteur protège les ressources de l’entreprise en créant un canal de communication entre Intune et le fournisseur de protection contre les menaces mobiles que vous avez choisi. Les partenaires de protection contre les menaces mobiles Intune offrent des applications intuitives et faciles à déployer pour les appareils mobiles, qui analysent de manière active les informations relatives aux menaces pour les partager avec Intune, à des fins de création de rapports ou d’application de stratégies. Par exemple, si une application de protection contre les menaces mobiles connectée signale au fournisseur de protection contre les menaces mobiles qu’un téléphone sur votre réseau est connecté à un réseau vulnérable aux « attaques de l’intercepteur », ces informations sont partagées et classées à un niveau de risque approprié (faible/moyen/élevé), qui peut ensuite être comparé à vos quotas de niveau de risque configurés dans Intune afin de déterminer si l’accès à certaines ressources doit être révoqué pendant que le appareil est compromis.

## <a name="sample-scenarios"></a>Exemples de scénario

Quand un appareil est considéré comme infecté par la solution de protection contre les menaces mobiles :

![Appareil Mobile Threat Defense infecté](../media/mtp/MTD-image-1.png)

L’accès est autorisé une fois que le problème lié à l’appareil a été résolu :

![Mobile Threat Defense - accès accordé](../media/mtp/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Partenaires de protection contre les menaces mobiles

Découvrez comment protéger l’accès aux ressources d’entreprise en fonction du risque évalué pour l’appareil, le réseau et l’application avec :

- [Lookout](/intune-classic/deploy-use/lookout-mobile-threat-defense-connector)
- [Skycure](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector)

