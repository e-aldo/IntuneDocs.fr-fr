---
title: "Affecter des licences Intune | Microsoft Docs"
description: Attribuer des licences aux utilisateurs de votre abonnement Intune
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 03/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 7db42e591df8ec6c21f73b7ce49be624e1e29690
ms.openlocfilehash: 793df9f3734b84c74ecac9b8192d0b06306607e8
ms.contentlocale: fr-fr
ms.lasthandoff: 05/02/2017


---

# <a name="assign-intune-licenses-to-your-user-accounts"></a>Affecter des licences Intune à vos comptes d’utilisateur

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Que vous ajoutiez des utilisateurs manuellement, ou procédiez à une synchronisation depuis un annuaire Active Directory local, vous devez d’abord affecter une licence Intune à chaque utilisateur et ce, avant qu’il n’inscrive ses appareils dans Intune.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Affecter une licence Intune dans le centre d’administration Office 365

Vous pouvez utiliser le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pour ajouter manuellement des utilisateurs basés sur le cloud et affecter des licences aux comptes d’utilisateur basés sur le cloud et aux comptes synchronisés depuis votre annuaire Active Directory local vers Azure AD.

1.  Connectez-vous au [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) à l’aide de vos informations d’identification d’administrateur du locataire, puis sélectionnez **Utilisateurs** > **Utilisateurs actifs**.

2.  Sélectionnez le compte d’utilisateur auquel vous souhaitez affecter une licence d’utilisateur Intune, puis choisissez **Licences du produit** > **Modifier**.

3.  Activez la fonction **Intune** ou **Enterprise Mobility + Security** en la définissant sur **Activé**, puis choisissez **Enregistrer**.

4. Maintenant, le compte d’utilisateur dispose des autorisations permettant d’utiliser le service et d’inscrire des appareils dans la fonction de gestion.

> [!NOTE]
> Les utilisateurs apparaissent dans la console d’administration une fois qu’ils ont inscrit un appareil. En outre, vous pouvez sélectionner un groupe d’utilisateurs afin de les modifier tous en même temps, en sélectionnant l’ajout ou le remplacement d’une licence pour tous les utilisateurs sélectionnés.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Utiliser School Data Sync pour affecter des licences aux utilisateurs dans Intune pour l’Éducation
Si vous êtes une entreprise de formation, vous pouvez utiliser SDS (School Data Sync) pour affecter des licences Intune pour l’Éducation aux utilisateurs synchronisés. Sélectionnez simplement la case à cocher Intune pour l’Éducation quand vous configurez votre profil SDS.  

![Image du paramètre de profil SDS](./media/i4e-sds-profile-setup-setting.png)

Quand vous affectez une licence Intune pour l’Éducation, vérifiez que la licence Intune A Direct est également affectée.

![Image de la configuration des licences des produits](./media/i4e-set-licenses.png)

Pour en savoir plus sur SDS, consultez cette [vue d’ensemble de School Data Sync](https://support.office.com/en-us/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US).

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Utiliser PowerShell pour gérer de manière sélective les licences utilisateur EMS
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

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Vérification avec :

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Synchroniser les utilisateurs avec Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organiser les utilisateurs et les appareils** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  

