---
title: Créer et déployer des stratégies de gestion des appareils mobiles
description: Suivez les instructions pas-à-pas de cette rubrique pour créer une stratégie de gestion des applications mobiles.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e751934549490885c1ebf2445ec8f112f640f5bd
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a>Créer et déployer des stratégies de protection des applications avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique décrit le processus de création d’une stratégie de protection des applications dans le **portail Azure**. Le portail Azure est la nouvelle console d’administration permettant de créer des stratégies de protection des applications. Nous vous recommandons de l’utiliser pour créer de telles stratégies. Le portail Azure prend en charge les scénarios GAM suivants :

- Appareils inscrits dans Intune.
- Appareils gérés par une solution de gestion des appareils mobiles (MDM) tierce.
- Appareils qui ne sont gérés par aucune solution de gestion des appareils mobiles (BYOD).

>[!IMPORTANT]
Voici quelques points à prendre en compte si vous utilisez la **console d’administration Intune** pour gérer vos appareils :

> * Vous pouvez créer une stratégie de protection des applications qui prend en charge les applications pour les appareils inscrits dans Intune à l’aide de la [console d’administration Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).
> * Vous ne pouvez pas importer les stratégies de protection des applications créées dans la console d’administration Intune dans le portail Azure.  Vous devez les recréer dans le portail Azure.

> * La console d’administration Intune peut ne pas afficher tous les paramètres de stratégie de protection des applications. Le portail Azure est la nouvelle console d’administration permettant de créer des stratégies de protection des applications.

> * Pour déployer des applications gérées, vous devez créer une stratégie de protection des applications dans la console d’administration Intune. Dans ce cas, vous souhaiterez peut-être créer des stratégies de protection des applications dans la console d’administration Intune et dans le portail Azure : dans la console d’administration Intune pour être sûr de pouvoir déployer des applications gérées, et dans le portail Azure puisqu’il s’agit de la nouvelle console d’administration qui contient tous les paramètres des stratégies de protection des applications.

> * Si vous créez des stratégies de protection des applications dans la console d’administration Intune et dans le portail Azure, la stratégie créée dans le portail est appliquée aux applications.

Pour afficher la liste des paramètres de stratégie pris en charge pour les plateformes Android et iOS, sélectionnez l’un des éléments suivants :

> [!div class="op_single_selector"]
- [Stratégies iOS](ios-mam-policy-settings.md)
- [Stratégies Android](android-mam-policy-settings.md)

- Pour obtenir une description plus détaillée du fonctionnement des stratégies de protection des applications et les scénarios pris en charge par les stratégies de protection des applications Intune, consultez [Protéger les données d’application à l’aide de stratégies de protection des applications](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).

