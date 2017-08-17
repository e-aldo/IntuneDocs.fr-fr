---
title: "Nouveautés des mois précédents dans Microsoft Intune"
titleSuffix: Intune on Azure
description: "Passer en revue les annonces antérieures sur la page Nouveautés d’Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 8/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31617fb9992937f43f5bfc3b882f09d4be7de7b6
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2017
---
# <a name="whats-new-in-the-microsoft-intune---previous-months"></a>Nouveautés de la préversion de Microsoft Intune - mois précédents

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="june-2017"></a>Juin 2017

### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Nouvel accès à l’administration basée sur les rôles pour les administrateurs Intune <!-- 1099990 -->  
Un nouveau rôle d’administrateur d’accès conditionnel est ajouté pour afficher, créer, modifier et supprimer des stratégies d’accès conditionnel dans Azure AD. Auparavant, seuls les administrateurs de sécurité et les administrateurs globaux disposaient de cette autorisation. Les administrateurs Intune peuvent obtenir cette autorisation de rôle afin d’avoir accès aux stratégies d’accès conditionnel.


### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Marquer les appareils d’entreprise avec un numéro de série <!-- 1215070 -->  
Intune prend désormais en charge le chargement de numéros de série iOS, macOS et Android en tant qu’identificateurs d’appareil d’entreprise. Vous ne pouvez pas utiliser les numéros de série pour empêcher des appareils personnels de s’inscrire pour le moment, car les numéros de série ne sont pas vérifiés lors de l’inscription. Le blocage des appareils personnels par numéro de série sera disponible dans un futur proche.


### <a name="new-remote-actions-for-ios-devices----854689---"></a>Nouvelles actions à distance pour les appareils iOS <!-- 854689 -->
Dans cette version, nous avons ajouté deux actions à distance pour les appareils iPad partagés qui gèrent l’application Apple Classroom :

-   [Déconnecter l’utilisateur actuel](device-logout-user.md) : déconnecte l’utilisateur actuel d’un appareil iOS que vous choisissez.
-   [Supprimer l’utilisateur](device-remove-user.md) : supprime un utilisateur que vous choisissez dans le cache local sur un appareil iOS.


### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Prise en charge des iPad partagés avec l’application Classroom d’iOS<!-- 1044681 -->
Dans cette version, nous avons développé la prise en charge de la gestion de l’application Classroom iOS afin d’inclure les étudiants qui se connectent à des iPad partagés à l’aide de leur ID Apple géré.


### <a name="changes-to-intune-built-in-apps----1332306---"></a>Modifications apportées aux applications intégrées Intune<!-- 1332306 -->
Intune contenait auparavant un certain nombre d’applications intégrées que l’on pouvait affecter rapidement. En réponse à vos commentaires, nous avons supprimé cette liste et ces applications intégrées n’apparaîtront plus.
Toutefois, si vous avez déjà affecté des applications intégrées, elles resteront visibles dans la liste des applications. Vous pouvez continuer à affecter ces applications en fonction de vos besoins.
Dans une version ultérieure, nous prévoyons d’ajouter une méthode plus simple pour sélectionner et affecter des applications intégrées sur le portail Intune.

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Installation plus facile des applications Office 365 <!--- 1121362 --->
À l’aide du nouveau type d’application **Office 365 ProPlus**, vous pouvez affecter facilement des applications Office 365 ProPlus 2016 aux appareils que vous gérez et qui exécutent la dernière version de Windows 10. Vous pouvez également installer Microsoft Project et Microsoft Visio si vous disposez des licences appropriées. Les applications souhaitées sont regroupées et apparaissent sous la forme d’une application unique dans la liste des applications de la console Intune.
Pour plus d’informations, consultez [Guide pratique pour ajouter des applications Office 365 pour Windows 10](apps-add-office365.md).


### <a name="support-for-offline-apps-from-the-microsoft-store-for-business-----777044----"></a>Prise en charge des applications hors connexion à partir du Microsoft Store pour Entreprises <!--- 777044 --->
Les applications en mode hors connexion que vous avez achetées sur le Microsoft Store pour Entreprises sont désormais synchronisées avec le portail Intune. Vous pouvez alors déployer ces applications sur des groupes d’utilisateurs ou d’appareils. Les applications en mode hors connexion sont installées par Intune et non par le Store.

### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>Les équipes Microsoft font désormais partie de la liste d’Autorités de certification basée sur l’application des applications approuvées<!-- 1257019 -->
L’application Microsoft Teams pour iOS et Android fait désormais partie des applications approuvées pour les stratégies d’accès conditionnel basé sur l’application pour Exchange et SharePoint Online. L’application peut être configurée via le panneau Intune App Protection dans le portail Azure pour tous les clients utilisant actuellement l’accès conditionnel basé sur l’application.

### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Managed Browser et intégration du proxy d’application <!-- 1287310 -->
Intune Managed Browser peut maintenant s’intégrer au service du proxy d’application Azure AD pour permettre aux utilisateurs d’accéder aux sites web internes même quand ils travaillent à distance. Les utilisateurs du navigateur entrent simplement l’URL du site comme ils le font normalement et Managed Browser achemine la demande via la passerelle web du proxy d’application. Pour plus d’informations, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser](app-configuration-managed-browser.md).

### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Nouveaux paramètres de configuration d’application pour Intune Managed Browser <!-- 682951 -->
Dans cette version, nous avons ajouté des configurations supplémentaires pour l’application Intune Managed Browser pour iOS et Android. Vous pouvez maintenant utiliser une stratégie de configuration d’application pour configurer la page d’accueil par défaut et les signets du navigateur.
Pour plus d’informations, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser](app-configuration-managed-browser.md)

### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Paramètres BitLocker pour Windows 10 <!-- 951707 -->
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


### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>L’application Portail d’entreprise pour Android présente désormais une nouvelle expérience d’utilisateur final pour les stratégies de protection des applications <!--1305217-->
En fonction des commentaires des clients, nous avons modifié l’application Portail d’entreprise pour Android afin d’afficher un bouton **Accéder au contenu de l’entreprise**. Le but est d’empêcher les utilisateurs finaux de passer inutilement par le processus d’inscription quand ils ont uniquement besoin d’accéder aux applications qui prennent en charge les stratégies de protection des applications, une fonctionnalité de gestion des applications mobiles Intune. Vous pouvez afficher ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nouvelle action de menu pour supprimer facilement le portail d’entreprise <!--1164569-->
Suite aux commentaires des utilisateurs, l’application Portail d’entreprise pour Android offre désormais une nouvelle action de menu pour lancer la suppression du portail d’entreprise à partir de votre appareil. Cette action supprime l’appareil de la gestion Intune afin que l’application puisse être supprimée à partir de l’appareil par l’utilisateur. Vous pouvez voir ces modifications sur la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md) et dans la [documentation pour les utilisateurs finaux d’Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Améliorations apportées à la synchronisation des applications avec Windows 10 Creators Update<!--676505-->
L’application Portail d’entreprise pour Windows 10 démarre maintenant automatiquement une synchronisation pour les demandes d’installation d’application sur les appareils exécutant Windows 10 Creators Update (version 1703). Cela permet de réduire le problème de blocage des installations d’applications à l’état « Synchronisation en attente ». En outre, les utilisateurs peuvent lancer manuellement une synchronisation à partir de l’application. Vous pouvez afficher ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nouvelle expérience interactive pour le portail d’entreprise Windows 10 <!---1058938--->
L’application Portail d’entreprise pour Windows 10 inclura une expérience de procédure pas à pas Intune interactive pour les appareils qui n’ont pas été identifiés ou inscrits. La nouvelle expérience fournit des instructions détaillées qui guident les utilisateurs lors de l’inscription à Azure Active Directory (requis pour les fonctionnalités d’accès conditionnel) et de l’inscription MDM (obligatoire pour les fonctionnalités de gestion des appareils). L’expérience guidée sera accessible à partir de la page d’accueil de portail d’entreprise. Les utilisateurs peuvent continuer à utiliser l’application s’ils ne terminent pas l’inscription, mais les fonctionnalités seront limitées.

Cette mise à jour est visible uniquement sur les appareils exécutant la Mise à jour anniversaire Windows 10 (build 1607) ou version ultérieure. Vous pouvez afficher ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).


### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Les consoles d’administration Microsoft Intune et d’accès conditionnel sont généralement disponibles
Nous annonçons la disponibilité générale de la nouvelle console d’administration Intune sur Azure et de la console d’administration d’accès conditionnel. Via Intune sur Azure, vous pouvez désormais gérer toutes les fonctionnalités MAM et MDM Intune dans une expérience d’administration consolidée et tirer parti du regroupement et du ciblage d’Azure AD. L’accès conditionnel dans Azure apporte des fonctionnalités riches sur Azure AD et Intune dans une console unifiée. Et niveau expérience d’administration, la migration vers la plateforme Azure vous permet d’utiliser les navigateurs modernes.

Intune est désormais visible sans l’étiquette **Version préliminaire** dans la console Azure sur portal.azure.com.

Aucune action n’est requise pour les clients existants à ce stade, sauf si vous avez reçu une série de messages dans le centre de message vous demandant d’agir afin que nous puissions faire migrer vos groupes. Vous avez peut-être également reçu un avis du centre de messages vous informant que la migration prenait plus de temps en raison de bogues de notre côté. Nous allons continuer à travailler sans relâche pour migrer les clients concernés.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Améliorations des vignettes de l’application dans l’application Portail d’entreprise pour iOS
Nous avons mis à jour l’apparence des vignettes d’application sur la page d’accueil afin de refléter la couleur de marque que vous définissez pour le portail d’entreprise. Pour en savoir plus, consultez [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Un sélecteur de compte est désormais disponible dans l’application Portail d’entreprise pour iOS
Les utilisateurs d’appareils iOS peuvent voir notre nouveau sélecteur de compte lorsqu’ils se connectent au portail d’entreprise s’ils utilisent leur compte professionnel ou scolaire pour se connecter à d’autres applications Microsoft. Pour en savoir plus, consultez [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).

## <a name="may-2017"></a>Mai 2017

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
- Définir simplement une stratégie de mot de passe de profil professionnel : les utilisateurs sont invités à entrer un code secret chaque fois qu’une application dans le profil professionnel est ouverte.
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



## <a name="april-2017"></a>Avril 2017

### <a name="support-for-managing-the-apple-classroom-app"></a>Prise en charge de la gestion de l’application Apple Classroom
Vous pouvez désormais gérer l’application iOS Classroom sur des appareils iPad. Configurez l’application Classroom sur l’iPad des enseignants avec les données sur les étudiants et les cours appropriées, puis configurez les iPad des étudiants inscrits à un cours, afin que vous puissiez les contrôler à l’aide de l’application.
Pour plus d’informations, consultez [Configurer les paramètres d’éducation iOS](education-settings-configure-ios.md).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Prise en charge des options de configuration gérées pour les applications Android <!-- 621621 -->
Les applications Android dans le Play Store qui prennent en charge les options de configuration gérées peuvent désormais être configurées par Intune.  Cette fonctionnalité permet au personnel informatique d’afficher la liste des valeurs de configuration prises en charge par une application, et fournit une interface interactive et guidée de premier plan pour lui permettre de configurer ces valeurs.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nouvelle stratégie Android pour les codes PIN complexes <!-- 722069 -->
Vous pouvez maintenant définir un type de [mot de passe](device-restrictions-android.md#password) requis « Chiffres complexes » dans un profil d’appareil Android pour les appareils qui exécutent Android 5.0 et versions ultérieures.  Utilisez ce paramètre pour empêcher les utilisateurs d’appareils de créer un code PIN qui contient des nombres répétés ou consécutifs, tel que 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Prise en charge supplémentaire des appareils Android for Work
- **Gérer les paramètres de profil professionnel et de mot de passe** <!-- 612808 -->

  Cette nouvelle stratégie de restriction d’appareil Android for Work vous permet maintenant de gérer les paramètres de profil professionnel et de mot de passe sur les appareils Android for Work que vous gérez.

- **Autoriser le partage de données entre profils professionnels et personnels** <!-- 1045102 -->

Ce profil de restriction d’appareil Android for Work a été enrichi de nouvelles options afin de vous aider à configurer le partage de données entre vos profils personnels et professionnels.

- **Limiter la copie et le collage entre profils professionnels et personnels** <!-- 1046094 -->

  Ce nouveau profil d’appareil personnalisé pour les appareils Android for Work vous permet de désormais limiter les actions Copier et Coller entre applications professionnelles et personnelles.

Pour plus d’informations, consultez [Device restrictions for Android for Work](device-restrictions-android-for-work.md) (Restrictions d’appareils pour Android for Work).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Affecter des applications métier aux appareils iOS et Android <!-- 1057568 -->
Vous pouvez désormais affecter des applications métier pour [iOS](lob-apps-ios.md) (fichiers .ipa) et [Android](lob-apps-android.md) (fichiers .apk) à des utilisateurs ou des appareils.


###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nouvelles stratégies d’appareil pour iOS <!-- 723774, 723815, 723826, 723830 -->
- **Applications dans l’écran d’accueil** : contrôle les applications qui s’affichent dans [l’écran d’accueil de l’appareil iOS](home-screen-settings-ios.md) d’un utilisateur. Cette stratégie change la disposition de l’écran d’accueil, mais ne déploie aucune application.

- **Connexions aux appareils AirPrint** : contrôle les [appareils AirPrint](air-print-settings-ios-macos.md) (imprimantes réseau) auxquels les utilisateurs finaux d’appareils iOS peuvent se connecter.

- **Connexions aux appareils AirPlay** : contrôle les [appareils AirPlay](airplay-settings-ios.md) (comme Apple TV) auxquels les utilisateurs finaux d’appareils iOS peuvent se connecter.

- **Message d’écran de verrouillage personnalisé** : permet de configurer un message personnalisé qui s’affiche sur l’écran de verrouillage des appareils iOS à la place du message d’écran de verrouillage par défaut. Pour plus d’informations, consultez [Activer le mode Perdu sur les appareils iOS](device-lost-mode.md)

### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restreindre les notifications Push pour les applications iOS <!-- 723767 -->
Dans un profil de restriction d’appareil Intune, vous pouvez maintenant configurer les [paramètres de notification](app-notification-settings-ios.md) suivants pour les appareils iOS :

- Activer ou désactiver entièrement la notification pour une application spécifiée.
- Activer ou désactiver la notification dans le Centre de notification pour une application spécifiée.
- Spécifier le type d’alerte : **Aucune**, **Bannière** ou **Alerte modale**.
- Spécifier si les badges sont autorisés pour cette application.
- Spécifier si les sons de notification sont autorisés.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configurer les applications iOS pour s’exécuter en mode Application unique autonome <!-- 737837 -->
Vous pouvez désormais utiliser un profil d’appareil Intune pour configurer les appareils iOS pour qu’ils exécutent les applications spécifiées en [mode Application unique autonome](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Quand ce mode est configuré et que l’application est exécutée, l’appareil est verrouillé et il ne peut exécuter que cette application. Vous pouvez par exemple utiliser ce mode quand vous configurez une application qui permet aux utilisateurs d’effectuer un test sur l’appareil. Une fois les actions de l’application terminées, ou si vous supprimez cette stratégie, l’appareil retourne à son état normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configurer des domaines approuvés pour l’e-mail et la navigation web sur des appareils iOS <!-- 723765 -->
À partir d’un profil de restriction d’appareil iOS, vous pouvez maintenant configurer les [paramètres de domaine suivants](device-restrictions-ios.md#domains) :

- **Domaines d’e-mail non marqués** - Les e-mails reçus ou envoyés par l’utilisateur qui ne correspondent pas aux domaines que vous spécifiez ici sont marqués comme non approuvés.

- **Domaines web gérés** - Les documents téléchargés à partir des URL que vous spécifiez ici sont considérés comme gérés (Safari uniquement).  

- **Domaines de remplissage automatique des mots de passe Safari** - Les utilisateurs peuvent enregistrer des mots de passe dans Safari uniquement à partir des URL qui correspondent aux modèles que vous spécifiez ici. Pour utiliser ce paramètre, il faut que l’appareil soit en mode supervisé et non configuré pour plusieurs utilisateurs. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Applications VPP disponibles dans le portail d’entreprise iOS <!-- 748782 -->
Vous pouvez désormais affecter des applications achetées en volume (VPP) iOS comme installations **disponibles** pour les utilisateurs finaux. Ces derniers auront besoin d’un compte Apple Store pour installer l’application.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchroniser des livres électroniques à partir de l’Apple VPP Store <!-- 800878 -->
Vous pouvez maintenant [synchroniser les livres](vpp-apps-ios.md) que vous avez achetés dans le Store VPP (Programme d’achat en volume) d’Apple avec Intune, et les attribuer à des utilisateurs.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gestion des utilisateurs multiples pour les appareils Samsung KNOX Standard <!-- 971988 -->
Les appareils qui exécutent Samsung KNOX Standard sont désormais pris en charge pour la [gestion des utilisateurs multiples](android-enroll.md) par Intune. Cela signifie que les utilisateurs finaux peuvent se connecter et se déconnecter de l’appareil avec leurs informations d’identification Azure Active Directory, et que l’appareil est géré de façon centralisée qu’il soit en cours d’utilisation ou non.  Quand les utilisateurs finaux se connectent, ils ont accès aux applications et les éventuelles stratégies sont appliquées à ces applications. Quand les utilisateurs se déconnectent, toutes les données d’application sont effacées.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Paramètres supplémentaires de restriction d’appareil Windows <!-- 818566 -->
Nous avons ajouté la prise en charge d’autres [paramètres de restriction d’appareil Windows](device-restrictions-windows-10.md), comme une prise en charge supplémentaire du navigateur Edge, la personnalisation de l’écran de verrouillage d’appareil, la personnalisation du menu Démarrer, les papiers peints Windows à la une et les paramètres de proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Prise en charge multi-utilisateur pour Windows 10 Creators Update <!-- 822547 -->
Nous avons ajouté la prise en charge de la [gestion des utilisateurs multiples](windows-enroll.md) pour les appareils qui exécutent Windows 10 Creators Update et sont joints à un domaine Azure Active Directory. Cela signifie que quand différents utilisateurs standard se connectent à l’appareil avec leurs informations d’identification Azure AD, ils reçoivent les applications et les stratégies qui ont été affectées à leur nom d’utilisateur. Les utilisateurs ne peuvent actuellement pas utiliser le portail d’entreprise pour les scénarios de libre-service tels que l’installation d’applications.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start pour les PC Windows 10<!-- 1004830 -->
Une nouvelle [action d’appareil Fresh Start](device-fresh-start.md) est maintenant disponible pour les PC Windows 10.  Quand vous exécutez cette action, les applications qui ont été installées sur l’ordinateur sont supprimées, et le PC est automatiquement mis à jour vers la dernière version de Windows. Vous pouvez ainsi supprimer des applications OEM préinstallées, comme celles qui sont souvent fournies avec un nouveau PC. Vous pouvez configurer si les données utilisateur sont conservées quand cette action est exécutée sur l’appareil.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Chemins de mise à niveau Windows 10 supplémentaires <!-- 903672 -->
Vous pouvez désormais créer une [stratégie de mise à niveau d’édition pour mettre à niveau les appareils](edition-upgrade-configure-windows-10.md) vers les éditions Windows 10 supplémentaires suivantes :

- Windows 10 Professionnel
- Windows 10 Professionnel N
- Windows 10 Professionnel Éducation
- Windows 10 Professionnel Éducation N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Inscription en bloc des appareils Windows 10 <!-- 747607 -->
Vous pouvez désormais joindre un grand nombre d’appareils qui exécutent la mise à jour Windows 10 Creators pour Azure Active Directory et Intune à l’aide du Concepteur de configuration Windows (WCD). Pour activer [l’inscription MDM en bloc](windows-bulk-enroll.md) pour votre client Azure AD, créez un package de configuration qui joint les appareils à votre client Azure AD à l’aide du Concepteur de configuration Windows, puis appliquez le package aux appareils d’entreprise que vous souhaitez inscrire et gérer en bloc. Une fois le package appliqué à vos appareils, ceux-ci se connectent à Azure AD et s’inscrivent dans Intune. Ils sont alors prêts pour que vos utilisateurs Azure AD s’y connectent.  Les utilisateurs d’Azure AD agissent sur ces appareils en tant qu’utilisateurs standard ; ils reçoivent les stratégies qui leur sont affectées ainsi que les applications dont ils ont besoin. Les scénarios de libre-service et de portail d’entreprise ne sont pas pris en charge actuellement.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nouveaux paramètres GAM pour les codes PIN et les emplacements de stockage géré <!-- 581122, 736644 -->
Deux nouveaux paramètres d’application sont désormais disponibles pour vous aider dans les scénarios de gestion des applications mobiles (GAM) :

- **Désactiver le code PIN de l’application quand le code PIN de l’appareil est géré** - Détecte si un code PIN d’appareil est présent sur l’appareil inscrit et, si c’est le cas, contourne le code PIN de l’application déclenché par les stratégies de protection des applications. Ce paramètre permet de réduire le nombre d’invites de code PIN pour les utilisateurs ouvrant une application GAM sur un appareil inscrit. Cette fonctionnalité est disponible pour iOS et Android.

- **Sélectionnez dans quels services de stockage les données d’entreprise peuvent être enregistrées** - Permet de spécifier les emplacements de stockage où enregistrer les données d’entreprise. Les utilisateurs peuvent enregistrer dans les services d’emplacement de stockage sélectionnés, ce qui signifie que tous les autres services d’emplacement de stockage non répertoriés seront bloqués.

  Liste des services d’emplacement de stockage pris en charge :

  - OneDrive Entreprise
  - SharePoint Online
  - Stockage local

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portail de dépannage du centre de support technique <!-- 907448 -->
Le nouveau [portail de dépannage](help-desk-operators.md) permet aux opérateurs du centre de support technique et aux administrateurs Intune de visualiser les utilisateurs et leurs appareils, et d’effectuer des tâches pour résoudre les problèmes techniques liés à Intune.

## <a name="march-2017"></a>Mars 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Prise en charge du mode Perdu iOS<!--431695-->
Pour les appareils iOS 9.3 et versions ultérieures, Intune a ajouté la prise en charge du **Mode Perdu**. Vous pouvez maintenant verrouiller un appareil pour éviter toute utilisation et afficher un numéro de téléphone de contact et un message sur l’écran de verrouillage de l’appareil.

L’utilisateur final ne peut pas déverrouiller l’appareil tant qu’un administrateur n’a pas désactivé le mode Perdu. Lorsque le mode Perdu est activé, vous pouvez utiliser l’action **Localiser l’appareil** pour afficher l’emplacement géographique de l’appareil sur une carte dans la console Intune.

L’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé.

Pour plus d’informations, consultez [Qu’est-ce que la gestion des appareils Microsoft Intune ?](device-management.md)

### <a name="improvements-to-device-actions-report---677150--"></a>Améliorations du rapport Actions de l’appareil <!--677150-->
Nous avons apporté des améliorations au rapport Actions de l’appareil afin d’optimiser les performances. En outre, il est désormais possible de filtrer le rapport par état. Par exemple, vous pouvez filtrer le rapport pour qu’il affiche uniquement les actions d’appareil qui ont été effectuées.

### <a name="custom-app-categories---748805--"></a>Catégories d’applications personnalisées <!--748805-->
Vous pouvez désormais créer, modifier et attribuer des catégories pour les applications que vous ajoutez à Intune. Actuellement, les catégories ne peuvent être spécifiées qu'en anglais.
Consultez [Guide pratique pour ajouter une application à Intune](apps-add.md).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Attribuer des applications cœur de métier aux utilisateurs disposant d’appareils non inscrits <!--748823-->
Vous pouvez désormais attribuer aux utilisateurs des applications cœur de métier à partir du Store, que leurs appareils soient ou non inscrits auprès d’Intune. Si l’appareil n’est pas inscrit auprès de Intune, l’utilisateur doit se rendre sur le site web du portail d’entreprise, au lieu de l’application du portail d’entreprise, pour l’installer.

### <a name="new-compliance-reports---846671--"></a>Nouveaux rapports de conformité <!--846671-->
Vous disposez désormais de rapports de conformité qui vous indiquent la situation de conformité des appareils de votre société et vous permettent de résoudre rapidement les problèmes liés à la conformité rencontrés par vos utilisateurs. Vous pouvez visualiser des informations sur les éléments suivants :

- État de conformité global des appareils
- État de conformité d’un paramètre spécifique
- État de conformité d’une stratégie spécifique

Vous pouvez également utiliser ces rapports pour explorer les détails d’un appareil individuel afin de visualiser les paramètres et stratégies spécifiques affectant cet appareil.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessiteront une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder à la version préliminaire, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.


## <a name="february-2017"></a>Février 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Possibilité de limiter l’inscription des appareils mobiles <!--747600, 795782-->
Intune ajoute de nouvelles restrictions d’inscription qui contrôlent les plateformes d’appareils mobiles autorisées à être inscrites. Intune sépare les plateformes d’appareils mobiles comme iOS, MacOS, Android, Windows et Windows Mobile.

* La restriction de l’inscription d’appareils mobiles ne limite pas l’inscription des clients de PC.  
* Pour iOS et Android uniquement, il existe une option supplémentaire pour bloquer l’inscription des appareils personnels.

Intune marque tous les nouveaux appareils comme personnels, sauf si l’administrateur prend des mesures pour les marquer comme appareils d’entreprise, comme expliqué dans [cet article](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Afficher toutes les actions sur les appareils gérés <!--677150-->
Un nouveau rapport __Actions de l’appareil__ indique l’utilisateur qui a effectué des actions à distance, comme un rétablissement des paramètres d’usine sur les appareils, et montre également l’état de cette action. Consultez [Qu’est-ce que la gestion des appareils ?](device-management.md).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Les appareils non gérés peuvent accéder aux applications attribuées <!--664691-->
Dans le cadre des modifications conceptuelles du site web du portail d’entreprise, les utilisateurs iOS et Android peuvent installer les applications attribuées indiquées comme « disponibles sans inscription » sur leurs appareils non gérés. À l’aide de leurs informations d’identification Intune, les utilisateurs peuvent se connecter au site web du portail d’entreprise et afficher la liste des applications qui leur sont attribuées. Les packages des applications « disponibles sans inscription » peuvent être téléchargés sur le site web du portail d’entreprise. Les applications dont l’installation nécessite une inscription ne sont pas affectées par cette modification, car les utilisateurs sont invités à inscrire leur appareil s’ils souhaitent installer ces applications.

### <a name="custom-app-categories---748805--"></a>Catégories d’applications personnalisées <!--748805-->
Vous pouvez désormais créer, modifier et attribuer des catégories pour les applications que vous ajoutez à Intune. Actuellement, les catégories ne peuvent être spécifiées qu'en anglais.
Consultez [Guide pratique pour ajouter une application à Intune](apps-add.md).

### <a name="display-device-categories---814654--"></a>Afficher des catégories d’appareils <!--814654-->
Vous pouvez maintenant afficher la catégorie d’appareil sous forme de colonne dans la liste des appareils. Vous pouvez également modifier la catégorie dans la section des propriétés du panneau Propriétés de l’appareil. Consultez [Guide pratique pour ajouter une application à Intune](apps-add.md).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Configurer les paramètres Windows Update for Business <!--776716-->

Windows en tant que service est la nouvelle façon de fournir des mises à jour pour Windows 10. À partir de Windows 10, les nouvelles mises à jour de fonctionnalités et qualité incluent le contenu de toutes les mises à jour précédentes. Cela signifie que tant que vous avez installé la dernière mise à jour, vous savez que vos appareils Windows 10 sont entièrement à jour. À la différence des versions précédentes de Windows, vous devez maintenant installer la mise à jour complète au lieu d’une partie seulement.

En utilisant Windows Update for Business, vous pouvez simplifier l’expérience de gestion des mises à jour et vous ne devez plus approuver des mises à jour propres à des groupes d’appareils. Vous pouvez toujours gérer les risques dans votre environnement en configurant une stratégie de déploiement de mises à jour afin que Windows Update fasse en sorte que les mises à jour soient installées au moment opportun. Microsoft Intune permet de configurer les paramètres de mise à jour des appareils et vous donne la possibilité de reporter l’installation des mises à jour. Intune ne stocke pas les mises à jour, seulement l’attribution des stratégies de mise à jour. Les appareils accèdent directement à Windows Update. Utilisez Intune pour configurer et gérer les **anneaux de mise à jour Windows 10**. Un anneau de mise à jour contient un groupe de paramètres permettant de configurer le moment et la façon d’installer les mises à jour Windows 10. Pour plus d’informations, consultez [Configurer les paramètres Windows Update for Business](windows-update-for-business-configure.md).

## <a name="january-2017"></a>Janvier 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Attribuer des applications métier que les appareils soient inscrits ou non<!--748823-->
Vous pouvez désormais attribuer aux utilisateurs des applications métier à partir du Store, que leurs appareils soient inscrits ou non auprès d'Intune. Si l'appareil de l’utilisateur n’est pas inscrit auprès d'Intune, ce dernier doit se rendre sur le site web du portail d’entreprise, au lieu de l’application du portail d’entreprise, pour l'installer. Consultez [Qu’est-ce que la gestion des applications](app-management.md).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Résoudre le problème quand les appareils iOS sont inactifs ou que la console d’administration ne peut pas communiquer avec eux
Quand les appareils des utilisateurs perdent le contact avec Intune, vous pouvez leur appliquer de nouvelles étapes de dépannage pour leur permettre de récupérer l’accès aux ressources d’entreprise. Consultez [Les appareils sont inactifs ou la console d’administration ne peut pas communiquer avec eux](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Décembre 2016 (première version)

### <a name="telecom-expense-management-integration-in-azure-portal--747605--"></a>Intégration de la gestion des dépenses de télécommunications dans le portail Azure<!--747605-->
Nous avons commencé à afficher un aperçu de l’intégration aux services de gestion des dépenses de télécommunications au sein du portail Azure. Vous pouvez utiliser Intune pour appliquer des limites à l’utilisation des données domestiques et itinérantes. Nous allons commencer ces intégrations avec [Saaswedo](http://www.saaswedo.com). Pour activer cette fonctionnalité dans votre client d’évaluation, veuillez [contacter le support technique Microsoft](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

- Déploiement et gestion des applications depuis un Store sur les appareils iOS, Android et Windows
- Déploiement et gestion des applications métier (LOB) pour appareils iOS, Android et Windows
- Déploiement et gestion des applications achetées en volume pour appareils iOS et Windows
- Déploiement et gestion des applications web pour les appareils Android, iOS et Windows
- Profils de configuration des applications gérées iOS
- Configuration de stratégies de protection d’application et déploiement d’applications métier sur des appareils qui ne sont pas inscrits avec Intune
- Profils VPN, VPN par application, Wi-Fi, messagerie et profils de certificat
- Stratégies de conformité
- Accès conditionnel pour Azure AD
- Accès conditionnel à Exchange local
- Inscription des appareils
- Contrôle d'accès en fonction du rôle

## <a name="deprecated-features-in-the-azure-portal"></a>Fonctionnalités déconseillées dans le portail Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Prise en charge de l’analyse ligne par ligne des identificateurs de matériel
Le portail Azure ne prend pas en charge l’analyse ligne par ligne des identificateurs de matériel pour les numéros IMEI et les numéros de série Apple. Dans la console Intune classique, vous pouvez importer des informations à partir d’un fichier à valeurs séparées par des virgules (.csv) et remplacer les informations existantes des identificateurs de matériel. Le portail Azure propose une option unique et simplifiée pour automatiquement remplacer les informations pour tous les identificateurs de matériel ou ignorer les nouvelles informations pour les identificateurs existants.

#### <a name="how-this-affects-you"></a>Comment cela vous affecte
Dans le portail Azure, vous ne serez pas en mesure de choisir, ligne par ligne, les appareils International Mobile Equipment Identity (IMEI) à mettre à jour. La console Intune classique continuera à prendre en charge cette fonctionnalité.

#### <a name="how-to-get-ready-for-this-change"></a>Comment se préparer à cette modification
Nous fournissons ces informations à l’avance. Ainsi, si elles vous concernent, vous pouvez informer vos administrateurs de cette modification. Cette modification coïncide avec la migration vers le portail Azure, attendu pour la première moitié de 2017.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Prise en charge par défaut des profils d’inscription d’appareil professionnel dans Apple DEP
Le portail Azure ne prend pas en charge le profil d’inscription d’appareil d’entreprise « Par défaut » pour les numéros de série d’appareil Apple DEP. Cette fonctionnalité, disponible dans la console Intune classique, est interrompue pour empêcher l’attribution de profils par inadvertance. Dans le portail Azure, les numéros de série synchronisés à partir d’un compte Apple DEP n’auront initialement aucun profil d’inscription d’appareil d’entreprise affecté.

#### <a name="how-this-affects-you"></a>Comment cela vous affecte
Dans le portail Azure, vous ne serez pas en mesure de définir une stratégie de profil par défaut sur tous les appareils Apple. La console Intune classique continuera à prendre en charge cette fonctionnalité.

#### <a name="how-to-get-ready-for-this-change"></a>Comment se préparer à cette modification
Nous fournissons ces informations à l’avance. Ainsi, si elles vous concernent, vous pouvez informer vos administrateurs de cette modification. Cela coïncide avec la migration vers le portail Azure, attendue pour la première moitié de 2017.

### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
