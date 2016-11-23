---
title: "Comptes d’administration, sites web et autorisations | Microsoft Intune"
description: "Sites web d’autorisations de comptes d’administration"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db3075e7-38fd-4dfe-b266-26aed10ac8ea
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9d44a6494bed0758b9768045bd204ea0eb481636
ms.openlocfilehash: e5282defb4560fee028e16d6526037c848678d1a


---

# <a name="administrative-accounts-websites-and-permissions-in-microsoft-intune"></a>Comptes d’administration, sites web et autorisations dans Microsoft Intune

Avant de configurer Microsoft Intune, consultez cette rubrique et les autres exigences indiquées dans [Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Pour administrer Intune, vous utiliserez :
- Deux types de comptes d’administrateur
- Des comptes d’utilisateur avec des autorisations supplémentaires
- Deux portails/consoles d’administration basés sur le web pour accorder à vos administrateurs l’accès aux éléments qu’ils doivent gérer.

Les sections suivantes décrivent ces comptes et portails.

## <a name="administrator-accounts-and-user-accounts-with-special-permissions"></a>Comptes d’administrateur et comptes d’utilisateur avec des autorisations spéciales

Voici les comptes et autorisations que vous utiliserez pour Intune.

### <a name="tenant-administrator"></a>Administrateur client
|Niveaux d'autorisation|Plus d'informations|
|--------------------------|-------------------------|
|Les administrateurs clients sont affectés à un seul rôle d'administrateur qui définit l'étendue administrative de l'utilisateur correspondant et les tâches qu'il peut gérer.<br /><br />Les rôles d’administrateur sont communs aux différents services cloud Microsoft, même si certains services peuvent ne pas prendre en charge certains rôles.<br /><br /> Microsoft Intune utilise les rôles suivants :<br /><br />- Administrateur général<br />- Administrateur de facturation<br />- Administrateur de mots de passe<br />- Administrateur de prise en charge de service<br />- Administrateur de gestion des utilisateurs|Par défaut, le compte que vous utilisez pour créer votre abonnement Microsoft Intune est un administrateur client ayant le rôle d’administrateur général.<br /></br>  En tant qu’administrateur client, vous utilisez le [!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)] pour gérer votre abonnement à [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et affecter les administrateurs clients à partir du [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />Utilisez un administrateur client doté du rôle d'administrateur général pour accéder à la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] afin d'affecter votre premier administrateur de services fédérés. Il est recommandé de ne pas utiliser un administrateur client pour des tâches de gestion quotidiennes. Un administrateur client n'a pas besoin d'une licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour accéder au [!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)].<br /><br />L'administrateur client est un concept commun entre les services cloud Microsoft. Quand vous vous abonnez à [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], votre service est un client de Microsoft Azure AD. Consultez la section sur les clients Azure AD dans [Qu’est-ce qu’un annuaire Azure AD ?](http://technet.microsoft.com/library/jj573650.aspx).|


### <a name="service-administrator"></a>Administrateur de services fédérés
|Niveaux d'autorisation|Plus d'informations|
|--------------------------|-------------------------|
|Les administrateurs de services fédérés reçoivent l'une des autorisations suivantes :<br /><br />**Accès complet** : permet d’accéder à toutes les zones de la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)], sans aucune restriction. Permet également d'ajouter et de gérer d'autres administrateurs de service.<br /><br />**Accès en lecture seule** : permet d’accéder en lecture à toutes les zones de la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]. Un administrateur de services fédérés en lecture seule ne peut pas modifier les données, mais il peut exécuter des rapports.<br /><br />**Support technique - Nœud Groupes** : accorde des autorisations qui permettent à l’administrateur de services d’exécuter uniquement un ensemble de tâches couramment associées à des scénarios de support technique. Pour plus d’informations sur ce jeu d’autorisations, consultez [Personnaliser les vues de la console Intune en fonction des rôles d’administrateur](/intune/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console).|Par défaut, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] n'affecte pas d'administrateur de services fédérés. Vous devez plutôt utiliser un administrateur client doté du rôle d'administrateur général pour affecter le premier administrateur de services fédérés de votre abonnement. </br></br> En tant qu’administrateur de services, vous utilisez la [!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)] pour gérer les tâches quotidiennes pour [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].<br /><br />Vous affectez les administrateurs de service à partir de la console d’administration. Un administrateur de services fédérés nécessite une licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour que le compte puisse accéder à la console Administrateur.|



