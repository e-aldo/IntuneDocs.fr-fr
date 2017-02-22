---
title: "Édition anticipée | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 68c7a23dc8769330c14f74e6aebb07eeb188a991
ms.openlocfilehash: 4bc9a2799bcce035c6847b7b2884ee24160426da


---


# <a name="the-early-edition-for-microsoft-intune---february-2017"></a>Édition anticipée pour Microsoft Intune - Février 2017

L’**édition anticipée** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
> Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisation du site web du portail d’entreprise <!--753980-->
Le site web du portail d’entreprise prend en charge les applications destinées aux utilisateurs qui n’ont pas d’appareils gérés. Le site web s’aligne sur les autres produits et services Microsoft et utilise un nouveau modèle de couleurs contrastées, des illustrations dynamiques et un « menu hamburger », ![Petite image du menu hamburger désormais en haut à gauche du site web du portail d’entreprise](./media/CP_hamburger_menu.png) qui contient les coordonnées du support technique et des informations sur les appareils gérés existants. Nous avons réorganisé la page d’accueil pour mettre en évidence les applications disponibles en les affichant dans des carrousels sous Applications proposées et Applications récemment mises à jour. Des images « Avant » et « Après » sont disponibles dans la [page des mises à jour de l’interface utilisateur](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nouvelle expérience interactive pour le portail d’entreprise Windows 10 <!--713927-->
À compter du mois de mars, le portail d’entreprise pour Windows 10 inclura une expérience de procédure pas à pas Intune interactive pour les appareils qui n’ont pas été identifiés ou inscrits. La nouvelle expérience fournit des instructions détaillées, adaptées à la version Windows 10 de l’utilisateur, qui guident les utilisateurs pour effectuer l’inscription AAD (obligatoire pour l’identification pour les fonctionnalités d’accès conditionnel) et l’inscription MDM (obligatoire pour les fonctionnalités de gestion des appareils). L’expérience interactive est accessible à partir de la page d’accueil du portail d’entreprise et est facultative. Les utilisateurs peuvent continuer à utiliser l’application s’ils n’effectuent pas l’enregistrement et l’inscription, mais les fonctionnalités peuvent être limitées.

###

## <a name="notices"></a>Remarques

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>La migration de groupe n’implique pas la mise à jour des groupes ou des stratégies pour les appareils iOS<!--898837-->
Pour chaque groupe d’appareils Intune préattribué par un profil d’inscription des appareils de l’entreprise, un groupe d’appareils dynamique correspondant est créé dans AAD à partir du nom du profil d’inscription des appareils de l’entreprise pendant la migration vers des groupes d’appareils Azure Active Directory. De cette façon, les appareils inscrits sont automatiquement regroupés et reçoivent les mêmes stratégies et applications que le groupe Intune d’origine.

Dès qu’un client entre dans l’étape de regroupement et de ciblage du processus de migration, Intune crée automatiquement un groupe AAD dynamique qui correspond à un groupe Intune ciblé par un profil d’inscription des appareils de l’entreprise. Si l’administrateur Intune supprime le groupe Intune cible, le groupe AAD dynamique correspondant n’est pas supprimé. Les membres du groupe et la requête dynamique disparaissent, mais le groupe lui-même est conservé jusqu’à ce que l’administrateur informatique le supprime dans le portail AAD.

De même, si l’administrateur informatique change le groupe Intune qui est ciblé par un profil d’inscription des appareils de l’entreprise, Intune crée un groupe dynamique qui reflète la nouvelle attribution de profil, mais ne supprime pas le groupe dynamique créé pour l’ancienne attribution.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nouvelle adresse du serveur MDM pour les appareils Windows <!--893007-->
Les utilisateurs de Windows et Windows Phone ne parviennent pas à inscrire un appareil s’ils entrent __manage.microsoft.com__ comme adresse du serveur MDM (s’ils y sont invités). L’adresse du serveur MDM __manage.microsoft.com__ devient __enrollment.manage.microsoft.com__. Demandez à vos utilisateurs d’utiliser __enrollment.manage.microsoft.com__ comme adresse du serveur MDM, s’ils y sont invités lors de l’inscription d’un appareil Windows ou Windows Phone. Cette mise à jour implique que tous les enregistrements CNAME dans DNS qui redirigent __EnterpriseEnrollment.contoso.com__ vers __manage.microsoft.com__ soient remplacés par des enregistrements CNAME dans DNS redirigeant __EnterpriseEnrollment.contoso.com__ vers __EnterpriseEnrollment-s.manage.microsoft.com__. Pour plus d’informations sur cette modification, visitez [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nouvelle expérience utilisateur dans l’application Portail d’entreprise pour Android <!--621622-->
À compter de mars, l’application Portail d’entreprise pour Android suit les [directives de conception matérielle](https://material.io/guidelines/material-design/introduction.html) pour créer une apparence plus moderne. Cette expérience utilisateur améliorée inclut les éléments suivants :

* __Couleurs__ : La couleur de l’en-tête des onglets peut être assortie à votre palette de couleurs personnalisée.
* __Interface__ : Les boutons Applications proposées et Toutes les applications ont été mis à jour sous l’onglet Applications. Le bouton Rechercher est désormais un bouton d’action flottant.
* __Navigation__ : Le bouton Toutes les applications propose une vue comprenant les onglets Applications proposées, Toutes les applications et Catégories pour faciliter la navigation.
* __Service__ : Les onglets Mes appareils et Contacter le service informatique sont plus lisibles.

Des images « Avant » et « Après » sont disponibles dans la [page des mises à jour de l’interface utilisateur](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Associer plusieurs outils de gestion à Windows Store pour Entreprises <!--926135-->
Si vous utilisez plusieurs outils de gestion pour déployer des applications Windows Store pour Entreprises, vous ne pouviez associer qu’un seul outil au Windows Store pour Entreprises. Désormais, vous pouvez associer plusieurs outils de gestion au Windows Store, par exemple, Intune et Configuration Manager. Pour plus d’informations, consultez [Gérer les applications que vous avez achetées dans le Windows Store pour Entreprises avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Préversion publique de la nouvelle expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](https://docs.microsoft.com/en-us/intune-azure/introduction/what-is-microsoft-intune).

Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### <a name="february-2017"></a>Février 2017

#### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Possibilité de limiter l’inscription des appareils mobiles <!--747600, 795782-->
Intune ajoute de nouvelles restrictions d’inscription qui contrôlent les plateformes d’appareils mobiles autorisées à être inscrites. Intune sépare les plateformes d’appareils mobiles comme iOS, MacOS, Android, Windows et Windows Mobile.

* La restriction de l’inscription d’appareils mobiles ne limite pas l’inscription des clients de PC.  
* Pour iOS et Android uniquement, il existe une option supplémentaire pour bloquer l’inscription des appareils personnels.

Intune marque tous les nouveaux appareils comme personnels, sauf si l’administrateur prend des mesures pour les marquer comme appareils d’entreprise, comme expliqué dans [cet article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

#### <a name="view-all-actions-on-managed-devices---677150--"></a>Afficher toutes les actions sur les appareils gérés <!--677150-->
Un nouveau rapport __Actions de l’appareil__ indique l’utilisateur qui a effectué des actions à distance, comme un rétablissement des paramètres d’usine sur les appareils, et montre également l’état de cette action.

#### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Les appareils non gérés peuvent accéder aux applications attribuées <!--664691-->
Dans le cadre des modifications conceptuelles du site web du portail d’entreprise, les utilisateurs iOS et Android peuvent installer les applications attribuées indiquées comme « disponibles sans inscription » sur leurs appareils non gérés. À l’aide de leurs informations d’identification Intune, les utilisateurs peuvent se connecter au site web du portail d’entreprise et afficher la liste des applications qui leur sont attribuées. Les packages des applications « disponibles sans inscription » peuvent être téléchargés sur le site web du portail d’entreprise. Les applications dont l’installation nécessite une inscription ne sont pas affectées par cette modification, car les utilisateurs sont invités à inscrire leur appareil s’ils souhaitent installer ces applications.

#### <a name="custom-app-categories---748805--"></a>Catégories d’applications personnalisées <!--748805-->
Vous pouvez désormais créer, modifier et attribuer des catégories pour les applications que vous ajoutez à Intune. Actuellement, les catégories ne peuvent être spécifiées qu'en anglais.
Consultez [Guide pratique pour ajouter une application à Intune](/intune-azure/manage-apps/add-apps).

#### <a name="display-device-categories---814654--"></a>Afficher des catégories d’appareils <!--814654-->
Vous pouvez maintenant afficher la catégorie d’appareil sous forme de colonne dans la liste des appareils. Vous pouvez également modifier la catégorie dans la section des propriétés du panneau Propriétés de l’appareil.

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



<!--HONumber=Feb17_HO2-->


