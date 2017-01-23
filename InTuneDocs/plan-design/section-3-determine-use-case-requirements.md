---
title: "Déterminer les exigences du scénario de cas d’utilisation Intune | Microsoft Docs"
description: "Cet article permet de déterminer les exigences du scénario de cas d’utilisation et de cas d&quot;utilisation secondaires Intune dans le cadre de l&quot;implémentation d&quot;un cloud Microsoft Intune uniquement."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Déterminer les exigences du scénario de cas d'utilisation Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Dans cette section, vous allez déterminer les exigences de chaque groupe organisationnel pour chaque scénario de cas d’utilisation. Ce processus vous aidera à mieux préparer les autres phases de planification du déploiement Intune comme l’architecture et la conception, l’intégration et le déploiement. Il peut également vous aider à identifier les lacunes potentielles et les difficultés liées à votre projet de déploiement Intune.

Vous pouvez avoir différents ensembles d'exigences pour vos scénarios de cas d'utilisation/cas d'utilisation secondaires, avec leurs groupes organisationnels et plateformes d'appareils mobiles associés. Par exemple, vos exigences de scénario de cas d’utilisation peuvent nécessiter l'inscription des appareils dans Intune avec un ensemble plus restrictif de paramètres d'appareil (par exemple, code PIN à 6 caractères, sauvegarde sur le cloud non autorisée), par rapport à votre scénario de cas d'utilisation « Apportez votre propre appareil » (Bring your own device, BYOD), qui nécessite des paramètres moins restrictifs (par exemple, code PIN à 4 caractères, sauvegarde sur le cloud autorisée).

Vous utilisez peut-être également des groupes organisationnels pour le scénario de cas d’utilisation d’entreprise avec différents ensembles d'exigences (par exemple, paramètres de code PIN, profil Wi-Fi ou VPN, applications déployées). En outre, vos exigences peuvent être déterminées par les fonctionnalités de la plateforme de l'appareil mobile (par exemple, lecteur d'empreinte digitale, profil de messagerie).

Voici quelques exemples d'exigences de cas d'utilisation d'une organisation, illustrant différents ensembles d'exigences pour chaque scénario de cas d'utilisation/cas d'utilisation secondaire, groupe organisationnel et plate-forme d'appareils mobiles. Vous pouvez également utiliser le tableau ci-dessous pour entrer les exigences de cas d’utilisation de votre organisation :

| **Scénarios d'utilisation** | **Cas d'utilisation secondaires** | **Groupes** | **Plateformes de système d’exploitation d'appareils** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Entreprise | Travailleurs de l’information | Ressources humaines, finances | iOS | Messagerie sécurisée, paramètres des appareils, profils, applications |                                                          
| Entreprise | Cadres | Ressources humaines, finances | iOS | Messagerie sécurisée, paramètres des appareils, profils, applications |                                                         
| Entreprise | Kiosque | Commerce | Android | Paramètres des appareils, profils, applications |
| BYOD | Travailleurs de l’information | Marketing, Ventes | iOS | Messagerie sécurisée, paramètres des appareils, profils, applications |                                                         
| BYOD | Cadres | Marketing, Ventes | iOS | Messagerie sécurisée, paramètres des appareils, profils, applications |

## <a name="examples-of-requirements"></a>Exemples d'exigences

Voici quelques exemples supplémentaires qui peuvent être utilisés dans la colonne « Exigences » référencée dans le tableau ci-dessus :

- **Messagerie sécurisée**
    - Accès conditionnel pour Exchange Online/sur site
    - Stratégies de protection des applications Outlook
<br></br>
- **Paramètres de l’appareil**
    - Code confidentiel avec quatre ou six caractères
    - Restreindre la sauvegarde sur le cloud
<br></br>
- **Profils**
    - Wi-Fi
    - VPN
    - E-mail (Windows 10 mobile)
<br></br>
- **Applications**
    - Office 365 avec stratégies de protection des applications
    - Activité commerciale avec stratégies de protection des applications

## <a name="next-section"></a>Section suivante

La section suivante fournit des conseils sur le [développement d'un plan de déploiement Intune](section-4-develop-a-rollout-plan.md).



<!--HONumber=Dec16_HO5-->