### <a name="device-enrollment-managers"></a>Gestionnaires d’inscription d’appareil
|Niveaux d'autorisation|Plus d'informations|
|--------------------------|-------------------------|
|Les gestionnaires d'inscription d'appareil sont des comptes d'utilisateur standard dotés d'autorisations supplémentaires pour inscrire plus de 15 appareils.|Par défaut, chaque utilisateur [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] peut inscrire jusqu'à 15 appareils. Toutefois, vous pouvez donner à un compte d'utilisateur l'autorisation de gestionnaire d'inscription d'appareil, puis utiliser ce compte pour inscrire de grands groupes d'appareils d'entreprise. Cela s’avère utile quand les appareils doivent être affectées aux utilisateurs de façon temporaire ou sont utilisés en mode plein écran alors qu’aucune association n’est requise entre un utilisateur et un appareil.|


## <a name="administrative-websites-for-intune"></a>Sites web d'administration pour Intune
 Différentes tâches d’administration vous obligent à utiliser l’un des sites d’administration suivants, auxquels vous pouvez accéder à l’aide d’un [navigateur web pris en charge](supported-web-browsers.md).

- [Portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Console d'administration Microsoft Intune](https://admin.manage.microsoft.com/)

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**En tant qu’administrateur client, utilisez ce portail pour gérer votre abonnement**, y compris les tâches suivantes quand votre rôle d’administrateur l’autorise :

- Gérez les comptes d’utilisateur de l’abonnement et configurez la synchronisation d’annuaires à partir de votre instance Active Directory locale.
- Gérez des groupes d'utilisateurs, appelés groupes de sécurité.
- Attribuez aux utilisateurs des licences d'utilisation de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Configurez le nom de domaine que vous utilisez avec votre abonnement. Le nom de domaine définit le compte avec lequel les utilisateurs se connectent.
- Gérez la facturation et les détails de l'achat de votre abonnement, notamment le nombre de licences dont vous disposez ou la quantité d'espace de stockage cloud que vous pouvez utiliser.
- Trouvez des liens pour afficher l'intégrité du service [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- En tant qu’administrateur client, vous pouvez vous connecter au portail Office 365 pour gérer l’abonnement même si votre compte ne possède pas de licence d’utilisation pour [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].
- Tout utilisateur qui possède une licence Intune mais qui n’est pas administrateur peut utiliser ce portail pour réinitialiser le mot de passe de son compte et modifier son profil.
- Pour accéder au portail Office 365, l’état de connexion de votre compte doit être **Autorisé**. Cet état diffère de celui défini pour la possession d’une licence pour l’abonnement. Par défaut, tous les comptes d’utilisateur sont définis avec l’état **Autorisé**.


### <a name="microsoft-intune-administrator-consolehttpsadminmanagemicrosoftcom"></a>[Console d'administration Microsoft Intune](https://admin.manage.microsoft.com/)

**En tant qu’administrateur de services, utilisez ce portail pour gérer les opérations quotidiennes**, notamment :

- Définir des stratégies pour les ordinateurs et les appareils mobiles.
- Télécharger et déployer des logiciels, comme des mises à jour logicielles et des applications.
- Gérer [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Endpoint Protection sur les ordinateurs.
- Afficher l'état des appareils et exécuter des rapports.
- Connectez-vous à ce portail. Vous devez avoir des autorisations d’administrateur de service ou être un administrateur client avec le rôle Administrateur général pour vous connecter à ce portail.


Seuls les utilisateurs disposant d’autorisations d’administrateur de service ou les administrateurs clients ayant le rôle Administrateur général peuvent se connecter à ce portail. Pour accéder à la console d’administration, votre compte doit posséder une licence d’utilisation de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et son état de connexion doit être **Autorisé**.

En savoir plus sur l’[ajout d’utilisateurs à votre abonnement](start-with-a-paid-subscription-to-microsoft-intune-step-3.md) et l’[affectation de licences pour votre abonnement](start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

 ### <a name="see-also"></a>Voir aussi
 [Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->


