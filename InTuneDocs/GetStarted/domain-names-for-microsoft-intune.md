---
title: Noms de domaine pour Microsoft Intune | Microsoft Intune
description: 
keywords: 
author: andredm7
manager: swadhwa
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3c136f0-330d-432a-a91f-16f7dd097e55
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3d99669f90fe7ebec7854b7a800b09b0685c314e
ms.openlocfilehash: aaede1500f28c6eb8c2a21924d7c3b7f633eca26


---



# Gestion des domaines personnalisés avec Microsoft Intune

Les étapes permettant d’ajouter et de vérifier un domaine personnalisé peuvent également être [effectuées dans Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-add-domain/).

Quand votre organisation s’inscrit à un service cloud de Microsoft comme Intune, vous recevez un nom de domaine initial hébergé dans Azure Active Directory qui ressemble à celui-ci : **votre_domaine.onmicrosoft.com**. Dans cet exemple, **votre_domaine** est le nom de domaine que vous avez choisi lors de votre inscription, et **onmicrosoft.com** est le suffixe attribué aux comptes que vous ajoutez à votre abonnement.

Vous ne pouvez pas renommer ou supprimer ce nom de domaine initial. Toutefois, vous pouvez ajouter, vérifier ou supprimer vos propres noms de domaines personnalisés à utiliser avec Intune, ce qui est utile si vous voulez conserver l’identité de votre entreprise.

## Pour ajouter et vérifier votre domaine personnalisé 

1. Accédez au [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) et connectez-vous à votre compte d’administrateur.
    > [!IMPORTANT]
    > Pour plus d’informations sur l’emplacement de gestion des utilisateurs, groupes et domaines Microsoft Intune, vérifiez l’annonce     [Le portail de compte Intune a fusionné avec le portail de gestion Office 365](https://docs.microsoft.com/en-us/intune/deploy-use/account-portal-merged-with-Office-365).
2. Dans le volet de navigation, choisissez **Paramètres** &gt; **Domaines**.
3. Choisissez **Ajouter un domaine**, puis tapez votre nom de domaine personnalisé.
4. La boîte de dialogue **Vérifier le domaine** s’ouvre. Elle contient les valeurs permettant de créer l’enregistrement TXT dans votre fournisseur d’hébergement DNS.
    > [!TIP]
    > Le portail de gestion Office 365 vous redirige vers la page de connexion de GoDaddy lors de l’utilisation d’un domaine GoDaddy. L’enregistrement TXT est créé automatiquement une fois que vous entrez vos informations d’identification et que vous acceptez le contrat d’autorisation de modification de domaine.
    > 
    > Vous pouvez également [créer l’enregistrement TXT manuellement lors de l’utilisation d’un domaine GoDaddy](https://support.office.com/en-us/article/Create-DNS-records-at-GoDaddy-for-Office-365-f40a9185-b6d5-4a80-bb31-aa3bb0cab48a?ui=en-US&rs=en-US&ad=US), en fonction des valeurs fournies dans cette étape.

    > [!NOTE]
    > Suivez les [instructions pas à pas](https://support.office.com/en-us/article/Create-DNS-records-at-Register-com-for-Office-365-55bd8c38-3316-48ae-a368-4959b2c1684e?ui=en-US&rs=en-US&ad=US#BKMK_verify) pour créer l’enregistrement TXT lors de l’utilisation d’un domaine Register.com, basé sur les valeurs fournies dans cette étape.

5. Prenez soin de créer un alias DNS (CNAME) pour [l’inscription des appareils Windows](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) lors de l’exécution de modifications dans votre fournisseur d’hébergement DNS.

Dans un scénario de cloud hybride, une fois que vous avez ajouté votre nom de domaine personnalisé et vérifié que votre organisation le possède, vous pouvez continuer à gérer les comptes d’utilisateur dans votre annuaire Active Directory, puis le synchroniser avec Azure AD.

## Pour synchroniser des utilisateurs locaux avec Azure AD##

1. [Ajoutez le suffixe UPN](https://technet.microsoft.com/en-us/library/cc772007.aspx) de votre domaine personnalisé dans votre annuaire Active Directory local.
2. Définissez le nouveau suffixe UPN pour les utilisateurs locaux que vous voulez importer.
3. Exécutez la [synchronisation Azure AD Connect](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/) pour intégrer vos utilisateurs locaux à Azure AD.
4. Une fois les informations sur le compte d’utilisateur correctement synchronisées, vous pouvez attribuer des licences Microsoft Intune à l’aide du [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx).

### Voir aussi

[À propos de votre domaine onmicrosoft.com initial dans Office 365](https://support.office.com/en-us/article/About-your-initial-onmicrosoft-com-domain-in-Office-365-B9FC3018-8844-43F3-8DB1-1B3A8E9CFD5A?ui=en-US&rs=en-US&ad=US)

[Informations à connaître avant de commencer à utiliser Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jun16_HO5-->


