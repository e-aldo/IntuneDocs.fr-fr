---
title: "Edition anticipée | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18d47678b0fbdbd98502f2d3b469b202b567b2e7
ms.openlocfilehash: 3c7edc236878232c6f4c0ae993733c967946e765


---

# <a name="the-early-edition-for-microsoft-intune---january"></a>Édition anticipée pour Microsoft Intune - Janvier

L’**édition anticipée** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
> Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="actions-for-non-compliance---730266--"></a>Actions en cas de non-conformité <!--730266-->
_Actions en cas de non-conformité_ est une nouvelle fonctionnalité de stratégies de conformité qui vous permet de prendre des mesures au niveau des appareils non conformes. Vous pouvez spécifier une ou plusieurs actions ainsi que la période à laquelle ces actions doivent se produire. Par exemple, vous pouvez avertir par courrier électronique les utilisateurs d'appareils non conformes immédiatement lorsque ces appareils deviennent non conformes, ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise après une période de grâce de 3 jours via l’accès conditionnel.


### <a name="in-console-reports-for-mam-without-enrollment---677961--"></a>Rapports dans la console pour MAM sans inscription <!--677961-->
De nouveaux rapports de protection des applications ont été ajoutés pour les appareils inscrits et les appareils qui n’ont pas été inscrits. Vous trouverez plus d'informations sur la façon dont vous pouvez [surveiller les stratégies de gestion des applications mobiles avec Intune ici](https://docs.microsoft.com/en-us/intune/deploy-use/monitor-mobile-app-management-policies-with-microsoft-intune).

### <a name="conditional-access-for-mam-with-sharepoint-online---679339--"></a>Accès conditionnel pour GAM avec SharePoint Online <!--679339-->
Vous pouvez empêcher les applications qui ne sont pas prises en charge par les stratégies de gestion des applications mobiles (GAM) d’accéder à SharePoint Online.  Vous pouvez commencer à l’aide de la gestion des applications mobiles Intune dans le portail Azure. Recherchez la section __Accès conditionnel__ dans le panneau __Paramètres__ qui inclut l’option pour SharePoint Online. Cette fonctionnalité sera disponible séparément du reste de la version. <!--Find out more about this new feature [here](https://docs.microsoft.com/intune/deploy-use/mam-ca-for-sharepoint-online).-->

### <a name="android-711-support---694397--"></a>Prise en charge d’Android 7.1.1 <!--694397-->
Intune prend désormais entièrement en charge et gère Android 7.1.1.

## <a name="notices"></a>Remarques

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Gestion par défaut des appareils de bureau Windows via les paramètres Windows <!--663050-->
Le comportement par défaut pour l’inscription d'ordinateurs de bureau Windows 10 change. Les nouvelles inscriptions se feront via le flux d'inscription d'agent MDM classique plutôt que via l’agent PC.

Le site Web du portail d’entreprise fournira aux utilisateurs d'ordinateurs de bureau Windows 10 des instructions d’inscription qui les guideront tout au long du processus d’ajout d’ordinateurs de bureau Windows 10 comme appareils mobiles. Cela n’affectera pas les ordinateurs actuellement inscrits, et votre organisation pourra toujours gérer des ordinateurs de bureau Windows 10 à l’aide de l’agent PC [si vous préférez](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Le portail d’entreprise pour obtenir des liens iOS s'ouvrir au sein de l’application<!--665954-->
Les liens au sein de l’application Portail d’entreprise pour iOS, y compris ceux vers la documentation et les applications, s’ouvriront directement dans l’application Portail d’entreprise à l’aide d’une vue dans l’application de Safari. Cette mise à jour sera disponible séparément à partir de la mise à jour de service de janvier.

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

### <a name="progress-bar-when-launching-the-company-portal-on-ios---665978--"></a>Barre de progression lors du lancement du portail d’entreprise sur iOS <!--665978-->
Le portail d’entreprise pour iOS introduit une barre de progression sur l’écran de démarrage pour fournir à l’utilisateur des informations sur les processus de chargement qui se produisent. Il y aura un déploiement échelonné de la barre de progression pour remplacer le compteur. Cela signifie que certains de vos utilisateurs verront la nouvelle barre de progression tandis que d’autres verront encore le compteur.

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Préversion publique de la nouvelle expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="january-2017"></a>Janvier 2017

#### <a name="custom-app-categories---748805--"></a>Catégories d’applications personnalisées <!--748805-->
Vous pouvez désormais créer, modifier et attribuer des catégories pour les applications que vous ajoutez à Intune. Actuellement, les catégories ne peuvent être spécifiées qu'en anglais.

#### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748803--"></a>Attribuer des applications métier que les appareils soient inscrits ou non<!--748803-->
Vous pouvez désormais attribuer aux utilisateurs des applications métier à partir du magasin, que leurs appareils soient inscrits ou non auprès d'Intune. Si l'appareil de l’utilisateur n’est pas inscrit auprès d'Intune, ce dernier doit se rendre sur le site Web du portail d’entreprise, au lieu de l’application du portail d’entreprise, pour l'installer.

### <a name="december-2016"></a>Décembre 2016

#### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Intégration de la gestion des dépenses de télécommunications dans la version préliminaire publique du portail Azure<!--747605-->
Nous avons commencé à afficher un aperçu de l’intégration aux services de gestion des dépenses de télécommunications au sein du portail Azure. Vous pouvez utiliser Intune pour appliquer des limites à l’utilisation des données domestiques et itinérantes. Nous allons commencer ces intégrations avec [Saaswedo](http://www.saaswedo.com). Pour activer cette fonctionnalité dans votre client d’évaluation, veuillez [contacter le support technique Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.



<!--HONumber=Dec16_HO4-->


