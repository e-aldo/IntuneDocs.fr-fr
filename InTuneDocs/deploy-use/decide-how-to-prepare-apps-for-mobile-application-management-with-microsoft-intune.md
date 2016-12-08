---
title: "Préparer les applications pour la gestion d’applications mobiles | Microsoft Intune"
description: "Cette rubrique présente des informations pour vous aider à déterminer quand utiliser l’outil de création de package de restrictions d’application et le SDK d’application pour permettre à vos applications métier personnalisées d’utiliser les stratégies de gestion d’applications mobiles."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 29e22121-8268-48b5-a671-f940a6be1d24
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 977716dd821bf9c487db199b57130c432b008a12


---

# <a name="decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune"></a>Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune
Vous pouvez configurer vos applications pour utiliser des stratégies de gestion des applications mobiles (GAM) à l’aide de l’outil de création de package de restrictions d’application Intune ou du SDK d’application Intune. Utilisez ces informations pour en savoir plus sur ces deux méthodes et quand les utiliser.

## <a name="intune-app-wrapping-tool"></a>Outil de création de package de restrictions d’application Intune
L’outil de création de package de restrictions d’application est utilisé principalement pour les applications métier internes. L’outil est une application en ligne de commande qui crée un wrapper autour de l’application, ce qui permet ensuite à l’application d’être gérée par une stratégie GAM Intune.

Vous n’avez pas besoin du code source pour utiliser l’outil, mais vous avez besoin des informations d’identification de signature.  Pour plus d’informations sur les informations d’identification de signature, consultez le [blog Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Pour obtenir la documentation de l’outil de création de package de restrictions d’application, consultez [Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) (Outil de création de package de restrictions d’application Android) et [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) (Outil de création de package de restrictions d’application iOS).

L’outil de création de package de restrictions d’application ne prend **pas** en charge les applications de l’Apple App Store ou du Google Play Store. Il ne prend pas non plus en charge certaines fonctionnalités qui nécessitent une intégration de développement (consultez le tableau comparatif des fonctionnalités suivant).


Pour plus d’informations sur l’outil de création de package de restrictions d’application pour GAM sur les appareils qui ne sont pas inscrits dans Intune, consultez [Protéger les données et applications métier sur des appareils non inscrits dans Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).

### <a name="reasons-to-use-the-app-wrapping-tool"></a>Raisons d’utiliser l’outil de création de package de restrictions d’application :
* Votre application n’a pas de fonctionnalités de protection des données intégrées.
* Votre application est simple.
* Votre application est déployée en interne.
* Vous n’avez pas accès au code source de l’application
* Vous n’avez pas développé l’application.
* Votre application a une authentification utilisateur minimale.


### <a name="supported-app-development-platforms"></a>Plateformes de développement d’applications prises en charge

|**Outil de création de package de restrictions d’application** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Oui|Oui|
|**Android**| Non |Oui|

## <a name="intune-app-sdk"></a>Kit SDK d’application Intune
Le SDK d’application est conçu principalement pour les clients qui ont des applications dans l’Apple App Store ou dans le Google Play Store, et qui veulent gérer ces applications avec Intune. Cependant, toute application peut tirer parti de l’intégration du SDK, même s’il s’agit d’applications métier.

Pour en savoir plus sur le SDK, consultez sa [présentation](/intune/develop/intune-app-sdk). Pour commencer à utiliser le SDK, consultez [Prise en main du Kit SDK d’application Microsoft Intune](/intune/develop/intune-app-sdk-get-started).

### <a name="reasons-to-use-the-sdk"></a>Raisons d’utiliser le SDK
* Votre application n’a pas de fonctionnalités de protection des données intégrées.
* Votre application est complexe et contient de nombreuses expériences.
* Votre application est déployée dans un app store public tel que Google Play ou l’App Store d’Apple.
* Vous êtes développeur d’applications et avez les compétences techniques pour utiliser le SDK.
* Votre application présente d’autres intégrations de SDK.
* Votre application est fréquemment mise à jour.

### <a name="supported-app-development-platforms"></a>Plateformes de développement d’applications prises en charge

|**SDK d’application Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Oui : utilisez le [composant Xamarin du SDK d’application Intune](/../develop/intune-app-sdk-xamarin).|Oui : utilisez le [plug-in Cordova du SDK d’application Intune](/../develop/intune-app-sdk-cordova).|
|**Android**| Oui : utilisez le [composant Xamarin du SDK d’application Intune](/../develop/intune-app-sdk-xamarin).|Oui : utilisez le [plug-in Cordova du SDK d’application Intune](/../develop/intune-app-sdk-cordova).|

## <a name="feature-comparison"></a>Comparaison des fonctionnalités
Ce tableau répertorie les paramètres que vous pouvez utiliser pour le Kit SDK et pour l’outil de création de package de restrictions d’application.

> [!NOTE]
> Vous pouvez utiliser l’outil de création de package de restrictions d’application avec Intune autonome ou Intune avec Configuration Manager.

|Fonction|Kit SDK d’application|Outil de création de package de restrictions d’application|
|-----------|---------------------|-----------|
|Afficher le contenu web uniquement dans Managed Browser|X|X|
|Empêcher les sauvegardes Android, iTunes ou iCloud|X|X|
|Autoriser l'application à transférer des données vers d'autres applications|X|X|
|Autoriser l'application à recevoir des données d'autres applications|X|X|
|Restreindre les opérations couper, copier et coller avec d'autres applications|X|X|
|Demander un code confidentiel simple pour l'accès|X|X|
|Remplacer le code confidentiel intégré de l’application par le code confidentiel Intune|X||
|Spécifier le nombre de tentatives avant réinitialisation du code confidentiel|X|X|
|Autoriser une empreinte digitale à la place du code confidentiel |X|X|
|Exiger des informations d'identification d'entreprise pour l'accès|X|X|
|Bloquer l’exécution des applications gérées sur les appareils jailbroken ou rootés|X|X|
|Chiffrer les données de l'application|X|X|
|Revérifier les spécifications requises pour l’accès après un nombre de minutes spécifié|X|X|
|Spécifier la période de grâce hors connexion|X|X|
|Bloquer la capture d’écran (Android uniquement)|X|X|
|Réinitialisation complète|X|X|
|Réinitialisation sélective <br></br>**Remarque :** pour iOS, quand le profil de gestion est supprimé, l’application est également supprimée.|X||
|Empêcher « Enregistrer sous » |X||
|Prise en charge des identités multiples|X||
|Prise en charge de GAM sans inscription de l’appareil|X|X|
|Style personnalisable |X|||
### <a name="see-also"></a>Voir aussi

[Outil de création de package de restrictions d’application Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Outil de création de package de restrictions d’application iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Utiliser le SDK pour activer des applications pour la gestion des applications mobiles](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO5-->


