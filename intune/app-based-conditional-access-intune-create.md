---
title: "Stratégie d’accès conditionnel basée sur l’application avec Intune"
description: "Cette rubrique décrit comment configurer une stratégie d’accès conditionnel basée sur l’application avec Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Configurer des stratégies d’accès conditionnel basées sur l’application

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique fournit des instructions sur la façon de configurer des stratégies d’accès conditionnel basées sur l’application pour les applications qui figurent sur la liste des applications approuvées. La liste des applications approuvées se compose d’applications ayant été testées par Microsoft.

> [!IMPORTANT]
> Cette rubrique décrit les étapes permettant d’ajouter une stratégie d’accès conditionnel basée sur l’application à l’aide d’Exchange Online, mais vous pouvez utiliser les mêmes étapes lors de l’ajout d’autres applications telles que SharePoint Online, Microsoft Teams, et ainsi de suite, à partir de la liste des applications approuvées.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Pour créer une stratégie d’accès conditionnelle basée sur l’application
1.  Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification.

2.  Choisissez **Plus de services** et tapez « Intune ».

3.  Choisissez **Protection des applications Intune**.

4.  Dans le panneau **Gestion des applications mobiles Intune**, choisissez **Tous les paramètres**.

5.  Dans la section **Accès conditionnel**, choisissez **Exchange Online**.

    ![Capture d’écran du panneau des paramètres présentant la section de l’accès conditionnel avec l’option Exchange Online mise en surbrillance](./media/MAM-conditional-access-1.png)

6. Dans le panneau **Applications autorisées**, choisissez l’option **Autoriser les applications qui prennent en charge les stratégies d’application Intune** pour autoriser uniquement les applications prises en charge par les stratégies de protection des applications Intune à accéder à Exchange Online. Quand vous sélectionnez cette option, la liste des applications prises en charge s’affiche.

    > [!NOTE]
    > Aucun des clients de messagerie Exchange Active Sync, y compris les clients de messagerie intégrés sur iOS et Android qui se connectent à Exchange Online, ne pourra envoyer ou recevoir des e-mails. Les utilisateurs recevront à la place un simple e-mail les informant qu’ils doivent utiliser l’application de messagerie Outlook.

7. Pour appliquer cette stratégie aux utilisateurs, ouvrez le panneau **Groupes d’utilisateurs restreints**, puis choisissez **Ajouter un groupe d’utilisateurs**. Sélectionnez un ou plusieurs groupes d’utilisateurs devant obtenir cette stratégie.

    ![Capture d’écran du panneau Groupes d’utilisateurs restreints avec l’option Ajouter un groupe d’utilisateurs mise en surbrillance](./media/mam-ca-add-user-group.png)

8. Vous souhaiterez peut-être que certains utilisateurs du groupe d’utilisateurs que vous avez sélectionné à l’étape précédente ne soient pas affectés par cette stratégie. Dans ce cas, ajoutez le groupe d’utilisateurs à la liste des groupes d’utilisateurs exemptés. Dans le panneau **Exchange Online**, choisissez **Groupes d’utilisateurs exemptés**. Choisissez **Ajouter un groupe d’utilisateurs** pour ouvrir la liste des groupes d’utilisateurs. Sélectionnez les groupes que vous souhaitez exclure de cette stratégie.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Pour modifier ou supprimer des groupes d’utilisateurs d’une stratégie d’accès conditionnel basé sur l’application existante

1. Ouvrez le panneau **Groupes d’utilisateurs restreints**, puis mettez en surbrillance le groupe d’utilisateurs que vous souhaitez supprimer.
2. Cliquez sur l’ellipse pour afficher les options de suppression.
3. Choisissez **Supprimer** pour supprimer le groupe d’utilisateurs de la liste.

## <a name="next-steps"></a>Étapes suivantes
[Bloquer les applications sans authentification moderne](app-modern-authentication-block.md)

### <a name="see-also"></a>Voir aussi

[Protéger les données d’application à l’aide de stratégies de protection des applications](app-protection-policies.md)
