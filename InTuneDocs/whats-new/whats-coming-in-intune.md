---
title: "Edition anticipée | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a5c4b0f15456a9f24c95954d669a17c63f96a459
ms.openlocfilehash: 273016d4fe114bbe60e9cebc06e89584c8f91f0b


---

# Nouveautés de Microsoft Intune - Octobre
L’**édition anticipée** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Vérifiez régulièrement les mises à jour Nouveautés à venir.

Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

### Gestion de l’impression à partir d’applications gérées à l’aide de stratégies MAM
Vous pouvez maintenant empêcher l’impression de données d’entreprise à partir d’applications dotées de stratégies MAM. Ce paramètre est disponible sur le [portail Azure](..deployuse/create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) et pris en charge sur les appareils [iOS](..deployuse/ios-mam-policy-settings) et [Android](..deployuse/android-mam-policy-settings).
<!--TFS 1014328-->

### Nouveau portail d’entreprise Microsoft Intune disponible pour les appareils Windows 10
Microsoft met en ligne un nouveau portail d’entreprise Microsoft Intune pour les appareils Windows 10. Cette application, au nouveau format Windows 10 universel, fournira à l’utilisateur une expérience inédite de l’application et une expérience identique sur tous les appareils Windows 10, PC et mobiles, tout en offrant les mêmes fonctionnalités qu’aujourd’hui.

La nouvelle application permettra également aux utilisateurs de tirer parti de fonctionnalités de plateforme supplémentaires telles que l’authentification unique (SSO) et par certificat sur les appareils Windows 10. Elle sera disponible en tant que mise à niveau du portail d’entreprise Windows 8.1 actuel et du portail d’entreprise Windows Phone 8.1 installés à partir du Windows Store.
<!--TFS 1016502-->

### Support d’Android for Work

Intune fait maintenant partie du [programme Android for Work](https://enterprise.google.com/android/partners/). Nous commencerons à déployer la prise en charge des fonctionnalités d’Android for Work dans Intune dès ce mois-ci.

[Lisez l’annonce de Microsoft concernant la prise en charge d’Intune dans Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

<!---This month, some newly provisioned Intune tenants will start seeing the Android for Work features. We will announce later when existing tenants will begin to see this feature.--->
<!--TFS 1043303-->

### Compatibilité d’Android Samsung KNOX avec Intune

Intune ne gère pas certains modèles de téléphone Samsung Galaxy Ace comme des appareils Samsung KNOX. Lorsque vous inscrivez ces appareils à Intune, ils sont gérés comme des appareils Android standard.
Les références de modèle concernées sont :

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Aucune autre action n’est requise de votre part ou de celle de vos utilisateurs.
Pour plus d’informations, consultez le site web [Samsung KNOX](https://www.samsungknox.com).

<!--TFS 1173566 iX blurb provided by Barry; requires PM signoff

### Multi-factor authentication for Android and iOS enrollment

In addition to Windows 8.1 and later, administrators can now enable multi-factor authentication for Android and iOS devices in the Microsoft Intune Enrollment application. -->    

### Arrêt de la prise en charge de l’application du portail d’entreprise pour Windows 8, ainsi que des plateformes Windows Phone 8 et Windows RT
Dès octobre 2016, Microsoft Intune ne prendra plus en charge le portail d’entreprise Windows 8. Microsoft Intune ne prendra également plus en charge les plateformes Windows Phone 8 et Windows RT. Ainsi, vous ne pourrez plus inscrire ni mettre à jour des appareils Windows Phone 8 ou Windows RT.

Néanmoins, vous pourrez continuer à gérer les appareils Windows Phone 8, Windows RT et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.

Dès novembre 2016, la prise en charge du portail d’entreprise Windows Phone 8 ne sera plus assurée.
<!--TFS 1255391-->

### Accès conditionnel à la gestion des applications mobiles
Vous pouvez maintenant créer une stratégie d’accès conditionnel pour empêcher les applications mobiles non gérées d’accéder à [Exchange Online](..deployuse/restrict-access-to-exchange-online-with-microsoft-intune.md) et [SharePoint Online](..deployuse/restrict-access-to-sharepoint-online-with-microsoft-intune.md). Vous pouvez bloquer les applications et clients intégrés dans lesquels la fonctionnalité MAM n’est pas activée avec le kit de développement logiciel (SDK) d’applications Intune.  Pour ce faire, créez une stratégie d’accès conditionnel et spécifiez les applications qui doivent avoir accès à Exchange Online et SharePoint Online à l’aide du portail Azure.
<!--TFS 1317673-->

<!--TFS 1318014; awaiting approval in notes as to whether to proceed

### "Default" policy is deprecated

To minimize unintentionally assigned profiles, Intune is removing support for the "default" Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers in the new Azure console. Serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.  A profile must be assigned manually after synchronization. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

<!--TFS 1318023; awaiting approval in notes as to whether to proceed

### Deprecation of row-by-row iOS Details review for iOS device CSV uploads

In order to streamline uploading IMEI numbers for Corporate devices and Apple serial numbers for Configurator enrollment, Intune is removing the row by row review of hardware identifiers already found in the system. This review allows the IT Pro to accept associated Details from the CSV to overwrite the existing details for a hardware identifier already in the system. The review will be replaced by a single option to automatically overwrite Details for all hardware identifiers or ignore new details for existing identifiers. This change will apply to the new console only. Until the existing Admin console is retired, no change will take place.
-->

### Intégration de la protection Lookout pour les appareils Android
En octobre, Microsoft intègre la solution de Lockout qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et d’autres menaces. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur leurs appareils, l’activer et corriger les menaces signalées par celles-ci pour accéder aux données d’entreprise.
<!--TFS 1319493-->

### Kit développement logiciel (SDK) d’applications Intune et outil de création de package de restrictions d’application Microsoft Intune pour Android
Vous pouvez configurer vos applications pour utiliser des stratégies de gestion des applications mobiles (MAM) à l’aide du Kit de développement logiciel (SDK) d’applications Intune ou de l’outil de création de package de restrictions d’application Intune. Les nouvelles mises à jour de l’outil de création de packages de restrictions d’application et du Kit de développement logiciel (SDK) incluront :

* la prise en charge d’Android N ;
* la prise en charge des stratégies MAM d’Intune sans nécessiter l’inscription d’appareils ;
* la prise en charge d’applications Android basées sur Xamarin.

Vous pouvez tester MAM sans prendre en charge Xamarin et l’inscription d’appareils dans la version préliminaire publique de l’outil de création de packages de restrictions d’application Android : [https://github.com/msintuneappsdk/intune-app-wrapper-android-preview](https://github.com/msintuneappsdk/intune-app-wrapper-android-preview)
<!--TFS 1319511; please create new TFS entry for WN text associated with this TFS item-->

<!--TFS 1319613; no iX review on PM text blurb

### Private preview customers using MAM Conditional Access will have their policies reset

Due to changes in the policy structure for Conditional Access for Mobile App Management, any existing policies that were set by customers through the private preview will be removed. Customers will need to set new policies once the change is made. The timing will coincide with the October service update.
-->

### Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.



<!--HONumber=Oct16_HO1-->


