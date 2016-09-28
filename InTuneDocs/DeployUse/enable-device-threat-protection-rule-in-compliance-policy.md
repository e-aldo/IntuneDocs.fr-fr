---
title: "Activer une règle de protection de l’appareil dans la stratégie de conformité | Microsoft Intune"
description: "Activer une règle de protection de l’appareil contre les menaces mobiles dans la stratégie de conformité."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: 761372b2c8b81699bc2584ab1ef8d0f9d523abe9


---

# Activer une règle de protection de l’appareil contre les menaces dans la stratégie de conformité
Avec la protection contre les menaces mobiles de Lookout, Intune vous donne la possibilité de détecter les menaces mobiles et d’évaluer le risque pour votre appareil.  
La règle de stratégie de conformité vous permet d’utiliser cette évaluation du risque pour déterminer si l’appareil est conforme à votre stratégie. Vous pouvez ensuite utiliser la stratégie d’accès conditionnel pour autoriser ou bloquer l’accès à Exchange, à SharePoint et à d’autres services basés sur la conformité de l’appareil.

Conditions pour utiliser la détection des menaces de Lookout MTP dans la stratégie de conformité de l’appareil :

1.  La règle **Protection de l’appareil contre les menaces** doit être activée dans la stratégie de conformité.

2.  La page **État de Lookout** dans la console Administrateur Intune doit afficher la valeur **Actif**. Pour plus d’informations et obtenir des instructions sur l’activation de l’intégration de Lookout, consultez la rubrique [Activer la connexion à Lookout MTP dans la console d’administration Intune](enable-lookout-mtp-connection-in-intune.md).


## Configurer la règle de protection de l’appareil contre les menaces

Avant de créer la règle de protection de l’appareil contre les menaces dans la stratégie de conformité, nous vous recommandons de [configurer votre abonnement à Lookout MTP](set-up-your-subscription-with-lookout-mtp.md), d’[activer la connexion à Lookout dans Intune](enable-lookout-mtp-connection-in-intune.md) et de [configurer l’application Lookout for Work](configure-and-deploy-lookout-for-work-apps.md). La règle de conformité est appliquée uniquement quand la configuration est terminée.

Pour activer la règle de protection de l’appareil contre les menaces, vous pouvez utiliser une stratégie de conformité existante ou en créer une autre.

Lors de la configuration de Lookout MTP, dans la [console Lookout MTP](https://aad.lookout.com), vous avez créé une stratégie qui classifie les diverses menaces selon leur niveau (élevé, moyen et faible). Dans la stratégie de conformité Intune, vous utilisez le niveau de menace pour définir le niveau de menace maximal autorisé.

Dans la console Administrateur Intune, dans la page de la stratégie de conformité, accédez à **Intégrité de l’appareil** et activez la règle **Protection de l’appareil contre les menaces** à l’aide du bouton bascule. Choisissez le niveau de menace maximal autorisé parmi les options suivantes :
* **Aucun (sécurisé)** : c’est le niveau de sécurité le plus haut.  L’appareil ne peut présenter aucune menace.  Si des menaces d’un autre niveau sont détectées sur l’appareil, celui-ci est évalué comme non conforme.  
* **Faible** : l’appareil est évalué comme conforme uniquement si les menaces détectées sont de niveau faible. La présence de menaces de niveau supérieur rend l’appareil non conforme.
* **Moyen** : l’appareil est évalué comme conforme si les menaces détectées sont de niveau faible ou moyen. La présence de menaces de niveau élevé rend l’appareil non conforme.
* **Élevé** : cette option est la moins sécurisée. Les menaces de tout niveau sont fondamentalement autorisées. Cette option peut être utile uniquement si vous utilisez cette solution pour créer des rapports.

![capture d’écran montrant la configuration de la règle de protection de l’appareil contre les menaces ](../media/mtp/mtp-compliance-policy-rule.png)

![capture d’écran montrant l’option de niveau de menace pour configurer la règle de protection de l’appareil contre les menaces](../media/mtp/mtp-compliance-policy-setting.png)

Si vous créez des stratégies d’accès conditionnel pour O365 et d’autres services, l’évaluation de la conformité ci-dessus est prise en compte, ce qui signifie que l’accès est bloqué pour les appareils non conformes tant que la menace n’est pas résolue.

Vous pouvez voir l’état de conformité d’un appareil dans la page Appareils de la console Administrateur Intune.

![capture d’écran de la page Appareils dans la console Administrateur Intune montrant l’état de conformité d’un appareil](../media/mtp/mtp-device-status-intune-console.png)

## Étapes suivantes
* Créer la stratégie d’accès conditionnel
  * [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [Exchange sur site](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [Skype Entreprise Online](restrict-access-to-skype-for-business-online-with-microsoft-intune,md)
  * [Dynamics CRM](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


