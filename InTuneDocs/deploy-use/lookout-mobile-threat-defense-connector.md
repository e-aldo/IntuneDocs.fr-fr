---
title: Connecteur de protection contre les menaces mobiles pour Lookout | Microsoft Docs
description: "Protégez l’accès aux ressources d’entreprise en fonction du risque lié aux appareils, au réseau et aux applications avec le connecteur de protection contre les menaces mobiles pour Lookout et Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: d42fa20a3bc6b6f4a74dd0872aae25cfb33067b9
ms.openlocfilehash: dfed1ece238210e8b98934d8add7dbb9b0f1c1fb
ms.lasthandoff: 03/21/2017


---

# <a name="lookout-mobile-threat-defense-connector-with-intune"></a>Connecteur de protection contre les menaces mobiles pour Lookout avec Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez contrôler l’accès des appareils mobiles aux ressources d’entreprise en fonction de l’évaluation des risques effectuée par Lookout, une solution de défense contre les menaces mobiles intégrée à Microsoft Intune. Le risque est évalué en fonction des données de télémétrie recueillies à partir des appareils par le service Lookout, notamment :
- Vulnérabilités du système d’exploitation
- Applications malveillantes installées
- Profils de réseau malveillants

Vous pouvez configurer des stratégies d’accès conditionnel basés sur l’évaluation des risques Lookout activée par le biais des stratégies de conformité Intune. Les paramètres vous permettent d’autoriser ou de bloquer les appareils non conformes en fonction des menaces détectées.

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a>Comment Intune et Lookout Mobile Threat Defense aident-ils à protéger les ressources de l’entreprise ?
L'application mobile Lookout, **Lookout for work**, est installée et exécutée sur les appareils mobiles. Cette application capture le système de fichiers, la pile réseau ainsi que les données de télémétrie des appareils et des applications (le cas échéant), puis les envoie au service cloud Lookout pour évaluer les risques de l’appareil face aux menaces mobiles. Vous pouvez modifier la classification des niveaux de risque des menaces dans la console Lookout pour l’adapter à vos besoins.  

La stratégie de conformité d’Intune inclut une règle Lookout Mobile Threat Defense basée sur l’évaluation des risques Lookout. Quand cette règle est activée, Intune évalue si l’appareil est conforme à la stratégie activée.

Si l’appareil est détecté non conforme, l’accès aux ressources comme Exchange Online et SharePoint Online peut être bloqué. Les utilisateurs d'appareils bloqués reçoivent une procédure à suivre pour résoudre le problème et accéder à nouveau aux ressources. Cette procédure est lancée à partir de l'application Lookout for work.

## <a name="supported-platforms"></a>Plateformes prises en charge :
Les plateformes suivantes sont prises en charge lorsque Lookout est inscrit dans Intune :
* **Android 4.1 et versions ultérieures**
* **iOS 8 et versions ultérieures** Pour plus d’informations sur les plate-formes et les langues prises en charge, consultez le [site Web de Lookout](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Prérequis :
* Abonnement Microsoft Intune
* Azure Active Directory
* Abonnement d’entreprise à Lookout Mobile EndPoint Security  

Pour plus d’informations, consultez [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)

## <a name="sample-scenarios"></a>Exemples de scénario
Voici quelques scénarios courants :

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Contrôler l’accès en fonction des menaces émanant des applications malveillantes
Lorsque des applications malveillantes telles que des logiciels malveillants sont détectés sur des appareils, vous pouvez isoler ces appareils jusqu'à ce que la menace soit résolue :
* Connexion à la messagerie de l’entreprise
* Synchroniser les fichiers d’entreprise à l’aide de l’application OneDrive for Work
* Accès aux applications d’entreprise

**Bloquer après la détection d’applications malveillantes :**
![diagramme montrant l’accès bloqué par la stratégie d’accès conditionnel quand un appareil est évalué comme non conforme en raison de la présence d’applications malveillantes](../media/mtp/malicious-apps-blocked.png)

**Accès accordé après correction :**

![diagramme montrant l’accès accordé par la stratégie d’accès conditionnel quand l’appareil est évalué comme conforme après la correction](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Contrôler l’accès en fonction de la menace pour le réseau
Détectez les menaces pour votre réseau, telles que les attaques de l’intercepteur (« Man-in-the-middle »), et protégez l’accès aux réseaux Wi-Fi en fonction du risque évalué pour l’appareil.

**Bloquer l'accès au réseau par Wi-Fi :**
![diagramme montrant l’accès Wi-Fi bloqué par la stratégie d’accès conditionnel en raison des menaces pour le réseau détectées](../media/mtp/network-wifi-blocked.png)

**Accès accordé après correction :**

![diagramme montrant l’accès accordé par la stratégie d’accès conditionnel après correction de la menace](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Contrôler l’accès à SharePoint Online en fonction de la menace pour le réseau

Détectez les menaces pour votre réseau, telles que les attaques de l’intercepteur, et empêchez la synchronisation des fichiers d’entreprise en fonction du risque évalué pour l’appareil.

**Bloquer SharePoint Online lorsque des menaces réseau sont détectées :**

![Diagramme montrant l’accès à SharePoint Online bloqué par la stratégie d’accès conditionnel en raison de la menace détectée](../media/mtp/network-spo-blocked.png)


**Accès accordé après correction :**

![Diagramme montrant l’accès accordé par la stratégie d’accès conditionnel après correction de la menace](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a>Étapes suivantes
Voici les principales étapes à effectuer pour implémenter cette solution :
1.    [Configurer votre abonnement Lookout](device-threat-protection-subscription-setup.md)
2.    [Activer Lookout Mobile Threat Defense dans Intune](device-threat-protection-enable.md)
3.  [Configurer et déployer l’application Lookout Mobile Threat Defense](device-threat-protection-apps.md)
4.    [Configurer la stratégie de conformité d’appareil Lookout](device-threat-protection-policy.md)
5.    [Résoudre les problèmes d’intégration Lookout Mobile Threat Defense](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)

