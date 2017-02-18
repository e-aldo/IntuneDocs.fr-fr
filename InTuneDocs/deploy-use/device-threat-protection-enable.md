---
title: Activer Lookout MTP dans Intune | Microsoft Docs
description: "Activer la protection contre les menaces mobiles (MTP) de Lookout dans la console d’administration Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 53862e49c922b75b414fd5aceec3bba2b10299a6
ms.openlocfilehash: 1297522d0f7b52ebe14eb7b938f3458e7308ae27


---

# <a name="enable-lookout-mtp-connection-in-the-intune-admin-console"></a>Activer la connexion à Lookout MTP dans la console d’administration Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour activer la connexion (MTP) de protection contre les menaces de Lookout dans Intune, vous devez avoir déjà configuré le connecteur Intune dans la console Lookout.  Si vous ne l’avez pas encore fait, [configurez votre abonnement pour la protection contre les menaces mobiles de Lookout](set-up-your-subscription-with-lookout-mtp.md).

Pour activer la connexion à Lookup MTP dans Intune, dans la page **Administration** de la [console Administrateur Microsoft Intune](https://manage.microsoft.com), choisissez **Intégration des services tiers**. Choisissez **État de Lookout** et activez **Synchronisation avec MTP** à l’aide du bouton bascule.

![Capture d’écran de la page Synchronisation avec MTP avec le bouton bascule d’activation mis en surbrillance](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Vous **devez** configurer l’application Lookout for Work avant de créer les règles de la stratégie de conformité et de configurer l’accès conditionnel. Cela garantit que l’application est prête et mise à la disposition des utilisateurs finaux qui souhaitent l’installer pour pouvoir accéder à leur messagerie ou aux autres ressources d’entreprise.

Cette opération termine la configuration de l’intégration de Lookup et d’Intune dans la console d’administration Intune.  Les prochaines étapes de l’implémentation de cette solution consistent à déployer les [applications Lookout for Work](configure-and-deploy-lookout-for-work-apps.md) et à définir la stratégie de [conformité](enable-device-threat-protection-rule-in-compliance-policy.md).


## <a name="next-steps"></a>Étapes suivantes
[Configurer l’application Lookout for Work](configure-and-deploy-lookout-for-work-apps.md)



<!--HONumber=Jan17_HO2-->


