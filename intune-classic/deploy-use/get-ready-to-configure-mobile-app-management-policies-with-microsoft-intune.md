---
title: Conditions préalables pour les stratégies de gestion des applications mobiles
description: Cette rubrique décrit les prérequis pour la configuration des utilisateurs avant de pouvoir créer des stratégies de gestion des applications mobiles.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b5d2ec278d182f3d9dbe03fbdf86791b59debf79
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Préparatifs avant la configuration de stratégies de protection des applications dans le portail Azure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique décrit les prérequis et les étapes que vous devez effectuer **avant** de pouvoir créer des stratégies de protection des applications dans le portail Azure.

Pour comprendre comment les stratégies de protection des applications Intune protègent les données de votre entreprise, consultez [Protéger les applications et les données à l’aide de stratégies de protection des applications](protect-apps-and-data-with-microsoft-intune.md).

## <a name="what-is-the-azure-portal"></a>Qu’est-ce que le portail Azure ?

Le portail Azure est la nouvelle console d’administration permettant de créer des stratégies de protection des applications. Il prend en charge les scénarios GAM suivants :
- Appareils mobiles inscrits dans Intune
- Appareils gérés par une autre solution de gestion des appareils mobiles
- Appareils qui ne sont gérés par aucune solution de gestion des appareils mobiles (BYOD)

À l’heure actuelle, la **console Administrateur Intune** et le **portail Azure** vous permettent de configurer des stratégies de protection des applications.  Considérez les points suivants :

* Les stratégies que vous créez dans le **portail Azure** sont prises en charge pour **tous les scénarios GAM** répertoriés ci-dessus. La **console Administrateur Intune** prend uniquement en charge la création de stratégies pour les **appareils qui sont inscrits et gérés par Intune**.

* Tous les paramètres des stratégies de protection des applications n’apparaissent pas forcément dans la console Administrateur Intune, car les **nouveaux paramètres** ne peuvent être ajoutés qu’au **portail Azure**.

* Si vous créez des stratégies de protection des applications dans la console d’administration Intune **et** dans le portail Azure, la stratégie créée dans **le portail Azure est appliquée aux applications et déployée sur les utilisateurs**.
    * Vous ne pouvez pas importer les stratégies de protection des applications créées dans la console d’administration Intune dans le portail Azure.  Vous devez les recréer dans le portail Azure.


* Les autres **fonctionnalités de gestion des applications**, telles que le déploiement d’applications et les stratégies de configuration d’application, ne sont disponibles que dans la **console Administrateur Intune**.


Si vous ne connaissez pas le portail Azure, consultez [Portail Azure pour les stratégies de protection des applications Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) pour découvrir les principes de base du portail.

