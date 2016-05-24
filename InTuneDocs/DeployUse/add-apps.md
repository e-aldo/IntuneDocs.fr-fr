---
# required metadata

title: Ajouter des applications | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b770f4f-6d36-41e4-b535-514b46e29aaa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ajouter des applications avec Microsoft Intune
Avant de commencer à déployer des applications avec Microsoft Intune, vous devez vous familiariser avec les concepts présentés dans cette rubrique. Ils vous aideront à identifier les applications que vous pouvez déployer sur les différentes plateformes, et à comprendre les conditions préalables.

## Types d’applications que vous pouvez déployer avec Intune
Vous pouvez déployer des applications vers tous les types d’appareils pris en charge par Intune. Selon le type d’application que vous voulez déployer, les processus et les appareils pris en charge diffèrent. Le tableau suivant vous aide à comprendre ce que vous pouvez ou non déployer :


### **Windows Installer (&#42;.exe, &#42;.msi)**
- Ce type d’application doit prendre en charge une installation sans assistance et sans entrée utilisateur. La documentation de votre application doit inclure les options de ligne de commande appropriées pour installer l’application sans assistance (par exemple **/q**).
- Tous les fichiers et dossiers supplémentaires requis par le programme d'installation de l'application doivent être disponibles à l'emplacement que vous spécifiez pour les fichiers d'installation de l'application.
- Dans la plupart des cas, les fichiers Windows Installer (.msi) et les fichiers du correctif Windows Installer (.msp) ne nécessitent pas d’arguments de ligne de commande pour être installés par Intune. Consultez la documentation de votre application. Si des arguments de ligne de commande sont requis, vous devez les entrer sous la forme de paires Nom=Valeur (telles que TRANSFORMS=custom_transform.mst).

Ce type d’application est chargé dans votre espace de stockage cloud.
### **Package d’application pour Android (fichier &#42;.apk)**
Ce type d’application est chargé dans votre espace de stockage cloud.
### **Package d’application pour iOS (fichier &#42;.ipa)**
- Pour déployer des applications iOS, vous devez disposer d’un package .ipa valide.
- Le package .ipa doit être signé par Apple et la date d’expiration indiquée dans le profil de configuration doit être valide. Intune peut distribuer des applications iOS de certificat d’entreprise. Toutes les applications de certificat du développeur Apple ne sont pas prises en charge.
- Votre entreprise doit être inscrite au programme iOS Developer Enterprise Program.
- Assurez-vous que le pare-feu de votre organisation autorise l'accès aux sites Web de mise en service et de certification iOS.
- Un fichier manifeste (.plist) n’est pas requis pour être déployé avec l’application.

Ce type d’application est chargé dans votre espace de stockage cloud.

