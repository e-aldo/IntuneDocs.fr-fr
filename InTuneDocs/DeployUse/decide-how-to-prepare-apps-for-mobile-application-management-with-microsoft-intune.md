---
title: "Préparer les applications pour la gestion d’applications mobiles | Microsoft Intune"
description: "Cette rubrique présente des informations pour vous aider à décider quand utiliser l’outil de création de package de restrictions d’application et le Kit de développement logiciel (SDK) d’application pour permettre à vos applications métier personnalisées d’utiliser les stratégies de gestion d’applications mobiles."
keywords: 
author: karthikaraman
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
ms.sourcegitcommit: 70f9fb5580b114fe1ba14a1bd05de58467d5cd00
ms.openlocfilehash: b5dd5bec0910a8ce3a940b5ed288907aba0f7ee4


---

# Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune
Vous pouvez configurer vos applications pour utiliser des stratégies de gestion des applications mobiles (GAM) à l’aide de l’outil de création de package de restrictions d’application Intune ou du Kit de développement logiciel (SDK) d’application Intune. Utilisez ces informations pour en savoir plus sur ces deux méthodes et quand les utiliser.

## Outil de création de package de restrictions d’application Intune
L’outil de création de package de restrictions d’application est utilisé principalement pour les applications métier internes. L’outil est une application de ligne de commande qui crée un wrapper autour de l’application, ce qui permet ensuite à l’application d’être gérée par une stratégie de gestion des applications mobiles Intune. Vous n’avez pas besoin du code source pour utiliser l’outil, mais vous avez besoin des informations d’identification de signature.  Pour plus d’informations sur les informations d’identification de signature, consultez le [blog Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/). Pour obtenir la documentation de l’outil de création de package de restrictions d’application, consultez [Android App Wrapping Tool](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) (Outil de création de package de restrictions d’application Android) et [iOS App Wrapping Tool](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) (Outil de création de package de restrictions d’application iOS).

L’outil de création de package de restrictions d’application ne prend pas en charge les applications de l’App Store ou du Play Store, ni les fonctionnalités qui nécessitent une intégration des temps de développement (voir le tableau comparatif des fonctions suivant).

Vous devez utiliser l’outil de création de package de restrictions d’application, plutôt que le Kit de développement logiciel (SDK), si l’application a déjà été écrite ou si le code source n’est pas disponible.

**L’outil de création de package de restrictions d’application pour la gestion des applications mobiles sur des appareils non inscrits dans Intune est pris en charge dans la préversion publique actuelle. Pour plus d’informations, consultez [Protéger les données et applications métier sur des appareils non inscrits dans Microsoft Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md)**.

### Plateformes prises en charge

|**Outil de création de package de restrictions d’application** | **Xamarin** |**Cordova** |
|------|----|----|
|**iOS** |Oui|Oui|
|**Android**| Non |Oui|
## Kit de développement logiciel (SDK) d’application Intune
Le Kit de développement logiciel (SDK) d’application est conçu principalement pour les clients qui ont des applications dans l’App Store ou dans le Play Store, et qui veulent gérer les applications avec Intune. Toute application peut cependant tirer parti de l’intégration du Kit de développement logiciel (SDK), même s’il s’agit d’une application métier.

Pour en savoir plus sur le SDK, consultez sa [présentation](/intune/develop/intune-app-sdk). Pour prendre en main le Kit de développement logiciel, consultez [Prise en main du Kit de développement logiciel (SDK) d’application Microsoft Intune](/intune/develop/intune-app-sdk-get-started).

### Plateformes prises en charge
|**Kit de développement logiciel (SDK) d’application Intune** |**Xamarin** |**Cordova**
|------|----|----|
|**iOS**|Oui : utilisez le composant Xamarin du SDK d’application Intune|Oui : utilisez le plug-in Cordova du SDK d’application Intune|
|**Android**| Oui : utilisez le composant Xamarin du SDK d’application Intune|Oui : utilisez le plug-in Cordova du SDK d’application Intune|

## Comparaison des fonctionnalités
Ce tableau répertorie les paramètres que vous pouvez utiliser pour le Kit de développement logiciel (SDK) et pour l’outil de création de package de restrictions d’application.

> [!NOTE]
> Vous pouvez utiliser l’outil de création de package de restrictions d’application avec Intune autonome ou Intune avec Configuration Manager.

|Fonction|Kit de développement logiciel (SDK) d’application|Outil de création de package de restrictions d’application|
|-----------|---------------------|-----------|
|Afficher le contenu web uniquement dans Managed Browser|X|X|
|Empêcher les sauvegardes Android, iTunes ou iCloud|X|X|
|Autoriser l'application à transférer des données vers d'autres applications|X|X|
|Autoriser l'application à recevoir des données d'autres applications|X|X|
|Restreindre les opérations couper, copier et coller avec d'autres applications|X|X|
|Demander un code confidentiel simple pour l'accès|X|X|
|Remplacer le code confidentiel intégré de l’application par le code confidentiel Intune|X||
|Spécifier le nombre de tentatives avant réinitialisation du code confidentiel|X|X|
|Exiger une empreinte digitale à la place du code confidentiel (iOS uniquement)<br></br>**Remarque :** disponible seulement dans les environnements GAM uniquement.|X||
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
### Voir aussi

[Outil de création de package de restrictions d’application Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Outil de création de package de restrictions d’application iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md)</br>
[Utiliser le Kit de développement logiciel (SDK) pour activer des applications pour la gestion des applications mobiles](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Sep16_HO2-->