##  <a name="create-an-app-protection-policy"></a>Créer une stratégie de protection des applications
Les stratégies de protection des applications sont créées dans le portail Azure. Si vous utilisez le portail Azure pour la première fois, lisez [Portail Azure pour les stratégies de protection des applications Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) pour vous familiariser avec celui-ci. Avant de créer une stratégie de protection des applications, passez en revue les informations sur [les prérequis et la prise en charge](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

Pour créer des stratégies de protection des applications, procédez comme suit :

1. Accédez au [portail Azure](https://portal.azure.com) et entrez vos informations d’identification.

2. Choisissez **Plus de services** et tapez « Intune ».

3. Choisissez **Protection des applications Intune**.

4. Choisissez **Gestion des applications mobiles Intune &gt; Paramètres** pour ouvrir le panneau **Tous les paramètres**.

    ![Capture d’écran du panneau Gestion des applications mobiles Intune](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  Dans le panneau **Tous les paramètres**, choisissez **Stratégie d’application**. Cette opération ouvre le panneau **Stratégie d’application** dans lequel vous allez créer des stratégies et modifier des stratégies existantes. Choisissez **Ajouter une stratégie**.

    ![Capture d’écran du panneau Stratégie d’application avec l’option de menu Ajouter une stratégie mise en surbrillance ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  Tapez un nom pour la stratégie, ajoutez une brève description et sélectionnez le type de plateforme de manière à créer une stratégie pour iOS ou Android. Vous pouvez créer plusieurs stratégies pour chaque plateforme.

    ![Capture d’écran du panneau Ajouter une stratégie](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  Choisissez **Applications** pour ouvrir le panneau **Applications** qui contient la liste des applications disponibles. Dans cette liste, sélectionnez une ou plusieurs applications à associer à la stratégie que vous créez. Une fois que vous avez sélectionné les applications, choisissez **Sélectionner** au bas du panneau **Applications** pour enregistrer votre sélection.

    > [!IMPORTANT]
    > Vous devez sélectionner au moins une application pour créer une stratégie.

5.  Dans le panneau **Ajouter une stratégie**, choisissez **Configurer les paramètres requis** pour ouvrir le panneau des paramètres de stratégie.

    Il existe deux catégories de paramètres de stratégie : **Réadressage des données** et **Accès**.  Les stratégies de réadressage des données sont applicables au déplacement des données vers l’intérieur et l’extérieur des applications, tandis que les stratégies d’accès déterminent comment l’utilisateur final accède aux applications dans un contexte de travail.
    Pour bien démarrer, les paramètres de stratégie sont définis par défaut. Il est inutile d’apporter des modifications si les valeurs par défaut répondent à vos besoins.

    > [!TIP]
    > Ces paramètres de stratégie sont appliqués uniquement quand vous utilisez des applications dans le contexte de travail.  Quand l’utilisateur final utilise l’application pour effectuer une tâche personnelle, il n’est pas affecté par ces stratégies.

    ![Capture d’écran du panneau Paramètres, avec le panneau Ajouter une stratégie](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  Choisissez **OK** pour enregistrer cette configuration. Vous êtes maintenant de retour dans le panneau **Ajouter une stratégie** . Choisissez **Créer** pour créer la stratégie et enregistrer vos paramètres.

    ![Capture d’écran du panneau Ajouter une stratégie montrant que les applications et les paramètres ont été configurés](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

Quand vous avez fini de créer une stratégie comme décrit dans la procédure précédente, elle n’est pas déployée sur les utilisateurs. Pour déployer une stratégie, consultez la section suivante, « Déployer une stratégie sur les utilisateurs ».

> [!IMPORTANT]
> Si vous créez une stratégie de protection des applications pour une application à l’aide de la console d’administration Intune et une autre à l’aide du portail Azure, celle créée à l’aide du portail est prioritaire. Cependant, la création de rapports dans la console Intune ou Configuration Manager indique les paramètres de stratégie créés à partir de la console d’administration Intune. Par exemple :
>
> -   Vous avez créé une stratégie de protection des applications dans la console d’administration Intune qui bloque la copie à partir d’une application.
> -   Vous avez créé une stratégie de protection des applications dans la console Azure qui autorise la copie à partir d’une application.
> -   Vous associez ces deux stratégies à la même application.
> -   La stratégie créée à partir de la console Azure est prioritaire et que la copie est autorisée.
> -   Cependant, l’état et les rapports dans la console Intune indiquent de façon erronée que la copie est bloquée.

## <a name="line-of-business-lob-apps-optional"></a>Applications métier (facultatif)

À compter de la version Intune 1703, vous pouvez ajouter des applications métier dans Intune de façon générale lors de la création d’une stratégie de protection des applications. Cela vous donne la possibilité de définir des stratégies de protection des applications pour les applications métier à l’aide du SDK GAM sans avoir besoin d’autorisations de déploiement d’application complètes.
/intune/app-sdk-get-started
> [!TIP]
> Vous pouvez également ajouter des applications métier dans Intune pendant que vous parcourez le flux de travail du [SDK d’application Intune](/intune/app-sdk-get-started).

> [!IMPORTANT]
> Si les utilisateurs disposent uniquement des autorisations spécifiques pour déployer des applications GAM, et non des autorisations de déploiement d’application complètes (ce qui leur permettrait de déployer n’importe quelle application dans Intune), ils ne peuvent pas parcourir le flux de travail du SDK Intune, mais ils peuvent toujours ajouter leurs applications métier par l’intermédiaire du flux de travail de création de stratégie de protection des applications GAM.

### <a name="to-add-lob-apps-ios-and-android"></a>Pour ajouter des applications métier (iOS et Android)

1.  Dans le panneau Ajouter une stratégie, choisissez Configurer les **applications** pour ouvrir le panneau Applications.

    ![Panneau GAM Ajouter une stratégie](../media/AppManagement/mam-lob-apps-1.png)

2.  Cliquez sur **Autres applications**, entrez l’**ID d’offre groupée** (pour iOS) ou l’**ID de package** (pour Android), puis cliquez sur Sélectionner pour ajouter vos applications métier.

    ![Panneau GAM Autres applications](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a>Pour ajouter des applications métier (Windows)

> [!IMPORTANT]
> Vous devez sélectionner Windows 10 dans la liste déroulante de plateforme lors de la création d’une stratégie de protection des applications.

1.  Dans le panneau Ajouter une stratégie, choisissez **Applications autorisées** ou **Applications exemptes** pour ouvrir le panneau du même nom.

    > [!NOTE]
    >
    - **Applications autorisées** : il s’agit des applications qui doivent se conformer à cette stratégie.
    - **Applications exemptes** : ces applications sont exemptes de cette stratégie et peuvent accéder aux données d’entreprise sans restrictions.
<br></br>
2. Dans le panneau Applications autorisées ou Applications exemptes, cliquez sur **Ajouter des applications**. Vous pouvez ajouter des applications Microsoft recommandées ou ajouter des applications de bureau ou de Store.

    a.  **Applications recommandées :** liste préremplie d’applications (principalement Office) que les administrateurs peuvent facilement importer dans la stratégie.

    b.  **Applications du Store :** l’administrateur peut ajouter n’importe quelle application du Windows Store à la stratégie.

    c.  **Applications de bureau Windows :** l’administrateur peut ajouter n’importe quelle application de bureau Windows traditionnelle à la stratégie (par exemple exe, dll, etc.)

## <a name="deploy-a-policy-to-users"></a>Déployer une stratégie sur les utilisateurs

1.  Dans le panneau **Stratégie**, choisissez **Groupes d’utilisateurs** pour ouvrir le panneau **Groupes d’utilisateurs**. Choisissez **Ajouter un groupe d’utilisateurs** dans le panneau **Groupes d’utilisateurs** pour ouvrir le panneau **Ajouter un groupe d’utilisateurs**.

    ![Capture d’écran du panneau Groupes d’utilisateurs avec l’option de menu Ajouter un groupe d’utilisateurs mise en surbrillance](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  Une liste de groupes d’utilisateurs s’affiche sur le panneau **Ajouter un groupe d’utilisateurs** . Il s’agit de la liste de tous les groupes de sécurité figurant dans **Azure Active Directory**. Sélectionnez les groupes d’utilisateurs auxquels vous souhaitez appliquer cette stratégie, puis choisissez **Sélectionner**. Si vous choisissez **Sélectionner**, la stratégie est déployée pour les utilisateurs.

    ![Capture d’écran du panneau Ajouter un groupe d’utilisateurs montrant la liste des utilisateurs Azure Active Directory](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    Vous avez créé une stratégie et l’avez déployée pour les utilisateurs.

Seuls les utilisateurs en possession de licences Intune sont affectés par la stratégie. Les utilisateurs figurant dans le groupe de sécurité que vous avez sélectionné et qui n’ont pas de licence Intune ne sont pas affectés.

>[!IMPORTANT]
> Si vous utilisez Intune avec Configuration Manager pour gérer vos appareils iOS et Android, la stratégie est appliquée uniquement aux utilisateurs figurant directement dans le groupe que vous avez sélectionné. Les membres des groupes enfants imbriqués dans le groupe que vous avez sélectionné ne sont pas affectés.

Les utilisateurs finaux peuvent télécharger les applications à partir de l’App Store ou de Google Play. Pour plus d'informations, voir :
* [Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application](/intune/end-user-mam-apps-android)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a>Modifier des stratégies existantes
Vous pouvez modifier une stratégie existante et l’appliquer aux utilisateurs ciblés. Toutefois, quand vous modifiez des stratégies existantes, les utilisateurs déjà connectés aux applications ne voient pas les modifications pendant une période de huit heures.

Pour voir immédiatement l’effet des modifications, l’utilisateur final doit se déconnecter de l’application et se reconnecter.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Pour modifier la liste des applications associées à la stratégie

1.  Dans le panneau **Stratégie d’application**, choisissez la stratégie à modifier. Cette opération ouvre un panneau spécifique à la stratégie que vous venez de sélectionner.

    ![Capture d’écran d’une stratégie existante ouverte dans un panneau distinct](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Dans le panneau de la stratégie, choisissez **Applications ciblées** pour afficher la liste des applications.

3.  Supprimez ou ajoutez des applications dans la liste et choisissez l’icône **Enregistrer** pour enregistrer les modifications.

### <a name="to-change-the-list-of-user-groups"></a>Pour modifier la liste des groupes d’utilisateurs

1.  Dans le panneau **Stratégie d’application**, choisissez la stratégie à modifier. Cette opération ouvre le panneau spécifique à la stratégie que vous avez sélectionnée.

2.  Dans le panneau de la stratégie, choisissez **Groupes d’utilisateurs** pour ouvrir le panneau **Groupe d’utilisateurs** contenant la liste des groupes d’utilisateurs actuels qui ont cette stratégie.

3.  Pour ajouter un nouveau groupe d’utilisateurs à la stratégie, choisissez **Ajouter un groupe d’utilisateurs**, puis sélectionnez le groupe d’utilisateurs. Choisissez **Sélectionner** pour déployer la stratégie pour le groupe que vous avez sélectionné.

    ![Capture d’écran du panneau Ajouter un groupe d’utilisateurs avec deux groupes d’utilisateurs sélectionnés](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  Pour supprimer un groupe d’utilisateurs, mettez-le en surbrillance. Choisissez ensuite le bouton de sélection (...), puis choisissez **Supprimer** pour supprimer le groupe d’utilisateurs.

    ![Capture d’écran montrant l’option Supprimer ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a>Pour modifier les paramètres d’une stratégie

1.  Dans le panneau **Stratégie d’application**, choisissez la stratégie à modifier. Cette opération ouvre un panneau spécifique à la stratégie que vous venez de sélectionner.

    ![Capture d’écran d’une stratégie existante ouverte dans un panneau distinct ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  Choisissez **Paramètres de stratégie** pour ouvrir le panneau **Paramètres de stratégie**.

3.  Modifiez les paramètres, puis choisissez l’icône **Enregistrer** pour enregistrer les modifications.

    ![Capture d’écran du panneau Paramètres de stratégie montrant l’option de menu Enregistrer en haut](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a>Paramètres de stratégie
Pour afficher la liste complète des paramètres de stratégie pour iOS et Android, sélectionnez l’un des éléments suivants :

> [!div class="op_single_selector"]
- [Stratégies iOS](ios-mam-policy-settings.md)
- [Stratégies Android](android-mam-policy-settings.md)

## <a name="next-steps"></a>Étapes suivantes
[Surveiller l’état de la conformité et des utilisateurs](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Voir aussi
* [Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application](/intune/end-user-mam-apps-android)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application](/intune/end-user-mam-apps-ios)
