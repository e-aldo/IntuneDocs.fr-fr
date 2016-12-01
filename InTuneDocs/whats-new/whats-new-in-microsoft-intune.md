---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8e88c14ad77d8fe1b4c0fe2e7676d126e6288146
ms.openlocfilehash: bcd77b751c2059131558e1cbfeebd4d3f71086e5


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Nouveautés de Microsoft Intune : novembre 2016
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

<!--### New Microsoft Intune Company Portal App for Windows 10 Devices
Microsoft is releasing a new Intune Company Portal for Windows 10 devices. This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike - while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store. It will also be available for sideloading.-->

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Une mise à jour sur Intune et Android for Work__

> Alors que vous pouvez déployer des applications Android for Work avec l’action __Obligatoire__, vous pouvez uniquement déployer les applications __disponibles__ si vos groupes Intune ont migré vers la nouvelle expérience Azure AD pour les groupes.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Le SDK d’application Intune pour le plug-in Cordova prend maintenant en charge la gestion des applications mobiles (GAM) sans inscription
Les développeurs d’applications peuvent maintenant utiliser le plug-in Cordova du SDK d’application Intune pour activer la fonctionnalité GAM sans inscription d’appareils dans leurs applications Cordova pour Android et iOS. Vous trouverez le plug-in Cordova du SDK d’application Intune [ici](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Le composant Xamarin du SDK d’application Intune prend maintenant en charge la gestion des applications mobiles (GAM) sans inscription
Les développeurs d’applications peuvent maintenant utiliser le composant Xamarin du SDK d’application Intune pour activer la fonctionnalité GAM sans inscription d’appareils dans leurs applications Xamarin pour Android et iOS. Vous pouvez trouver le composant Xamarin du SDK d’application Intune [ici](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Remarques

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>Le certificat de signature Symantec n’a plus besoin du portail d’entreprise Windows Phone 8 signé pour le chargement
Le chargement du certificat de signature Symantec n’a plus besoin de l’application Portail d’entreprise Windows Phone 8 signée. Le certificat peut être chargé séparément.

## <a name="deprecations"></a>Dépréciations

### <a name="support-for-the-windows-phone-8-company-portal"></a>Prise en charge du portail d’entreprise Windows Phone 8
La prise en charge du portail d’entreprise Windows Phone 8 est désormais dépréciée. La prise en charge des plateformes Windows Phone 8 et WinRT a été dépréciée en octobre 2016. La prise en charge du portail d’entreprise Windows 8 a également été dépréciée en octobre 2016.


### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Versions Release précédentes d’Intune](whats-new-archive.md)



<!--HONumber=Nov16_HO3-->