Pour obtenir des instructions sur la création d’une stratégie de protection des applications dans la console Administrateur Intune, consultez [Configurer et déployer des stratégies de protection des applications dans la console Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  <a name="supported-platforms"></a>Plateformes prises en charge
- iOS 8.1 ou version ultérieure
- Android 4 ou version ultérieure
- Windows 10

>[!NOTE]
>Depuis la version 1703, vous pouvez définir les stratégies de protection des applications pour les appareils Windows 10 dans la GAM sans scénario d’inscription. Pour plus d’informations, consultez [Protéger vos données d’entreprise à l’aide de la Protection des informations Windows (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).

##  <a name="supported-apps"></a>Applications prises en charge
* **Applications Microsoft :** ces applications intègrent le SDK d’application Intune et ne nécessitent aucun traitement supplémentaire avant la mise en œuvre des stratégies de protection des applications.
Pour afficher la liste complète des applications Microsoft prises en charge, accédez à la [Galerie d’applications mobiles Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) dans la page des partenaires d’application Microsoft Intune. Cliquez sur l’application pour afficher les scénarios et les plateformes pris en charge et savoir si l’application prend en charge plusieurs identités.

* **Applications métier de votre organisation :** vous devez préparer ces applications pour qu’elles incluent le SDK d’application Intune avant la mise en œuvre des stratégies de protection des applications.

  * Pour les appareils gérés par Intune, consultez [Décider comment préparer les applications pour la gestion des applications mobiles](/intune/apps-prepare-mobile-application-management).

  * Pour les appareils qui ne sont pas gérés (comme les appareils appartenant aux employés) ou pour les appareils qui sont gérés par une autre solution de gestion des appareils mobiles, consultez [Protéger les données et applications métier sur les appareils non inscrits dans Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

## <a name="prerequisites"></a>Prérequis

-   **Un abonnement Microsoft Intune**. Les utilisateurs ont besoin de licences Intune pour obtenir les applications avec des stratégies de protection d’application.
Vous disposez déjà d’un abonnement Intune si vous utilisez actuellement Intune pour gérer vos appareils. Vous disposez également d’un abonnement Intune si vous avez acheté une licence EMS (Enterprise Mobility Suite). Si vous essayez Intune pour tester les fonctionnalités de gestion des applications mobiles, vous pouvez obtenir un compte d’évaluation dans la [page Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/).

    Pour vérifier si vous avez un abonnement Intune, dans le portail Office, accédez à la page de **facturation**.  Si vous avez un abonnement, Intune doit être indiqué comme **Actif** dans les abonnements.

-   **Un abonnement Office 365**, qui est nécessaire pour les opérations suivantes :

  - Appliquer des stratégies de protection des applications aux applications prenant en charge plusieurs identités.

  - Créer des comptes professionnels SharePoint Online et Exchange Online. Les versions locales d’Exchange et de SharePoint ne sont pas prises en charge.

-   **Configuration de Skype Entreprise Online pour l’authentification moderne**. Pour en savoir plus, voir [Activer l’authentification moderne](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) pour créer des utilisateurs. Azure AD authentifie les utilisateurs lorsqu’ils ouvrent l’application et entrent leurs informations d’identification professionnelles.

    > [!NOTE]
    > Les groupes d’utilisateurs doivent être configurés dans Azure AD. Vous ne pouvez pas utiliser de groupes d’utilisateurs Intune pour déployer des stratégies de protection des applications dans le portail Azure.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Créer des utilisateurs et attribuer des licences Microsoft Intune

1.  Connectez-vous au [portail Office](https://portal.office.com) à l’aide de vos informations d’identification d’administrateur.

2.  Ajoutez des utilisateurs comme décrit dans la section **Étapes de l’exécution d’une version d’évaluation de 30 jours d’Intune** du [Guide d’évaluation de Microsoft Intune](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune), puis attribuez des licences Intune. Pour permettre à un utilisateur d’accéder au portail Office, au portail Azure AD et au portail Azure, affectez-lui le **rôle d’administrateur général**.

5.  Les stratégies de protection des applications sont déployées sur des groupes d’utilisateurs dans Azure Active Directory. Pour créer des groupes d’utilisateurs pour vos stratégies de protection des applications, créez un groupe d’utilisateurs comme décrit dans la section **Créer un groupe d’utilisateurs** de la rubrique [Créer des groupes pour organiser les utilisateurs et les appareils de l’abonnement à la version d’évaluation](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### <a name="assign-roles-to-non-global-admin-users"></a>Attribuer des rôles à des utilisateurs administrateurs non généraux

Les administrateurs généraux ont accès au [portail Azure](https://portal.azure.com).  Si vous voulez que les utilisateurs qui ne sont pas des administrateurs généraux puissent configurer des stratégies et effectuer d’autres tâches de gestion des applications mobiles, lisez l’article [Utiliser des attributions de rôle pour gérer l’accès aux ressources de votre abonnement Azure](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/).

## <a name="next-steps"></a>Étapes suivantes
[Créer et déployer des stratégies de protection des applications avec Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
