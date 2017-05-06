---
title: "Créer et déployer des stratégies de protection d’applications"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez comment les stratégies de protection d’application Intune peuvent vous aider à protéger les données utilisées par les applications que vous gérez."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 0aabb7af82bc7c9ed55eca91e615bace5e299d11
ms.lasthandoff: 04/24/2017

---

# <a name="how-to-create-and-assign-app-protection-policies"></a>Guide pratique de gestion et affectation des stratégies de protection des applications

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

**Si vous n’êtes pas dans le service Intune dans le programme de préversion du portail Azure**, cette rubrique explique [comment créer des stratégies de protection d’application](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) dans la console Intune classique.

Les stratégies de protection d'application peuvent être appliquées à des applications qui s’exécutent sur des appareils gérés ou non par Intune. Pour une description plus détaillée du fonctionnement des stratégies de protection d’application et les scénarios pris en charge par les stratégies de protection d’application Intune, consultez [Nouveautés des stratégies de protection d’application Microsoft Intune](what-is-app-protection-policy.md).

##  <a name="create-an-app-protection-policy"></a>Créer une stratégie de protection des applications
1.  Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Stratégies de protection d’application**.

2.  Cette opération ouvre le panneau **Stratégies de protection d’application** dans lequel vous allez créer des stratégies et modifier des stratégies existantes. Choisissez **Ajouter une stratégie**.

  ![Capture d’écran du panneau Ajouter une stratégie](../media/app-protection-add-policy.png)

3.  Tapez un nom pour la stratégie, ajoutez une brève description et sélectionnez le type de plateforme de manière à créer une stratégie pour iOS ou Android. Vous pouvez créer plusieurs stratégies pour chaque plateforme.

4.  Choisissez **Applications** pour ouvrir le panneau **Applications** qui contient la liste des applications disponibles. Dans cette liste, sélectionnez une ou plusieurs applications à associer à la stratégie que vous créez. Une fois que vous avez sélectionné les applications, choisissez **Sélectionner** au bas du panneau **Applications** pour enregistrer votre sélection.

    > [!IMPORTANT]
    > Vous devez sélectionner au moins une application pour créer une stratégie.

5.  Dans le panneau **Ajouter une stratégie**, choisissez **Configurer les paramètres requis** pour ouvrir le panneau des paramètres de stratégie.

    Il existe deux catégories de paramètres de stratégie : **Réadressage des données** et **Accès**.  Les stratégies de réadressage des données sont applicables au déplacement des données vers l’intérieur et l’extérieur des applications, tandis que les stratégies d’accès déterminent comment l’utilisateur final accède aux applications dans un contexte de travail.
    Pour bien démarrer, les paramètres de stratégie sont définis par défaut. Il est inutile d’apporter des modifications si les valeurs par défaut répondent à vos besoins.

    > [!TIP]
    > Ces paramètres de stratégie sont appliqués uniquement quand vous utilisez des applications dans le contexte de travail.  Quand l’utilisateur final utilise l’application pour effectuer une tâche personnelle, il n’est pas affecté par ces stratégies.



6.  Choisissez **OK** pour enregistrer cette configuration. Vous êtes maintenant de retour dans le panneau **Ajouter une stratégie** . Choisissez **Créer** pour créer la stratégie et enregistrer vos paramètres.


Quand vous avez fini de créer une stratégie comme décrit dans la procédure précédente, elle n’est pas déployée sur les utilisateurs. Pour déployer une stratégie, consultez la section suivante, « Déployer une stratégie sur les utilisateurs ».

## <a name="deploy-a-policy-to-users"></a>Déployer une stratégie sur les utilisateurs

1.  Dans le panneau **Stratégie**, choisissez **Groupes d’utilisateurs** pour ouvrir le panneau **Groupes d’utilisateurs**. Choisissez **Ajouter un groupe d’utilisateurs** dans le panneau **Groupes d’utilisateurs** pour ouvrir le panneau **Ajouter un groupe d’utilisateurs**.

  ![Capture d’écran du panneau Groupes d’utilisateurs avec l’option de menu Ajouter un groupe d’utilisateurs mise en surbrillance](../media/app-protection-policy-add-users.png)

