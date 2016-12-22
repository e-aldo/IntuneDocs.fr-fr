---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9fd309a10d9eb020795c5ce46df124b13dc1a006
ms.openlocfilehash: d117c929fbde4dd0a39503b8da695aa9c9ea91ad


---
# <a name="whats-new-in-microsoft-intune---december-2016"></a>Nouveautés de Microsoft Intune : décembre 2016
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

> [!Note]
> Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure--736542--"></a>Préversion publique de la nouvelle expérience d’administrateur Intune sur Azure<!--736542-->
Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph. Avant la disponibilité générale de ce portail pour tous les clients Intune, nous sommes heureux d’annoncer que nous commencerons le déploiement d’une préversion de cette nouvelle expérience d’administration ce mois-ci pour certains clients.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, découvrez toutes les nouveautés de Microsoft Intune dans le portail Azure dans notre [nouvelle documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Intégration de la gestion des dépenses de télécommunications dans la version préliminaire publique du portail Azure<!--747605-->
Nous avons commencé à afficher un aperçu de l’intégration aux services de gestion des dépenses de télécommunications au sein du portail Azure. Vous pouvez utiliser Intune pour appliquer des limites à l’utilisation des données domestiques et itinérantes. Nous allons commencer ces intégrations avec [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Authentification multifacteur sur toutes les plateformes <!--747590-->
Vous pouvez appliquer l’authentification multifacteur (MFA) sur un groupe sélectionné d’utilisateurs lorsqu’ils inscrivent un appareil iOS, Android, Windows 8.1+ ou Windows Phone 8.1+ depuis le portail de gestion Azure en configurant l’authentification MFA sur l’application de l’inscription à Microsoft Intune dans Azure Active Directory.

<!--VSO 679339, awaiting chrisgre for go-live--><!--### Conditional access for MAM with SharePoint Online
Vous pouvez empêcher les applications qui ne sont pas prises en charge par les stratégies de gestion des applications mobiles (GAM) d’accéder à SharePoint Online.  Vous pouvez commencer à l’aide de la gestion des applications mobiles Intune dans le portail Azure. Recherchez la section __Accès conditionnel__ dans le panneau __Paramètres__ qui inclut l’option pour SharePoint Online. Cette fonctionnalité sera disponible séparément du reste de la version. En savoir plus sur cette nouvelle fonctionnalité [ici](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="ability-to-restrict-mobile-device-enrollment--747596--"></a>Possibilité de limiter l’inscription des appareils mobiles<!--747596-->
Intune ajoute de nouvelles restrictions d’inscription qui contrôlent les plateformes d’appareils mobiles autorisées à être inscrites. Intune sépare les plateformes d’appareils mobiles comme iOS, MacOS, Android, Windows et Windows Mobile.
* La restriction de l’inscription d’appareils mobiles ne limite pas l’inscription des clients de PC.
* Pour iOS uniquement, il existe une option supplémentaire pour bloquer l’inscription des appareils personnels.

Intune marque tous les nouveaux appareils comme personnels, sauf si l’administrateur prend des mesures pour les marquer comme appareils d’entreprise, comme expliqué dans [cet article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Remarques

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Déplacement de l’authentification multifacteur sur l’inscription vers le portail Azure <!--VSO 750545-->
Auparavant, les administrateurs accédaient à la console Intune ou à la console Configuration Manager (antérieure à la version d’octobre 2016) pour définir l’authentification multifacteur pour les inscriptions Intune. Grâce à cette fonctionnalité mise à jour, vous pouvez désormais vous connecter au [portail Microsoft Azure](https://manage.windowsazure.com) à l’aide de vos informations d’identification Intune et configurer les paramètres de l’authentification multifacteur via Azure AD. En savoir plus sur ce point [ici](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>L’application Portail d’entreprise pour Android est désormais disponible en Chine <!--VSO 658093-->
Nous publions l’application Portail d’entreprise pour Android pour le téléchargement en Chine. En l’absence de Google Play Store en Chine, les appareils Android doivent obtenir les applications dans les places de marché des applications chinoises. L’application Portail d’entreprise pour Android sera disponible en téléchargement dans les boutiques suivantes :
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

L’application Portail d’entreprise pour Android utilise les services Google Play pour communiquer avec le service Microsoft Intune. Étant donné que les services Google Play ne sont pas encore disponibles en Chine, le traitement des tâches suivantes peut prendre jusqu’à 8 heures. 

|Console d’administration Intune| Application Portail d’entreprise Intune pour Android |Site web du portail d’entreprise Intune|   
|---|---|---|
|réinitialisation complète| Supprimer un appareil distant| Supprimer l’appareil (local et distant)|
|réinitialisation sélective| Réinitialiser l’appareil| Réinitialiser l’appareil|
|Déploiements d’applications nouvelles ou mises à jour| Installation des applications métier disponibles| Réinitialisation du code d’accès de l’appareil|
|Verrouillage à distance|||
|Réinitialiser le code secret|||

## <a name="deprecations"></a>Dépréciations

### <a name="firefox-to-no-longer-support-silverlight--vso-tba--"></a>Firefox ne prendra plus en charge Silverlight<!--VSO TBA-->
Mozilla supprime la prise en charge de Silverlight dans la version 52 du [navigateur Firefox](https://www.mozilla.org/firefox), à compter de mars 2017. Ainsi, vous ne pourrez plus vous connecter à la console Intune existante à l’aide de versions de Firefox ultérieures à la version 51. Nous vous recommandons d’utiliser Internet Explorer 10 ou 11 pour accéder à la console d’administration, ou une [version de Firefox antérieure à la version 52](https://ftp.mozilla.org/pub/firefox/releases/). La transition d’Intune vers le portail Azure lui permettra de prendre en charge plusieurs [navigateurs modernes](https://docs.microsoft.com/en-us/azure/azure-preview-portal-supported-browsers-devices) sans dépendance envers Silverlight.

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Suppression des stratégies de boîte de réception mobile Exchange Online <!--770687-->
À compter du mois décembre, les administrateurs ne seront plus en mesure d’afficher ou de configurer les stratégies de boîte aux lettres mobile Exchange Online (EAS) dans la console Intune. Cette modification s’appliquera à tous les clients Intune entre décembre et janvier. La configuration des stratégies existantes restera inchangée. Pour configurer de nouvelles stratégies, utilisez l’environnement de ligne de commande Exchange Management Shell. Obtenez plus d’informations [ici](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Les applications Intune AV Player, Image Viewer et PDF Viewer ne sont plus prises en charge sur Android <!--747553-->
À partir de mi-décembre 2016, les utilisateurs ne seront n’est plus en mesure d’utiliser les applications Intune AV Player, Image Viewer et PDF Viewer. Ces applications ont été remplacées par l’application Azure Information Protection. En savoir plus sur l’application Azure Information Protection [ici](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Versions précédentes d’Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO2-->


