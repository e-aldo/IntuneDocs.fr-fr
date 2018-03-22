---
title: Facteurs de migration spécifiques à prendre en compte
titlesuffix: Microsoft Intune
description: Cet article présente les facteurs de migration spécifiques à prendre en compte avant de lancer une campagne de migration vers Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: bd59cf3a4764cc66d0e7d1f47e69c2ff93352387
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="special-migration-considerations"></a>Facteurs de migration spécifiques à prendre en compte

Selon l’environnement de votre fournisseur MDM existant, certains facteurs de migration spécifiques peuvent s’appliquer.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Réinitialisation des paramètres d’origine pour le programme Apple DEP (Device Enrollment Program)

Le programme Apple DEP définit des configurations d’appareil qui ne peuvent pas être supprimées par l’utilisateur final. Pour conserver les fonctionnalités de gestion avancée du programme DEP, vous devez rétablir les paramètres d’usine de l’appareil et restaurer son état initial pour pouvoir l’inscrire sur Intune.

Pour continuer à utiliser DEP pour gérer les appareils dans Intune, [configurez l’inscription des appareils iOS avec le programme d’inscription des appareils](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Étapes suivantes

[Phase 2 : Campagne de migration](migration-guide-campaign.md)
