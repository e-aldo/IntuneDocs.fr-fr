---
title: "Configurer des stratégies de mise à jour iOS dans Microsoft Intune"
titlesuffix: 
description: "Configurez des stratégies de mise à jour pour iOS pour forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.openlocfilehash: 2062f9cd551ec6d7f42449041e6c8de837221631
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Configurer des stratégies de mise à jour iOS dans Microsoft Intune
Les stratégies de mise à jour pour iOS vous permettent de forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible. Vous pouvez configurer les jours et les heures pendant lesquels vous ne souhaitez pas que les appareils installent la mise à jour.

## <a name="configure-the-ios-update-policy"></a>Configurer la stratégie de mise à jour d’iOS
1. Accédez à la page Intune dans le portail Azure.
2. Dans la page **Intune**, choisissez **Mises à jour logicielles** > **Stratégies de mise à jour iOS**.
4. Dans la page de stratégies, choisissez **Créer**, puis entrez un nom et une description pour la stratégie.
5. Sélectionnez **Paramètres** > **Configurer**, puis indiquez quand les appareils iOS ne sont pas forcés à installer la dernière mise à jour.
6. Choisissez **OK** pour enregistrer cette configuration. Vous êtes maintenant de retour dans la page **Créer une stratégie de mise à jour**. Choisissez **Créer** pour créer la stratégie et enregistrer vos paramètres.

Le profil est créé et s’affiche dans la page de la liste des stratégies de mise à jour iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Affecter une stratégie de mise à jour d’iOS à des utilisateurs
Pour affecter une stratégie de mise à jour d’iOS à des utilisateurs, choisissez une stratégie que vous avez configurée. Les stratégies existantes sont disponibles dans la page **Mises à jour logicielles** > **Stratégies de mise à jour iOS**.
1. Choisissez la stratégie que vous souhaitez attribuer aux utilisateurs, puis **Affectations**. Dans la page qui s’ouvre, vous pouvez sélectionner des groupes de sécurité Azure Active Directory et les affecter à la stratégie.
2. Choisissez **Sélectionner des groupes** pour ouvrir la page qui affiche les groupes de sécurité Azure AD. Choisissez **Sélectionner** pour déployer la stratégie sur les utilisateurs.

Vous avez appliqué la stratégie à des utilisateurs. La conformité de la mise à jour des appareils utilisés par les utilisateurs ciblés par la stratégie de conformité est évaluée.

## <a name="change-the-restricted-days-for-the-policy"></a>Changer les jours restreints pour la stratégie
1. Dans la page **Mises à jour logicielles**, choisissez **Stratégies de mise à jour iOS**.
2. Sélectionnez la stratégie de mise à jour d’iOS à changer.
3. Sélectionnez **Propriétés** et changez les informations sur les jours restreints.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Surveiller les appareils iOS équipés d’anciennes versions d’iOS 
<!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est accessible dans la page **Mises à jour logicielles** > **Stratégies de mise à jour iOS**. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour d’iOS et qui n’ont pas été mis à jour. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour.