---
title: "Surveiller les stratégies de conformité d’appareils Intune"
titlesuffix: Azure portal
description: "Apprenez à surveiller les stratégies de conformité des appareils."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f82293ee3803f189cbb67549b1a6cd653572eaaf
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="monitor-intune-device-compliance-policies"></a>Surveiller les stratégies de conformité d’appareils Intune

Les rapports de conformité aident les administrateurs à analyser la situation de conformité des appareils de leur société, et à résoudre rapidement les problèmes liés à la conformité rencontrés par les utilisateurs de l’organisation. Vous pouvez afficher des informations sur l’état de conformité générale des appareils, l’état de conformité d’un paramètre spécifique, l’état de conformité d’une stratégie spécifique. Vous pouvez également explorer en détail des appareils spécifiques pour afficher des paramètres spécifiques et les stratégies qui ont une incidence sur l’appareil.

## <a name="before-you-begin"></a>Avant de commencer

Suivez les étapes ci-dessous pour trouver le **tableau de bord Conformité de l’appareil Intune** dans le portail Azure :

1.  Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification Intune.

2.  Choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

3.  Choisissez **Intune** &gt; **Conformité de l’appareil** &gt; **Présentation**. Le **tableau de bord Conformité de l’appareil** s’ouvre.

> [!IMPORTANT] 
> Les appareils doivent être inscrits dans Intune pour recevoir des stratégies de conformité d’appareils.

## <a name="device-compliance-dashboard"></a>Tableau de bord Conformité de l’appareil

Dans le **tableau de bord Conformité de l’appareil**, vous pouvez surveiller l’état des stratégies de conformité d’appareils, et générer des rapports différents dans différentes vignettes qui vous montrent la situation des appareils de votre organisation en matière de conformité. Vous pouvez afficher les rapports suivants :

-   Conformité globale des appareils

-   Conformité des appareils par stratégie

-   Conformité des appareils par paramètre

![Tableau de bord Conformité de l’appareil](./media/idc-1.png)

Vous pouvez également afficher des stratégies de conformité spécifiques et les paramètres qui s’appliquent à un appareil donné, ainsi que l’état de conformité finale de chacun de ces paramètres sur l’appareil.

### <a name="overall-device-compliance-aggregate-report"></a>Rapport Conformité globale des appareils

Il s’agit d’un graphique indiquant l’état de conformité globale de tous les appareils Intune inscrits. Les états de conformité des appareils sont conservés dans deux bases de données : Intune et Azure Active Directory. Voici plus de détails sur les états disponibles pour les stratégies de conformité d’appareils :

-   **Conforme** : l’appareil a correctement appliqué un ou plusieurs paramètres de stratégie de conformité d’appareil ciblés par l’administrateur.

-   **Non conforme :** l’appareil n’a pas pu appliquer un ou plusieurs paramètres de stratégie de conformité d’appareils ciblés par l’administrateur ou l’utilisateur n’a pas respecté les stratégies ciblées par l’administrateur.

-   **In Grace period (Dans la période de grâce) :** l’appareil a été ciblé par l’administrateur avec un ou plusieurs paramètres de stratégies de conformité d’appareils, mais l’utilisateur n’a pas encore appliqué les stratégies, ce qui signifie que l’appareil est non conforme. Il est toutefois dans la période de grâce définie par l’administrateur.

    -   Découvrez plus d’informations sur les actions destinées aux appareils non conformes.

-   **Appareil non synchronisé :** l’appareil n’a pas pu signaler son état de stratégie de conformité d’appareil pour l’une des raisons suivantes :

    -   **Inconnu** : l’appareil est hors connexion ou n’a pas pu communiquer avec Intune ou Azure AD pour d’autres raisons.

    -   **Erreur** : l’appareil n’a pas pu communiquer avec Intune et Azure AD et a reçu un message d’erreur avec une explication.

> [!IMPORTANT] 
> Les appareils inscrits dans Intune, mais qui ne sont pas ciblés par les stratégies de conformité d’appareils, sont inclus dans ce rapport sous le compartiment **Conforme**.

#### <a name="drill-down-option"></a>Option d’exploration

