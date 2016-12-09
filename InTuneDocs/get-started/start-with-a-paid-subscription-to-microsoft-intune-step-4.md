---
title: "Gérer les licences Intune | Microsoft Intune"
description: Attribuer des licences aux utilisateurs de votre abonnement Intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: f0f9d60a27afa580aaba8a3c24fff6325ae53f08


---

# <a name="manage-intune-licenses"></a>gérer les licences Intune
Pour que les utilisateurs puissent se connecter pour utiliser le service Intune ou inscrire leurs appareils dans la gestion, vous devez d’abord leur attribuer à chacun une licence dans votre abonnement Intune via le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854).

Les organisations qui utilisent Microsoft Enterprise Mobility + Security (EMS) peuvent avoir des utilisateurs qui ont uniquement besoin d’Azure Active Directory Premium ou des services Intune dans le package EMS. Vous pouvez attribuer un service ou un groupe de services à l’aide des [applets de commande Azure Active Directory PowerShell](https://msdn.microsoft.com/library/jj151815.aspx). Pour plus d’informations, consultez [Gérer les licences Intune avec PowerShell](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## <a name="how-intune-licenses-are-assigned"></a>Mode d’attribution des licences Intune
Lorsque les comptes d’utilisateur sont synchronisés à partir de votre annuaire Active Directory local ou ajoutés manuellement à votre abonnement aux services cloud par le biais du [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), ils ne reçoivent pas automatiquement une licence Intune. Au lieu de cela, un administrateur Intune doit modifier le compte d’utilisateur à une date ultérieure pour attribuer une licence à l’utilisateur à partir du portail Office 365.

Quand votre abonnement partage Azure AD avec d’autres services cloud associés à votre abonnement, vous avez également accès aux utilisateurs qui ont été ajoutés à ces services. Ces utilisateurs ne disposeront pas d'une licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] tant que vous n'aurez pas attribué une licence à chacun d'entre eux.

> [!TIP]
> Si l’option permettant d’attribuer ou de retirer une licence [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] est désactivée, il se peut que votre abonnement inclue des options de licences en volume disponibles en cas d’utilisation d’[Enterprise Mobility Suite + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Consultez la documentation de vos options de licence pour plus d'informations sur l'attribution ou le retrait des licences.

## <a name="assign-an-intune-user-license"></a>Attribuer une licence d’utilisateur Intune

Vous utilisez le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pour ajouter manuellement des utilisateurs basés sur le cloud et attribuer des licences aux comptes d’utilisateur basés sur le cloud et aux comptes synchronisés à partir de votre annuaire Active Directory local vers Azure AD.

1.  Connectez-vous au [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) à l’aide de vos informations d’identification d’administrateur du locataire, puis sélectionnez **Personnes** > **Tous les utilisateurs**.

2.  Sélectionnez le compte d’utilisateur auquel vous souhaitez attribuer une licence utilisateur Intune, puis sélectionnez **Microsoft Intune** (autonome) ou **Enterprise Mobility Suite**.

3.  Maintenant, le compte d’utilisateur dispose des autorisations nécessaires pour utiliser le service et inscrire des appareils dans la gestion.

> [!NOTE]
> Les utilisateurs apparaissent dans la console une fois qu’ils ont inscrit un appareil.

### <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Utiliser PowerShell pour gérer de manière sélective les licences utilisateur EMS
Les organisations qui utilisent Microsoft Enterprise Mobility + Security (anciennement Entreprise Mobility Suite) peuvent avoir des utilisateurs qui ont uniquement besoin d’Azure Active Directory Premium ou des services Intune dans le package EMS. Vous pouvez attribuer un service ou un groupe de services à l’aide des [applets de commande Azure Active Directory PowerShell](https://msdn.microsoft.com/library/jj151815.aspx).

Pour assigner de manière sélective des licences utilisateur pour les services EMS, ouvrez PowerShell en tant qu’administrateur sur un ordinateur où le [module Azure Active Directory pour Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) est installé. Vous pouvez installer PowerShell sur un ordinateur local ou sur un serveur ADFS.

Vous devez créer une nouvelle définition de référence (SKU) de licence qui s’applique uniquement aux plans de service requis. Pour ce faire, désactivez les plans que vous ne souhaitez pas appliquer. Par exemple, vous pouvez créer une définition de référence de licence qui n’attribue pas de licence Intune. Pour afficher une liste des services disponibles, tapez :

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Vous pouvez exécuter la commande suivante pour exclure le plan de service Intune. Vous pouvez utiliser la même méthode pour étendre la procédure à un groupe de sécurité entier ou vous pouvez utiliser des filtres plus granulaires.

**Exemple 1**<br>
Créer un nouvel utilisateur sur la ligne de commande et affecter une licence EMS sans activer la partie Intune de la licence :

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Vérification avec :

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Exemple 2**<br>
Désactiver la partie Intune de la licence EMS pour un utilisateur qui a déjà une licence :

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

Vérification avec :

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Synchroniser les utilisateurs avec Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organiser les utilisateurs et les appareils** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Dec16_HO2-->


