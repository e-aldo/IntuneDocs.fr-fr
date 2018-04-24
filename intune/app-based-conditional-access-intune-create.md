---
title: Configurer une stratégie d’accès conditionnel basée sur l’application avec Intune
description: Découvrez comment créer une stratégie d’accès conditionnel basée sur l’application avec Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7e3654021935495189b62da5257793383586137
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Configurer des stratégies d’accès conditionnel basées sur des applications avec Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cet article décrit comment configurer des stratégies d’accès conditionnel basées sur des applications pour les applications qui figurent dans la liste des applications approuvées. La liste des applications approuvées se compose d’applications ayant été testées par Microsoft.

> [!IMPORTANT]
> Cet article décrit les étapes permettant d’ajouter une stratégie d’accès conditionnel basée sur l’application à l’aide d’Exchange Online, mais vous pouvez utiliser les mêmes étapes lors de l’ajout d’autres applications telles que SharePoint Online, Microsoft Teams, et ainsi de suite, à partir de la liste des applications approuvées.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Pour créer une stratégie d’accès conditionnelle basée sur l’application
1.  Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification.

2.  Choisissez **Tous les services** et tapez « Intune ».

3.  Choisissez **Protection des applications Intune**.

4.  Dans **Protection d’application Intune** sous la section **Accès conditionnel**, choisissez **Exchange Online**.

    ![Capture d’écran du volet des paramètres présentant la section de l’accès conditionnel avec l’option Exchange Online mise en surbrillance](./media/MAM-conditional-access-1.png)

6. Dans le volet **Applications autorisées**, choisissez l’option **Autoriser les applications qui prennent en charge les stratégies d’application Intune** pour autoriser uniquement les applications prises en charge par les stratégies de protection d’application Intune à accéder à Exchange Online. Quand vous sélectionnez cette option, la liste des applications prises en charge s’affiche.

    > [!NOTE]
    > Aucun des clients de messagerie Exchange Active Sync, notamment les clients de messagerie intégrés sur iOS et Android qui se connectent à Exchange Online, ne peut envoyer ou recevoir des e-mails. Les utilisateurs recevront à la place un simple e-mail les informant qu’ils doivent utiliser l’application de messagerie Outlook.

7. Pour appliquer cette stratégie aux utilisateurs, ouvrez le volet **Groupes d’utilisateurs restreints**, puis choisissez **Ajouter un groupe d’utilisateurs**. Sélectionnez un ou plusieurs groupes d’utilisateurs devant obtenir cette stratégie.

    ![Capture d’écran du volet Groupes d’utilisateurs restreints avec l’option Ajouter un groupe d’utilisateurs mise en surbrillance](./media/mam-ca-add-user-group.png)

8. Vous souhaiterez peut-être que certains utilisateurs du groupe d’utilisateurs que vous avez sélectionné à l’étape précédente ne soient pas affectés par cette stratégie. Dans ce cas, ajoutez le groupe d’utilisateurs à la liste des groupes d’utilisateurs exemptés. Dans le volet **Exchange Online**, choisissez **Groupes d’utilisateurs exemptés**. Choisissez **Ajouter un groupe d’utilisateurs** pour ouvrir la liste des groupes d’utilisateurs. Sélectionnez les groupes que vous souhaitez exclure de cette stratégie.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Pour modifier ou supprimer des groupes d’utilisateurs d’une stratégie d’accès conditionnel basé sur l’application existante

1. Ouvrez le volet **Groupes d’utilisateurs restreints**, puis mettez en surbrillance le groupe d’utilisateurs à supprimer.
2. Cliquez sur l’ellipse pour afficher les options de suppression.
3. Choisissez **Supprimer** pour supprimer le groupe d’utilisateurs de la liste.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Création de stratégies d’accès conditionnel basé sur l’application dans la charge de travail Azure AD

À compter d’Intune version 1708, les administrateurs informatiques peuvent créer des stratégies d’accès conditionnel basé sur l’application à partir de la charge de travail Azure AD. C’est plus pratique, car il n’est plus nécessaire de basculer entre les charges de travail Azure et Intune.

> [!IMPORTANT]
> Vous devez disposer d’une licence Azure AD Premium pour créer des stratégies d’accès conditionnel Azure AD à partir du portail Intune Azure.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Pour créer une stratégie d’accès conditionnelle basée sur l’application

> [!IMPORTANT]
> Les [stratégies de protection des applications Intune](app-protection-policies.md) doivent être appliquées à vos applications avant d’utiliser des stratégies d’accès conditionnel basé sur l’application.

1. Dans le **tableau de bord Intune**, choisissez **Accès conditionnel**.

2. Dans le volet **Stratégies**, choisissez **Nouvelle stratégie** pour créer votre stratégie d’accès conditionnel basé sur l’application.

4. Une fois que vous entrez un nom de stratégie et configuré les paramètres disponibles dans la section **Affectations**, choisissez **Octroyer** sous la section **Contrôles d’accès**.

5. Choisissez **Demander une application cliente approuvée** , **Sélectionner**, puis **Créer** pour enregistrer la nouvelle stratégie.

## <a name="next-steps"></a>Étapes suivantes
[Bloquer les applications sans authentification moderne](app-modern-authentication-block.md)

### <a name="see-also"></a>Voir aussi

[Protéger les données d’application à l’aide de stratégies de protection des applications](app-protection-policies.md)
[Accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
