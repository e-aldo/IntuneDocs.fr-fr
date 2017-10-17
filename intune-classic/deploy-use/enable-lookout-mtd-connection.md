---
title: Activer Lookout MTP dans Intune
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
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f34697140a287d41203d1bad5df59250f07d08ce
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a>Activer la connexion Lookout MTD dans le portail classique Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour activer la connexion Lookout Mobile Threat Defense (MTD) dans Intune, vous devez avoir déjà configuré le connecteur Intune dans la console Lookout.  Si vous ne le n'avez pas déjà fait, vous devez [configurer votre abonnement Lookout Mobile Threat Defense](setup-your-lookout-mtd-subscription.md).

Pour activer la connexion à Lookup MTP dans Intune, dans la page **Administration** de la [console Administrateur Microsoft Intune](https://manage.microsoft.com), choisissez **Intégration des services tiers**. Choisissez **État de Lookout** et activez **Synchronisation avec MTP** à l’aide du bouton bascule.

![Capture d’écran de la page Synchronisation avec MTP avec le bouton bascule d’activation mis en surbrillance](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> Vous **devez** configurer l’application Lookout for Work avant de créer les règles de la stratégie de conformité et de configurer l’accès conditionnel. Cela garantit que l’application est prête et mise à la disposition des utilisateurs finaux qui souhaitent l’installer pour pouvoir accéder à leur messagerie ou aux autres ressources d’entreprise.

Cette opération termine la configuration de l’intégration de Lookup et d’Intune dans la console d’administration Intune.  Les prochaines étapes de l’implémentation de cette solution consistent à déployer la stratégie pour les [applications Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).


## <a name="next-steps"></a>Étapes suivantes
[Configurer l’application Lookout for Work](/intune-classic/deploy-use/device-threat-protection-apps)
