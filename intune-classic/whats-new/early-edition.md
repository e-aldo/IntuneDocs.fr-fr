---
title: "Édition anticipée | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>Édition anticipée pour Microsoft Intune - Mai 2017

L’**édition anticipée** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
> Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Prise en charge de l’authentification unique entre le portail d’entreprise pour iOS et Outlook pour iOS <!--834012-->

Les utilisateurs n’ont plus besoin de se connecter à l’application Outlook s’ils sont connectés à l’application Portail d’entreprise pour iOS sur le même appareil avec le même compte. Quand les utilisateurs lancent l’application Outlook, ils peuvent sélectionner leur compte et se connecter automatiquement. Nous travaillons également à l’ajout de cette fonctionnalité à d’autres applications Microsoft.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notification améliorée pour les codes PIN de démarrage Samsung KNOX<!--1087143-->

Quand les utilisateurs finaux doivent définir un code PIN de démarrage sur les appareils Samsung KNOX pour être compatibles avec le chiffrement, la notification affichée aux utilisateurs finaux les mène à l’emplacement exact dans l’application Paramètres lors de l’appui sur la notification.  Auparavant, la notification menait l’utilisateur final à l’écran de modification de mot de passe.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Promotion de la version la plus récente du portail d’entreprise pour Android <!--1098661-->

Les utilisateurs finaux reçoivent une notification dans l’application quand une nouvelle version recommandée de l’application Portail d’entreprise pour Android a été publiée. Cette notification signale aux utilisateurs qu’une « mise à jour du portail d’entreprise est disponible ». Un appui sur la notification ouvre une page web affichant la liste des magasins d’applications où ils peuvent télécharger la version mise à jour. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Améliorations apportées à la synchronisation des applications avec Windows 10 Creators Update<!-- 676505 -->

Le portail d’entreprise pour Windows 10 démarre automatiquement une synchronisation pour les demandes d’installation d’application sur les appareils exécutant Windows 10 Creators Update (1704). Cela permet de réduire le problème de blocage des installations d’applications à l’état « Synchronisation en attente ». En outre, les utilisateurs peuvent lancer manuellement une synchronisation à partir de l’application. 

Le portail d’entreprise pour Windows 10 expose également un bouton d’actualisation permettant à l’utilisateur d’actualiser le contenu de l’application quand il le souhaite. 

## <a name="notices"></a>Remarques

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->

La société Apple a annoncé qu’à compter du printemps 2017, elle appliquera des exigences de sécurité spécifiques pour Application Transport Security (ATS). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->

Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure en version préliminaire. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessiteront une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder à la version préliminaire, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Nouveautés pour Appx dans Intune sur Azure <!-- 1000270 -->

Dans le cadre de la migration vers Intune sur Azure, nous avons apporté trois modifications à appx :

1. Ajout d’un nouveau type d’application appx dans la console Intune classique qui ne peut être déployé que vers des appareils inscrits pour la gestion des appareils mobiles.
2. Réaffectation du type d’application appx existant pour cibler uniquement les ordinateurs gérés par l’intermédiaire de l’agent de PC Intune.
3. Conversion de tous les appxs existants en appxs MDM avec la migration.

Cela n’affecte aucun de vos déploiements existants vers des appareils qui sont gérés par l’intermédiaire de l’agent de PC Intune. Toutefois, après la migration, vous ne pourrez pas déployer ces appxs migrés vers de nouveaux appareils gérés par l’intermédiaire de l’agent de PC Intune qui n’étaient pas précédemment ciblés.