Dans le **tableau de bord Conformité de l’appareil**, si vous cliquez sur la vignette Conformité de l’appareil, vous pouvez explorer l’**état de conformité**, l’**alias de messagerie de l’utilisateur**, le **modèle d’appareil** et l’**emplacement** de chaque appareil ciblé par les stratégies de conformité d’appareils.

![Exploration du tableau de bord Conformité de l’appareil](./media/idc-2.png)

Si vous avez besoin de plus de détails sur un utilisateur spécifique, vous pouvez filtrer le rapport du graphique de conformité d’appareil en tapant l’alias de messagerie de l’utilisateur.

![Tableau de bord Conformité de l’appareil pour un utilisateur spécifique](./media/idc-3.png)

Vous pouvez également cliquer sur l’état de conformité sur le graphique de conformité de l’appareil pour obtenir plus d’informations sur l’état des stratégies de conformité d’appareils de l’utilisateur.

![Différents états du tableau de bord Conformité de l’appareil](./media/idc-4.png)

#### <a name="filter"></a>Filtre

Si vous cliquez sur le **bouton Filtrer**, le filtre volant s’ouvre avec les options suivantes :

-   Modèle

    -   Zone de texte acceptant une chaîne de recherche libre
<br></br>
-   Plate-forme

    -   Android

    -   iOS

    -   Mac OS

    -   Windows

    -   Windows Phone

-   État

    -   Conforme

    -   Non conforme

    -   In Grace period (Dans la période de grâce)

    -   Unknown

    -   Erreur

Si vous cliquez sur le **bouton Mettre à jour**, le filtre volant doit se fermer et les résultats doivent se mettre à jour selon les critères de filtre sélectionnés.

##### <a name="device-details"></a>Détails sur l'appareil

Cliquez sur un appareil pour ouvrir le panneau **Appareils** avec l’appareil sélectionné. Cela fournit plus de détails sur le paramètre de stratégie de conformité d’appareil appliqué à cet appareil.

![Tableau de bord Conformité de l’appareil](./media/idc-6.png)

Lorsque vous cliquez sur le paramètre de stratégie d’appareil lui-même, vous pouvez voir le nom de stratégie de conformité d’appareil provenant du paramètre de conformité d’appareil ciblé par l’administrateur.

![Nom du paramètre de conformité de l’appareil](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a>Rapport de conformité d’appareil par stratégie

Ce rapport indique chaque stratégie de conformité d’appareil et le nombre total d’appareils dans chaque état de conformité. Le titre **Conformité à la stratégie** est disponible dans le **tableau de bord Conformité de l’appareil**. Il affiche toutes les stratégies créées précédemment par l’administrateur, les plateformes auxquelles la stratégie s’applique, ainsi que le nombre d’appareils conformes et non conformes.

![Rapport de conformité d’appareil par stratégie](./media/idc-8.png)

Lorsque vous cliquez sur la vignette Conformité aux stratégies, puis sur une des stratégies de conformité d’appareils, vous pouvez voir l’**état de conformité**, l’**alias de messagerie de l’utilisateur**, le **modèle d’appareil** et l’**emplacement** de chaque appareil ciblé par la stratégie de conformité d’appareils.

![Vignette Conformité aux stratégies](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a>Rapport de conformité d’appareil par paramètre

Ce rapport vous permet d’afficher, en fonction du paramètre de conformité choisi, le nombre total d’appareils dans chaque état de conformité. Le titre **Définition de la conformité** est disponible dans le **tableau de bord Conformité de l’appareil**. Il affiche tous les paramètres de toutes les stratégies de conformité d’appareil créées par l’administrateur, les plateformes auxquelles les paramètres de stratégie ont été appliqués et le nombre d’appareils non conformes.

![Rapport de conformité d’appareil par paramètre](./media/idc-10.png)

Lorsque vous cliquez sur la vignette Définition de la conformité, puis sur l’un des paramètres de stratégie de conformité d’appareil, vous pouvez afficher l’**état de conformité**, l’**alias de messagerie de l’utilisateur**, le **modèle d’appareil** et l’**emplacement** de chaque appareil ciblé par le paramètre de stratégie de conformité d’appareil.

![Vignette Définition de la conformité](./media/idc-11.png)
