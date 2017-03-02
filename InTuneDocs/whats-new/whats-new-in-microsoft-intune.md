---
title: "Nouveautés | Microsoft Docs"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: cacampbell
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 846084a3810e43d9fd6a6c254f1b0167a36f37ff
ms.openlocfilehash: b99731c7becd90f4092ec758234a96e202d95130
ms.lasthandoff: 02/15/2017


---
# <a name="whats-new-in-microsoft-intune---february-2017"></a>Nouveautés de Microsoft Intune : février 2017
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

> [!Note]
> Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="modernizing-the-company-portal-website---753980--"></a>Modernisation du site web du portail d’entreprise <!--753980-->
Le site web du portail d’entreprise prend en charge les applications destinées aux utilisateurs qui n’ont pas d’appareils gérés. Le site web s’aligne sur les autres produits et services Microsoft et utilise un nouveau modèle de couleurs contrastées, des illustrations dynamiques et un « menu hamburger », ![Petite image du menu hamburger désormais en haut à gauche du site web du portail d’entreprise](./media/CP_hamburger_menu.png) qui contient les coordonnées du support technique et des informations sur les appareils gérés existants. Nous avons réorganisé la page d’accueil pour mettre en évidence les applications disponibles en les affichant dans des carrousels sous Applications proposées et Applications récemment mises à jour. Des images « Avant » et « Après » sont disponibles dans la [page des mises à jour de l’interface utilisateur](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="new-guided-experience-for-windows-10-company-portal---713927--"></a>Nouvelle expérience interactive pour le portail d’entreprise Windows 10 <!--713927-->
À compter du mois de mars, le portail d’entreprise pour Windows 10 inclura une expérience de procédure pas à pas Intune interactive pour les appareils qui n’ont pas été identifiés ou inscrits. La nouvelle expérience fournit des instructions détaillées, adaptées à la version Windows 10 de l’utilisateur, qui guident les utilisateurs pour effectuer l’inscription AAD (obligatoire pour l’identification pour les fonctionnalités d’accès conditionnel) et l’inscription MDM (obligatoire pour les fonctionnalités de gestion des appareils). L’expérience interactive est accessible à partir de la page d’accueil du portail d’entreprise et est facultative. Les utilisateurs peuvent continuer à utiliser l’application s’ils n’effectuent pas l’enregistrement et l’inscription, mais les fonctionnalités peuvent être limitées.

## <a name="notices"></a>Remarques

### <a name="group-migration-will-not-require-any-updates-to-groups-or-policies-for-ios-devices---898837--"></a>La migration de groupe n’implique pas la mise à jour des groupes ou des stratégies pour les appareils iOS<!--898837-->
Pour chaque groupe d’appareils Intune préattribué par un profil d’inscription des appareils de l’entreprise, un groupe d’appareils dynamique correspondant est créé dans AAD à partir du nom du profil d’inscription des appareils de l’entreprise pendant la migration vers des groupes d’appareils Azure Active Directory. De cette façon, les appareils inscrits sont automatiquement regroupés et reçoivent les mêmes stratégies et applications que le groupe Intune d’origine. 

Dès qu’un client entre dans l’étape de regroupement et de ciblage du processus de migration, Intune crée automatiquement un groupe AAD dynamique qui correspond à un groupe Intune ciblé par un profil d’inscription des appareils de l’entreprise. Si l’administrateur Intune supprime le groupe Intune cible, le groupe AAD dynamique correspondant n’est pas supprimé. Les membres du groupe et la requête dynamique disparaissent, mais le groupe lui-même est conservé jusqu’à ce que l’administrateur informatique le supprime dans le portail AAD.

De même, si l’administrateur informatique change le groupe Intune qui est ciblé par un profil d’inscription des appareils de l’entreprise, Intune crée un groupe dynamique qui reflète la nouvelle attribution de profil, mais ne supprime pas le groupe dynamique créé pour l’ancienne attribution.

### <a name="defaulting-to-managing-windows-desktop-devices-through-windows-settings---663050--"></a>Gestion par défaut des appareils de bureau Windows via les paramètres Windows <!--663050-->
Le comportement par défaut pour l’inscription d'ordinateurs de bureau Windows 10 change. Les nouvelles inscriptions se feront via le flux d'inscription d'agent MDM classique plutôt que via l’agent PC. Le site Web du portail d’entreprise fournira aux utilisateurs d'ordinateurs de bureau Windows 10 des instructions d’inscription qui les guideront tout au long du processus d’ajout d’ordinateurs de bureau Windows 10 comme appareils mobiles. Cela n’affectera pas les ordinateurs actuellement inscrits, et votre organisation pourra toujours gérer des ordinateurs de bureau Windows 10 à l’aide de l’agent PC [si vous préférez](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

### <a name="improving-mobile-app-management-support-for-selective-wipe---581242--"></a>Amélioration de la prise en charge de la gestion des applications mobiles pour la réinitialisation sélective <!--581242-->
Les utilisateurs finaux recevront des instructions supplémentaires sur la façon de récupérer l’accès aux données professionnelles ou scolaires si ces données sont supprimées automatiquement en raison de la stratégie de « Intervalle en mode hors connexion avant la réinitialisation des données d’application ».<!--, or the removal of the Intune Company Portal on Android.-->

### <a name="company-portal-for-ios-links-open-inside-the-app---665954--"></a>Le portail d’entreprise pour obtenir des liens iOS s'ouvrir au sein de l’application<!--665954-->
Les liens au sein de l’application Portail d’entreprise pour iOS, y compris ceux vers la documentation et les applications, s’ouvriront directement dans l’application Portail d’entreprise à l’aide d’une vue dans l’application de Safari. Cette mise à jour sera disponible séparément à partir de la mise à jour de service de janvier.

### <a name="new-mdm-server-address-for-windows-devices---893007--"></a>Nouvelle adresse du serveur MDM pour les appareils Windows <!--893007-->
Les utilisateurs de Windows et Windows Phone ne parviennent pas à inscrire un appareil s’ils entrent __manage.microsoft.com__ comme adresse du serveur MDM (s’ils y sont invités). L’adresse du serveur MDM __manage.microsoft.com__ devient __enrollment.manage.microsoft.com__. Demandez à vos utilisateurs d’utiliser __enrollment.manage.microsoft.com__ comme adresse du serveur MDM, s’ils y sont invités lors de l’inscription d’un appareil Windows ou Windows Phone. Pour plus d’informations sur cette modification, visitez [aka.ms/intuneenrollsvrchange](https://aka.ms/intuneenrollsvrchange).

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622--"></a>Nouvelle expérience utilisateur dans l’application Portail d’entreprise pour Android <!--621622-->
À compter de mars, l’application Portail d’entreprise pour Android suit les [directives de conception matérielle](https://material.io/guidelines/material-design/introduction.html) pour créer une apparence plus moderne. Cette expérience utilisateur améliorée inclut les éléments suivants :

* __Couleurs__ : La couleur de l’en-tête des onglets peut être assortie à votre palette de couleurs personnalisée.
* __Interface__ : Les boutons Applications proposées et Toutes les applications ont été mis à jour sous l’onglet Applications. Le bouton Rechercher est désormais un bouton d’action flottant.
* __Navigation__ : Le bouton Toutes les applications propose une vue comprenant les onglets Applications proposées, Toutes les applications et Catégories pour faciliter la navigation.
* __Service__ : Les onglets Mes appareils et Contacter le service informatique sont plus lisibles.

Des images « Avant » et « Après » sont disponibles dans la [page des mises à jour de l’interface utilisateur](https://docs.microsoft.com/intune/whats-new/whats-new-in-intune-app-ui).

### <a name="associate-multiple-management-tools-with-the-windows-store-for-business---926135--"></a>Associer plusieurs outils de gestion à Windows Store pour Entreprises <!--926135-->
Si vous utilisez plusieurs outils de gestion pour déployer des applications Windows Store pour Entreprises, vous ne pouviez associer qu’un seul outil au Windows Store pour Entreprises. Désormais, vous pouvez associer plusieurs outils de gestion au Windows Store, par exemple, Intune et Configuration Manager. Pour plus d’informations, consultez [Gérer les applications que vous avez achetées dans le Windows Store pour Entreprises avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune#associate-your-windows-store-for-business-account-with-intune).

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nouveautés de la préversion publique de l’expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](https://docs.microsoft.com/intune-azure/introduction/whats-new).

Si vous avez des questions concernant la chronologie de la migration de votre client, contactez notre équipe de migration à l’adresse suivante : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

Vous pouvez découvrir les nouveautés de la préversion Intune dans Azure [ici](https://docs.microsoft.com/intune-azure/introduction/whats-new).

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de la préversion Azure](https://docs.microsoft.com/intune-azure/introduction/whats-new)
* [Nouveautés de l’interface utilisateur du portail d’entreprise](https://docs.microsoft.com/intune/whats-new/whats-new-in-company-portal-ui)
* [Archive des nouveautés](whats-new-archive.md)

