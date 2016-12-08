---
title: "Edition anticipée | Microsoft Intune"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6dd584397451d38be86fa0780efff435ffb9b2af
ms.openlocfilehash: d70ebf87bc930f853741ddc0d572d2174c636dac


---

# <a name="the-early-edition-for-microsoft-intune---december"></a>Édition anticipée pour Microsoft Intune - Décembre

L’**édition anticipée** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

<!--736542-->
## <a name="public-preview-of-the-new-intune-admin-experience-on-azure"></a>Préversion publique de la nouvelle expérience administrateur sur Azure

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la nouvelle documentation.

Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Intégration de la gestion des dépenses de télécommunications dans la version préliminaire publique du portail Azure<!--747605-->
Nous avons commencé à afficher un aperçu de l’intégration aux services de gestion des dépenses de télécommunications au sein du portail Azure. Vous pouvez utiliser Intune pour appliquer des limites à l’utilisation des données domestiques et itinérantes. Nous allons commencer ces intégrations avec [Saaswedo](http://www.saaswedo.com).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="multi-factor-authentication-across-all-platforms---747590--"></a>Authentification multifacteur sur toutes les plateformes <!--747590-->
Vous pouvez appliquer l’authentification multifacteur (MFA) sur un groupe sélectionné d’utilisateurs lorsqu’ils inscrivent un appareil iOS, Android, Windows 8.1+ ou Windows Phone 8.1+ depuis le portail de gestion Azure en configurant l’authentification MFA sur l’application de l’inscription à Microsoft Intune dans Azure Active Directory.

### <a name="conditional-access-for-mam-with-sharepoint-online---vso-679339--"></a>Accès conditionnel pour GAM avec SharePoint Online <!--VSO 679339-->
Vous pouvez empêcher les applications qui ne sont pas prises en charge par les stratégies de gestion des applications mobiles (GAM) d’accéder à SharePoint Online.  Vous pouvez commencer à l’aide de la gestion des applications mobiles Intune dans le portail Azure. Recherchez la section __Accès conditionnel__ dans le panneau __Paramètres__ qui inclut l’option pour SharePoint Online. Cette fonctionnalité sera disponible séparément du reste de la version.

### <a name="ability-to-restrict-intune-mobile-device-enrollment"></a>Possibilité de limiter l’inscription des appareils mobiles Intune
Intune ajoute de nouvelles restrictions d’inscription qui contrôlent les plateformes d’appareils mobiles autorisées à être inscrites. Intune sépare les plateformes d’appareils mobiles comme iOS, MacOS, Android, Windows et Windows Mobile. 
* MacOS et Windows 8.1 ou ultérieur peuvent ne pas être autorisés à être inscrits comme plateformes d’appareils mobiles. 
* La restriction de l’inscription d’appareils mobiles ne limite pas l’inscription d’agents de PC. 
* Pour iOS uniquement, il existe une option supplémentaire pour bloquer l’inscription des appareils personnels. Intune marque tous les nouveaux appareils comme personnels, sauf si l’administrateur prend des mesures pour les marquer comme appareils d’entreprise, comme expliqué dans [cet article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).


## <a name="notices"></a>Remarques

### <a name="multi-factor-authentication-on-enrollment-moving-to-the-azure-portal---vso-750545--"></a>Déplacement de l’authentification multifacteur sur l’inscription vers le portail Azure <!--VSO 750545-->
Auparavant, les administrateurs accédaient à la console Intune ou à la console Configuration Manager (antérieure à la version 1610) pour définir l’authentification multifacteur pour les inscriptions Intune. Grâce à cette fonctionnalité mise à jour, vous pouvez désormais vous connecter au [portail Microsoft Azure](https://manage.windowsazure.com) à l’aide de vos informations d’identification Intune et configurer les paramètres de l’authentification multifacteur via Azure AD. En savoir plus sur ce point [ici](https://aka.ms/mfa_ad).

### <a name="company-portal-app-for-android-now-available-in-china---vso-658093--"></a>L’application Portail d’entreprise pour Android est désormais disponible en Chine <!--VSO 658093-->
Nous publions l’application Portail d’entreprise pour Android pour le téléchargement en Chine. En l’absence de Google Play Store en Chine, les appareils Android doivent obtenir les applications dans les places de marché des applications chinoises. L’application Portail d’entreprise pour Android sera disponible en téléchargement sur 360, Tencent, Xiaomi, Wandoujia et Huawei. 

L’application Portail d’entreprise pour Android utilise les services Google Play pour communiquer avec le service Microsoft Intune. Étant donné que les services Google Play ne sont pas encore disponibles en Chine, le traitement des tâches suivantes peut prendre jusqu’à 8 heures. 

|Console d’administration Intune| Application Portail d’entreprise Intune pour Android |Site web du portail d’entreprise Intune|   
|---|---|---|
|réinitialisation complète| Supprimer un appareil distant| Supprimer l’appareil (local et distant)|
|réinitialisation sélective| Réinitialiser l’appareil| Réinitialiser l’appareil|
|Déploiements d’applications nouvelles ou mises à jour| Installation des applications métier disponibles| Réinitialisation du code d’accès de l’appareil|
|Verrouillage à distance|||
|Réinitialiser le code secret|||

## <a name="deprecations"></a>Désapprobations

### <a name="removal-of-exchange-online-mobile-inbox-policies---770687--"></a>Suppression des stratégies de boîte de réception mobile Exchange Online <!--770687-->
À compter du mois décembre, les administrateurs ne seront plus en mesure d’afficher ou de configurer les stratégies de boîte aux lettres mobile Exchange Online (EAS) dans la console Intune. Cette modification s’appliquera à tous les clients Intune entre décembre et janvier. La configuration des stratégies existantes restera inchangée. Pour configurer de nouvelles stratégies, utilisez l’environnement de ligne de commande Exchange Management Shell. Obtenez plus d’informations [ici](https://technet.microsoft.com/en-us/library/bb123783%28v=exchg.150%29.aspx).

### <a name="intune-av-player-image-viewer-and-pdf-viewer-apps-are-no-longer-supported-on-android---747553--"></a>Les applications Intune AV Player, Image Viewer et PDF Viewer ne sont plus prises en charge sur Android <!--747553-->
À partir de mi-décembre 2016, les utilisateurs ne seront n’est plus en mesure d’utiliser les applications Intune AV Player, Image Viewer et PDF Viewer. Ces applications ont été remplacées par l’application Azure Information Protection. En savoir plus sur l’application Azure Information Protection [ici](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq).

### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.



<!--HONumber=Nov16_HO5-->


