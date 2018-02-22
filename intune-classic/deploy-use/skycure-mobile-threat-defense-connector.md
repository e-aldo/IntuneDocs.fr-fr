---
title: Connecteur de protection contre les menaces mobiles pour Skycure
description: "Protégez l’accès aux ressources de l’entreprise en fonction du risque au niveau de l’appareil, du réseau et de l’application avec le connecteur Skycure Mobile Threat Defense et Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 096cd7f2f7895531b00d77c5d26413471fb9bbcf
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Connecteur Skycure Mobile Threat Defense

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez contrôler l’accès des appareils mobiles aux ressources de l’entreprise à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Skycure, une solution de protection contre les menaces mobiles qui s’intègre à Microsoft Intune. Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Skycure, notamment :

-   Défense physique

-   Défense du réseau

-   Défense des applications

-   Défense contre les vulnérabilités

Vous pouvez configurer des stratégies d’accès conditionnel basées sur l’évaluation des risques de Skycure par le biais des stratégies de conformité d’appareil Intune, et les utiliser pour autoriser ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise en fonction des menaces détectées.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Comment Intune et Skycure aident-ils à protéger les ressources de votre entreprise ?

L’application mobile Skycure pour Android ou iOS capture le système de fichiers, la pile réseau, les appareils et les données de télémétrie de l’application lorsqu’elles sont disponibles, puis les envoie au service cloud Skycure pour évaluer les risques de l’appareil face aux menaces mobiles.

La stratégie de conformité d’appareil Intune inclut une règle pour Skycure Mobile Threat Defense, basée sur l’évaluation des risques Skycure. Quand cette règle est activée, Intune évalue si l’appareil est conforme à la stratégie activée.

Si l’appareil est détecté comme non conforme, l’accès aux ressources comme Exchange Online et SharePoint Online est bloqué. Les utilisateurs d’appareils bloqués reçoivent de l’aide à partir de l’application mobile Skycure pour résoudre le problème et récupérer l’accès aux ressources de l’entreprise.

Intune prend en charge deux modes d’intégration avec Skycure :

-   **Configuration de base** : un mode en lecture seule qui permet à Skycure d’identifier les appareils dans Intune.

-   **Intégration complète** : qui permet à Skycure de transmettre à Intune des informations sur les incidents de sécurité et les risques de l’appareil.

## <a name="sample-scenarios"></a>Exemples de scénario

Voici quelques scénarios courants :

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Contrôler l’accès en fonction des menaces émanant des applications malveillantes

Lorsque des applications malveillantes, des logiciels malveillants par exemple, sont détectées sur des appareils, vous pouvez bloquer ces appareils jusqu'à ce que la menace soit écartée :

-   Connexion à la messagerie de l’entreprise

-   Synchroniser les fichiers d’entreprise à l’aide de l’application OneDrive for Work

-   Accès aux applications d’entreprise

**Blocage lorsque des applications malveillantes sont détectées :**

![Applications malveillantes détectées](../media/mtp/skycure-arch-1.png)

**Accès accordé après correction :**

![Applications malveillantes détectées et accès accordé](../media/mtp/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Contrôler l’accès en fonction de la menace pour le réseau

Détectez les menaces, par exemple les interceptions (**Man-in-the-middle**), sur le réseau et protégez l’accès aux réseaux Wi-Fi compte tenu du risque de l’appareil.

**Bloquer l’accès au réseau via le Wi-Fi :**

![Bloquer l’accès au réseau via le Wi-Fi](../media/mtp/skycure-arch-3.png)

**Accès accordé après correction :**

![Accès accordé après correction](../media/mtp/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Contrôler l’accès à SharePoint Online en fonction de la menace pour le réseau

Détectez les menaces, par exemple les interceptions (**Man-in-the-middle**), sur le réseau et empêchez la synchronisation des fichiers d’entreprise compte tenu du risque de l’appareil.

**Bloquer SharePoint Online lorsque des menaces réseau sont détectées :**

![Bloquer SharePoint Online lorsque des menaces réseau sont détectées](../media/mtp/skycure-arch-5.png)

**Accès accordé après correction :**

![Accès accordé après correction pour un exemple Sharepoint](../media/mtp/skycure-arch-6.png)

## <a name="supported-platforms"></a>Plateformes prises en charge

-   **Android 4.1 et versions ultérieures**

-   **iOS 8 et versions ultérieures**

## <a name="pre-requisites"></a>Conditions préalables

-   Azure Active Directory Premium

-   Abonnement Microsoft Intune

-   Abonnement Skycure Mobile Threat Defense

Pour plus d'informations, consultez le [site web Skycure](https://www.skycure.com/skycure-microsoft-integration/).

## <a name="next-steps"></a>Étapes suivantes

Voici les étapes que vous devez effectuer pour intégrer Intune à Skycure :

1.  [Configurer Skycure pour utiliser Azure Active Directory Single Sign On (SSO)](/intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [Télécharger la stratégie de configuration d’application iOS Skycure](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [Ajouter des applications Skycure, Microsoft Authenticator et une stratégie de configuration d’application iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [Déployer des applications Skycure, Microsoft Authenticator et une stratégie de configuration d’application iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [Configurer l’intégration de Skycure à Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [Activer Skycure Mobile Threat Defense dans Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [Créer la stratégie de conformité Skycure Mobile Threat Defense dans Intune](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
