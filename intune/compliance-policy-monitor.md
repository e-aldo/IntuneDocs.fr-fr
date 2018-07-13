---
title: Surveiller les stratégies de conformité des appareils dans Microsoft Intune - Azure | Microsoft Docs
description: Utilisez le tableau de bord de conformité des appareils pour analyser la conformité globale des appareils, afficher des rapports et afficher la conformité des appareils par stratégie et par paramètre.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e9de6f1ac8bca1d65a94294d3b049dfccbe44c7
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905357"
---
# <a name="monitor-intune-device-compliance-policies"></a>Surveiller les stratégies de conformité d’appareils Intune

Les rapports de conformité aident les administrateurs à analyser la situation de conformité des appareils de leur organisation, et à résoudre rapidement les problèmes liés à la conformité rencontrés par les utilisateurs de l’organisation. Vous pouvez afficher des informations sur l’état de conformité générale des appareils, l’état de conformité d’un paramètre spécifique, l’état de conformité d’une stratégie spécifique. Vous pouvez également explorer en détail des appareils spécifiques pour afficher des paramètres spécifiques et les stratégies qui ont une incidence sur l’appareil.

## <a name="before-you-begin"></a>Avant de commencer

Suivez les étapes ci-dessous pour rechercher le **tableau de bord de conformité des appareils Intune** dans le portail Azure :

