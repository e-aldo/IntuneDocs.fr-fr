---
title: "Nouveautés | Microsoft Docs"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 2e6452a066aa7eaeb295a3b531d83dc3b632bcf5
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---
# <a name="whats-new-in-microsoft-intune---april-2017"></a>Nouveautés de Microsoft Intune - Avril 2017
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

> [!Note]
> Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps disponibles pour Managed Browser <!--822308, 822303-->

Microsoft MyApps bénéficie d’une meilleure prise en charge dans Managed Browser. Les utilisateurs de Managed Browser qui ne sont pas ciblés pour la gestion sont dirigés directement vers le service MyApps, où il peuvent accéder à leurs applications SaaS configurées par l’administrateur. Les utilisateurs ciblés pour la gestion Intune continueront à pouvoir accéder à MyApps à partir du signet Managed Browser intégré.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431-971473--"></a>Nouvelles icônes pour Managed Browser et le portail d’entreprise <!--918433, 918431, 971473-->

Managed Browser reçoit des icônes mises à jour pour les versions iOS et Android de l’application. La nouvelle icône contient le badge Intune mis à jour, pour une meilleure cohérence avec d’autres applications Enterprise Mobility + Security (EM+S). Vous pouvez voir la nouvelle icône de Managed Browser sur la [page Nouveautés de l’interface utilisateur des applications Intune](whats-new-in-intune-app-ui.md).

Le portail d’entreprise reçoit également des icônes mises à jour pour les versions Android, iOS et Windows de l’application, afin d’améliorer la cohérence avec d’autres applications dans EM + S. Ces icônes seront publiées progressivement sur toutes les plateformes du mois d’avril jusqu’à fin mai.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicateur de progression de connexion dans le portail d’entreprise Android <!--953374-->

Une mise à jour de l’application Portail d’entreprise Android affiche un indicateur de progression de connexion quand l’utilisateur lance l’application ou effectue une reprise. L’indicateur affiche successivement les nouveaux états, en commençant par « Connexion... », puis « Connexion en cours », puis « Vérification des exigences de sécurité... », avant d’autoriser l’utilisateur à accéder à l’application. Vous pouvez voir les nouveaux écrans de l’application Portail d’entreprise pour Android sur la [page Nouveautés de l’interface utilisateur des applications Intune](whats-new-in-intune-app-ui.md).

### <a name="block-apps-from-accessing-sharepoint-online----679339---"></a>Empêcher les applications d’accéder à SharePoint Online<!-- 679339 -->

Vous pouvez maintenant créer une stratégie d’accès conditionnel basé sur l’application pour bloquer l’accès à [SharePoint Online](/intune-classic/deploy-use/mam-ca-for-sharepoint-online) pour les applications sur lesquelles n’a été appliquée aucune stratégie de protection des applications. Dans le scénario d’accès conditionnel basé sur les applications, vous pouvez spécifier les applications qui doivent avoir accès à SharePoint Online à l’aide du portail Azure.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Prise en charge de l’authentification unique entre le portail d’entreprise pour iOS et Outlook pour iOS <!--834012-->
Les utilisateurs n’ont plus besoin de se connecter à l’application Outlook s’ils sont connectés à l’application Portail d’entreprise pour iOS sur le même appareil avec le même compte. Quand les utilisateurs lancent l’application Outlook, ils peuvent sélectionner leur compte et se connecter automatiquement. Nous travaillons également à l’ajout de cette fonctionnalité à d’autres applications Microsoft.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Amélioration de la messagerie d’état dans l’application Portail d’entreprise pour iOS <!--744866-->
De nouveaux messages d’erreur plus spécifiques sont désormais affichés dans l’application Portail d’entreprise pour iOS, afin de fournir des informations plus accessibles sur ce qui se passe sur les appareils. Ces cas d’erreur étaient dans un message d’erreur général intitulé « Portail d’entreprise temporairement indisponible ». En outre, si un utilisateur lance le portail d’entreprise sur iOS quand il ne dispose pas d’une connexion Internet, une barre d’état persistante indiquant « Aucune connexion Internet » est affichée dans la page d’accueil.

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Amélioration de l’état d’installation de l’application pour l’application Portail d’entreprise Windows 10 <!--676495-->

Parmi les améliorations apportées aux installations d’applications démarrées dans l’application Portail d’entreprise Windows 10, citons les suivantes :
-    Indication plus rapide de la progression de l’installation des packages MSI
-    Indication plus rapide de la progression de l’installation d’applications modernes sur les appareils exécutant au minimum Mise à jour anniversaire Windows 10
-    Nouvelle barre de progression pour les installations d’applications modernes sur les appareils exécutant au minimum Mise à jour anniversaire Windows 10

Vous pouvez voir la nouvelle barre de progression dans la [page Nouveautés de l’interface utilisateur des applications Intune](whats-new-in-intune-app-ui.md).

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Inscription en bloc des appareils Windows 10 <!-- 747607 -->

