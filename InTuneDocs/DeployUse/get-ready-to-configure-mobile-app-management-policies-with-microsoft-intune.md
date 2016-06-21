---
# required metadata

title: Se préparer à configurer des stratégies de gestion des applications mobiles | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Se préparer à configurer des stratégies de gestion des applications mobiles avec Microsoft Intune
Cette rubrique décrit ce que vous devez faire avant de pouvoir créer des stratégies de gestion des applications mobiles (GAM) dans le portail Azure.

Le portail Azure est la nouvelle console d’administration permettant de créer des stratégies de gestion des applications mobiles (GAM) et nous vous recommandons de l’utiliser pour créer ces stratégies. Le portail Azure prend en charge les scénarios GAM suivants :
- Appareils inscrits dans Intune
- Appareils gérés par une solution de gestion des appareils mobiles tierce
- Appareils qui ne sont gérés par aucune solution de gestion des appareils mobiles (BYOD).

Si vous ne connaissez pas le portail Azure, lisez la rubrique [Portail Azure pour les stratégies de gestion des applications mobiles Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) pour bénéficier d’un aperçu rapide.

Si vous utilisez actuellement la **console d’administration Intune** pour gérer vos appareils, vous pouvez créer des stratégies de gestion des applications mobiles qui prennent en charge des applications pour les appareils inscrits dans Intune à l’aide de la **console d’administration Intune**, mais il est recommandé d’utiliser le portail Azure même pour les appareils inscrits dans Intune. Pour obtenir des instructions sur la création d’une stratégie GAM à l’aide de la console d’administration Intune, cliquez [ici](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

>[!IMPORTANT]
> La console d’administration Intune peut ne pas afficher tous les paramètres de stratégie de gestion des applications mobiles. Si vous créez ces stratégies à la fois sur la console d’administration Intune et le portail Azure, la stratégie dans le portail Azure est appliquée aux applications et déployée sur les utilisateurs.


##  Plateformes prises en charge
- iOS 8.1 ou version ultérieure

- Android 4 ou version ultérieure

##  Applications prises en charge
* **Applications Microsoft :** ces applications intègrent le SDK de l’application Intune et ne nécessitent aucun traitement supplémentaire avant d’appliquer les stratégies GAM.
Pour afficher la liste complète des applications Microsoft prises en charge, accédez à la [Galerie d’applications mobiles Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) dans la page des partenaires d’application Microsoft Intune. Cliquez sur l’application pour afficher les scénarios pris en charge, connaître les plateformes et savoir si elle prend en charge plusieurs identités.
* Vos **applications métier** internes : vous devez préparer les applications pour inclure le SDK de l’application Intune avant de pouvoir appliquer les stratégies GAM.

  * Pour les appareils gérés par Intune, consultez [Décider comment préparer les applications pour la gestion des applications mobiles](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
  * Pour les appareils qui ne sont pas gérés comme des appareils appartenant à un employé ou pour les appareils qui sont gérés par une solution tierce de gestion des appareils mobiles, consultez [Protéger les données et applications métier sur les appareils non inscrits dans Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

**Avant** de pouvoir configurer des stratégies GAM, vous avez besoin des éléments suivants :

-   **Un abonnement à Microsoft Intune**.    Les utilisateurs finaux ont besoin de licences [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour obtenir des applications avec une stratégie GAM.

-   Un abonnement **Office 365 (O365)** nécessaire pour :
  - Appliquer des stratégies GAM aux applications prenant en charge plusieurs identités.
  - Créer des comptes professionnels SharePoint Online et Exchange Online. Exchange et SharePoint en local ne sont pas pris en charge.
-    **Authentification moderne activée** pour **Skype Entreprise Online**. Connectez-vous à Microsoft Connect et remplissez [ce formulaire](https://connect.microsoft.com/office/Survey/NominationSurvey.aspx?SurveyID=17299&ProgramID=8715) pour vous inscrire au programme d’authentification moderne.


- **Azure Active Directory (Azure AD)** pour créer des utilisateurs. Azure AD authentifie l’utilisateur final quand il lance l’application et entre ses informations d’identification professionnelles.

    > [!NOTE] Si vous configurez des utilisateurs à l’aide de la console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], n’oubliez pas que la configuration de la stratégie GAM figure désormais sur le portail Azure et que pour utiliser ce portail vous devez configurer des groupes d’utilisateurs Azure AD à l’aide du portail Office 365.


## Créer des utilisateurs et attribuer des licences Microsoft Intune

1. Vous avez besoin d’un abonnement Intune : vous disposez déjà d’un abonnement [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] si vous utilisez actuellement [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour gérer vos appareils.  Vous disposez également d’un abonnement [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] si vous avez acheté une licence EMS. Si vous essayez [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour tester les fonctionnalités de gestion des applications mobiles, vous pouvez obtenir un compte d’évaluation [ici](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Pour vérifier si vous avez un abonnement [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dans le portail Office, accédez à la page Facturation.  Vous devez voir **Actif** apparaître pour [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] sous les abonnements.

2.  Connectez-vous au   [portail Office](http://portal.office.com) à l’aide de vos informations d’identification d’administrateur.

3.  Accédez à la page **Utilisateurs actifs** pour ajouter des utilisateurs et attribuer des licences [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Page d’ajout d’utilisateurs du portail Office](../media/AppManagement/OfficePortal_AddUsers.png)

4.  Pour permettre à un utilisateur d’accéder au portail Office, au portail Azure AD et au portail Azure, affectez-lui le **rôle d’administrateur général**.

    ![Capture d’écran du portail Office affichant la page Utilisateurs actifs ](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  Les stratégies de gestion des applications mobiles sont déployées pour des groupes d’utilisateurs dans Azure Active Directory. Pour créer des groupes d’utilisateurs à utiliser pour vos stratégies GAM, accédez à la page **Groupes** du **portail Office** et cliquez sur l’icône **+** pour créer un groupe de sécurité.  Tapez un nom et une description, puis cliquez sur **Créer**. Quand le groupe est créé, vous pouvez ajouter des utilisateurs au groupe en cliquant sur **Modifier les membres** dans le groupe de sécurité nouvellement créé. Le groupe de sécurité est créé dans Azure Active Directory.

    ![Capture d’écran de la page illustrant la sélection du rôle d’administrateur général dans la page Edit user roles (Modifier les rôles d’utilisateur)](../media/AppManagement/OfficePortal_CreateGroups.png)

Le tableau suivant répertorie les rôles et autorisations que vous pouvez attribuer aux utilisateurs administrateurs.

|||
|--|----|
|**Rôle**|**Autorisations**|
|Administrateur général (portail O365)|Accès au portail O365, et au portail Azure AD<br /><br />Accès au portail Azure (permet d’effectuer à la fois des tâches de gestion de rôles et d’applications mobiles).|
|Rôle de propriétaire (portail Azure)|Accès au portail Azure (permet d’effectuer à la fois des tâches de gestion de rôles et d’applications mobiles).|
|Rôle de collaborateur (portail Azure)|Accès au portail Azure (permet uniquement d’effectuer des tâches de gestion d’applications mobiles).|

## Affecter le rôle de collaborateur à un utilisateur

Les **administrateurs généraux** ont accès au [portail Azure](https://portal.azure.com).  Si vous voulez que d’autres utilisateurs administrateurs puissent configurer des stratégies et effectuer d’autres tâches de gestion des applications mobiles, vous pouvez leur affecter le **rôle de collaborateur** comme décrit ci-dessous :


1.  Dans le panneau **Paramètres**, dans la section **Gestion des ressources**, cliquez sur **Utilisateurs**.

    ![Capture d’écran du panneau Utilisateurs dans le portail Azure](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Cliquez sur **Ajouter** pour ouvrir le panneau **Ajouter un accès** .

3.  Cliquez sur **Sélectionner un rôle**, puis sur **Rôle Collaborateur**.

    ![Capture d’écran du panneau Sélectionner un rôle dans le portail Azure](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Une fois que vous avez sélectionné le rôle, cliquez sur **Ajouter un utilisateur**, puis recherchez l’utilisateur par son nom ou son adresse électronique. Les utilisateurs qui figurent dans cette liste sont les 1 000 premiers utilisateurs que vous avez créés précédemment dans Azure AD à l’aide du portail Office. Cliquez sur **OK** dans le panneau **Ajouter un accès** pour enregistrer et attribuer le rôle à l’utilisateur.

    ![Capture d’écran du panneau Ajouter des utilisateurs dans le portail Azure](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT] Si vous sélectionnez un utilisateur qui n’a pas de licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], il ne pourra pas accéder au portail.

## Étapes suivantes
[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=Jun16_HO1-->


