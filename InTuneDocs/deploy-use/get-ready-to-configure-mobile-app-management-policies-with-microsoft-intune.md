---
title: "Conditions préalables pour les stratégies de gestion des applications mobiles | Microsoft Intune"
description: "Cette rubrique décrit les prérequis pour la configuration des utilisateurs avant de pouvoir créer des stratégies de gestion des applications mobiles."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: ac820146d81fb121a60f7029f6a52a0056d6ab0a


---

# <a name="get-ready-to-configure-mobile-app-management-policies-on-the-azure-portal"></a>Se préparer à configurer des stratégies de gestion des applications mobiles sur le portail Azure
Cette rubrique décrit les conditions préalables et les étapes que vous devez effectuer **avant** de pouvoir créer des stratégies de gestion des applications mobiles dans le portail Azure.

Pour comprendre comment les stratégies GAM Intune peuvent protéger les données de votre entreprise, consultez [Protéger les applications et les données à l’aide des stratégies de gestion des applications mobiles](protect-apps-and-data-with-microsoft-intune.md).

## <a name="what-is-the-azure-portal"></a>Qu’est-ce que le portail Azure ?

Le portail Azure est la nouvelle console d’administration pour créer des stratégies de gestion des applications mobiles. Il prend en charge les scénarios GAM suivants :
- Appareils mobiles inscrits dans Intune
- Appareils gérés par une autre solution de gestion des appareils mobiles
- Appareils qui ne sont gérés par aucune solution de gestion des appareils mobiles (BYOD)

À l’heure actuelle, la **console Administrateur Intune** et le **portail Azure** vous permettent de configurer des stratégies GAM.  Considérez les points suivants :

* Les stratégies que vous créez dans le **portail Azure** sont prises en charge pour **tous les scénarios GAM** répertoriés ci-dessus. La **console Administrateur Intune** prend uniquement en charge la création de stratégies pour les **appareils qui sont inscrits et gérés par Intune**.

* Tous les paramètres de stratégie GAM n’apparaissent pas forcément dans la console Administrateur Intune, car les **nouveaux paramètres** ne peuvent être ajoutés qu’au **portail Azure**.

* Si vous créez ces stratégies **à la fois** sur la console d’administration Intune et le portail Azure, la stratégie dans le **portail Azure est appliquée aux applications et déployée sur les utilisateurs**.
    * Les stratégies de gestion des applications mobiles créées dans la console d’administration Intune ne peuvent pas être importées dans le portail Azure.  Elles doivent être recréées dans le portail Azure.


* Les autres **fonctionnalités de gestion des applications**, telles que le déploiement d’applications et les stratégies de configuration d’application, ne sont disponibles que dans la **console Administrateur Intune**.


Si vous ne connaissez pas le portail Azure, consultez [Portail Azure pour les stratégies de gestion des applications mobiles Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) pour acquérir les bases de l’utilisation du portail Azure.