Actuellement, les utilisateurs finaux ne peuvent pas installer des applications d'entreprise à partir de l'application de portail d'entreprise Intune pour iOS. Cela est dû à des restrictions placées sur des applications sont publiées dans l'App Store iOS (voir [directives de révision App Store](https://developer.apple.com/app-store/review/guidelines/)). Les utilisateurs peuvent accéder aux applications d’entreprise (y compris les applications gérées de l’App Store et les packages d’application métier) en lançant l’application Portail d’entreprise sur leur appareil et en sélectionnant la vignette Applications d’entreprise, qui ouvre le navigateur et les redirige vers le portail web d’Intune.

### **Package d’application Windows Phone (&#42;.xap, .appx, .appxbundle)**
- Pour déployer des applications, vous aurez besoin d’un certificat de signature de code mobile d’entreprise. Pour plus d’informations, consultez [Configurer la gestion de Windows Phone avec Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md).

Ce type d’application est chargé dans votre espace de stockage cloud.

Vous trouverez ci-dessous des informations sur l’installation d’applications de plateforme Windows universelle (UWP) métier avec Intune.

### **Package d'application Windows (.appx, .appxbundle)**
- Pour déployer des applications, vous aurez besoin d’un certificat de signature de code mobile d’entreprise. Pour plus d’informations, consultez [Configurer la gestion des appareils Windows avec Microsoft Intune](set-up-windows-device-management-with-microsoft-intune.md).

Ce type d’application est chargé dans votre espace de stockage cloud.
### **Windows Installer par le biais de la gestion des appareils mobiles (&#42;.msi)**
Ce type de programme d’installation vous permet de créer et de déployer des applications Windows Installer sur des PC inscrits qui exécutent Windows 10.<br /><br />Tenez compte des points suivants quand vous utilisez ce type de programme d’installation :
- Vous ne pouvez charger qu’un seul fichier avec l’extension .msi.
- Le code de produit et la version de produit du fichier sont utilisés pour la détection d’applications.
- Le comportement de redémarrage par défaut de l’application sera utilisé. Intune ne contrôle pas ceci.
- Les packages MSI par utilisateur sont installés pour un utilisateur unique.
- Les packages MSI par ordinateur sont installés pour tous les utilisateurs sur l’appareil.
- Les packages MSI en mode double sont actuellement installés uniquement pour tous les utilisateurs sur l’appareil.
- Les mises à jour d’application sont prises en charge quand les codes de produit MSI de toutes les versions sont identiques.

Ce type d’application est chargé dans votre espace de stockage cloud.
### **Lien externe**
Utilisé quand vous avez :
- **URL** qui permet aux utilisateurs de télécharger une application à partir d’une boutique d’applications.
- **Lien** vers une application web qui s’exécute à partir du navigateur web.

Les applications basées sur les liens externes ne sont pas stockées dans votre espace de stockage cloud Intune.
### **Application iOS gérée à partir de l'App Store**
Vous permet de gérer et de déployer des applications iOS gratuites à partir de l’App Store. Vous permet également d’associer des [stratégies de gestion des applications mobiles](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) à des [applications compatibles](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) et de consulter leur état dans la console Administrateur.<br /><br />Les applications iOS gérées ne sont pas stockées dans votre espace de stockage cloud Intune.
> [!TIP]
> Les options pour les appareils mobiles ne sont pas disponibles tant que vous n’avez pas [configuré Intune comme autorité de gestion des appareils mobiles](get-ready-to-enroll-devices-in-microsoft-intune.md).

## Prise en charge des applications de plateforme Windows universelle (UWP)
Les appareils Windows 10 n’ont pas besoin d’une clé de sideloading pour installer des applications métier. Cependant, la clé de Registre **HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Appx\AllowAllTrustedApps** doit avoir la valeur **1** pour activer le chargement indépendant.

Si cette clé de Registre n’est pas configurée, Intune lui attribue automatiquement la valeur **1** la première fois que vous déployez une application sur l’appareil. Si vous avez défini la valeur **0**, Intune ne peut pas modifier automatiquement la valeur et le déploiement d’applications métier échoue.

Les applications métier de plateforme Windows universelle doivent être signées avec un certificat de code de signature approuvé sur chaque appareil sur lequel l’application est déployée. Vous pouvez utiliser des certificats issus d’une infrastructure PKI interne ou un certificat issu d’un certificat racine public tiers installé sur l’appareil.

Sur les appareils Windows 10 Mobile, vous pouvez utiliser un certificat de code de signature non Symantec pour signer les applications **.appx** universelles. Pour les applications **.appx**, mais aussi les packages **.appx** générés pour Windows Phone 8.1 que vous voulez installer sur des appareils Windows 10 Mobile, vous devez utiliser un certificat de signature de code Symantec.

## Étapes suivantes 

Ensuite, vous devez ajouter les applications à la console Intune avant de les déployer. Vous pouvez ajouter des applications pour des [appareils inscrits](add-apps-for-mobile-devices-in-microsoft-intune.md) ou pour des [PC Windows que vous gérez avec le logiciel client Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

<!--HONumber=May16_HO1-->


