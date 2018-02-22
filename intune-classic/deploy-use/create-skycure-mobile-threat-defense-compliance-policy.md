---
title: "Créer la stratégie de conformité Skycure Mobile Threat Defense"
description: "Créez la stratégie de conformité Skycure Mobile Threat Defense dans le portail classique Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ea45ac89064756f4b8ebd8ca9d163a151b6e6cc2
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Créer la stratégie de conformité Skycure Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune avec Skycure Mobile Threat Defense vous permet de détecter les menaces sur les appareils mobiles et d’évaluer les risques sur ces appareils. Vous pouvez créer une règle de stratégie de conformité Intune qui évalue les risques et détermine si l’appareil est conforme. Vous pouvez ensuite utiliser la stratégie d’accès conditionnel pour autoriser ou bloquer l’accès à des services basés sur la conformité de l’appareil.

## <a name="before-you-begin"></a>Avant de commencer

Configuration requise pour la stratégie de conformité avec protection contre les menaces sur les appareils Skycure :

-   [Configurer l’intégration de Skycure à Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [Activation de la connexion Skycure dans Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

Dans le cadre de la configuration de la défense contre les menaces mobiles Skycure, dans la console Skycure, vous avez créé une stratégie qui classe les diverses menaces selon leur gravité : élevée, moyenne et faible. Vous devez maintenant définir le nombre maximal de menaces autorisées au niveau de la stratégie de conformité Intune.

## <a name="to-create-skycure-compliance-policy"></a>Pour créer la stratégie de conformité Skycure

1.  Accédez au [portail classique Intune](https://manage.microsoft.com/) puis entrez vos informations d’identification.

2.  Choisissez **Stratégie** &gt; **Stratégies de conformité**. Vous pouvez utiliser une stratégie de conformité existante ou en créer une.

3.  Choisissez **Ajouter** &gt; **Intégrité de l’appareil**, puis activer **Protection de l'appareil contre les menaces**.

4.  Sélectionnez le **Niveau de menace maximal autorisé** :

    a.  **Aucun (sécurisé)** : c’est le niveau de sécurité le plus haut. L'appareil ne peut pas avoir de menace présente et accéder aux ressources de l’entreprise. Si des menaces sont détectées, l’appareil est évalué comme non conforme.

    b.  **Faible** : l’appareil est conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.

    c.  **Moyen** : l’appareil est conforme si les menaces détectées sont de niveau faible ou moyen. Si des menaces de niveau élevé sont détectées, l’appareil est déterminé comme non conforme.

    d.  **Élevé** : cette option est la moins sécurisée. Cela active tous les niveaux de menace et utilise la défense contre les menaces mobiles Skycure uniquement à des fins de création de rapport.

> [!IMPORTANT]
> Si vous créez des stratégies d’accès conditionnel pour Office 365 ou d’autres services, l’évaluation de la conformité est effectuée et les appareils non conformes ne peuvent pas accéder à ces services tant que la menace n’est pas résolue.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Étapes suivantes

-   Créer une stratégie d’accès conditionnel pour :

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Exchange sur site](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype Entreprise Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