Après la migration, vous devez retélécharger l’appx en tant qu’appx PC si vous voulez effectuer de nouveaux déploiements de PC. Pour en savoir plus, consultez [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Changement relatif aux appx dans Intune sur Azure) sur le blog de l’équipe de support technique Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Préversion publique de la nouvelle expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](https://docs.microsoft.com/intune/what-is-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Prise en charge des options de configuration gérées pour les applications Android <!-- 621621 -->

Vous pouvez configurer des applications Android dans le Play Store qui prennent en charge les options de configuration gérées.  Cette fonctionnalité vous permet d’afficher la liste des valeurs de configuration prises en charge par une application, et fournit une interface interactive et guidée de premier plan pour vous permettre de configurer ces valeurs.

### <a name="remote-assistance-for-android-devices----675418---"></a>Assistance à distance pour les appareils Android <!-- 675418 -->

Intune utilise le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs qui utilisent des appareils Android.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Préconfigurer les autorisations d’appareils pour les applications Android for Work<!-- 621614 -->

Pour les applications déployées sur des profils professionnels Android for Work, vous pouvez configurer l’état des autorisations pour chacune des applications. Par défaut, les applications Android qui nécessitent des autorisations d’appareils telles que l’accès à l’emplacement ou à l’appareil photo invitent les utilisateurs à accepter ou à refuser les autorisations.  Par exemple, si une application utilise le microphone de l’appareil, l’utilisateur final est invité à autoriser l’application à utiliser le microphone. Cette fonctionnalité vous permet de définir des autorisations pour le compte de l’utilisateur final.  L’administrateur peut configurer des autorisations pour

- Refuser automatiquement sans avertir l’utilisateur
- Approuver automatiquement sans avertir l’utilisateur
- Inviter l’utilisateur à accepter ou à refuser

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Définir un code PIN propre à l’application pour les appareils Android for Work<!--728976-->

Vous pouvez définir une stratégie de mot de passe qui s’applique uniquement aux applications dans le profil professionnel pour les appareils Android 7.0 et versions ultérieures gérés comme des appareils Android for Work.  Les options sont les suivantes :

- Définir simplement une stratégie de mot de passe au niveau de l’appareil : il s’agit du code secret que l’utilisateur final doit utiliser pour déverrouiller son appareil.
- Définir simplement une stratégie de mot de passe de profil professionnel : les utilisateurs finaux sont invités à entrer un code secret chaque fois qu’une application dans le profil professionnel est ouverte.
- Définir à la fois une stratégie d’appareil et une stratégie de profil professionnel : vous pouvez définir à la fois une stratégie de code secret d’appareil et une stratégie de code secret de profil professionnel à des niveaux différents (par exemple, un code PIN à quatre chiffres pour déverrouiller l’appareil, mais un code PIN à six chiffres pour ouvrir une application professionnelle).

>[!NOTE]
> Cette fonctionnalité est disponible uniquement sur Android 7.0 et versions ultérieures.  Par défaut, l’utilisateur final peut utiliser les deux codes PIN définis séparément, ou il peut choisir de combiner les deux codes PIN définis dans le plus sécurisé des deux.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Gérer les paramètres de mot de passe et autres paramètres Android for Work<!--1102534-->

Nous avons ajouté une nouvelle stratégie de restriction d’appareil Android for Work qui vous permet de gérer les paramètres de profil professionnel et de mot de passe sur les appareils Android for Work.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Nouvelle stratégie de filtrage de contenu web pour les appareils iOS <!-- 723832 -->

Vous pouvez contrôler les sites web auxquels les utilisateurs d’appareils iOS peuvent accéder à l’aide de l’une des deux méthodes suivantes :

  - Ajouter des URL autorisées et bloquées à l’aide du filtrage de contenu web intégré d’Apple.
  - Autoriser uniquement l’accès aux sites web spécifiés par le navigateur Safari. Des signets seront créés dans Safari pour chaque site que vous spécifiez.

### <a name="apple-school-manager-asm-support---748864--"></a>Prise en charge d’Apple School Manager (ASM) <!--748864-->

Intune prend en charge l’utilisation d’Apple School Manager (ASM) à la place du Programme d’inscription d’appareils Apple pour fournir l’inscription des appareils iOS par défaut. L’intégration d’ASM est nécessaire pour utiliser l’application Classroom pour les iPad partagés et pour permettre la synchronisation des données d’ASM vers Azure Active Directory par l’intermédiaire de Microsoft School Data Sync (SDS).  

### <a name="shared-ipad-support---770395-1044681---"></a>Prise en charge des iPad partagés<!--770395, 1044681 -->

Intune prend en charge la configuration du mode iPad partagé dans le profil d’inscription pour le Programme d’inscription d’appareils Apple ou Apple School Manager. Ce paramètre permet à plusieurs ID Apple gérés de se connecter au même appareil.

Nous allons également développer la prise en charge de la gestion de l’application Classroom iOS afin d’inclure les étudiants qui se connectent à des iPad partagés à l’aide de leur ID Apple géré.

### <a name="new-windows-device-restriction-settings---978585--"></a>Nouveaux paramètres de restriction d’appareil Windows <!--978585-->

Nous avons ajouté au profil de restriction d’appareil Windows des paramètres qui contrôlent des fonctionnalités telles que les affichages sans fil, la détection des appareils, le basculement de tâche et les messages d’erreur de carte SIM.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>Application Office 365 ProPlus disponible pour les appareils Windows 10 <!--1121362-->

Nous avons ajouté le nouveau type d’application Office 365 ProPlus, qui simplifie l’affectation d’applications Office 365 ProPlus à des appareils Windows 10. En outre, vous pouvez installer Microsoft Project et Microsoft Visio si vous possédez les licences requises. Les applications souhaitées sont regroupées et apparaissent en tant qu’application unique dans la liste des applications dans la console Intune.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Nouvelles listes verte/rouge pour Managed Browser <!--682960-->

Vous pouvez configurer les listes verte/rouge de domaines et d’URL pour Managed Browser avec les paramètres de Configuration de l’application Intune dans le portail Azure. Vous pouvez configurer ces listes pour Managed Browser même s’il est utilisé sur un appareil non géré.

### <a name="new-app-configuration-capabilities----677969---"></a>Nouvelles fonctionnalités de configuration d’application <!-- 677969 -->

Cette fonctionnalité équivaut à la configuration de l’application de Gestion des appareils mobiles (MDM). Elle permet aux administrateurs d’appliquer des valeurs de configuration d’application autres que celles disponibles par le biais des stratégies de protection des applications dans la GAM sans canal d’inscription.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>Nouvelles conditions de stratégies de protection des applications pour la GAM<!--679864-->

Vous pouvez définir un ensemble de spécifications de GAM pour les utilisateurs sans inscription par l’intermédiaire de la Console d’administration qui applique les éléments suivants :

- Version minimale de l’application
- Version minimale du système d’exploitation
- Version minimale du SDK d’application Intune de l’application cible (iOS uniquement)

Cette fonctionnalité est disponible sur iOS et Android. Intune prend en charge l’application de la version minimale pour les versions de plateformes de système d’exploitation, les versions d’applications et le SDK d’application Intune. Sur iOS, les applications intégrées au SDK peuvent également définir l’application de la version minimale au niveau du SDK.

L’utilisateur ne peut pas accéder à l’application cible si la configuration minimale requise par la stratégie de protection des applications n’est pas satisfaite aux trois niveaux différents mentionnés ci-dessus. À ce stade, l’utilisateur peut supprimer son compte (pour les applications à plusieurs identités), fermer l’application et/ou mettre à jour la version de son système d’exploitation ou de l’application pour satisfaire à la configuration requise.

De plus, vous pouvez configurer des paramètres supplémentaires par l’intermédiaire de la Console d’administration pour fournir une notification non bloquante qui recommande une mise à niveau du système d’exploitation ou de l’application. Cette notification peut être fermée et l’application peut être utilisée normalement.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Changer votre autorité de gestion des appareils mobiles sans annuler l’inscription des appareils gérés <!--1103950-->

Vous pouvez changer votre autorité de gestion des appareils mobiles sans avoir à contacter le Support Microsoft et sans avoir à annuler l’inscription et à réinscrire vos appareils gérés existants. Dans la console Configuration Manager, vous pouvez faire basculer votre autorité de gestion des appareils mobiles de Définir sur Configuration Manager (hybride) à Microsoft Intune (autonome), ou inversement.


### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.

