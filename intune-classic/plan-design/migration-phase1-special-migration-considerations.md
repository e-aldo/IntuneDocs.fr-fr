---
title: "Facteurs de migration spécifiques à prendre en compte | Microsoft Docs"
description: "Cet article détaille diverses considérations spécifiques de la migration que les clients doivent prendre en compte avant de démarrer une campagne de migration."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7e0adb862d8c60805b3b34406e193df5a93be381
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-special-migration-considerations"></a>Phase 1 : Facteurs de migration spécifiques à prendre en compte

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Selon l’environnement de fournisseur de GPM existant, certaines remarques spécifiques de la migration peuvent être applicables.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Réinitialisation des paramètres d’origine pour le programme Apple DEP (Device Enrollment Program)

Le programme Apple DEP définit des configurations d’appareil qui ne peuvent pas être supprimées par l’utilisateur final. Pour conserver les fonctionnalités de gestion avancée du programme DEP, vous devez réinitialiser les paramètres d’origine sur l’appareil, afin de rétablir l’état prêt à l’emploi, pour pouvoir l’inscrire auprès de Microsoft Intune.

Si vous voulez continuer à utiliser DEP pour gérer les appareils dans Intune, procédez comme suit :

1.  Embarquez le programme [DEP dans Intune](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

2.  Accédez à votre compte Apple DEP et [réaffectez les numéros de série des appareils DEP](https://help.apple.com/deployment/business/#/tesf9562af26) de votre fournisseur de GPM existant vers Intune.

3.  [Synchronisez](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) votre compte DEP avec Intune.

4.  [Créez et affectez](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune) les profils d’inscription DEP appropriés aux numéros de série dans Intune.

5.  Réinitialisez les paramètres d’usine sur les appareils (à distance, via le fournisseur de GPM actuel, ou manuellement, sur chaque appareil).

6.  Distribuez les appareils aux utilisateurs finaux.

## <a name="next-steps"></a>Étapes suivantes 

[Phase 2 : Campagne de migration](/intune-classic/plan-design/migration-phase2-migration-campaign)

