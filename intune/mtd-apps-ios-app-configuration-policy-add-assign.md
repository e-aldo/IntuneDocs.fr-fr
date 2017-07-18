---
title: Ajouter et affecter des applications MTD dans Intune
titleSuffix: Intune on Azure
description: "Ajouter des applications MTD, l’application Microsoft Authenticator et une stratégie de configuration iOS dans Intune sur Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Ajouter et affecter des applications Mobile Threat Defense (MTD) avec Intune

Vous pouvez utiliser Intune pour ajouter et déployer des applications MTD afin que les utilisateurs finaux puissent recevoir des notifications quand une menace est identifiée sur leurs appareils mobiles et recevoir des conseils pour contrer les menaces.

Pour les appareils iOS, vous avez besoin de [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) pour que l’identité des utilisateurs puisse être vérifiée par Azure AD. Vous avez aussi besoin de la stratégie de configuration d’application iOS qui indique l’application iOS MTD à utiliser avec Intune.

> [!TIP]
> Le portail d’entreprise Intune fonctionne en tant que service broker sur les appareils Android, pour que l’identité des utilisateurs puisse être vérifiée par Azure AD.

## <a name="before-you-begin"></a>Avant de commencer

-   Les étapes ci-dessous doivent être effectuées dans le [portail Azure](https://portal.azure.com/).

-   Vérifiez que vous êtes familiarisé avec ce processus :

    -   [Ajout d’une application dans Intune](apps-add.md).

    -   [Ajout d’une stratégie de configuration d’applications iOS dans Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Affectation d’une application avec Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Ajout d’une stratégie de configuration d’application iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Pour ajouter des applications

### <a name="skycure-app-for-android"></a>Application Skycure pour Android

- Consultez les instructions relatives à [l’ajout d’applications de l’App Store Android à Microsoft Intune](store-apps-android.md). Utilisez cette [URL d’App Store Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) à **l’étape 7**.

### <a name="skycure-app-for-ios"></a>Application Skycure pour iOS

- Consultez les instructions relatives à [l’ajout d’applications de l’App Store iOS à Microsoft Intune](store-apps-ios.md). Utilisez cette [URL d’App Store Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) à **l’étape 5** dans la section **Configurer les informations sur l’application**.

### <a name="microsoft-authenticator-app-for-ios"></a>Application Microsoft Authenticator pour iOS

- Consultez les instructions relatives à [l’ajout d’applications de l’App Store iOS à Microsoft Intune](store-apps-ios.md). Utilisez cette [URL d’App Store Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) à **l’étape 5** dans la section **Configurer les informations sur l’application**.

### <a name="lookout-for-work-android-app"></a>Application Android Lookout for Work

- Consultez les instructions relatives à [l’ajout d’applications de l’App Store Android à Microsoft Intune](store-apps-android.md). Utilisez cette [URL d’App Store Google Lookout for work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) à **l’étape 7**.

### <a name="lookout-for-work-ios-app"></a>Application iOS Lookout for Work

- Consultez les instructions relatives à [l’ajout d’applications de l’App Store iOS à Microsoft Intune](store-apps-ios.md). Utilisez cette [URL d’App Store iOS Lookout for Work](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) à **l’étape 5** dans la section **Configurer les informations sur l’application**.

### <a name="lookout-for-work-app-outside-the-apple-store"></a>Application Lookout for Work en dehors de l’Apple Store

Vous devez resigner l’application iOS Lookout for Work. Lookout distribue son application iOS Lookout for Work en dehors de l’App Store iOS. Avant de distribuer l’application, vous devez resigner l’application avec votre certificat de développeur d’entreprise iOS.

Pour obtenir des instructions détaillées pour resigner des applications iOS Lookout for Work, consultez [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) (Processus pour resigner des applications iOS Lookout for Work) sur le site web de Lookout.

#### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Activer l’authentification Azure AD pour l’application iOS Lookout for Work

Activez l’authentification Azure Active Directory pour les utilisateurs iOS de la manière suivante :

1. Accédez au [portail Azure](https://portal.sazure.com), connectez-vous avec vos informations d’identification, puis accédez à la page d’application.
  
2. Ajoutez l’**application iOS Lookout for Work**  comme **application cliente native**.

3. Remplacez **com.lookout.enterprise.nom_de_votre_entreprise** par l’ID d’ensemble client que vous avez sélectionné quand vous avez signé le package IPA.

4.  Ajouter un URI de redirection supplémentaire : **&lt;companyportal://code/>** suivi d’une version encodée URL de votre URI de redirection d’origine.

5.  Ajoutez **Autorisations déléguées** à votre application.

    > [!NOTE] 
    > Pour plus d’informations, consultez [Configurer une application cliente native avec Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

#### <a name="add-the-lookout-for-work-ipa-file"></a>Ajouter le fichier ipa Lookout for Work

- Chargez le fichier .ipa resigné comme décrit dans la rubrique [Ajouter des applications métier iOS avec Intune](lob-apps-ios.md). Vous devez aussi définir la version de système d’exploitation minimale sur iOS version 8.0 ou ultérieure.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Pour associer l’application MTD à une stratégie de configuration d’application iOS

### <a name="for-skycure"></a>Pour Skycure

-   Utilisez le même compte Azure AD configuré précédemment dans la console de gestion Skycure, qui doit être le même compte utilisé pour vous connecter à la console classique Intune.

-   Vous devez disposer du fichier d’intégration Skycure prêt à l’emploi. Il s’agit du fichier .zip téléchargé précédemment à partir de la console de gestion Skycure, qui contient le fichier **skycure\_configuration.plist** avec les paramètres de stratégie de configuration d’applications iOS.

- Consultez les instructions [d’utilisation de stratégies de configuration d’application Microsoft Intune pour iOS](app-configuration-policies-use-ios.md) pour ajouter la stratégie de configuration d’application iOS Skycure.
    - À l’étape 8, utilisez l’option **Entrer des données XML**, copiez le contenu à partir du fichier **skycure_configuration.plist** et collez son contenu dans le corps de la stratégie de configuration.

Vous pouvez également copier le contenu de **skycure_configuration.plist** à partir de cet emplacement :

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-lookout"></a>Pour Lookout

- Créez la stratégie de configuration d’application iOS comme décrit dans la rubrique [Utilisation de la stratégie de configuration d’application iOS](app-configuration-policies-use-ios.md).

## <a name="to-assign-mtd-apps"></a>Pour affecter des applications MTD

- Consultez les instructions relatives à [l’affectation des applications à des groupes avec Intune](apps-deploy.md).

## <a name="next-steps"></a>Étapes suivantes

[Configurer l’intégration de Skycure avec Intune](skycure-mtd-connector-integration.md)
[Configurer l’intégration de Lookout avec Intune](lookout-mtd-connector-integration.md)
