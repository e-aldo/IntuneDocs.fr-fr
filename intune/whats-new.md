---
title: "Nouveautés de Microsoft Intune"
titleSuffix: Intune on Azure
description: "Découvrez les nouveautés du portail Intune Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dec4fb1d373f49c1f6c15b1f2a9acb2f8d20138d
ms.sourcegitcommit: be12974a7eaa4ce9cffe45aabe456c858d582e20
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Nouveautés de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Découvrez les nouveautés hebdomadaires dans Microsoft Intune. Vous pouvez également découvrir les [modifications à venir](#whats-coming), les [avis importants](#notices) sur le service et des informations sur les [versions précédentes](whats-new-archive.md).

> [!Note]
> De nombreuses de ces fonctionnalités seront finalement prises en charge pour les déploiements hybrides avec Configuration Manager. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   



## <a name="week-of-june-26th-2017"></a>Semaine du 26 juin 2017

### <a name="role-based-access-control"></a>Contrôle d'accès en fonction du rôle
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nouvel accès à l’administration basée sur les rôles pour les administrateurs Intune <!-- 1099990 -->  
Un nouveau rôle d’administrateur d’accès conditionnel est ajouté pour afficher, créer, modifier et supprimer des stratégies d’accès conditionnel dans Azure AD. Auparavant, seuls les administrateurs de sécurité et les administrateurs globaux disposaient de cette autorisation. Les administrateurs Intune peuvent obtenir cette autorisation de rôle afin d’avoir accès aux stratégies d’accès conditionnel.


### <a name="device-enrollment"></a>Inscription des appareils
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Marquer les appareils d’entreprise avec un numéro de série <!-- 1215070 -->  
Intune prend désormais en charge le chargement de numéros de série iOS, macOS et Android en tant qu’identificateurs d’appareil d’entreprise. Vous ne pouvez pas utiliser les numéros de série pour empêcher des appareils personnels de s’inscrire pour le moment, car les numéros de série ne sont pas vérifiés lors de l’inscription. Le blocage des appareils personnels par numéro de série sera disponible dans un futur proche.


### <a name="device-management"></a>Gestion des appareils
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nouvelles actions à distance pour les appareils iOS <!-- 854689 -->
Dans cette version, nous avons ajouté deux actions à distance pour les appareils iPad partagés qui gèrent l’application Apple Classroom :

-   [Déconnecter l’utilisateur actuel](device-logout-user.md) : déconnecte l’utilisateur actuel d’un appareil iOS que vous choisissez.
-   [Supprimer l’utilisateur](device-remove-user.md) : supprime un utilisateur que vous choisissez dans le cache local sur un appareil iOS.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Prise en charge des iPad partagés avec l’application Classroom d’iOS<!-- 1044681 -->
Dans cette version, nous avons développé la prise en charge de la gestion de l’application Classroom iOS afin d’inclure les étudiants qui se connectent à des iPad partagés à l’aide de leur ID Apple géré.


### <a name="app-management"></a>Gestion d'applications  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a>Modifications apportées aux applications intégrées Intune<!-- 1332306 -->

Intune contenait auparavant un certain nombre d’applications intégrées que l’on pouvait affecter rapidement. En réponse à vos commentaires, nous avons supprimé cette liste et ces applications intégrées n’apparaîtront plus.
Toutefois, si vous avez déjà affecté des applications intégrées, elles resteront visibles dans la liste des applications. Vous pouvez continuer à affecter ces applications en fonction de vos besoins.
Dans une version ultérieure, nous prévoyons d’ajouter une méthode plus simple pour sélectionner et affecter des applications intégrées sur le portail Intune.


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>Prise en charge des applications hors connexion à partir du Windows Store pour Entreprises <!--- 777044 --->
Les applications en mode hors connexion que vous avez achetées auprès du Windows Store pour Entreprises seront synchronisées avec le portail Intune. Vous pouvez alors déployer ces applications sur des groupes d’utilisateurs ou d’appareils. Les applications en mode hors connexion sont installées par Intune et non par le Store.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Les équipes Microsoft font désormais partie de la liste d’Autorités de certification basée sur l’application des applications approuvées<!-- 1257019 -->

L’application Microsoft Teams pour iOS et Android fait désormais partie des applications approuvées pour les stratégies d’accès conditionnel basé sur l’application pour Exchange et SharePoint Online. L’application peut être configurée via le panneau Intune App Protection dans le portail Azure pour tous les clients utilisant actuellement l’accès conditionnel basé sur l’application.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser et intégration du proxy d’application <!-- 1287310 -->
 Intune Managed Browser peut maintenant s’intégrer au service du proxy d’application Azure AD pour permettre aux utilisateurs d’accéder aux sites web internes même quand ils travaillent à distance. Les utilisateurs du navigateur entrent simplement l’URL du site comme ils le font normalement et Managed Browser achemine la demande via la passerelle web du proxy d’application. Pour plus d’informations, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser](app-configuration-managed-browser.md).


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nouveaux paramètres de configuration d’application pour Intune Managed Browser <!-- 682951 -->
Dans cette version, nous avons ajouté des configurations supplémentaires pour l’application Intune Managed Browser pour iOS et Android. Vous pouvez maintenant utiliser une stratégie de configuration d’application pour configurer la page d’accueil par défaut et les signets du navigateur.
Pour plus d’informations, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser](app-configuration-managed-browser.md)




