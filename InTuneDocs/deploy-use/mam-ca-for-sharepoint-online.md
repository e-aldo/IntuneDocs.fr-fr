---
title: "Configurer l’accès aux applications pour SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 992273f88e4bbe234f11f936d6416dbaf0d394e9
ms.lasthandoff: 04/19/2017


---

# <a name="create-a-sharepoint-online-conditional-access-policy-to-only-allow-apps-supported-by-mam"></a>Créer une stratégie d’accès conditionnel à SharePoint Online pour autoriser uniquement les applications prises en charge par la gestion des applications mobiles
Cette rubrique fournit des instructions étape par étape pour configurer l’accès conditionnel pour Exchange Online afin d’autoriser uniquement les applications mobiles qui prennent en charge les stratégies de gestion des applications mobiles (GAM).

## <a name="configure-a-sharepoint-online-policy"></a>Configurer une stratégie SharePoint Online
**Étape 1 :** connectez-vous au [portail Azure](https://portal.azure.com) qui inclut la fonctionnalité d’accès aux applications. Si vous n’avez pas l’habitude d’utiliser le portail Azure, lisez la rubrique [Portail Azure pour les stratégies de gestion des appareils mobiles](azure-portal-for-microsoft-intune-mam-policies.md).

**Étape 2 :** choisissez **Parcourir > Intune > panneau Gestion des applications mobiles Intune > Paramètres** et, dans la section **Accès conditionnel**, choisissez **SharePoint Online**.

![Capture d’écran du panneau Paramètres affichant la section relative à l’accès conditionnel avec panneau SharePoint Online ouvert](../media/mam-ca-settings-spo.png)

**Étape 3 :** dans le panneau **Applications autorisées**, choisissez l’option **Autoriser les applications qui prennent en charge les stratégies d’application Intune** pour autoriser uniquement les applications prises en charge par les stratégies GAM Intune à accéder à SharePoint Online. Lorsque vous sélectionnez l’option qui autorise uniquement les applications prises en charge par les stratégies GAM Intune, la liste des applications prises en charge s’affiche.

![Capture d’écran du panneau des applications autorisées montrant la liste des applications](../media/mam-ca-spo-allowed-apps.png)

**Étape 4 :** pour appliquer cette stratégie aux utilisateurs, ouvrez le panneau **Groupes d’utilisateurs restreints**, puis choisissez **Ajouter un groupe d’utilisateurs**. Sélectionnez un ou plusieurs groupes d’utilisateurs devant obtenir cette stratégie.

![Capture d’écran du panneau Groupes d’utilisateurs restreints avec l’option Ajouter un groupe d’utilisateurs mise en surbrillance](../media/mam-ca-spo-restricted-groups.png)


**Étape 5 :** vous souhaiterez peut-être que certains utilisateurs du groupe d’utilisateurs que vous avez sélectionné à l’étape précédente ne soient pas affectés par cette stratégie. Dans ce cas, ajoutez le groupe d’utilisateurs à la liste des groupes d’utilisateurs exemptés. Dans le panneau **SharePoint Online**, choisissez **Groupes d’utilisateurs exemptés**. Choisissez **Ajouter un groupe d’utilisateurs** pour ouvrir la liste des groupes d’utilisateurs. Sélectionnez les groupes que vous souhaitez exclure de cette stratégie.  

## <a name="modifying-an-existing-policy"></a>Modifier une stratégie existante
### <a name="adding-or-deleting-user-groups"></a>Ajouter ou supprimer des groupes d’utilisateurs
Pour **supprimer un groupe d’utilisateurs** de la liste **Groupes d’utilisateurs restreints**, ouvrez le panneau Groupes d’utilisateurs restreints, mettez en surbrillance le groupe d’utilisateurs que vous souhaitez supprimer, puis cliquez sur l’ellipse (...) pour voir l’option Supprimer. Choisissez **Supprimer** pour supprimer le groupe d’utilisateurs de la liste. Vous pouvez suivre la même procédure pour supprimer un groupe d’utilisateurs de la liste **Groupes d’utilisateurs exemptés**.


## <a name="next-steps"></a>Étapes suivantes
[Configurer l’accès aux applications pour Exchange Online](mam-ca-for-exchange-online.md)

[Bloquer les applications sans authentification moderne](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Voir aussi

[Protéger les données d’application avec des stratégies GAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

