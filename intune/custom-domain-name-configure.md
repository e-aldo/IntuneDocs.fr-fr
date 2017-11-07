---
title: "configurer un nom de domaine personnalisé"
description: "Ajouter un nom de domaine personnalisé à votre abonnement Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ca480869e1130fff0c6942e42dfe54647ad52021
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2017
---
# <a name="configure-a-custom-domain-name"></a>configurer un nom de domaine personnalisé

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Cette rubrique explique aux administrateurs comment créer un enregistrement CNAME DNS pour simplifier et personnaliser la procédure d’ouverture de session.

Quand votre organisation souscrit à un service cloud Microsoft comme Intune, vous recevez un nom de domaine initial hébergé dans Azure Active Directory (AD) qui se présente sous la forme **votre_domaine.onmicrosoft.com**. Dans cet exemple, **votre_domaine** est le nom de domaine que vous avez choisi au moment de la souscription. **onmicrosoft.com** est le suffixe attribué aux comptes que vous ajoutez à votre abonnement. Vous pouvez configurer le domaine personnalisé de votre organisation de sorte qu’il accède à Intune à la place du nom de domaine qui vous a été fourni avec votre abonnement.

Avant de créer des comptes d’utilisateur ou de synchroniser votre instance Active Directory locale, nous vous recommandons vivement de choisir entre l’utilisation seule du domaine .onmicrosoft.com et l’ajout d’un ou plusieurs de vos domaines personnalisés. Pour simplifier la gestion des utilisateurs, configurez un domaine personnalisé avant d’ajouter des utilisateurs. Les utilisateurs pourront ainsi se connecter avec les informations d’identification qu’ils utilisent pour accéder aux autres ressources du domaine.

Lorsque vous vous abonnez à un service cloud Microsoft, votre instance de ce service devient un client Microsoft [Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), qui fournit des services d’identité et d’annuaires à votre service cloud. Et puisque les tâches permettant de configurer Intune pour utiliser le nom de domaine personnalisé de votre organisation sont identiques à celles appliquées aux autres clients Azure AD, vous pouvez utiliser les informations et les procédures du document [Ajouter votre domaine](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Pour plus d’informations sur les domaines personnalisés, consultez [Vue d’ensemble conceptuelle des noms de domaine personnalisés dans Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Vous ne pouvez pas renommer ou supprimer le nom de domaine onmicrosoft.com initial. Vous pouvez ajouter, vérifier ou supprimer les noms de domaine personnalisés utilisés avec Intune pour clarifier l’identité de votre entreprise.

## <a name="to-add-and-verify-your-custom-domain"></a>Pour ajouter et vérifier votre domaine personnalisé

1. Accédez au [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) et connectez-vous à votre compte d’administrateur.

2. Dans le volet de navigation, choisissez **Paramètres** &gt; **Domaines**.

3. Choisissez **Ajouter un domaine**, puis tapez votre nom de domaine personnalisé.
   ![Capture d’écran du Centre d’administration Office 365 avec Paramètres > Domaines sélectionné et l’ajout d’un nouveau nom de domaine](./media/domain-custom-add.png)
4. La boîte de dialogue **Vérifier le domaine** s’ouvre. Elle contient les valeurs permettant de créer l’enregistrement TXT dans votre fournisseur d’hébergement DNS.
    - **Utilisateurs GoDaddy** : le portail de gestion Office 365 vous redirige vers la page de connexion de GoDaddy. L’enregistrement TXT est créé automatiquement une fois que vous entrez vos informations d’identification et que vous acceptez le contrat d’autorisation de modification de domaine. Vous pouvez également [créer un enregistrement TXT](https://support.office.com/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a).
    - **Utilisateurs Register.com** : suivez les [instructions détaillées](https://support.office.com/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e#BKMK_verify) pour créer l’enregistrement TXT.

Les étapes permettant d’ajouter et de vérifier un domaine personnalisé peuvent également être [effectuées dans Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

Pour plus d’informations, consultez [À propos de votre domaine onmicrosoft.com initial dans Office 365](https://support.office.com/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A).
