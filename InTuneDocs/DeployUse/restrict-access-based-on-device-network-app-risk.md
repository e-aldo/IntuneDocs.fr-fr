---
title: "Restreindre l’accès à l’aide de la protection contre les menaces mobiles | Microsoft Intune"
description: "Restreindre l’accès aux ressources d’entreprise en fonction du risque évalué pour l’appareil, le réseau et l’application."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 61480eb11cc8f4b6b336e48a50c2fe1b5fcd3fac
ms.openlocfilehash: c05dfc8154cd13b74f42b4f63262613be8956d87


---

# Restreindre l’accès aux ressources d’entreprise en fonction du risque évalué pour l’appareil, le réseau et l’application
Vous pouvez contrôler l’accès aux ressources d’entreprise à partir d’appareils mobiles, en utilisant l’évaluation du risque effectuée par Lookout, une solution de protection contre les menaces mobiles (MTP) qui est intégrée à Microsoft Intune. Le risque est évalué sur la base des données de télémétrie que le service Lookout MTP collecte des appareils concernant les vulnérabilités du système d’exploitation, les applications malveillantes installées et les profils réseau. Sur la base de cette évaluation du risque, vous pouvez ensuite configurer des stratégies d’accès conditionnel dans Intune et autoriser ou bloquer des appareils évalués comme non conformes en raison des menaces qui y ont été détectées.  Cette fonctionnalité est prise en charge uniquement pour les appareils **Android** qui exécutent la version **4.1 ou ultérieure** et qui sont inscrits dans Microsoft Intune.  
## Quel problème cette fonctionnalité résout-elle ?
Les entreprises et les organisations doivent protéger leurs données sensibles contre diverses menaces émergentes, notamment les menaces ciblant le matériel, les applications et le réseau, ainsi que les vulnérabilités du système d’exploitation.

Depuis plusieurs années, les entreprises et les organisations ont mis en place une politique active de protection des PC contre les attaques malveillantes. En revanche, les appareils mobiles ne sont souvent pas protégés correctement. Les plateformes mobiles offrent maintenant une protection intégrée du système d’exploitation par le biais de techniques telles que l’isolation d’application et la vérification des applications des App Store, mais elles restent vulnérables aux attaques sophistiquées. Les appareils mobiles sont de plus en plus utilisés par les employés dans un cadre professionnel et nécessitent un accès à des informations parfois sensibles et stratégiques. Il est donc essentiel de protéger ces appareils contre les diverses attaques sophistiquées actuelles.

Intune vous permet de contrôler l’accès aux ressources et données d’entreprise sur la base de l’évaluation du risque effectuée par des solutions MTP comme Lookout.

## Comment la protection contre les menaces mobiles d’Intune et de Lookout vous aide-t-elle à protéger les ressources d’entreprise ?
Quand l’application mobile de Lookout (Lookout for Work) est exécutée sur un appareil mobile, elle capture des données de télémétrie sur le système de fichiers, la pile réseau, l’appareil et l’application (le cas échéant), puis elle envoie toutes ces données au service cloud Lookout MTP (Mobile Threat Protection), qui calcule le risque cumulé des menaces mobiles pour l’appareil. Vous pouvez également modifier la classification des niveaux de risque des menaces dans la console MTP selon vos besoins.  
La stratégie de conformité dans Intune inclut une nouvelle règle pour la protection contre les menaces mobiles de Lookout qui est basée sur l’évaluation du risque réalisée par le service Lookout MTP. Quand cette règle est activée, Microsoft Intune évalue si l’appareil est conforme à la stratégie activée.

Si l’appareil est évalué comme non conforme à la stratégie de conformité, l’accès aux ressources telles que SharePoint Online et Exchange Online peut être bloqué à l’aide de stratégies d’accès conditionnel. Si l’accès est bloqué, une procédure pas à pas est indiquée aux utilisateurs finaux pour les aider à résoudre le problème et à récupérer l’accès aux ressources d’entreprise. Cette procédure pas à pas s’affiche dans l’application Lookout for Work.

## Exemples de scénarios
Voici quelques scénarios courants :
### Menace provenant d’applications malveillantes :
Quand des applications ou programmes malveillants sont détectés sur un appareil, vous pouvez empêcher l’appareil d’effectuer les opérations suivantes :
* Se connecter à la messagerie d’entreprise tant que la menace n’est pas résolue.
* Synchroniser les fichiers d’entreprise à l’aide de l’application OneDrive pour le travail.
* Accéder à des applications stratégiques.

**Accès bloqué après la détection d’applications malveillantes :**
![diagramme montrant l’accès bloqué par la stratégie d’accès conditionnel quand un appareil est évalué comme non conforme en raison de la présence d’applications malveillantes](../media/mtp/malicious-apps-blocked.png)

**Appareil débloqué pouvant accéder aux ressources d’entreprise après correction de la menace :**

![diagramme montrant l’accès accordé par la stratégie d’accès conditionnel quand l’appareil est évalué comme conforme après la correction](../media/mtp/malicious-apps-unblocked.png)
### Menaces pour le réseau :
Détectez les menaces pour votre réseau, telles que les attaques de l’intercepteur (« Man-in-the-middle »), et restreignez l’accès aux réseaux Wi-Fi en fonction du risque évalué pour l’appareil.

**Accès au réseau via le Wi-Fi bloqué :**
![diagramme montrant l’accès Wi-Fi bloqué par la stratégie d’accès conditionnel en raison des menaces pour le réseau détectées](../media/mtp/network-wifi-blocked.png)

**Accès accordé après correction :**

![diagramme montrant l’accès accordé par la stratégie d’accès conditionnel après correction de la menace](../media/mtp/network-wifi-unblocked.png)
### Menaces pour le réseau (accès à SharePoint Online bloqué) :

Détectez les menaces pour votre réseau, telles que les attaques de l’intercepteur, et empêchez la synchronisation des fichiers d’entreprise en fonction du risque évalué pour l’appareil.

**Accès à SharePoint Online bloqué en raison de la menace pour le réseau détectée sur l’appareil :**

![Diagramme montrant l’accès à SharePoint Online bloqué par la stratégie d’accès conditionnel en raison de la menace détectée](../media/mtp/network-spo-blocked.png)


**Accès accordé après correction :**

![Diagramme montrant l’accès accordé par la stratégie d’accès conditionnel après correction de la menace](../media/mtp/network-spo-unblocked.png)

## Étapes suivantes
Voici les principales étapes à effectuer pour implémenter cette solution :
1.  [Configurer votre abonnement pour la protection contre les menaces mobiles de Lookout](set-up-your-subscription-with-lookout-mtp.md)
2.  [Activer la connexion à Lookout MTP dans la console d’administration Intune](enable-lookout-mtp-connection-in-intune.md)
3.  [Configurer et déployer l’application Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)
4.  [Configurer une stratégie de conformité](enable-device-threat-protection-rule-in-compliance-policy.md)
5.  [Résoudre les problèmes d’intégration de Lookout](http://docs.microsoft.com/en-us/intune/troubleshoot/troubleshooting-lookout-integration.md)



<!--HONumber=Sep16_HO2-->


