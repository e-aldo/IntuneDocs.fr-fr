---
title: "Nouveautés | Microsoft Docs"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2fdf4086ccf4b4f256596b7d0f7192b70a4efd2a
ms.openlocfilehash: a2f3eab11f208c0260dc4dbc245801416dc36633


---
# <a name="whats-new-in-microsoft-intune---january-2017"></a>Nouveautés de Microsoft Intune : janvier 2017
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

> [!Note]
> Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

<!--### Actions for non-compliance <!--730266
_Actions for non-compliance_ is a new feature of compliance policies that lets you take action on devices that are out of compliance. You can specify single or multiple actions and specify the time period at which those actions must occur. For example, you can notify users of non-compliant devices immediately after the devices become non-compliant through email, or you can block non-compliant devices from accessing corporate resources after a 3-day grace period via Conditional Access.-->

### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Rapports dans la console pour MAM sans inscription <!--677961-->
De nouveaux rapports de protection des applications ont été ajoutés pour les appareils inscrits et les appareils qui n’ont pas été inscrits. Vous trouverez plus d'informations sur la façon dont vous pouvez [surveiller les stratégies de gestion des applications mobiles avec Intune ici](https://docs.microsoft.com/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

<!--### Conditional access for MAM with SharePoint Online <!--679339
You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint Online.  You can get started using Intune mobile app management in the Azure portal. Look for the __Conditional Access__ section in the __Settings__ blade which will include the option for SharePoint Online. This feature will ship separately from the rest of the service release. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Prise en charge d’Android 7.1.1 <!--694397-->
Intune prend désormais entièrement en charge et gère Android 7.1.1.

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Résoudre le problème quand les appareils iOS sont inactifs ou que la console d’administration ne peut pas communiquer avec eux

Quand les appareils des utilisateurs perdent le contact avec Intune, vous pouvez leur appliquer de nouvelles étapes de dépannage pour leur permettre de récupérer l’accès aux ressources d’entreprise. Consultez [Les appareils sont inactifs ou la console d’administration ne peut pas communiquer avec eux](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="notices"></a>Remarques

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Gestion par défaut des appareils de bureau Windows via les paramètres Windows <!--663050-->
Le comportement par défaut pour l’inscription d'ordinateurs de bureau Windows 10 change. Les nouvelles inscriptions se feront via le flux d'inscription d'agent MDM classique plutôt que via l’agent PC.

Le site Web du portail d’entreprise fournira aux utilisateurs d'ordinateurs de bureau Windows 10 des instructions d’inscription qui les guideront tout au long du processus d’ajout d’ordinateurs de bureau Windows 10 comme appareils mobiles. Cela n’affectera pas les ordinateurs actuellement inscrits, et votre organisation pourra toujours gérer des ordinateurs de bureau Windows 10 à l’aide de l’agent PC [si vous préférez](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

<!--### Company Portal for iOS links open inside the app <!--665954
Links inside of the Company Portal app for iOS, including those to documentation and apps, will open directly in the Company Portal app using an in-app view of Safari. This update will ship separately from the service update in January.-->

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Amélioration de la prise en charge de la gestion des applications mobiles pour la réinitialisation sélective <!--581242-->
Les utilisateurs finaux recevront des instructions supplémentaires sur la façon de récupérer l’accès aux données professionnelles ou scolaires si ces données sont supprimées automatiquement en raison de la stratégie de « Intervalle en mode hors connexion avant la réinitialisation des données d’application ».<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="new-documentation-for-app-protection-policies---583398--"></a>Nouvelle documentation pour les stratégies de protection des applications <!--583398-->
Nous avons mis à jour notre documentation pour les administrateurs et les développeurs d'applications qui souhaitent activer les stratégies de protection des applications (appelées stratégies MAM) dans leurs applications iOS et Android à l’aide de l'outil de création de package de restrictions d’application Intune ou du SDK d’application Intune.

Les articles suivants ont été mis à jour :

* [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune)
* [Préparer des applications iOS pour la gestion des applications mobiles avec l’outil de création de package de restrictions d’application Intune](https://docs.microsoft.com/intune/deploy-use/prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool)
* [Prise en main du Kit de développement logiciel (SDK) d’applications Microsoft Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-get-started)
* [Guide du Kit de développement logiciel (SDK) d’applications Intune pour les développeurs iOS](https://docs.microsoft.com/intune/develop/intune-app-sdk-ios)

Les articles suivants constituent de nouveaux ajouts à la bibliothèque de documents :

* [Plug-in Cordova du SDK d’application Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-cordova)
* [Composant Xamarin du SDK d’application Intune](https://docs.microsoft.com/intune/develop/intune-app-sdk-xamarin)

<!--### Progress bar when launching the Company Portal on iOS <!--665978
The Company Portal for iOS is introducing a progress bar on the launch screen to provide the user with information about the loading processes that occur. There will be a phased rollout of the progress bar to replace the spinner. This means that some of your users will see the new progress bar while others will continue to see the spinner.-->

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nouveautés de la préversion publique de l’expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Vous pouvez découvrir les nouveautés de la préversion Intune dans Azure [ici](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de la préversion Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Archive des nouveautés](whats-new-archive.md)



<!--HONumber=Jan17_HO2-->


