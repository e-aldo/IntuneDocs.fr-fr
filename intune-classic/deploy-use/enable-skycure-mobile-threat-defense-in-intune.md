---
title: Activer Skycure Mobile Threat Defense dans Intune
description: Activez Skycure Mobile Threat Defense dans le portail classique Intune.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 971600d59a6afe019f5f3bd51459964c168afa82
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a>Activer Skycure Mobile Threat Defense dans Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour activer la protection contre les menaces mobiles Skycure, vous devez avoir déjà configuré le [connecteur Intune dans la console Skycure] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a>Pour activer la connexion Skycure MTD dans Intune

1.  Accédez au [portail classique Intune](https://manage.microsoft.com/) puis entrez vos informations d’identification.

2.  Choisissez **Administrateur** &gt; **Intégration de service tiers**, puis choisissez **État de Skycure** et **Synchronisation avec MTD** à l’aide du bouton bascule.

    ![Activer le bouton bascule Skycure dans le portail classique Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> Vous devez configurer les applications Skycure avant de créer les règles de la stratégie de conformité et de configurer l’accès conditionnel. De cette façon, l’application est prête et disponible pour l’installation afin de permettre aux utilisateurs finaux d’accéder à la messagerie et à d’autres ressources de l’entreprise.

Cette opération termine la configuration de l’intégration de Skycure et d’Intune dans la console d’administration Intune. Les prochaines étapes de l’implémentation de cette solution consistent à déployer les applications Skycure et à définir la stratégie de conformité.

## <a name="next-steps"></a>Étapes suivantes

[Créer la stratégie de conformité Skycure Mobile Threat Defense](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