### <a name="device-configuration"></a>Configuration des appareils  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Paramètres BitLocker pour Windows 10 <!-- 951707 -->
Vous pouvez maintenant configurer des paramètres BitLocker pour les appareils Windows 10 à l’aide d’un nouveau profil d’appareil Intune. Par exemple, vous pouvez exiger que les appareils soient chiffrés et configurer également d’autres paramètres qui sont appliqués quand BitLocker est activé.
Pour plus d’informations, consultez [Paramètres Endpoint Protection pour Windows 10 et versions ultérieures](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Nouveaux paramètres pour le profil de restriction d’appareils Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

Dans cette version, nous avons ajouté de nouveaux paramètres pour le profil de restriction d’appareil Windows 10 dans les catégories suivantes :

 -  Windows Defender
-  Cellulaire et connectivité
-  Expérience d’écran de verrouillage
-  Confidentialité
-  Search
-  Windows à la une
-  Navigateur Edge

Pour plus d’informations sur les paramètres Windows 10, consultez [Paramètres de restriction des appareils Windows 10 et versions ultérieures](device-restrictions-windows-10.md).

## <a name="week-of-june-12-2017"></a>Semaine du 12 juin 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>L’application Portail d’entreprise pour Android présente désormais une nouvelle expérience d’utilisateur final pour les stratégies de protection des applications <!--1305217-->
En fonction des commentaires des clients, nous avons modifié l’application Portail d’entreprise pour Android afin d’afficher un bouton **Accéder au contenu de l’entreprise**. Le but est d’empêcher les utilisateurs finaux de passer inutilement par le processus d’inscription quand ils ont uniquement besoin d’accéder aux applications qui prennent en charge les stratégies de protection des applications, une fonctionnalité de gestion des applications mobiles Intune. Vous pouvez afficher ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nouvelle action de menu pour supprimer facilement le portail d’entreprise <!--1164569-->
Suite aux commentaires des utilisateurs, l’application Portail d’entreprise pour Android offre désormais une nouvelle action de menu pour lancer la suppression du portail d’entreprise à partir de votre appareil. Cette action supprime l’appareil de la gestion Intune afin que l’application puisse être supprimée à partir de l’appareil par l’utilisateur. Vous pouvez voir ces modifications sur la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md) et dans la [documentation pour les utilisateurs finaux d’Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Améliorations apportées à la synchronisation des applications avec Windows 10 Creators Update<!--676505-->

L’application Portail d’entreprise pour Windows 10 démarre maintenant automatiquement une synchronisation pour les demandes d’installation d’application sur les appareils exécutant Windows 10 Creators Update (version 1703). Cela permet de réduire le problème de blocage des installations d’applications à l’état « Synchronisation en attente ». En outre, les utilisateurs peuvent lancer manuellement une synchronisation à partir de l’application. Vous pouvez afficher ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nouvelle expérience interactive pour le portail d’entreprise Windows 10 <!---1058938--->

L’application Portail d’entreprise pour Windows 10 inclura une expérience de procédure pas à pas Intune interactive pour les appareils qui n’ont pas été identifiés ou inscrits. La nouvelle expérience fournit des instructions détaillées qui guident les utilisateurs lors de l’inscription à Azure Active Directory (requis pour les fonctionnalités d’accès conditionnel) et de l’inscription MDM (obligatoire pour les fonctionnalités de gestion des appareils). L’expérience guidée sera accessible à partir de la page d’accueil de portail d’entreprise. Les utilisateurs peuvent continuer à utiliser l’application s’ils ne terminent pas l’inscription, mais les fonctionnalités seront limitées.

Cette mise à jour est visible uniquement sur les appareils exécutant la Mise à jour anniversaire Windows 10 (build 1607) ou version ultérieure. Vous pouvez afficher ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

## <a name="week-of-june-5-2017"></a>Semaine du 5 juin 2017

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Les consoles d’administration Microsoft Intune et d’accès conditionnel sont généralement disponibles

Nous annonçons la disponibilité générale de la nouvelle console d’administration Intune sur Azure et de la console d’administration d’accès conditionnel. Via Intune sur Azure, vous pouvez désormais gérer toutes les fonctionnalités MAM et MDM Intune dans une expérience d’administration consolidée et tirer parti du regroupement et du ciblage d’Azure AD. L’accès conditionnel dans Azure apporte des fonctionnalités riches sur Azure AD et Intune dans une console unifiée. Et niveau expérience d’administration, la migration vers la plateforme Azure vous permet d’utiliser les navigateurs modernes.

Intune est désormais visible sans l’étiquette **Version préliminaire** dans la console Azure sur portal.azure.com.

Aucune action n’est requise pour les clients existants à ce stade, sauf si vous avez reçu une série de messages dans le centre de message vous demandant d’agir afin que nous puissions faire migrer vos groupes. Vous avez peut-être également reçu un avis du centre de messages vous informant que la migration prenait plus de temps en raison de bogues de notre côté. Nous allons continuer à travailler sans relâche pour migrer les clients concernés.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Améliorations des vignettes de l’application dans l’application Portail d’entreprise pour iOS
Nous avons mis à jour l’apparence des vignettes d’application sur la page d’accueil afin de refléter la couleur de marque que vous définissez pour le portail d’entreprise. Pour en savoir plus, consultez [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Un sélecteur de compte est désormais disponible dans l’application Portail d’entreprise pour iOS
Les utilisateurs d’appareils iOS peuvent voir notre nouveau sélecteur de compte lorsqu’ils se connectent au portail d’entreprise s’ils utilisent leur compte professionnel ou scolaire pour se connecter à d’autres applications Microsoft. Pour en savoir plus, consultez [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

## <a name="week-of-may-29-2017"></a>Semaine du 29 mai 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Changer votre autorité de gestion des appareils mobiles sans annuler l’inscription des appareils gérés <!--1103950-->

Vous pouvez maintenant changer votre autorité de gestion des appareils mobiles sans avoir à contacter le Support Microsoft et sans avoir à annuler l’inscription et à réinscrire vos appareils gérés existants. Dans la console Configuration Manager, vous pouvez faire [basculer votre autorité de gestion des appareils mobiles](/sccm/mdm/deploy-use/change-mdm-authority) de Définir sur Configuration Manager (hybride) à Microsoft Intune (autonome), ou inversement.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notification améliorée pour les codes PIN de démarrage Samsung KNOX<!--1087143-->
Quand les utilisateurs finaux doivent définir un code PIN de démarrage sur les appareils Samsung KNOX pour être compatibles avec le chiffrement, la notification affichée aux utilisateurs finaux les mène à l’emplacement exact dans l’application Paramètres lors de l’appui sur la notification.  Auparavant, la notification menait l’utilisateur final à l’écran de modification de mot de passe.


### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Prise en charge d’Apple School Manager (ASM) avec iPad partagé <!-- 748864, 770395-->

Intune prend maintenant en charge l’utilisation d’Apple School Manager (ASM) à la place du Programme d’inscription d’appareils Apple pour fournir l’inscription des appareils iOS par défaut. L’intégration d’ASM est nécessaire pour utiliser l’application Classroom pour les iPad partagés et pour permettre la synchronisation des données d’ASM vers Azure Active Directory par l’intermédiaire de Microsoft School Data Sync (SDS). Pour plus d’informations, consultez [Activer l’inscription des appareils iOS avec Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> La configuration d’iPad partagés pour travailler avec l’application Classroom requiert des configurations d’éducation iOS dans Azure qui ne sont pas encore disponibles.  Cette fonctionnalité sera bientôt disponible.

### <a name="device-management"></a>Gestion des appareils

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Fournir une assistance à distance sur des appareils Android à l’aide de TeamViewer <!-- 675418 -->

Intune peut maintenant utiliser le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs qui utilisent des appareils Android. Pour plus d’informations, consultez [Fournir une assistance à distance pour les appareils Android gérés par Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Gestion d'applications

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Nouvelles conditions de stratégies de protection des applications pour la GAM<!-- 679864 -->

Vous pouvez maintenant définir un ensemble de spécifications de GAM pour les utilisateurs sans inscription qui applique les éléments suivants :

- Version minimale de l’application
- Version minimale du système d’exploitation
- Version minimale du SDK d’application Intune de l’application cible (iOS uniquement)

Cette fonctionnalité est disponible sur iOS et Android. Intune prend en charge l’application de la version minimale pour les versions de plateformes de système d’exploitation, les versions d’applications et le SDK d’application Intune. Sur iOS, les applications intégrées au SDK peuvent également définir l’application de la version minimale au niveau du SDK. L’utilisateur ne peut pas accéder à l’application cible si la configuration minimale requise par la stratégie de protection des applications n’est pas satisfaite aux trois niveaux différents mentionnés ci-dessus. À ce stade, l’utilisateur peut supprimer son compte (pour les applications à plusieurs identités), fermer l’application et/ou mettre à jour la version de son système d’exploitation ou de l’application.

De plus, vous pouvez configurer des paramètres supplémentaires pour fournir une notification non bloquante qui recommande une mise à niveau du système d’exploitation ou de l’application. Cette notification peut être fermée et l’application peut être utilisée normalement.

Pour plus d’informations, consultez les [paramètres de stratégie de protection des applications iOS](app-protection-policy-settings-ios.md) et les [paramètres de stratégie de protection des applications Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Configurer les configurations d’application pour Android for Work <!-- 621621 -->
Certaines applications Android du Store prennent en charge des options de configuration gérées qui permettent à un administrateur informatique de contrôler la façon dont une application s’exécute dans le profil de travail. Avec Intune, vous pouvez désormais afficher les configurations prises en charge par une application et les configurer à partir du portail Intune avec un concepteur de configuration ou dans un éditeur JSON. Pour plus d’informations, consultez [Utiliser des configurations d’application pour Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nouvelle fonctionnalité de configuration d’application pour la gestion des applications mobiles sans inscription <!-- 677969 -->

Vous pouvez désormais créer des stratégies de configuration d’application via la gestion des applications mobiles sans canal d’inscription. Cette fonctionnalité équivaut aux stratégies de configuration d’application disponibles dans la configuration de l’application de Gestion des appareils mobiles (MDM). Pour un exemple de configuration d’application avec gestion des applications mobiles sans inscription, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Configurer des listes d’URL autorisées et bloquées pour Managed Browser <!-- 682960 -->

Vous pouvez désormais configurer une liste de domaines et d’URL autorisés et bloqués pour Intune Managed Browser avec les paramètres de configuration d’application dans le portail Azure. Vous pouvez configurer ces paramètres même s’il est utilisé sur un appareil non géré. Pour plus d’informations, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Vue du support technique pour les stratégies de protection d’application <!-- 1069473 -->

Les utilisateurs du support technique informatique peuvent désormais vérifier l’état des licences utilisateur et l’état des applications de stratégie de protection d’application affectées aux utilisateurs dans le panneau de la résolution des problèmes. Pour plus d’informations, consultez [Résolution des problèmes](./help-desk-operators.md).

### <a name="device-configuration"></a>Configuration des appareils

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Visites pour le site web de contrôle sur les appareils iOS <!-- 723832 -->

Vous pouvez maintenant contrôler les sites web auxquels les utilisateurs d’appareils iOS peuvent accéder à l’aide de l’une des deux méthodes suivantes :

- Ajouter des URL autorisées et bloquées à l’aide du filtrage de contenu web intégré d’Apple.

- Autoriser uniquement l’accès aux sites web spécifiés par le navigateur Safari. Des signets sont créés dans Safari pour chaque site que vous spécifiez.

Pour plus d’informations, consultez [Paramètres de filtre de contenu web pour les appareils iOS](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Préconfigurer les autorisations d’appareils pour les applications Android for Work<!-- 621614 -->

Pour les applications déployées sur des profils professionnels Android for Work, vous pouvez maintenant configurer l’état des autorisations pour chacune des applications.  Par défaut, les applications Android qui nécessitent des autorisations d’appareils telles que l’accès à l’emplacement ou à l’appareil photo invitent les utilisateurs à accepter ou à refuser les autorisations.  Par exemple, si une application utilise le microphone de l’appareil, l’utilisateur final est invité à autoriser l’application à utiliser le microphone. Cette fonctionnalité vous permet de définir des autorisations pour le compte de l’utilisateur final.  Vous pouvez configurer des autorisations pour a) refuser automatiquement sans en avertir l’utilisateur, b) automatiquement approuver sans en avertir l’utilisateur, ou c) inviter l’utilisateur à accepter ou refuser. Pour plus d’informations, consultez [Paramètres de restriction des appareils Android for Work dans Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Définir un code PIN propre à l’application pour les appareils Android for Work<!-- 728976, 1102534 -->

Vous pouvez définir une stratégie de mot de passe qui s’applique uniquement aux applications dans le profil professionnel pour les appareils Android 7.0 et versions ultérieures avec un profil de travail géré en tant qu’appareil Android for Work.  Les options sont les suivantes :

- Définir simplement une stratégie de mot de passe au niveau de l’appareil : il s’agit du code secret que l’utilisateur final doit utiliser pour déverrouiller son appareil.
 Définir simplement une stratégie de mot de passe de profil professionnel : les utilisateurs sont invités à entrer un code secret chaque fois qu’une application dans le profil professionnel est ouverte.
- Définir à la fois une stratégie d’appareil et une stratégie de profil professionnel : l’administrateur informatique peut définir à la fois une stratégie de code secret d’appareil et une stratégie de code secret de profil professionnel à des niveaux différents (par exemple, un code PIN à quatre chiffres pour déverrouiller l’appareil, mais un code PIN à six chiffres pour ouvrir une application professionnelle).

Pour plus d’informations, consultez [Paramètres de restriction des appareils Android for Work dans Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Cette fonctionnalité est uniquement disponible sur Android 7.0 et versions ultérieures.  Par défaut, l’utilisateur final peut utiliser les deux codes PIN définis séparément, ou il peut choisir de combiner les deux codes PIN définis dans le plus sécurisé des deux.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Nouveaux paramètres pour les appareils Windows 10 <!-- 978585 -->

Nous avons ajouté [de nouveaux paramètres de restriction d’appareil Windows](device-restrictions-windows-10.md) qui contrôlent des fonctionnalités telles que les affichages sans fil, la détection des appareils, le basculement de tâche et les messages d’erreur de carte SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Mises à jour à la configuration de certificat <!-- 918991 and 823198 -->

Lors de la création d’un profil de certificat SCEP, l’option **Personnalisé** option est disponible pour **Format du nom du sujet** sur les appareils iOS, Android et Windows. Avant cette mise à jour, le champ **Personnalisé** était disponible pour les appareils iOS uniquement. Pour plus d’informations, consultez [Guide de création d’un profil de certificat SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Lors de la création d’un profil de certificat PKCS, pour **Autre nom de l’objet**, **Attribut personnalisé Azure AD** est disponible. L’option **Service** est disponible lorsque vous sélectionnez **Attribut personnalisé Azure AD**. Pour plus d’informations, consultez [Guide de création d’un profil de certificat PKCS] (certificates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Configurer plusieurs applications qui peuvent s’exécuter quand un appareil Android est en mode plein écran <!-- 662059 -->

Lorsqu’un appareil Android est en mode plein écran, vous ne pouviez précédemment configurer qu’une application autorisée à s’exécuter. Vous pouvez désormais configurer plusieurs applications à l’aide de l’ID d’application ou de l’URL du Store, ou en sélectionnant une application Android que vous gérez déjà. Pour plus d’informations, consultez [Paramètres du mode plein écran](device-restrictions-android.md#kiosk).


## <a name="notices"></a>Remarques

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Adresses IP pour Intune mises à jour <!-- 1175274 -->

Une [liste mise à jour de noms DNS et d’adresses IP](/intune/network-bandwidth-use) est disponible pour les paramètres de proxy de pare-feu.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Utiliser Azure Active Directory pour l’accès conditionnel <!-- 967947 -->

L’accès conditionnel est disponible dans la section Azure Active Directory de la console Azure et fournit une infrastructure plus puissante et flexible pour la définition de stratégies pour des applications cloud comme Office 365 Exchange Online et SharePoint Online.  Utilisez le panneau **accès conditionnel dans Azure Active Directory** au lieu de la console Intune classique pour configurer des stratégies. Les stratégies existantes dans la console Intune classique doivent être recréées dans la console Azure. Pour plus d’informations, consultez [Créer des stratégies d’accès conditionnel Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->

Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessitent une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder au portail Azure, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure

Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Nouveautés à venir

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fin de la prise en charge d’Android 4.3 et antérieur <!---1171127, 1326920 --->
Les applications gérées et l’application Portail d’entreprise pour Android nécessiteront Android 4.4 et ultérieur pour accéder aux ressources de l’entreprise. Les appareils qui ne sont pas mis à jour avant début octobre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. En décembre, tous les appareils inscrits seront obligatoirement mis hors service et perdront l’accès aux ressources de l’entreprise. Si vous utilisez des stratégies de protection des applications sans MDM, les applications ne recevront aucune mise à jour et perdront en qualité au fil du temps.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Rappel de prise en charge de la plateforme : le support standard de Windows Phone 8.1 prendra fin le 11 juillet 2017
<!-- 1327781 -->

Le 11 juillet 2017, le support standard de la plateforme Windows Phone 8.1 prend fin. Le support des PC Windows 8.1 n’est pas impacté.

Il n’existe aucun impact immédiat sur les appareils Windows Phone 8.1 gérés par le service Intune. Les appareils inscrits continuent de fonctionner, tout comme l’ensemble des stratégies, des configurations et des applications. Notez qu’aucune amélioration n’est prévue pour la plateforme Windows Phone 8.1 au sein du service Intune, ni pour l’application Portail d’entreprise Windows Phone 8.1.

Nous vous recommandons de mettre à niveau les appareils Windows Phone 8.1 éligibles vers Windows 10 Mobile dès que possible. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Modifications apportées à la prise en charge de l’application Portail d’entreprise Intune iOS <!-- 1164474  -->


Une nouvelle version de l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 9.0 ou ultérieure, sera bientôt disponible. La version du portail d’entreprise qui prend en charge iOS 8 sera toujours disponible pendant une très courte période. Toutefois, notez que si vous utilisez également des applications iOS compatibles GAM, nous prenons en charge iOS 9.0 et ultérieur ; vous devez donc vérifier que les utilisateurs finaux effectuent la mise à jour vers le système d’exploitation le plus récent. 

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?
Nous vous donnons cette information à l’avance, même si nous n’avons pas les dates précises, afin que vous ayez le temps de planifier. Vérifiez que vos utilisateurs effectuent la mise à jour vers iOS 9+ et, quand l’application Portail d’entreprise sera publiée, demandez-leur de mettre à jour leur application Portail d’entreprise.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?

Encouragez les utilisateurs à effectuer la mise à jour vers iOS version 9.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  Encouragez les utilisateurs à installer la nouvelle version du portail d’entreprise et à bénéficier des nouvelles fonctionnalités qu’elle propose.

Accédez à Intune dans le portail Azure et affichez Appareils > Tous les appareils, puis filtrez par version d’iOS pour voir tous les appareils actuels avec des systèmes d’exploitation antérieurs à iOS 9.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Amélioration de l’expérience de connexion sur l’ensemble des applications du portail d’entreprise pour toutes les plates-formes<!--User Story 1132123-->

Dans les mois à venir, nous introduirons des changements visant à améliorer l’expérience de connexion aux applications Portail d’entreprise Intune pour Android, iOS et Windows. La nouvelle expérience utilisateur s’affiche automatiquement sur toutes les plates-formes utilisées pour l’application du portail d’entreprise lorsqu’Azure AD apporte cette modification. En outre, les utilisateurs peuvent désormais se connecter au portail d’entreprise à partir d’un autre appareil grâce à un code à usage unique automatiquement généré. Cette fonction se révèle particulièrement utile lorsque les utilisateurs doivent se connecter sans informations d’identification.

Sur la page [Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune](/intune/whats-new-app-ui), vous trouverez des captures d’écran illustrant l’expérience de connexion précédente, la nouvelle expérience de connexion avec informations d’identification, ainsi que la nouvelle expérience de connexion depuis un autre appareil.

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
* [Nouveautés de l’interface utilisateur du portail d’entreprise](whats-new-app-ui.md)
* [Nouveautés des mois précédents](whats-new-archive.md)
