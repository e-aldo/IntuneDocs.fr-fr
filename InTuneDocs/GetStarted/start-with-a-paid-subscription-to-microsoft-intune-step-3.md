---
title: "Synchroniser Active Directory et ajouter des utilisateurs à Intune | Microsoft Intune"
description: "Synchroniser des utilisateurs locaux avec Azure AD et octroyer des autorisations d’administrateur pour votre abonnement Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 29b6e5a3d319c741482fcc2b600842e2e42b96e2
ms.openlocfilehash: 33534c685ad3a4ddfd4b605e088132f2b8ff2c36


---


# <a name="sync-active-directory-and-add-users-to-intune"></a>Synchroniser Active Directory et ajouter des utilisateurs à Intune
Vous pouvez configurer la synchronisation d’annuaires pour importer des comptes d’utilisateur de votre instance Active Directory locale vers Microsoft Azure Active Directory (Azure AD). Le fait que votre service Active Directory local soit connecté à tous vos services Azure Active Directory facilite grandement la gestion des identités des utilisateurs. Vous pouvez aussi configurer les fonctionnalités d'authentification unique pour permettre à vos utilisateurs de s'authentifier de manière simple et naturelle.

Pour faciliter encore les choses, lorsque vous utilisez plusieurs services avec le même [client Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/), les comptes d’utilisateur que vous avez précédemment synchronisés sont disponibles pour tous les services cloud qui partagent le même abonnement client Azure AD.

## <a name="synchronize-on-premises-users-with-azure-ad"></a>Synchroniser les utilisateurs locaux avec Azure AD
Le seul outil dont vous avez besoin pour synchroniser vos comptes d’utilisateur avec Azure AD est l’[Assistant Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). L’Assistant Azure AD Connect vous offre une expérience simplifiée qui vous guide pour connecter votre infrastructure d’identité locale au cloud.  Choisissez votre topologie et vos besoins (un ou plusieurs annuaires, synchronisation de mot de passe ou fédération) pour que l’Assistant déploie et configure tous les composants nécessaires à la mise en service de votre connexion. Notamment les services de synchronisation, les services AD FS et le module PowerShell Azure AD.