2.  Une liste de groupes d’utilisateurs s’affiche sur le panneau **Ajouter un groupe d’utilisateurs** . Il s’agit de la liste de tous les groupes de sécurité figurant dans **Azure Active Directory**. Sélectionnez les groupes d’utilisateurs auxquels vous souhaitez appliquer cette stratégie, puis choisissez **Sélectionner**. Si vous choisissez **Sélectionner**, la stratégie est déployée pour les utilisateurs.
  ![Capture d’écran du panneau Ajouter un groupe d’utilisateurs présentant la liste des utilisateurs Azure Active Directory](../media/azure-ad-user-group-list.png)

Vous avez créé une stratégie et l’avez déployée pour les utilisateurs.

Seuls les utilisateurs en possession de licences Microsoft Intune sont affectés par la stratégie. Les utilisateurs figurant dans le groupe de sécurité que vous avez sélectionné et qui n’ont pas de licence Microsoft Intune ne sont pas affectés.

>[!IMPORTANT]
> Si vous utilisez Intune avec Configuration Manager pour gérer vos appareils iOS et Android, la stratégie est appliquée uniquement aux utilisateurs figurant directement dans le groupe que vous avez sélectionné. Les membres des groupes enfants imbriqués dans le groupe que vous avez sélectionné ne sont pas affectés.

Les utilisateurs finaux peuvent télécharger les applications à partir de l’App Store ou de Google Play. Pour plus d'informations, voir :
* [Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application](app-protection-enabled-android-apps.md)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application](app-protection-enabled-ios-apps.md)

##  <a name="change-existing-policies"></a>Modifier des stratégies existantes
Vous pouvez modifier une stratégie existante et l’appliquer aux utilisateurs ciblés. Toutefois, quand vous modifiez des stratégies existantes, les utilisateurs déjà connectés aux applications ne voient pas les modifications pendant une période de huit heures.

Pour voir immédiatement l’effet des modifications, l’utilisateur final doit se déconnecter de l’application et se reconnecter.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>Pour modifier la liste des applications associées à la stratégie

1.  Dans le panneau **Stratégie d’application**, choisissez la stratégie à modifier. Cette opération ouvre un panneau spécifique à la stratégie que vous venez de sélectionner.

2.  Dans le panneau de la stratégie, choisissez **Applications ciblées** pour afficher la liste des applications.

3.  Supprimez ou ajoutez des applications dans la liste et choisissez l’icône **Enregistrer** pour enregistrer les modifications.

### <a name="to-change-the-list-of-user-groups"></a>Pour modifier la liste des groupes d’utilisateurs

1.  Dans le panneau **Stratégie d’application**, choisissez la stratégie à modifier. Cette opération ouvre le panneau spécifique à la stratégie que vous avez sélectionnée.

2.  Dans le panneau de la stratégie, choisissez **Groupes d’utilisateurs** pour ouvrir le panneau **Groupe d’utilisateurs** contenant la liste des groupes d’utilisateurs actuels qui ont cette stratégie.

3.  Pour ajouter un nouveau groupe d’utilisateurs à la stratégie, choisissez **Ajouter un groupe d’utilisateurs**, puis sélectionnez le groupe d’utilisateurs. Choisissez **Sélectionner** pour déployer la stratégie pour le groupe que vous avez sélectionné.

4.  Pour supprimer un groupe d’utilisateurs, mettez-le en surbrillance. Choisissez ensuite le bouton de sélection (...), puis choisissez **Supprimer** pour supprimer le groupe d’utilisateurs.
  ![Capture d’écran montrant l’option Supprimer](../media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>Pour modifier les paramètres d’une stratégie

1.  Dans le panneau **Stratégie d’application**, choisissez la stratégie à modifier. Cette opération ouvre un panneau spécifique à la stratégie que vous venez de sélectionner.


2.  Choisissez **Paramètres de stratégie** pour ouvrir le panneau **Paramètres de stratégie**.

3.  Modifiez les paramètres, puis choisissez l’icône **Enregistrer** pour enregistrer les modifications.

## <a name="policy-settings"></a>Paramètres de stratégie
Pour afficher la liste complète des paramètres de stratégie pour iOS et Android, sélectionnez l’un des éléments suivants :

> [!div class="op_single_selector"]
- [Stratégies iOS](ios-app-protection-policy-settings.md)
- [Stratégies Android](android-app-protection-policy-settings.md)

## <a name="next-steps"></a>Étapes suivantes
[Surveiller l’état de la conformité et des utilisateurs](monitor-app-protection-policies-with-microsoft-intune.md)

### <a name="see-also"></a>Voir aussi
* [Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application](app-protection-enabled-android-apps.md)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application](app-protection-enabled-ios-apps.md)