1. Dans le [portail Azure](https://portal.azure.com), connectez-vous avec vos informations d’identification Intune.

2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.

3. Sélectionnez **Conformité de l’appareil** > **Vue d’ensemble**. Le **tableau de bord de conformité des appareils** s’ouvre.

> [!IMPORTANT]
> Les appareils doivent être inscrits dans Intune pour recevoir des stratégies de conformité d’appareils.

## <a name="device-compliance-dashboard"></a>Tableau de bord Conformité de l’appareil

Dans le **tableau de bord de conformité des appareils**, vous pouvez surveiller la conformité de différents appareils, leur état de protection et bien plus encore. Vous pouvez afficher les rapports suivants :

- Conformité globale des appareils

- Conformité des appareils par stratégie

- Conformité des appareils par paramètre

- État de la protection d’appareil

- État de l’agent de menace

![Image illustrant le tableau de bord de la conformité des appareils](./media/idc-1.png)

Vous pouvez également afficher des stratégies de conformité spécifiques et les paramètres qui s’appliquent à un appareil donné, ainsi que l’état de conformité finale de chacun de ces paramètres sur l’appareil.

### <a name="overall-device-compliance-aggregate-report"></a>Rapport Conformité globale des appareils

Il s’agit d’un graphique indiquant l’état de conformité globale de tous les appareils Intune inscrits. Les états de conformité des appareils sont conservés dans deux bases de données : Intune et Azure Active Directory. Voici plus de détails sur les états disponibles pour les stratégies de conformité d’appareils :

- **Conforme** : l’appareil a correctement appliqué un ou plusieurs paramètres de stratégie de conformité d’appareil ciblés par l’administrateur.

- **Non conforme :** l’appareil n’a pas pu appliquer un ou plusieurs paramètres de stratégie de conformité d’appareils ciblés par l’administrateur ou l’utilisateur n’a pas respecté les stratégies ciblées par l’administrateur.

- **In Grace period (Dans la période de grâce) :** l’appareil a été ciblé par l’administrateur avec un ou plusieurs paramètres de stratégies de conformité d’appareils, mais l’utilisateur n’a pas encore appliqué les stratégies, ce qui signifie que l’appareil est non conforme. Il est toutefois dans la période de grâce définie par l’administrateur.

  - Découvrez plus d’informations sur les actions destinées aux appareils non conformes.

- **Appareil non synchronisé :** échec de signalement par l’appareil de son l’état de sa stratégie de conformité des appareils pour l’une des raisons suivantes :

  - **Inconnu** : l’appareil est hors connexion ou n’a pas pu communiquer avec Intune ou Azure AD pour d’autres raisons.

  - **Erreur** : l’appareil n’a pas pu communiquer avec Intune et Azure AD et a reçu un message d’erreur avec une explication.

> [!IMPORTANT]
> Les appareils inscrits dans Intune, mais non ciblés par des stratégies de conformité des appareils, sont inclus dans ce rapport sous le compartiment **Conforme**.

#### <a name="drill-down-option"></a>Option d’exploration

Dans le **tableau de bord de conformité des appareils**, sélectionnez la vignette de conformité d’appareil pour explorer **l’état de conformité**, **l’alias de messagerie de l’utilisateur**, le **modèle d’appareil** et **l’emplacement** de chaque appareil ciblé par les stratégies de conformité d’appareils.

![Image illustrant le zoom avant du tableau de bord de la conformité des appareils](./media/idc-2.png)

Si vous avez besoin de plus de détails sur un utilisateur spécifique, vous pouvez filtrer le rapport du graphique de conformité d’appareil en tapant l’alias de messagerie de l’utilisateur.

![Image illustrant l’utilisateur spécifique au tableau de bord de conformité des appareils](./media/idc-3.png)

Vous pouvez également cliquer sur l’état de conformité sur le graphique de conformité de l’appareil pour obtenir plus d’informations sur l’état des stratégies de conformité d’appareils de l’utilisateur.

![Image illustrant les différents états du tableau de bord de conformité des appareils](./media/idc-4.png)

#### <a name="filter"></a>Filtre

Quand vous sélectionnez le **bouton Filtrer**, le filtre dynamique s’ouvre avec les options suivantes :

- Modèle

  - Zone de texte acceptant une chaîne de recherche libre

- Plate-forme

  - Android

  - iOS

  - macOS

  - Windows

  - Windows Phone

- État

  - Conforme

  - Non conforme

  - In Grace period (Dans la période de grâce)

  - Unknown

  - Erreur

Quand vous sélectionnez le **bouton Mettre à jour**, le filtre dynamique se ferme et les résultats sont mis à jour avec les critères de filtre sélectionnés.

##### <a name="device-details"></a>Détails sur l'appareil

Le fait de sélectionner un appareil ouvre **Appareils** avec l’appareil sélectionné. Ceci fournit plus de détails sur le paramètre de stratégie de conformité d’appareil appliqué à cet appareil.

Quand vous sélectionnez le paramètre de stratégie d’appareil lui-même, vous pouvez voir le nom de la stratégie de conformité d’appareil provenant du paramètre de conformité d’appareil ciblé par l’administrateur.

### <a name="devices-without-compliance-policy"></a>Appareils sans stratégie de conformité
Ce rapport identifie les appareils auxquels aucune stratégie de conformité n’est affectée. Avec l’introduction du paramètre de sécurité qui identifie tous les appareils sans stratégie de conformité comme étant « non conformes », il est important de pouvoir identifier ces appareils. Vous pouvez ensuite leur affecter au moins une stratégie de conformité.

> [!NOTE]
> Vous pouvez configurer le nouveau paramètre de sécurité dans le portail Intune. Sélectionnez **Conformité de l’appareil**, puis sous **Installation**, choisissez **Paramètres de stratégie de conformité**. Utilisez ensuite le bouton bascule pour affecter à l’option **Marquer les appareils sans stratégie de conformité comme étant** la valeur **Conforme** ou **Non conforme**. En savoir plus sur cette [amélioration de la sécurité du service Intune](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

![Image montrant le rapport des appareils sans stratégie de conformité](./media/idc-12.png)

La vignette **Appareils sans stratégie de conformité** est disponible dans le tableau de bord Conformité de l’appareil. Elle permet de voir tous les appareils sans stratégie de conformité, l’utilisateur de l’appareil, l’état de conformité et le modèle de l’appareil.

> [!NOTE]
> Les utilisateurs auxquels une stratégie de conformité est affectée ne s’affichent pas dans le rapport, quelle que soit la plateforme de l’appareil. Par exemple, si vous avez involontairement affecté une stratégie de conformité Windows à un utilisateur disposant d’un appareil Android, celui-ci ne figure pas dans le rapport. Toutefois, Intune considère que l’appareil Android n’est pas conforme. Pour éviter les problèmes, nous vous recommandons de créer des stratégies pour chaque plateforme d’appareil et de les déployer pour tous les utilisateurs.

### <a name="per-policy-device-compliance-report"></a>Rapport de conformité d’appareil par stratégie

Ce rapport indique chaque stratégie de conformité d’appareil et le nombre total d’appareils dans chaque état de conformité. Le titre **Conformité à la stratégie** est disponible dans le **tableau de bord Conformité de l’appareil**. Il affiche toutes les stratégies créées précédemment par l’administrateur, les plateformes auxquelles la stratégie s’applique, ainsi que le nombre d’appareils conformes et non conformes.

![Image illustrant le rapport de conformité des appareils par stratégie](./media/idc-8.png)

Quand vous cliquez sur la vignette Conformité aux stratégies, puis sur une des stratégies de conformité des appareils, vous pouvez voir l’**état de conformité**, l’**alias de messagerie de l’utilisateur**, le **modèle d’appareil** et l’**emplacement** de chaque appareil ciblé par cette stratégie de conformité d’appareils.

## <a name="setting-compliance-report"></a>Rapport de conformité par paramètre

Ce rapport vous permet d’afficher, en fonction du paramètre de conformité choisi, le nombre total d’appareils dans chaque état de conformité. Le titre **Conformité des paramètres** est disponible dans le **tableau de bord de conformité des appareils**. Il affiche tous les paramètres des stratégies de conformité des appareils créées par l’administrateur, les plateformes auxquelles les paramètres de stratégie ont été appliqués et le nombre d’appareils non conformes.

![Image illustrant le rapport de conformité des appareils par paramètre](./media/idc-10.png)

Quand vous cliquez sur la vignette Définition de la conformité, puis sur l’un des paramètres de stratégie de conformité d’appareil, vous pouvez afficher l’**état de conformité**, l’**alias de messagerie de l’utilisateur**, le **modèle d’appareil** et l’**emplacement** de chaque appareil ciblé par le paramètre de stratégie de conformité d’appareil.

## <a name="view-status-of-device-policies"></a>Voir l’état des stratégies d’appareil

Vous pouvez vérifier les différents états de vos stratégies, par plateforme. Par exemple, vous avez une stratégie de conformité macOS. Vous souhaitez voir les appareils qui sont impactés par cette stratégie et savoir s’il existe des conflits ou des échecs.

Cette fonctionnalité est incluse dans le rapport d’état des appareils :

1. Sélectionnez **Conformité de l’appareil** > **Stratégies**. La liste des stratégies apparaît, dont la plateforme, si la stratégie est affectée.
2. Sélectionnez une stratégie, puis choisissez **Vue d’ensemble**. Dans cette vue, l’affectation de stratégie inclut les états suivants :

  - Réussi
  - Erreur
  - Conflit
  - En attente
  - Non applicable

3. Pour voir les détails sur les appareils utilisant cette stratégie, sélectionnez un des états. Par exemple, sélectionnez **Réussi**. La fenêtre suivante montre les détails propres aux appareils, notamment leur nom et l’état du déploiement.

## <a name="how-intune-resolves-policy-conflicts"></a>Résolution des conflits de stratégie par Intune
Des conflits de stratégie peuvent se produire quand plusieurs stratégies Intune sont appliquées à un appareil. Si les paramètres de stratégie se chevauchent, Intune résout les conflits en appliquant les règles suivantes :

- Si les paramètres en conflit proviennent d’une stratégie de configuration Intune et d’une stratégie de conformité, les paramètres de la stratégie de conformité sont prioritaires sur ceux de la stratégie de configuration. Cela est valable même si les paramètres de la stratégie de configuration sont plus sécurisés.

- Si vous avez déployé plusieurs stratégies de conformité, Intune utilise la plus sécurisée d’entre elles.

