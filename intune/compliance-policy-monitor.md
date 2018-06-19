---
title: Analyser les stratégies de conformité des appareils Microsoft Intune
titlesuffix: ''
description: Utilisez le tableau de bord de conformité des appareils pour analyser la conformité globale des appareils, afficher des rapports et afficher la conformité des appareils par stratégie et par paramètre.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 2/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c4c3c3a2d73c6390ef5761f1bd0b12fe55855c6e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31831869"
---
# <a name="monitor-intune-device-compliance-policies"></a>Surveiller les stratégies de conformité d’appareils Intune

Les rapports de conformité aident les administrateurs à analyser la situation de conformité des appareils de leur organisation, et à résoudre rapidement les problèmes liés à la conformité rencontrés par les utilisateurs de l’organisation. Vous pouvez afficher des informations sur l’état de conformité générale des appareils, l’état de conformité d’un paramètre spécifique, l’état de conformité d’une stratégie spécifique. Vous pouvez également explorer en détail des appareils spécifiques pour afficher des paramètres spécifiques et les stratégies qui ont une incidence sur l’appareil.

> [!NOTE]
> À partir de vos commentaires, nous avons apporté quelques améliorations à la sécurité du service Intune en mars. En fonction de la configuration de vos stratégies de conformité, vous devrez peut-être prendre des mesures pour éviter à vos utilisateurs finaux de perdre l’accès à leurs e-mails. Pour plus d’informations, consultez [Améliorations de la sécurité à venir](https://blogs.technet.microsoft.com/intunesupport/2018/02/09/updated-upcoming-security-enhancements-in-the-intune-service/).

## <a name="before-you-begin"></a>Avant de commencer

Suivez les étapes ci-dessous pour rechercher le **tableau de bord de conformité des appareils Intune** dans le portail Azure :

1.  Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification Intune.

2.  Choisissez **Tous les services** dans le menu de gauche, puis entrez **Intune** dans le filtre de la zone de texte.

3.  Choisissez **Intune** &gt; **Conformité de l’appareil** &gt; **Présentation**. Le **tableau de bord Conformité de l’appareil** s’ouvre.

> [!IMPORTANT]
> Les appareils doivent être inscrits dans Intune pour recevoir des stratégies de conformité d’appareils.

## <a name="device-compliance-dashboard"></a>Tableau de bord Conformité de l’appareil

Dans le **tableau de bord de conformité des appareils**, vous pouvez surveiller l’état des stratégies de conformité des appareils, et générer différents rapports dans différentes vignettes, qui vous montrent la situation des appareils de votre organisation en termes de conformité. Vous pouvez afficher les rapports suivants :

-   Conformité globale des appareils

-   Conformité des appareils par stratégie

-   Conformité des appareils par paramètre

![Image illustrant le tableau de bord de la conformité des appareils](./media/idc-1.png)

Vous pouvez également afficher des stratégies de conformité spécifiques et les paramètres qui s’appliquent à un appareil donné, ainsi que l’état de conformité finale de chacun de ces paramètres sur l’appareil.

### <a name="overall-device-compliance-aggregate-report"></a>Rapport Conformité globale des appareils

Il s’agit d’un graphique indiquant l’état de conformité globale de tous les appareils Intune inscrits. Les états de conformité des appareils sont conservés dans deux bases de données : Intune et Azure Active Directory. Voici plus de détails sur les états disponibles pour les stratégies de conformité d’appareils :

-   **Conforme** : l’appareil a correctement appliqué un ou plusieurs paramètres de stratégie de conformité d’appareil ciblés par l’administrateur.

-   **Non conforme :** l’appareil n’a pas pu appliquer un ou plusieurs paramètres de stratégie de conformité d’appareils ciblés par l’administrateur ou l’utilisateur n’a pas respecté les stratégies ciblées par l’administrateur.

-   **In Grace period (Dans la période de grâce) :** l’appareil a été ciblé par l’administrateur avec un ou plusieurs paramètres de stratégies de conformité d’appareils, mais l’utilisateur n’a pas encore appliqué les stratégies, ce qui signifie que l’appareil est non conforme. Il est toutefois dans la période de grâce définie par l’administrateur.

    -   Découvrez plus d’informations sur les actions destinées aux appareils non conformes.

-   **Appareil non synchronisé :** échec de signalement par l’appareil de son l’état de sa stratégie de conformité des appareils pour l’une des raisons suivantes :

    -   **Inconnu** : l’appareil est hors connexion ou n’a pas pu communiquer avec Intune ou Azure AD pour d’autres raisons.

    -   **Erreur** : l’appareil n’a pas pu communiquer avec Intune et Azure AD et a reçu un message d’erreur avec une explication.

> [!IMPORTANT]
> Les appareils inscrits dans Intune, mais non ciblés par des stratégies de conformité des appareils, sont inclus dans ce rapport sous le compartiment **Conforme**.

#### <a name="drill-down-option"></a>Option d’exploration

Dans le **tableau de bord de conformité des appareils**, si vous cliquez sur la vignette Conformité de l’appareil, vous pouvez explorer l’**état de conformité**, l’**alias de messagerie de l’utilisateur**, le **modèle d’appareil** et l’**emplacement** de chaque appareil ciblé par les stratégies de conformité d’appareils.

![Image illustrant le zoom avant du tableau de bord de la conformité des appareils](./media/idc-2.png)

Si vous avez besoin de plus de détails sur un utilisateur spécifique, vous pouvez filtrer le rapport du graphique de conformité d’appareil en tapant l’alias de messagerie de l’utilisateur.

![Image illustrant l’utilisateur spécifique au tableau de bord de conformité des appareils](./media/idc-3.png)

Vous pouvez également cliquer sur l’état de conformité sur le graphique de conformité de l’appareil pour obtenir plus d’informations sur l’état des stratégies de conformité d’appareils de l’utilisateur.

![Image illustrant les différents états du tableau de bord de conformité des appareils](./media/idc-4.png)

#### <a name="filter"></a>Filtre

Si vous cliquez sur le **bouton Filtrer**, le filtre volant s’ouvre avec les options suivantes :

-   Modèle

    -   Zone de texte acceptant une chaîne de recherche libre
<br></br>
-   Plate-forme

    -   Android

    -   iOS

    -   macOS

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

Cliquer sur un appareil, permet d’ouvrir le **volet Appareils** avec l’appareil sélectionné, qui fournit des détails supplémentaires sur le paramètre des stratégies de conformité des appareils appliqués à cet appareil.

Lorsque vous cliquez sur le paramètre de stratégie d’appareil lui-même, vous pouvez voir le nom de stratégie de conformité d’appareil provenant du paramètre de conformité d’appareil ciblé par l’administrateur.

### <a name="devices-without-compliance-policy"></a>Appareils sans stratégie de conformité
Ce rapport identifie les appareils auxquels aucune stratégie de conformité n’a été affectée. Avec l’introduction du paramètre de sécurité qui identifie tous les appareils sans stratégie de conformité comme étant « non conformes », il est important de pouvoir identifier ces appareils. Vous pouvez ensuite leur affecter au moins une stratégie de conformité.

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