Pour obtenir des instructions sur la façon de créer une stratégie de gestion des applications mobiles dans la console d’administration Intune, consultez [Configurer et déployer des stratégies de gestion des applications mobiles dans la console Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Plateformes prises en charge
- iOS 8.1 ou version ultérieure
- Android 4 ou version ultérieure

>[!NOTE]
>Les appareils Windows ne prennent pas en charge ces stratégies de gestion des applications mobiles. Toutefois, quand vous inscrivez des appareils Windows 10 auprès d’Intune, vous pouvez utiliser la Protection des informations Windows, qui offre des fonctionnalités similaires. Pour plus d’informations, consultez [Protéger vos données d’entreprise à l’aide de la Protection des informations Windows (WIP)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Applications prises en charge
* **Applications Microsoft :** ces applications intègrent le Kit SDK d’application Intune et ne nécessitent aucun traitement supplémentaire avant d’appliquer les stratégies de gestion des applications mobiles.
Pour afficher la liste complète des applications Microsoft prises en charge, accédez à la [Galerie d’applications mobiles Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) dans la page des partenaires d’application Microsoft Intune. Cliquez sur l’application pour afficher les scénarios et les plateformes pris en charge et savoir si l’application prend en charge plusieurs identités.

* **Applications métier de votre organisation :** vous devez préparer ces applications pour inclure le SDK d’application Intune avant de pouvoir appliquer des stratégies de gestion des applications mobiles.

  * Pour les appareils gérés par Intune, consultez [Décider comment préparer les applications pour la gestion des applications mobiles](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

  * Pour les appareils qui ne sont pas gérés (comme les appareils appartenant aux employés) ou pour les appareils qui sont gérés par une autre solution de gestion des appareils mobiles, consultez [Protéger les données et applications métier sur les appareils non inscrits dans Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Conditions préalables

-   **Un abonnement Microsoft Intune**. Les utilisateurs ont besoin de licences [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour obtenir des applications avec une stratégie de gestion des applications mobiles.
Vous êtes déjà inscrit à [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] si vous utilisez actuellement [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour gérer vos appareils. Vous êtes également inscrit à [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] si vous avez acheté une licence Enterprise Mobility Suite (EMS). Si vous essayez [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour tester les fonctionnalités de gestion des applications mobiles, vous pouvez obtenir un compte d’essai sur la [page Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/).

    Pour vérifier si vous avez un abonnement à [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dans le portail Office, accédez à la page de **facturation**.  Si vous avez un abonnement, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] doit être indiqué comme **Actif** dans les abonnements.

-   **Un abonnement Office 365**, qui est nécessaire pour les opérations suivantes :

  - Appliquer des stratégies de gestion des applications mobiles aux applications prenant en charge plusieurs identités.

  - Créer des comptes professionnels SharePoint Online et Exchange Online. Les versions locales d’Exchange et de SharePoint ne sont pas prises en charge.

-   **Configuration de Skype Entreprise Online pour l’authentification moderne**. Pour en savoir plus, voir [Activer l’authentification moderne](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) pour créer des utilisateurs. Azure AD authentifie les utilisateurs lorsqu’ils ouvrent l’application et entrent leurs informations d’identification professionnelles.

    > [!NOTE]
    > Les groupes d’utilisateurs doivent être configurés dans Azure AD. Les groupes d’utilisateurs Intune ne peuvent pas être utilisés pour déployer des stratégies GAM dans le portail Azure.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Créer des utilisateurs et attribuer des licences Microsoft Intune

1.  Connectez-vous au [portail Office](http://portal.office.com) à l’aide de vos informations d’identification d’administrateur.

2.  Ajoutez des utilisateurs comme décrit dans la section **Étapes de l’exécution d’une version d’évaluation de 30 jours d’Intune** du [Guide d’évaluation de Microsoft Intune](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune), puis attribuez des licences Intune. Pour permettre à un utilisateur d’accéder au portail Office, au portail Azure AD et au portail Azure, affectez-lui le **rôle d’administrateur général**.

5.  Les stratégies de gestion des applications mobiles sont déployées pour des groupes d’utilisateurs dans Azure Active Directory. Pour créer des groupes d’utilisateurs pour vos stratégies GAM, créez un groupe d’utilisateurs comme décrit dans la section **Créer un groupe d’utilisateurs** de la rubrique [Créer des groupes pour organiser les utilisateurs et les appareils de l’abonnement à la version d’évaluation](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### <a name="assign-roles-to-non-global-admin-users"></a>Attribuer des rôles à des utilisateurs administrateurs non généraux

Les administrateurs généraux ont accès au [portail Azure](https://portal.azure.com).  Si vous voulez que les utilisateurs qui ne sont pas administrateurs généraux puissent configurer des stratégies et effectuer d’autres tâches de gestion des applications mobiles, vous pouvez leur affecter le rôle de collaborateur. Pour obtenir des instructions détaillées, consultez [Utiliser les attributions de rôle pour gérer l’accès à vos ressources d’abonnement Azure](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/).



Le tableau suivant répertorie les rôles et autorisations que vous pouvez attribuer aux utilisateurs administrateurs.



|||
|--|----|
|**Rôle**|**Autorisations**|
|Administrateur général (portail Office 365)|Accès au portail Office 365 et au portail Azure AD.<br /><br />Accès au portail Azure (permet d’effectuer à la fois des tâches de gestion de rôles et d’applications mobiles).|
|Propriétaire (portail Azure)|Accès au portail Azure (permet d’effectuer à la fois des tâches de gestion de rôles et d’applications mobiles).|
|Collaborateur (portail)|Accès au portail Azure (permet uniquement d’effectuer des tâches de gestion d’applications mobiles).|




## <a name="next-steps"></a>Étapes suivantes
[Créer et déployer des stratégies de gestion des applications mobiles à l’aide de Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


