---
title: "Configurer des stratégies de mise à jour iOS dans Microsoft Intune"
titlesuffix: 
description: "Configurez des stratégies de mise à jour pour iOS pour forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 6ba354fb3b39544f09363651abfd9e1a5c0f6154
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Configurer des stratégies de mise à jour iOS dans Microsoft Intune
Les stratégies de mise à jour pour iOS vous permettent de forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible. Vous pouvez configurer les jours et les heures pendant lesquels vous ne souhaitez pas que les appareils installent la mise à jour.

## <a name="configure-the-ios-update-policy"></a>Configurer la stratégie de mise à jour d’iOS
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Monitoring + Gestion**.
2. Sur le volet **Intune**, choisissez **Mises à jour logicielles** > **Stratégies de mise à jour iOS**.
4. Dans le volet Stratégies, choisissez **Créer**, puis entrez un nom et une description de la stratégie.
5. Sélectionnez **Paramètres** > **Configurer**, puis indiquez quand les appareils iOS ne sont pas forcés à installer la dernière mise à jour.
6. Choisissez **OK** pour enregistrer cette configuration. Vous êtes maintenant de retour dans le volet **Créer une stratégie de mise à jour**. Choisissez **Créer** pour créer la stratégie et enregistrer vos paramètres.

Le profil est créé et s’affiche dans le volet de la liste des stratégies de mise à jour iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Affecter une stratégie de mise à jour d’iOS à des utilisateurs
Pour affecter une stratégie de mise à jour d’iOS à des utilisateurs, choisissez une stratégie que vous avez configurée. Les stratégies existantes sont disponibles dans le volet **Mises à jour logicielles** > **Stratégies de mise à jour iOS**.
1. Choisissez la stratégie que vous souhaitez attribuer aux utilisateurs, puis **Affectations**. Le volet dans lequel vous pouvez sélectionner des groupes de sécurité Azure Active Directory et les assigner à la stratégie est ouvert.
2. Choisissez **Groupes sélectionnés** pour ouvrir le volet qui affiche les groupes de sécurité Azure AD.
3. Choisissez **Enregistrer** pour déployer la stratégie aux utilisateurs.

Vous avez appliqué la stratégie à des utilisateurs. La conformité de la mise à jour des appareils utilisés par les utilisateurs ciblés par la stratégie de conformité est évaluée.

## <a name="change-the-restricted-days-for-the-policy"></a>Changer les jours restreints pour la stratégie
1. Dans le volet **Mises à jour logicielles**, choisissez **Stratégies de mise à jour iOS**.
2. Sélectionnez la stratégie de mise à jour d’iOS à changer.
3. Sélectionnez **Propriétés** > **Paramètres** pour mettre à jour les informations sur les jours restreints.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Surveiller les appareils iOS équipés d’anciennes versions d’iOS
<!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est accessible dans le volet **Mises à jour logicielles** > **Stratégies de mise à jour iOS**. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour d’iOS et qui n’ont pas été mis à jour. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour.
