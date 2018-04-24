---
title: Configurer des stratégies de mise à jour du logiciel iOS dans Microsoft Intune
titlesuffix: ''
description: Configurez des stratégies de mise à jour pour iOS pour forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.openlocfilehash: 58727a501d6a8ec14e964094eac9fcd6eb3868da
ms.sourcegitcommit: c3ae3c3dc46b62d9191813d25a196874ba4927be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ios-update-policies-in-microsoft-intune"></a>Configurer des stratégies de mise à jour iOS dans Microsoft Intune

Les stratégies de mise à jour du logiciel iOS vous permettent de forcer les appareils exécutant iOS 10.3 et ultérieur supervisés à installer automatiquement la dernière mise à jour de système d’exploitation disponible. Cette fonctionnalité est disponible uniquement pour les appareils supervisés. Vous pouvez configurer les jours et les heures pendant lesquels vous ne souhaitez pas que les appareils installent la mise à jour. 

Quand l’appareil s’enregistre, environ toutes les huit heures, si une mise à jour est disponible et que ce n’est pas pendant un créneau horaire restreint, l’appareil tente de télécharger et d’installer la dernière mise à jour du système d’exploitation. Aucune interaction utilisateur n’est nécessaire pour mettre à jour l’appareil. La stratégie n’empêchera pas un utilisateur de mettre à jour le système d’exploitation.

## <a name="configure-the-ios-update-policy"></a>Configurer la stratégie de mise à jour d’iOS
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Sur le volet **Intune**, choisissez **Mises à jour logicielles** > **Stratégies de mise à jour iOS**.
4. Dans le volet Stratégies, choisissez **Créer**, puis entrez un nom et une description de la stratégie.
5. Sélectionnez **Paramètres** > **Configurer**, puis indiquez quand les appareils iOS ne sont pas forcés à installer la dernière mise à jour. Vous pouvez configurer les jours de la semaine, le fuseau horaire, l’heure de début et l’heure de fin.
6. Choisissez **OK** pour enregistrer cette configuration. Vous êtes maintenant de retour dans le volet **Créer une stratégie de mise à jour**. Choisissez **Créer** pour créer la stratégie et enregistrer vos paramètres.

Le profil est créé et s’affiche dans le volet de la liste des stratégies de mise à jour iOS. Apple MDM ne permet pas de forcer l’appareil à installer la mise à jour avant une certaine date ou heure. 

## <a name="change-the-restricted-times-for-the-policy"></a>Changer les heures restreintes de la stratégie

1.  Dans le panneau **Mises à jour logicielles**, choisissez **Stratégies de mise à jour d’iOS**.
2.  Sélectionnez la stratégie de mise à jour d’iOS à changer.
3.  Sélectionnez **Propriétés** et changez les informations sur les heures restreintes.
4.  Choisir les jours de la semaine
5.  Fuseau horaire dans lequel cette stratégie sera appliquée
6.  Heure de début et de fin pour les heures sur liste rouge

## <a name="assign-an-ios-update-policy-to-users"></a>Affecter une stratégie de mise à jour d’iOS à des utilisateurs

Pour affecter une stratégie de mise à jour d’iOS à des utilisateurs, choisissez une stratégie que vous avez configurée. Les stratégies existantes sont disponibles dans le volet **Mises à jour logicielles** > **Stratégies de mise à jour iOS**.

1. Choisissez la stratégie que vous souhaitez attribuer aux utilisateurs, puis **Affectations**. Le volet dans lequel vous pouvez sélectionner des groupes de sécurité Azure Active Directory et les assigner à la stratégie est ouvert.
2. Choisissez **Groupes sélectionnés** pour ouvrir le volet qui affiche les groupes de sécurité Azure AD. Déterminez qui a accès à la stratégie en affectant des groupes à inclure et à exclure.
3. Choisissez **Enregistrer** pour déployer la stratégie aux utilisateurs.

Vous avez appliqué la stratégie à vos utilisateurs ou appareils. La conformité de la mise à jour des appareils utilisés par les utilisateurs ciblés par la stratégie de conformité est évaluée. Cette stratégie prend également en charge les appareils sans utilisateur.

## <a name="monitor-ios-device-installation-failures"></a>Suivre les échecs d’installation d’appareil iOS
<!-- 1352223 -->
Le rapport **Échecs d’installation pour les appareils iOS** est disponible dans le volet **Mises à jour logicielles**. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour d’iOS, qui ont tenté d’effectuer une mise à jour et qui n’ont pas pu être mis à jour. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour. Les appareils intègres et à jour ne sont pas affichés dans la liste. Le terme « à jour » signifie que l’appareil dispose de la mise à jour la plus récente qu’il peut prendre en charge.

