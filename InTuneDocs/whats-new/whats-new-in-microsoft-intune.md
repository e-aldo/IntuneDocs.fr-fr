---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 503719953031bf5079b2bf5bc84a0497d708f79a
ms.openlocfilehash: 730809e0841a248b90f5fe157f2c6338bfd32b2d


---
# Nouveautés de Microsoft Intune : octobre 2016
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## Nouveautés

### Accès conditionnel à la gestion des applications mobiles
Vous pourrez restreindre l’accès à Exchange Online en autorisant uniquement l’accès à partir d’applications qui prennent en charge les stratégies Intune de gestion des applications mobiles, comme Outlook. [Cette nouvelle fonctionnalité](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) est complémentaire des stratégies Intune de gestion des applications mobiles (GAM), car vous pouvez bloquer l’accès aux clients de messagerie intégrés ou autres applications qui n’ont pas été configurés avec les stratégies Intune GAM. Cela permet de vous assurer que tous les utilisateurs accèdent aux données de votre organisation à l’aide d’applications qui peuvent être protégées avec la gestion des applications mobiles Intune. Vous pouvez démarrer la gestion des applications mobiles Intune via le Portail Azure, dans la nouvelle section Accès conditionnel du panneau « Paramètres ».

### Accès conditionnel pour les PC Windows
Vous pouvez maintenant créer des stratégies d’accès conditionnel via la console d’administration Intune pour bloquer l’accès des PC Windows à [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) et à [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Vous pouvez également créer des stratégies d’accès conditionnel pour bloquer l’accès à des applications de bureau Office et à des applications universelles.

### Support d’Android for Work
Intune fait maintenant partie du programme Android for Work. Nous commencerons à déployer la prise en charge des fonctionnalités d’Android for Work dans Intune dès ce mois-ci.
[Lisez l’annonce de Microsoft concernant la prise en charge d’Intune dans Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Les rubriques Intune suivantes sont nouvelles ou sont mises à jour avec des informations relatives à Android for Work :

Pour les informaticiens :
- [Configurer Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Restreindre l’accès à la messagerie Exchange Online et Exchange Online Dedicated (nouvel environnement) avec Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restreindre l’accès à la messagerie Exchange sur site et Exchange Online Dedicated (environnement hérité) avec Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Paramètres de stratégie de conformité Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Comment déployer des applications Android for Work](/intune/deploy-use/android-for-work-apps)
- [Configurer des applications Android for Work avec des stratégies de configuration des applications mobiles](/intune/deploy-use/afw-app-configuration-policy)
- [Paramètres de stratégie Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Pour les utilisateurs finaux :
- [Ce qui se passe quand vous créez un profil professionnel](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Créer un profil professionnel et inscrire votre appareil dans Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### Intégration de la protection Lookout pour les appareils Android
En octobre, Microsoft intègre la solution de Lockout qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et d’autres menaces. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur leurs appareils, l’activer et corriger les menaces signalées par celles-ci pour accéder aux données d’entreprise. Découvrez comment [configurer et déployer l’application Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### Outil de création de package de restrictions d’application Intune pour Android
Vous pouvez configurer vos applications pour utiliser des stratégies de gestion des applications mobiles (GAM) à l’aide de l’outil de création de package de restrictions d’application Intune. La prise en charge des stratégies GAM d’Intune sans nécessiter l’inscription d’appareils est désormais disponible.

### Gestion de l’impression à partir d’applications gérées à l’aide de stratégies MAM
Vous pouvez maintenant empêcher l’impression de données d’entreprise à partir d’applications dotées de stratégies MAM. Ce paramètre est disponible sur le [portail Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) et pris en charge sur les appareils [iOS](/Intune/deploy-use/ios-mam-policy-settings) et [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

## Remarques

### Compatibilité d’Android Samsung KNOX avec Intune
Intune ne gère pas certains modèles de téléphone Samsung Galaxy Ace comme des appareils Samsung KNOX. Lorsque vous inscrivez ces appareils à Intune, ils sont gérés comme des appareils Android standard.

Les références de modèle concernées sont :

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Aucune autre action n’est requise de votre part ou de celle de vos utilisateurs. Pour plus d’informations, consultez le site web [Samsung KNOX](https://www.samsungknox.com).

### Arrêt de la prise en charge de l’application du portail d’entreprise pour Windows 8, ainsi que des plateformes Windows Phone 8 et Windows RT
Dès octobre 2016, Microsoft Intune ne prendra plus en charge le portail d’entreprise Windows 8. Microsoft Intune ne prendra également plus en charge les plateformes Windows Phone 8 et Windows RT. Ainsi, vous ne pourrez plus inscrire ni mettre à jour des appareils Windows Phone 8 ou Windows RT.

Néanmoins, vous pourrez continuer à gérer les appareils Windows Phone 8, Windows RT et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.

Dès novembre 2016, la prise en charge du portail d’entreprise Windows Phone 8 ne sera plus assurée.
<!--TFS 1255391-->

## Nouveautés à venir

### Nouveau portail d’entreprise Microsoft Intune disponible pour les appareils Windows 10
Microsoft met en ligne un nouveau portail d’entreprise Microsoft Intune pour les appareils Windows 10. Cette application, au nouveau format Windows 10 universel, fournira à l’utilisateur une expérience inédite de l’application et une expérience identique sur tous les appareils Windows 10, PC et mobiles, tout en offrant les mêmes fonctionnalités qu’aujourd’hui.

La nouvelle application permettra également aux utilisateurs de tirer parti de fonctionnalités de plateforme supplémentaires telles que l’authentification unique (SSO) et par certificat sur les appareils Windows 10. Elle sera disponible en tant que mise à niveau du portail d’entreprise Windows 8.1 actuel et du portail d’entreprise Windows Phone 8.1 installés à partir du Windows Store. Pour plus d’informations, consultez [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

### Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Versions précédentes d’Intune](previous-intune-releases.md)



<!--HONumber=Oct16_HO3-->


