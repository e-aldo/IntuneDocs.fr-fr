---
title: "Protéger l’accès à l’aide de la protection de l’appareil contre les menaces | Microsoft Docs"
description: "Protégez l’accès aux ressources d’entreprise en fonction du risque évalué pour l’appareil, le réseau et l’application."
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
ms.sourcegitcommit: 931f222898a224c2f646ad203f12676c39b78946
ms.openlocfilehash: aaa0965c2bd4d4093da0c57eaa2e3bd05eb6779a


---

# <a name="protect-access-to-company-resource-based-on-device-network-and-application-risk"></a>Protéger l’accès aux ressources d’entreprise en fonction du risque évalué pour l’appareil, le réseau et l’application

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez contrôler l’accès aux ressources d’entreprise à partir des appareils mobiles, en fonction de l’évaluation des risques effectuée par Lookout, une solution de protection contre les menaces sur les appareils qui est intégrée à Microsoft Intune. Le risque est évalué en fonction des données de télémétrie recueillies à partir des appareils par le service Lookout, notamment :
- Vulnérabilités du système d’exploitation
- Applications malveillantes installées
- Profils de réseau malveillants

Vous pouvez configurer des stratégies d’accès conditionnel basés sur l’évaluation des risques Lookout activée par le biais des stratégies de conformité Intune. Les paramètres vous permettent d’autoriser ou de bloquer les appareils non conformes en fonction des menaces détectées.  

## <a name="what-problem-does-this-solve"></a>Quel problème cette fonctionnalité résout-elle ?
Les entreprises doivent protéger leurs données sensibles contre diverses menaces émergentes, notamment les menaces ciblant le matériel, les applications et le réseau, ainsi que les vulnérabilités du système d’exploitation.

Historiquement, les entreprises ont été proactives en matière de protection des PC contre les attaques, tandis que les appareils mobiles restent non contrôlés et non protégés. Les plateformes mobiles offrent maintenant une protection intégrée grâce notamment à l’isolation d’application et à la vérification des applications des App Store, mais elles restent vulnérables aux attaques sophistiquées. Aujourd'hui, de plus en plus d’employés utilisent des appareils pour travailler et ils ont besoin d’accéder à des informations sensibles. Les appareils doivent être protégés contre des attaques de plus en plus sophistiquées.

Intune vous permet de contrôler l’accès aux ressources d’entreprise sur la base de l’évaluation du risque fournie par des solutions de protection contre les menaces comme Lookout.

## <a name="how-do-intune-and-lookout-device-threat-protection-help-protect-company-resources"></a>Comment Intune et la protection contre les menaces sur les appareils de Lookout vous aident-ils à protéger les ressources d’entreprise ?
L'application mobile Lookout, **Lookout for work**, est installée et exécutée sur les appareils mobiles. Cette application capture le système de fichiers, la pile réseau ainsi que les données de télémétrie des appareils et des applications (le cas échéant), puis les envoie au service cloud Lookout pour évaluer les risques de l’appareil face aux menaces mobiles. Vous pouvez modifier la classification des niveaux de risque des menaces dans la console Lookout pour l’adapter à vos besoins.  

La stratégie de conformité dans Intune inclut une règle pour la protection contre les menaces mobiles de Lookout basée sur l’évaluation du risque Lookout. Quand cette règle est activée, Intune évalue si l’appareil est conforme à la stratégie activée.

Si l’appareil est considéré comme non conforme, l'accès aux ressources comme Exchange Online et SharePoint Online peut être bloqué. Les utilisateurs d'appareils bloqués reçoivent une procédure à suivre pour résoudre le problème et accéder à nouveau aux ressources. Cette procédure est lancée à partir de l'application Lookout for work.

## <a name="supported-platforms"></a>Plateformes prises en charge :
Les plateformes suivantes sont prises en charge lorsque Lookout est inscrit dans Intune :
* **Android 4.1 et versions ultérieures**
* **iOS 8 et versions ultérieures** Pour plus d’informations sur les plate-formes et les langues prises en charge, consultez le [site Web de Lookout](https://personal.support.lookout.com/hc/en-us/articles/114094140253).

## <a name="prerequisites"></a>Conditions préalables :
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
1.    [Configurer votre abonnement avec la protection des appareils contre les menaces](device-threat-protection-subscription-setup.md)
2.    [Activer la connexion de la protection des appareils contre les menaces dans Intune](device-threat-protection-enable.md)
3.  [Configurer et déployer l’application de protection des appareils contre les menaces](device-threat-protection-apps.md)
4.    [Configurer une stratégie de conformité pour la protection des appareils contre les menaces](device-threat-protection-policy.md)
5.    [Résoudre les problèmes d’intégration de la protection des appareils contre les menaces](http://docs.microsoft.com/intune/troubleshoot/device-threat-protection-troubleshooting)



<!--HONumber=Jan17_HO4-->


