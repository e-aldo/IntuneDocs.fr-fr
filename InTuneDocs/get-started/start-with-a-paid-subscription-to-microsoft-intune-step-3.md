---
title: Ajouter des utilisateurs et accorder des autorisations | Microsoft Docs
description: "Synchroniser des utilisateurs locaux avec Azure AD et octroyer des autorisations d’administrateur pour votre abonnement Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: b1f16df329c01aeb45885f3981e2d9d7ef854e8b


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Ajouter des utilisateurs et accorder une autorisation d’administration à Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique explique aux administrateurs comment ajouter des utilisateurs à Intune et décrit les autorisations d’administration disponibles dans le service Intune.

En tant qu’administrateur, vous pouvez ajouter directement des utilisateurs ou synchroniser des utilisateurs à partir de votre annuaire Active Directory local. Une fois ajoutés, les utilisateurs peuvent inscrire des appareils et accéder aux ressources de l’entreprise. Vous pouvez également attribuer aux utilisateurs des autorisations supplémentaires, notamment celles d’*administrateur client*, d’*administrateur de service* et de *gestionnaire d’inscription d’appareil*.

Cette rubrique vous aide à effectuer les tâches suivantes :

- [Ajouter des utilisateurs à Intune](#add-users-to-intune)
- [Accorder des autorisations Intune supplémentaires](#grant-intune-permissions), notamment :
  - [Administrateur client](#tenant-administrator)
  - [Administrateur de service](#service-administrator)
  - [Gestionnaires d’inscription d’appareil](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Ajouter des utilisateurs à Intune
Vous pouvez ajouter manuellement des utilisateurs à votre abonnement Intune par le biais du [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), mais une licence Intune ne leur est pas attribuée automatiquement. Au lieu de cela, un administrateur Intune doit modifier le compte d’utilisateur à une date ultérieure pour attribuer une licence à l’utilisateur à partir du portail Office 365. Pour obtenir des instructions, consultez [Ajouter des utilisateurs individuellement ou en bloc à Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="sync-active-directory-and-add-users-to-intune"></a>Synchroniser Active Directory et ajouter des utilisateurs à Intune
Vous pouvez configurer la synchronisation d’annuaires pour importer des comptes d’utilisateur de votre instance Active Directory locale vers Microsoft Azure Active Directory (Azure AD), qui comprend les utilisateurs Intune. Le fait que votre service Active Directory local soit connecté à tous vos services Azure Active Directory facilite grandement la gestion des identités des utilisateurs. Vous pouvez aussi configurer les fonctionnalités d'authentification unique pour permettre à vos utilisateurs de s'authentifier de manière simple et naturelle. Si vous liez le même [locataire Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) à plusieurs services, les comptes d’utilisateur que vous avez précédemment synchronisés sont accessibles à tous les services cloud.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Guide pratique pour synchroniser les utilisateurs locaux avec Azure AD
Le seul outil dont vous avez besoin pour synchroniser vos comptes d’utilisateur avec Azure AD est l’[Assistant Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). L’Assistant Azure AD Connect vous offre une expérience simplifiée qui vous guide pour connecter votre infrastructure d’identité locale au cloud.  Choisissez votre topologie et vos besoins (un ou plusieurs annuaires, synchronisation de mot de passe ou fédération) pour que l’Assistant déploie et configure tous les composants nécessaires à la mise en service de votre connexion. Notamment les services de synchronisation, les services AD FS et le module PowerShell Azure AD.

> [!TIP]
> Azure AD Connect comporte des fonctionnalités qui étaient auparavant connues sous les noms Dirsync et Azure AD Sync. Obtenez des informations plus détaillées sur l’[intégration d’annuaire](http://technet.microsoft.com/library/jj573653.aspx). Pour en savoir plus sur les avantages de la synchronisation des comptes d’utilisateur de votre annuaire local sur Azure AD, consultez [Ressemblances entre Active Directory et Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-intune-permissions"></a>Accorder des autorisations Intune

Après avoir ajouté des utilisateurs à votre abonnement Intune, nous vous recommandons d’attribuer une autorisation d’administration à quelques comptes d’utilisateur. Pour administrer Intune, vous pouvez accorder aux utilisateurs trois types d’autorisation Intune.
-   **Administrateur client** : utilisez le portail Office 365 pour affecter ce type d’administrateur à la gestion de votre abonnement, notamment la facturation, le stockage cloud et la gestion des utilisateurs qui peuvent utiliser Intune.
-   **Administrateur de service** : utilisez la console d’administration Microsoft Intune pour affecter ce type d’administrateur chargé des tâches quotidiennes, notamment la gestion des appareils et des ordinateurs, le déploiement de stratégie ou d’applications, et l’exécution de rapports.
-   **Gestionnaire d’inscription d’appareil** : utilisez la console d’administration Microsoft Intune pour affecter ce type d’administrateur chargé des tâches quotidiennes, notamment la gestion des appareils et des ordinateurs, le déploiement de stratégie ou d’applications, et l’exécution de rapports.


### <a name="tenant-administrator"></a>Administrateur client


Les administrateurs clients sont affectés à un seul rôle d'administrateur qui définit l'étendue administrative de l'utilisateur correspondant et les tâches qu'il peut gérer. Les rôles d’administrateur sont communs aux différents services cloud Microsoft, même si certains services peuvent ne pas prendre en charge certains rôles. Intune utilise les rôles suivants :
- **Administrateur général** : accède à toutes les fonctionnalités d’administration dans Intune. Par défaut, la personne qui s’inscrit à Intune devient un administrateur général. Les administrateurs généraux sont les seuls administrateurs qui peuvent affecter d’autres rôles d’administrateur. Vous pouvez avoir plusieurs administrateurs généraux dans votre organisation. En guise de bonne pratique, nous vous recommandons d’attribuer ce rôle à seulement quelques membres de votre entreprise pour réduire les risques.
- **Administrateur de facturation** : il effectue des achats, gère les abonnements et les tickets de support, et surveille l’intégrité des services.
- **Administrateur de mots de passe** : il réinitialise les mots de passe, gère les demandes de service et surveille l’intégrité des services. Les administrateurs de mots de passe sont limités à la réinitialisation des mots de passe des utilisateurs.
- **Administrateur du support technique du service** : il ouvre les demandes de support auprès de Microsoft, et visualise le tableau de bord du service et le centre de messages. Il dispose d’une autorisation « Afficher uniquement », sauf pour l’ouverture et la lecture des tickets de support.
- **Administrateur de gestion des utilisateurs** : il réinitialise les mots de passe, surveille l’intégrité du service, ajoute et supprime des comptes d’utilisateur, et gère les demandes de service. L’administrateur de gestion des utilisateurs ne peut pas supprimer un administrateur général, créer d’autres rôles d’administrateur ou réinitialiser des mots de passe pour les administrateurs de facturation, généraux et de service.

Par défaut, le compte que vous utilisez pour créer votre abonnement Microsoft Intune est un administrateur client ayant le rôle d’administrateur général. En tant qu’administrateur de clients, vous utilisez la console Administrateur Intune pour gérer votre abonnement à Intune et affecter des administrateurs clients à partir du [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854). Utilisez un administrateur de clients ayant le rôle d’administrateur général pour accéder au portail et affecter votre premier administrateur de service. Il est recommandé de ne pas utiliser un administrateur client pour des tâches de gestion quotidiennes. Un administrateur de clients n’a pas besoin de licence Intune pour accéder à la console Administrateur Intune. L'administrateur de clients est un concept commun entre les services cloud Microsoft. Quand vous vous abonnez à Intune, votre service est un locataire d’Azure AD. Pour plus d’informations, consultez la section sur les locataires Azure AD dans [Qu’est-ce qu’un annuaire Azure AD ?](http://technet.microsoft.com/library/jj573650.aspx).

En tant qu’administrateur de clients, utilisez le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pour gérer votre abonnement, notamment pour effectuer les tâches suivantes quand votre rôle d’administrateur l’autorise :

- Gérer les comptes d’utilisateur et configurer la synchronisation d’annuaires à partir de votre instance Active Directory locale
- Gérer des groupes d’utilisateurs, appelés groupes de sécurité
- Attribuer des licences utilisateur pour Intune
- Configurer le nom de domaine pour votre abonnement utilisé quand les utilisateurs se connectent (par exemple, contoso.com)
- Gérer la facturation et les achats, notamment les licences et l’espace de stockage cloud
- Rechercher des liens pour afficher l’intégrité du service Intune

Pour accéder au portail Office 365, l’état de connexion de votre compte doit être **Autorisé**. Cet état diffère de celui défini pour la possession d’une licence pour l’abonnement. Par défaut, tous les comptes d’utilisateur sont définis avec l’état **Autorisé**. Les utilisateurs sans autorisations d’administrateur peuvent utiliser le portail Office 365 pour réinitialiser les mots de passe Intune.

### <a name="service-administrator"></a>Administrateur de services fédérés

Par défaut, Intune n’affecte pas d’administrateur de services fédérés. Vous devez plutôt utiliser un administrateur client doté du rôle d'administrateur général pour affecter le premier administrateur de services fédérés de votre abonnement. En tant qu’administrateur de service, vous utilisez la [console Administrateur Intune](https://manage.microsoft.com/) pour gérer les tâches quotidiennes pour Intune. Vous affectez les administrateurs de service à partir de la console d’administration. Un administrateur de service a besoin d’une licence Intune pour accéder à la console Administrateur.

Les administrateurs de service reçoivent l'une des autorisations suivantes :
- **Accès complet** : accès illimité à toutes les zones de la console Administration Intune, ajouter et gérer d’autres administrateurs de service.
- **Accès en lecture seule** : autorisation de lecture à toutes les zones de la console Administration Intune, ne peut pas modifier les données, mais peut exécuter des rapports
- **Support technique - Nœud Groupes** : permet à l’administrateur de service d’effectuer uniquement les tâches associées à des scénarios de support technique. Voir [Personnaliser les affichages de la console Intune en fonction des rôles d’administrateur](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).

En tant qu’administrateur de service, utilisez ce portail pour gérer les opérations quotidiennes, notamment :

- Créer et définir des stratégies pour les ordinateurs et les appareils mobiles
- Charger et déployer des mises à jour logicielles et des applications
- Gérer Endpoint Protection sur les ordinateurs
- Afficher l’état des appareils et exécuter des rapports

### <a name="device-enrollment-managers"></a>Gestionnaires d’inscription d’appareil

Les gestionnaires d’inscription d’appareil sont des comptes d’utilisateur standard dotés d’autorisations supplémentaires pour inscrire davantage d’appareils sans utilisateur. Par défaut, chaque utilisateur Intune peut inscrire jusqu’à&15; appareils. En tant qu’administrateur, vous pouvez accorder à un compte d’utilisateur l’autorisation Gestionnaire d’inscription d’appareil. Ce compte peut inscrire un grand nombre d’appareils d’entreprise. Cela s’avère utile quand les appareils doivent être affectées aux utilisateurs de façon temporaire ou sont utilisés en mode plein écran alors qu’aucune association n’est requise entre un utilisateur et un appareil. Pour plus d’informations, consultez [Gestionnaire d’inscription d’appareil](https://docs.microsoft.com/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Paramètres du domaine**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gérer les licences Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Feb17_HO3-->


