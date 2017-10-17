---
title: "Créer une stratégie d’accès conditionnel basé sur l’application pour SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 4183df8e8ed982e7aba2d55d82923564f215ad53
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>Configurer des stratégies d’accès conditionnel basé sur l’application pour SharePoint Online

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Cette rubrique fournit des conseils sur la façon de configurer une stratégie d’accès conditionnel basé sur l’application pour SharePoint Online. L’accès conditionnel basé sur l’application permet aux administrateurs d’autoriser uniquement les applications mobiles auxquelles des stratégies de protection des applications Intune sont appliquées.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>Pour créer la stratégie d’accès conditionnel basé sur l’application pour SharePoint Online

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification.

    > [!NOTE]
    > Si vous n’avez pas l’habitude d’utiliser le portail Azure, lisez la rubrique [Portail Azure pour les stratégies de protection des applications](azure-portal-for-microsoft-intune-mam-policies.md).

2. Choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

3. Choisissez **Protection des applications Intune** > **Gestion des applications mobiles Intune** > **Tous les paramètres**.

4. Dans le panneau Gestion des applications mobiles Intune, choisissez la vignette SharePoint Online.

5. Dans le panneau **Applications autorisées**, choisissez l’option **Autoriser les applications qui prennent en charge les stratégies d’application Intune** pour autoriser uniquement les applications prises en charge par les stratégies de protection des applications Intune.

    > [!NOTE] 
    > Quand vous sélectionnez l’option qui autorise uniquement les applications prises en charge par les stratégies de protection des applications Intune, une liste contenant **uniquement** les applications prises en charge est affichée.

    ![Capture d’écran du panneau des applications autorisées montrant la liste des applications](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>Pour affecter des stratégies d’accès conditionnel basé sur l’application à vos utilisateurs

1. Ouvrez le panneau **Groupes d’utilisateurs restreints**, puis choisissez **Ajouter un groupe d’utilisateurs**.

2. Sélectionnez un ou plusieurs groupes d’utilisateurs devant obtenir cette stratégie.

    ![Capture d’écran du panneau Groupes d’utilisateurs restreints avec l’option Ajouter un groupe d’utilisateurs mise en surbrillance](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Vous souhaiterez peut-être que certains utilisateurs du groupe d’utilisateurs que vous avez sélectionné à l’étape précédente ne soient pas affectés par cette stratégie. Dans ce cas, ajoutez le groupe d’utilisateurs à la liste des groupes d’utilisateurs exemptés. 

3. Dans le panneau **SharePoint Online**, choisissez **Groupes exemptés**, puis **Ajouter un groupe d’utilisateurs** pour ouvrir la liste des groupes d’utilisateurs.

4. Sélectionnez les groupes que vous souhaitez exclure de cette stratégie.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Pour modifier ou supprimer des groupes d’utilisateurs d’une stratégie d’accès conditionnel basé sur l’application existante

1. Ouvrez le panneau **Groupes d’utilisateurs restreints**, puis mettez en surbrillance le groupe d’utilisateurs que vous souhaitez supprimer.
2. Cliquez sur l’ellipse pour afficher les options de suppression.
3. Choisissez **Supprimer** pour supprimer le groupe d’utilisateurs de la liste.

> [!NOTE] 
> Vous pouvez suivre la même procédure pour supprimer un groupe d’utilisateurs de la liste **Groupes exemptés**.

## <a name="next-steps"></a>Étapes suivantes

[Bloquer les applications qui n’utilisent pas l’authentification moderne](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Voir aussi

[Protéger les données d’application à l’aide de stratégies de protection des applications](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Configurer l’accès conditionnel basé sur l’application pour Exchange Online](mam-ca-for-exchange-online.md)
