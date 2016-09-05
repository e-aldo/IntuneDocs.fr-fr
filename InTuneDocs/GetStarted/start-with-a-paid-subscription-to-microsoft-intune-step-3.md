---
title: "Synchroniser Active Directory et ajouter des utilisateurs à Intune | Microsoft Intune"
description: "Cette rubrique décrit la synchronisation d’utilisateurs locaux avec Azure AD et l’octroi d’autorisations d’administrateur pour votre abonnement Intune"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6d1c7c670341692d4ea0c823e4a9a96746b83067
ms.openlocfilehash: fb38e2ba5ffcff202504ee1ebb934000c1f074f1


---


# Synchroniser Active Directory et ajouter des utilisateurs à Intune
Vous pouvez configurer la synchronisation d’annuaires pour importer des comptes d’utilisateur de votre instance Active Directory locale vers Microsoft Azure Active Directory (Azure AD). Le fait que votre service Active Directory local soit connecté à tous vos services Azure Active Directory facilite grandement la gestion des identités des utilisateurs. Vous pouvez aussi configurer les fonctionnalités d'authentification unique pour permettre à vos utilisateurs de s'authentifier de manière simple et naturelle.

Pour faciliter encore les choses, lorsque vous utilisez plusieurs services avec le même [client Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), les comptes d’utilisateur que vous avez précédemment synchronisés sont disponibles pour tous les services cloud qui partagent le même abonnement client Azure AD.

## Synchroniser les utilisateurs locaux avec Azure AD
Le seul outil dont vous avez besoin pour synchroniser vos comptes d’utilisateur avec Azure AD est l’[Assistant Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). L’Assistant Azure AD Connect vous offre une expérience simplifiée qui vous guide pour connecter votre infrastructure d’identité locale au cloud.  Choisissez votre topologie et vos besoins (un ou plusieurs annuaires, synchronisation de mot de passe ou fédération) pour que l’Assistant déploie et configure tous les composants nécessaires à la mise en service de votre connexion. Notamment les services de synchronisation, les services AD FS et le module PowerShell Azure AD.

> [!TIP]
> Azure AD Connect comporte des fonctionnalités qui étaient auparavant connues sous les noms Dirsync et Azure AD Sync. Obtenez des informations plus détaillées sur l’[intégration d’annuaire](http://technet.microsoft.com/library/jj573653.aspx). Pour en savoir plus sur les avantages de la synchronisation des comptes d’utilisateur de votre annuaire local sur Azure AD, consultez [Ressemblances entre Active Directory et Azure AD](http://technet.microsoft.com/library/dn518177.aspx).

## Accorder des autorisations d’administrateur
Après avoir ajouté des utilisateurs à votre abonnement Intune, nous vous recommandons d’attribuer des [informations d’identification d’administration](administrative-accounts-websites-perms.md) à quelques comptes d’utilisateur. La console que vous utilisez pour affecter des informations d'identification d'administration varie selon le type d'administrateur que vous souhaitez affecter :

-   **Administrateur client** : utilisez le **[!INCLUDE[wit_icp_1](../includes/wit_icp_1_md.md)]** pour affecter ce type d’administrateur à la gestion de votre abonnement, notamment la facturation, le stockage cloud et la gestion des utilisateurs qui peuvent utiliser [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

-   **Administrateur de service ** : utilisez la **[!INCLUDE[wit_adminconsole](../includes/wit_adminconsole_md.md)]** pour affecter ce type d’administrateur chargé des tâches quotidiennes, notamment la gestion des appareils mobiles ou des ordinateurs, le déploiement d’une stratégie ou de logiciels, et l’exécution de rapports.


### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 3 du *Guide de démarrage rapide pour Intune*.

>[!div class="step-by-step"]

>[&larr; **Paramètres du domaine**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gérer les licences Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  



<!--HONumber=Aug16_HO4-->


