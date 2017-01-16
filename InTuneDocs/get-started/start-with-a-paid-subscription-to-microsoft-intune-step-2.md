---
title: "Configurer un nom de domaine personnalisé | Microsoft Docs"
description: "Ajouter un nom de domaine personnalisé à votre abonnement Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: b40ce33560ea49fdc966889a1bf2cac2ae537578


---


# <a name="configure-a-custom-domain-name"></a>configurer un nom de domaine personnalisé

Quand votre organisation s’inscrit à un service cloud de Microsoft comme Intune, vous recevez un nom de domaine initial hébergé dans Azure Active Directory (AD) qui ressemble à celui-ci : **votre_domaine.onmicrosoft.com**. Dans cet exemple, **votre_domaine** est le nom de domaine que vous avez choisi lors de votre inscription, et **onmicrosoft.com** est le suffixe attribué aux comptes que vous ajoutez à votre abonnement. Si votre organisation possède un domaine personnalisé, vous pouvez configurer votre instance d’Intune de sorte qu’elle utilise ce nom de domaine à la place du domaine attribué avec votre abonnement.

Avant de créer des comptes d’utilisateur ou de synchroniser votre instance Active Directory locale, nous vous recommandons vivement de choisir entre l’utilisation seule du domaine .onmicrosoft.com et l’ajout d’un ou plusieurs de vos domaines personnalisés. Le fait de configurer un domaine personnalisé avant d'ajouter des utilisateurs peut simplifier la gestion des identités des utilisateurs de votre abonnement en permettant aux utilisateurs de se connecter à l'aide des informations d'identification qu'ils utilisent pour accéder aux autres ressources du domaine.

Lorsque vous vous abonnez à un service cloud Microsoft, votre instance de ce service devient un client Microsoft [Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), qui fournit des services d’identité et d’annuaires à votre service cloud. Et puisque les tâches permettant de configurer Intune pour utiliser le nom de domaine personnalisé de votre organisation sont identiques à celles appliquées aux autres clients Azure AD, vous pouvez utiliser les informations et les procédures du document [Ajouter votre domaine](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Pour plus d’informations sur l’utilisation de votre domaine personnalisé avec un service cloud Microsoft, consultez [Vue d’ensemble conceptuelle des noms de domaine personnalisés dans Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

Vous ne pouvez pas renommer ou supprimer ce nom de domaine initial. Toutefois, vous pouvez ajouter, vérifier ou supprimer vos propres noms de domaines personnalisés à utiliser avec Intune, ce qui est utile si vous voulez conserver l’identité de votre entreprise.

## <a name="to-add-and-verify-your-custom-domain"></a>Pour ajouter et vérifier votre domaine personnalisé

1. Accédez au [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) et connectez-vous à votre compte d’administrateur.

2. Dans le volet de navigation, choisissez **Paramètres** &gt; **Domaines**.

3. Choisissez **Ajouter un domaine**, puis tapez votre nom de domaine personnalisé.

4. La boîte de dialogue **Vérifier le domaine** s’ouvre. Elle contient les valeurs permettant de créer l’enregistrement TXT dans votre fournisseur d’hébergement DNS.
    - **Utilisateurs GoDaddy** : le portail de gestion Office 365 vous redirige vers la page de connexion de GoDaddy. L’enregistrement TXT est créé automatiquement une fois que vous entrez vos informations d’identification et que vous acceptez le contrat d’autorisation de modification de domaine. Vous pouvez également [créer un enregistrement TXT](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US).
    - **Utilisateurs Register.com** : suivez les [instructions détaillées](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) pour créer l’enregistrement TXT.

    > [!TIP]
    > Prenez soin de créer un alias DNS (CNAME) pour [l’inscription des appareils Windows](/Intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) lors de l’exécution de modifications dans votre fournisseur d’hébergement DNS.

Les étapes permettant d’ajouter et de vérifier un domaine personnalisé peuvent également être [effectuées dans Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Pour plus d’informations, consultez [À propos de votre domaine onmicrosoft.com initial dans Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US).

>[!div class="step-by-step"]

>[&larr; **Se connecter à Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Ajouter des utilisateurs à Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Dec16_HO2-->