> [!TIP]
> Azure AD Connect comporte des fonctionnalités qui étaient auparavant connues sous les noms Dirsync et Azure AD Sync. Obtenez des informations plus détaillées sur l’[intégration d’annuaire](http://technet.microsoft.com/library/jj573653.aspx). Pour en savoir plus sur les avantages de la synchronisation des comptes d’utilisateur de votre annuaire local sur Azure AD, consultez [Ressemblances entre Active Directory et Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## <a name="grant-administrator-permissions"></a>Accorder des autorisations d’administrateur

Pour administrer Intune, vous utiliserez :
- Deux types de comptes d’administrateur
- Des comptes d’utilisateur avec des autorisations supplémentaires
- Deux portails/consoles d’administration basés sur le web pour accorder à vos administrateurs l’accès aux éléments qu’ils doivent gérer.

Après avoir ajouté des utilisateurs à votre abonnement Intune, nous vous recommandons d'attribuer des informations d'identification d'administration à quelques comptes d'utilisateur. La console que vous utilisez pour affecter des informations d'identification d'administration varie selon le type d'administrateur que vous souhaitez affecter :

-   **Administrateur client** : utilisez le **portail des comptes Microsoft Intune** pour affecter ce type d’administrateur à la gestion de votre abonnement, notamment la facturation, le stockage cloud et la gestion des utilisateurs qui peuvent utiliser Intune.

-   **Administrateur de service ** : utilisez la **console d’administration Microsoft Intune** pour affecter ce type d’administrateur chargé des tâches quotidiennes, notamment la gestion des appareils mobiles ou des ordinateurs, le déploiement d’une stratégie ou de logiciels, et l’exécution de rapports.

Les sections suivantes décrivent ces comptes et portails.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Comptes d’administrateur et comptes d’utilisateur avec des autorisations spéciales

Voici les comptes et autorisations que vous utiliserez pour Intune.

### <a name="tenant-administrator"></a>Administrateur client
|Niveaux d'autorisation|Plus d'informations|
|--------------------------|-------------------------|
|Les administrateurs clients sont affectés à un seul rôle d'administrateur qui définit l'étendue administrative de l'utilisateur correspondant et les tâches qu'il peut gérer.<br /><br />Les rôles d’administrateur sont communs aux différents services cloud Microsoft, même si certains services peuvent ne pas prendre en charge certains rôles.<br /><br /> Microsoft Intune utilise les rôles suivants :<br /><br />- Administrateur général<br />- Administrateur de facturation<br />- Administrateur de mots de passe<br />- Administrateur de prise en charge de service<br />- Administrateur de gestion des utilisateurs|Par défaut, le compte que vous utilisez pour créer votre abonnement Microsoft Intune est un administrateur client ayant le rôle d’administrateur général.<br /></br>  En tant qu’administrateur client, vous utilisez le [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] pour gérer votre abonnement à Intune et affecter les administrateurs clients à partir du [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Utilisez un administrateur client doté du rôle d'administrateur général pour accéder à la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] afin d'affecter votre premier administrateur de services fédérés. Il est recommandé de ne pas utiliser un administrateur client pour des tâches de gestion quotidiennes. Un administrateur client n’a pas besoin d’une licence Intune pour accéder au [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />L'administrateur client est un concept commun entre les services cloud Microsoft. Quand vous vous abonnez à Intune, votre service est un client de Microsoft Azure AD. Consultez la section sur les clients Azure AD dans [Qu’est-ce qu’un annuaire Azure AD ?](http://technet.microsoft.com/library/jj573650.aspx).|


### <a name="service-administrator"></a>Administrateur de services fédérés
|Niveaux d'autorisation|Plus d'informations|
|--------------------------|-------------------------|
|Les administrateurs de services fédérés reçoivent l'une des autorisations suivantes :<br /><br />**Accès complet** : permet d’accéder à toutes les zones de la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], sans aucune restriction. Permet également d'ajouter et de gérer d'autres administrateurs de service.<br /><br />**Accès en lecture seule** : permet d’accéder en lecture à toutes les zones de la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Un administrateur de services fédérés en lecture seule ne peut pas modifier les données, mais il peut exécuter des rapports.<br /><br />**Support technique - Nœud Groupes** : accorde des autorisations qui permettent à l’administrateur de services d’exécuter uniquement un ensemble de tâches couramment associées à des scénarios de support technique. Pour plus d’informations sur ce jeu d’autorisations, consultez [Personnaliser les vues de la console Intune en fonction des rôles d’administrateur](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Par défaut, Intune n’affecte pas d’administrateur de services fédérés. Vous devez plutôt utiliser un administrateur client doté du rôle d'administrateur général pour affecter le premier administrateur de services fédérés de votre abonnement. </br></br> En tant qu’administrateur de services, vous utilisez la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] pour gérer les tâches quotidiennes pour Intune.<br /><br />Vous affectez les administrateurs de service à partir de la console d’administration. Un administrateur de services fédérés nécessite une licence Intune pour que le compte puisse accéder à la console Administrateur.|



### <a name="device-enrollment-managers"></a>Gestionnaires d’inscription d’appareil
|Niveaux d'autorisation|Plus d'informations|
|--------------------------|-------------------------|
|Les gestionnaires d'inscription d'appareil sont des comptes d'utilisateur standard dotés d'autorisations supplémentaires pour inscrire plus de cinq appareils.|Par défaut, chaque utilisateur [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] peut inscrire jusqu'à cinq appareils. Toutefois, vous pouvez donner à un compte d'utilisateur l'autorisation de gestionnaire d'inscription d'appareil, puis utiliser ce compte pour inscrire de grands groupes d'appareils d'entreprise. Cela s’avère utile quand les appareils doivent être affectées aux utilisateurs de façon temporaire ou sont utilisés en mode plein écran alors qu’aucune association n’est requise entre un utilisateur et un appareil.|




>[!div class="step-by-step"]

>[&larr; **Paramètres du domaine**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gérer les licences Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Nov16_HO4-->