Vous pouvez ajouter un grand nombre d’appareils exécutant Windows 10 Creators Update à Azure Active Directory et Intune avec le Concepteur de configuration Windows /intune-classic/deploy-use/bulk-enroll-windows) pour votre locataire Azure AD, créer un package d’approvisionnement qui ajoute des appareils à votre locataire Azure AD à l’aide du Concepteur de configuration Windows et appliquer le package aux appareils de l’entreprise que vous voulez inscrire et gérer en bloc. Une fois le package appliqué à vos appareils, ceux-ci se connectent à Azure AD et s’inscrivent dans Intune. Ils sont alors prêts pour que vos utilisateurs Azure AD s’y connectent.  Les utilisateurs d’Azure AD agissent sur ces appareils en tant qu’utilisateurs standard ; ils reçoivent les stratégies qui leur sont affectées ainsi que les applications dont ils ont besoin. Les scénarios de libre-service et de portail d’entreprise ne sont pas pris en charge pour le moment.

## <a name="notices"></a>Remarques

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->

Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure en version préliminaire. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessiteront une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder à la version préliminaire, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Nouveautés pour Appx dans Intune sur Azure <!-- 1000270 -->

Dans le cadre de la migration vers Intune sur Azure, nous avons apporté trois modifications à appx :

1. Ajout d’un nouveau type d’application appx dans la console Intune classique qui ne peut être déployé que vers des appareils inscrits pour la gestion des appareils mobiles.
2. Réaffectation du type d’application appx existant pour cibler uniquement les ordinateurs gérés par l’intermédiaire de l’agent de PC Intune.
3. Conversion de tous les appxs existants en appxs MDM avec la migration.

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?

Cela n’affecte aucun de vos déploiements existants vers des appareils qui sont gérés par l’intermédiaire de l’agent de PC Intune. Toutefois, après la migration, vous ne pourrez pas déployer ces appxs migrés vers de nouveaux appareils gérés par l’intermédiaire de l’agent de PC Intune qui n’étaient pas précédemment ciblés.

#### <a name="what-action-do-i-need-to-take"></a>Que dois-je faire ?

Après la migration, vous devez retélécharger l’appx en tant qu’appx PC si vous voulez effectuer de nouveaux déploiements de PC. Pour en savoir plus, consultez [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Changement relatif aux appx dans Intune sur Azure) sur le blog de l’équipe de support technique Intune.  

## <a name="whats-new-in-the-public-preview-of-the-intune-admin-experience-on-azure---736542--"></a>Nouveautés de la préversion publique de l’expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](/intune/whats-new).

> [!Note]
> En ce qui concerne la préversion du portail Azure, nous déployons actuellement les mises à jour pour ce mois. Toutefois, il se peut que les modifications ne soient pas disponibles immédiatement selon la façon dont le service Intune est mis à jour.  Plusieurs composants du service doivent être actualisés de façon séquentielle avant que les nouvelles fonctionnalités du portail soient disponibles. Recherchez les modifications dans la préversion du portail Azure qui seront publiées à une date ultérieure ce mois-ci. Pour obtenir la liste complète des modifications, consultez [Nouveautés de la préversion de Microsoft Intune](/intune/whats-new).

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure

Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Nouveautés à venir

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Amélioration de l’expérience de connexion sur l’ensemble des applications du portail d’entreprise pour toutes les plates-formes<!--User Story 1132123-->

Dans les mois à venir, nous introduirons des changements visant à améliorer l’expérience de connexion aux applications Portail d’entreprise Intune pour Android, iOS et Windows. La nouvelle expérience utilisateur s’affiche automatiquement sur toutes les plates-formes utilisées pour l’application du portail d’entreprise lorsqu’Azure AD apporte cette modification. En outre, les utilisateurs peuvent désormais se connecter au portail d’entreprise à partir d’un autre appareil grâce à un code à usage unique automatiquement généré. Cette fonction se révèle particulièrement utile lorsque les utilisateurs doivent se connecter sans informations d’identification.

La page [Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune](whats-new-in-intune-app-ui.md) contient des captures d’écran illustrant l’expérience de connexion précédente, la nouvelle expérience de connexion avec informations d’identification, ainsi que la nouvelle expérience de connexion depuis un autre appareil.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Modification planifiée : Intune transforme l’expérience du portail pour les partenaires Intune<!-- 1050016 -->

Nous supprimons la page des partenaires Intune du site manage.microsoft.com à compter de la mise à jour de service prévue mi-mai 2017.  

Si vous êtes un administrateur de partenaires, vous ne pourrez plus afficher la page des partenaires Intune et agir pour le compte de vos clients, et vous devrez vous connecter à un des deux autres portails des partenaires sur le site de Microsoft.

Le [Centre pour partenaires Microsoft](https://partnercenter.microsoft.com/) et l[’Espace d’administration des partenaires Microsoft Office 365](https://portal.office.com/) vous permettent de vous connecter aux comptes client que vous gérez. En tant que partenaire, utilisez à partir de maintenant l’un de ces sites pour gérer vos clients.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->

La société Apple a annoncé qu’elle appliquera des exigences spécifiques pour ATS (Application Transport Security). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS.

Nous avons publié, par le biais du programme Apple TestFlight, une version de l’application Portail d’entreprise pour iOS qui respecte les nouvelles exigences d’ATS. Si vous souhaitez l’essayer pour tester votre conformité à ATS, envoyez un e-mail à <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> en indiquant votre prénom, votre nom, votre adresse e-mail et le nom de votre société. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de la préversion Azure](https://docs.microsoft.com/intune/whats-new)
* [Nouveautés de l’interface utilisateur du portail d’entreprise](/intune-classic/whats-new/whats-new-in-company-portal-ui)
* [Archive des nouveautés](whats-new-archive.md)

