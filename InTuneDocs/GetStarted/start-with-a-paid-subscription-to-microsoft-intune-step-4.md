---
# required metadata

title: Gérer les licences Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# gérer les licences Intune
Un utilisateur doit avoir une licence de votre abonnement Intune pour pouvoir se connecter et utiliser le service ou pour inscrire des appareils afin de les gérer. Dès qu’il en obtient une, l’utilisateur devient membre du groupe d’utilisateurs [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]. Ce groupe inclut tous les utilisateurs qui disposent d'une licence d'utilisation de l'abonnement. **Chaque licence utilisateur prend en charge l’inscription de 5 appareils maximum**.

## Mode d’attribution des licences Intune
Lorsque les comptes d’utilisateur sont synchronisés à partir de votre annuaire Active Directory local ou ajoutés manuellement à votre abonnement aux services cloud via le portail de compte, ils ne reçoivent pas automatiquement une licence Intune. Au lieu de cela, à une date ultérieure, un administrateur Intune doit modifier le compte d’utilisateur pour attribuer une licence à l’utilisateur à partir du portail de compte.

Quand votre abonnement partage Azure AD avec d’autres services cloud associés à votre abonnement, vous avez également accès aux utilisateurs qui ont été ajoutés à ces services. Ces utilisateurs ne disposeront pas d'une licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tant que vous n'aurez pas attribué une licence à chacun d'entre eux.

> [!TIP]
> Si l’option permettant d’attribuer ou de retirer une licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] est désactivée, il se peut que votre abonnement inclue des options de licences en volume disponibles en cas d’utilisation d’[Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Consultez la documentation de vos options de licence pour plus d'informations sur l'attribution ou le retrait des licences.

## Attribuer une licence d’utilisateur Intune

Vous utilisez **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** pour ajouter manuellement des utilisateurs basés sur le cloud et attribuer des licences aux comptes d’utilisateur basés sur le cloud et aux comptes synchronisés à partir de votre annuaire Active Directory local vers Azure AD.

1.  Connectez-vous au portail de compte Intune à l’aide de vos informations d’identification d’administration de client.

2.  Sélectionnez le compte d’utilisateur auquel vous souhaitez attribuer une licence utilisateur Intune et cochez la case **Microsoft Intune** dans les propriétés du compte utilisateur.

3.  Le compte d’utilisateur est alors ajouté au groupe d’utilisateurs Microsoft Intune qui autorise l’utilisateur à utiliser le service et à inscrire ses appareils pour les gérer.

### Utiliser PowerShell pour gérer de manière sélective les licences utilisateur EMS
Les organisations qui utilisent Microsoft Enterprise Mobility Suite (EMS) peuvent avoir des utilisateurs qui ont uniquement besoin d’Azure Active Directory Premium ou des services Intune dans le package EMS. Vous pouvez attribuer un service ou un sous-ensemble de services à l’aide des [applets de commande Azure Active Directory PowerShell](https://msdn.microsoft.com/library/jj151815.aspx). 

Pour assigner de manière sélective des licences utilisateur pour les services EMS, ouvrez PowerShell en tant qu’administrateur sur un ordinateur où le [module Azure Active Directory pour Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) est installé. Vous pouvez installer PowerShell sur un ordinateur local ou sur un serveur ADFS.

Vous devez créer une nouvelle définition de référence (SKU) de licence qui s’applique uniquement aux plans de service requis. Pour ce faire, désactivez les plans que vous ne souhaitez pas appliquer. Par exemple, vous pouvez créer une définition de référence de licence qui n’attribue pas de licence Intune. Pour afficher une liste des services disponibles, tapez :
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Vous pouvez exécuter la commande suivante pour exclure le plan de service Intune. Vous pouvez utiliser la même méthode pour étendre la procédure à un groupe de sécurité entier ou vous pouvez utiliser des filtres plus granulaires. 

**Exemple 1**
Créer un nouvel utilisateur sur la ligne de commande et affecter une licence EMS sans activer la partie Intune de la licence :

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Vérification avec :

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Exemple 2**
Désactiver la partie Intune de la licence EMS pour un utilisateur qui a déjà une licence :

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Vérification avec :
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 4 du *guide de démarrage rapide Intune*.
>[!div class="step-by-step"]

>[&larr; **Synchroniser les utilisateurs avec Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organiser les utilisateurs et appareils** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->


