---
title: "Configurer des stratégies de mise à jour d’iOS"
titlesuffix: Azure portal
description: "Configurez des stratégies de mise à jour pour iOS pour forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: 199760a60ee2290560ebdf933192de0eaf569e9e
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2017
---
# <a name="configure-ios-update-policies"></a>Configurer des stratégies de mise à jour d’iOS
Les stratégies de mise à jour pour iOS vous permettent de forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible. Vous pouvez configurer les jours et les heures pendant lesquels vous ne souhaitez pas que les appareils installent la mise à jour.

## <a name="configure-the-ios-update-policy"></a>Configurer la stratégie de mise à jour d’iOS
1. Accédez au panneau Intune dans le portail Azure.
2. Dans le panneau **Intune**, choisissez **Mises à jour logicielles** > **Stratégies de mise à jour d’iOS**.
4. Dans le panneau de stratégies, choisissez **Créer**, puis entrez un nom et une description pour la stratégie.
5. Sélectionnez **Paramètres** > **Configurer**, puis indiquez quand les appareils iOS ne sont pas forcés à installer la dernière mise à jour.
6. Choisissez **OK** pour enregistrer cette configuration. Vous êtes maintenant de retour dans le panneau **Créer une stratégie de mise à jour**. Choisissez **Créer** pour créer la stratégie et enregistrer vos paramètres.

Le profil est créé et s’affiche dans le panneau de la liste des stratégies de mise à jour d’iOS.

## <a name="assign-an-ios-update-policy-to-users"></a>Affecter une stratégie de mise à jour d’iOS à des utilisateurs
Pour affecter une stratégie de mise à jour d’iOS à des utilisateurs, choisissez une stratégie que vous avez configurée. Les stratégies existantes sont disponibles dans le panneau **Mises à jour logicielles** > **Stratégies de mise à jour d’iOS**.
1. Choisissez la stratégie que vous souhaitez attribuer aux utilisateurs, puis **Affectations**. Dans le panneau qui s’ouvre, vous pouvez sélectionner des groupes de sécurité Azure Active Directory et les affecter à la stratégie.
2. Choisissez **Sélectionner des groupes** pour ouvrir le panneau qui affiche les groupes de sécurité Azure AD. Choisissez **Sélectionner** pour déployer la stratégie sur les utilisateurs.

Vous avez appliqué la stratégie à des utilisateurs. La conformité de la mise à jour des appareils utilisés par les utilisateurs ciblés par la stratégie de conformité est évaluée.

## <a name="change-the-restricted-days-for-the-policy"></a>Changer les jours restreints pour la stratégie
1. Dans le panneau **Mises à jour logicielles**, choisissez **Stratégies de mise à jour d’iOS**.
2. Sélectionnez la stratégie de mise à jour d’iOS à changer.
3. Sélectionnez **Propriétés** et changez les informations sur les jours restreints.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Surveiller les appareils iOS équipés d’anciennes versions d’iOS 
<!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est accessible à partir du panneau **Mises à jour logicielles** > **Stratégies de mise à jour d’iOS**. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour d’iOS et qui n’ont pas été mis à jour. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour.