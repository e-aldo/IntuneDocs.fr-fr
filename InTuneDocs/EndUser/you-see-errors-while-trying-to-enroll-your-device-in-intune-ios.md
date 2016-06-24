---
# required metadata

title: Des erreurs se produisent pendant l’inscription de votre appareil iOS dans Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 92a8d06d-0ecb-4912-898b-993e8eaf4e58

# optional metadata

ROBOTS: noindex
#audience:
#ms.devlang:
ms.reviewer: esmich
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Des erreurs se produisent pendant l’inscription de votre appareil iOS dans Intune

Le tableau suivant répertorie les erreurs que vous pouvez rencontrer lors de l’inscription de votre appareil iOS dans Intune. Partagez ce lien avec votre service administrateur informatique. Pour obtenir ses informations de contact, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).

|Message d’erreur|Problème|Informations à communiquer à votre administrateur informatique|
|-----------------|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
|DeviceCapReached|Vous avez trop d’appareils mobiles déjà inscrits.|L’utilisateur doit supprimer un de ses appareils mobiles actuellement inscrits à partir du portail d’entreprise, avant d’en inscrire un autre. Consultez les instructions correspondant au type d’appareil que vous utilisez : [Android](unenroll-your-device-from-intune-android.md), [iOS](unenroll-your-device-from-intune-ios), [Windows](unenroll-your-device-from-intune-windows).|
|APNSCertificateNotValid|Il existe un problème avec le certificat qui autorise votre appareil mobile à communiquer avec le réseau de votre entreprise.<br /><br />Contactez vos administrateurs informatiques en leur indiquant que vous avez reçu le message **APNSCertificateNotValid** quand vous essayez d’inscrire votre appareil mobile et qu’ils peuvent trouver comment résoudre le problème dans ce tableau.|Les Services de notifications Push Apple (APNS) offrent un canal permettant d'atteindre les appareils iOS inscrits. Si les étapes permettant d’obtenir un certificat APNs n’ont pas été effectuées ou si le certificat APNs est expiré, les tentatives d’inscription échouent et ce message apparaît.<br /><br />Passez en revue les informations sur la configuration des utilisateurs dans les rubriques [Synchroniser Active Directory et ajouter des utilisateurs à Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3) et [Organisation des utilisateurs et des appareils](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|AccountNotOnboarded|Il existe un problème avec le certificat qui autorise votre appareil mobile à communiquer avec le réseau de votre entreprise.<br /><br />Contactez vos administrateurs informatiques en leur indiquant que vous avez reçu le message **APNSNotOnboarded** quand vous essayez d’inscrire votre appareil mobile et qu’ils peuvent trouver comment résoudre le problème dans ce tableau.|Les Services de notifications Push Apple (APNS) offrent un canal permettant d'atteindre les appareils iOS inscrits. Si les étapes permettant d’obtenir un certificat APNs n’ont pas été effectuées ou si le certificat APNs est expiré, les tentatives d’inscription échouent et ce message apparaît.<br /><br />Pour plus d’informations, consultez [Configurer la gestion iOS et Mac avec Microsoft Intune](/Intune/Deployuse/set-up-ios-and-mac-management-with-microsoft-intune).|
|DeviceTypeNotSupported|Vous avez peut-être tenté une inscription en utilisant un appareil non-iOS. Le type d’appareil mobile que vous essayez d’inscrire n’est pas pris en charge.<br /><br />Vérifiez que votre appareil exécute iOS version 7.1 ou ultérieure.<br /><br />Contactez vos administrateurs informatiques en leur indiquant que vous avez reçu le message **DeviceTypeNotSupported** quand vous essayez d’inscrire votre appareil mobile et qu’ils peuvent trouver comment résoudre le problème dans ce tableau.|Vérifiez que l’appareil de votre utilisateur exécute iOS version 7.1 ou ultérieure.|
|UserLicenseTypeInvalid|Vous ne pouvez pas inscrire votre appareil mobile, car votre compte d’utilisateur n’est pas encore membre d’un groupe d’utilisateurs requis.<br /><br />Contactez vos administrateurs informatiques en leur indiquant que vous avez reçu le message **UserLicenseTypeInvalid** quand vous essayez d’inscrire votre appareil mobile et qu’ils peuvent trouver comment résoudre le problème dans ce tableau.|Pour pouvoir inscrire leurs appareils, les utilisateurs doivent être membres du groupe d’utilisateurs approprié. Ce message signifie qu’ils ont un type de licence incorrect pour l’autorité de gestion des appareils mobiles désignée. Par exemple, si Intune a été désigné comme autorité de gestion des appareils mobiles et que vous avez une licence System Center 2012 R2 Configuration Manager, vous recevez ce message d’erreur.<br /><br />Pour plus d’informations, consultez les éléments suivants :<br /><br />Consultez [Configurer la gestion iOS et Mac avec Microsoft Intune](/Intune/Deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) et passez en revue les informations sur la configuration des utilisateurs dans les rubriques [Synchroniser Active Directory et ajouter des utilisateurs à Intune](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-3 et [Organisation des utilisateurs et des appareils](/Intune/Get-Started/start-with-a-paid-subscription-to-microsoft-intune-step-5).|
|MdmAuthorityNotDefined|Votre administrateur informatique doit configurer la façon dont les appareils mobiles sont gérés dans votre entreprise.<br /><br />Contactez vos administrateurs informatiques en leur indiquant que vous avez reçu le message **MdmAuthorityNotDefined** quand vous essayez d’inscrire votre appareil mobile et qu’ils peuvent trouver comment résoudre le problème dans ce tableau.|L’autorité de gestion des appareils mobiles n’a pas été désignée dans Intune.<br /><br />Consultez l’élément 1 de la section « Étape 6 : Inscrire des appareils mobiles et installer une application » dans [Prise en main de la version d’évaluation de 30 jours de Microsoft Intune](/Intune/Understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune).|

### Voir aussi
[Using your iOS or Mac OS X device with Intune](using-your-ios-or-mac-os-x-device-with-intune.md)

<!--HONumber=Jun16_HO2-->


