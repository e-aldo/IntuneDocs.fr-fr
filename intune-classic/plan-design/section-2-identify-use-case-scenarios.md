---
title: "Identifier des scénarios de cas d&quot;utilisation Intune | Microsoft Docs"
description: "Cet article permet de déterminer les scénarios de cas d’utilisation et cas d&quot;utilisation secondaires Intune dans le cadre de l&quot;implémentation d&quot;un cloud Microsoft Intune uniquement."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 031820d505e0e9cb007e47a5397934d0e505aed4
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="identify-intune-use-case-scenarios"></a>Identifier des scénarios de cas d'utilisation Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Les scénarios de cas d'utilisation de gestion d'appareils mobiles décrivent le type d’utilisateur ou rôle ainsi que la propriété de son appareil (par exemple, professionnel ou personnel). Les scénarios de cas d’utilisation sont utiles car ils vous permettent de segmenter vos utilisateurs en groupes gérables. Identifier vos scénarios de cas d'utilisation représente une partie importante du processus de planification pour un déploiement Intune réussi.

Examinons quelques exemples qui aideront votre organisation à identifier les scénarios de cas d'utilisation Intune, ainsi que les groupes organisationnels et les plateformes d’appareils mobiles associés à chaque cas d’utilisation.

## <a name="use-case-scenarios"></a>Scénarios de cas d’utilisation

Vous pouvez commencer en vous reportant aux objectifs de déploiement Intune de votre organisation afin d’identifier les principaux scénarios de cas d’utilisation pour votre déploiement. Dans le cadre de votre plan de déploiement Intune, vous devrez répondre aux questions suivantes :

-   Envisagez-vous de prendre en charge des appareils appartenant à l’entreprise ?

-   Envisagez-vous de prendre en charge des appareils appartenant aux employés (BYOD) ?

### <a name="sub-use-case-scenarios"></a>Scénarios de cas d'utilisation secondaires

Après avoir identifié vos principaux scénarios de cas d’utilisation, vous devrez déterminer si chaque scénario de cas d’utilisation inclut également des cas d'utilisation secondaires. Par exemple, une organisation peut avoir identifié les exigences pour prendre en charge un scénario de cas d’utilisation d’entreprise incluant d'autres cas d’utilisation secondaires :

-   Travailleur de l'information

-   Cadres

-   Kiosque

Voici quelques exemples de scénarios de cas d’utilisation et cas d'utilisation secondaires. Vous pouvez utiliser le tableau ci-dessous pour entrer les scénarios de cas d’utilisation et cas d’utilisation secondaires de votre organisation :

| **Scénarios d'utilisation** | **Cas d'utilisation secondaires** |
|:---:|:---:|
| Entreprise | Travailleur de l'information |              
| Entreprise | Cadres |           
| Entreprise | Kiosque |
| BYOD | Travailleur de l'information |           
| BYOD | Cadres |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>Identifier les groupes organisationnels associées aux scénarios de cas d'utilisation

Maintenant, vous devez identifier les groupes organisationnels associés à chaque scénario de cas d'utilisation et cas d'utilisation secondaire. Voici quelques exemples de groupes organisationnels associés à des scénarios de cas d'utilisation et cas d'utilisation secondaires que vous pouvez utiliser comme modèle pour entrer les informations de votre organisation :

| **Scénarios d'utilisation** | **Cas d'utilisation secondaires** | **Groupes organisationnels** |
|:---:|:---:|:---:|
| Entreprise | Travailleur de l'information | Ressources humaines, finances |               
| Entreprise | Équipe dirigeante | Ressources humaines, finances |            
| Entreprise | Kiosque | Commerce |
| BYOD | Travailleur de l'information | Marketing, Ventes |            
| BYOD | Équipe dirigeante | Marketing, Ventes |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Identifier les plateformes d’appareils mobiles pour les scénarios de cas d'utilisation

Ici, vous allez identifier les plateformes d'appareils mobiles associés à chaque scénario de cas d’utilisation. Par exemple, le scénario de cas d’utilisation de votre entreprise peut prendre en charge les plateformes iOS et Android Samsung KNOX, et votre stratégie BYOD peut inclure la prise en charge de plateformes mobiles supplémentaires comme Android (NON-Samsung KNOX) et Windows 10 Mobile. Voici des exemples de plateformes d'appareils mobiles associées à chaque scénario de cas d’utilisation. Vous pouvez utiliser le tableau ci-dessous pour entrer vos plateformes d’appareils associées aux scénarios de cas d'utilisation :

| **Scénarios d'utilisation** | **Cas d'utilisation secondaires** | **Groupes** | **Plateformes d'appareils** |   
|:---:|:---:|:---:|:---:|
| Entreprise | Travailleur de l'information | Ressources humaines, finances | iOS |                                                           
| Entreprise | Cadres | Ressources humaines, finances | iOS |                                                           
| Entreprise | Kiosque | Commerce | Android |
| BYOD | Travailleur de l'information | Marketing, Ventes | iOS |                                                           
| BYOD | Cadres | Marketing, Ventes | iOS |

## <a name="next-steps"></a>Étapes suivantes

La section suivante fournit des conseils sur [l'identification des exigences Intune pour chaque scénario de cas d’utilisation](section-3-determine-use-case-requirements.md).

