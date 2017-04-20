---
title: "Édition anticipée | Microsoft Docs"
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0a39abc7f19f4c2c8074de66a9cd5df9cef78ed5
ms.openlocfilehash: 2b6e29e7323d42b1ce3d75a46648203a7a43165c
ms.lasthandoff: 04/13/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>Édition anticipée pour Microsoft Intune - Avril 2017

L’**édition anticipée** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
> Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nouvelles fonctionnalités

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Amélioration de l’état d’installation de l’application pour l’application Portail d’entreprise Windows 10 <!--676495-->

L’application Portail d’entreprise Windows 10 fournit désormais une barre de progression d’installation pour toutes les installations d’applications modernes démarrées à partir du portail d’entreprise.

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Amélioration de la messagerie d’état dans l’application Portail d’entreprise pour iOS <!--744866-->

De nouveaux messages d’erreur plus spécifiques sont désormais affichés dans l’application Portail d’entreprise pour iOS, afin de fournir des informations plus accessibles sur ce qui se passe sur les appareils. Ces cas d’erreur étaient dans un message d’erreur général intitulé « Portail d’entreprise temporairement indisponible ». En outre, si un utilisateur lance le portail d’entreprise sur iOS quand il ne dispose pas d’une connexion Internet, une barre d’état persistante indiquant « Aucune connexion Internet » est affichée dans la page d’accueil.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps disponibles pour Managed Browser <!--822308, 822303-->

Microsoft MyApps bénéficie d’une meilleure prise en charge dans Managed Browser. Les utilisateurs de Managed Browser qui ne sont pas ciblés pour la gestion sont dirigés directement vers le service MyApps, où il peuvent accéder à leurs applications SaaS configurées par l’administrateur. Les utilisateurs ciblés pour la gestion Intune continueront à pouvoir accéder à MyApps à partir du signet Managed Browser intégré.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nouvelles icônes pour Managed Browser et le portail d’entreprise <!--918433, 918431-->

Managed Browser reçoit des icônes mises à jour pour les versions iOS et Android de l’application. La nouvelle icône contient le badge Intune mis à jour, pour une meilleure cohérence avec d’autres applications Enterprise Mobility + Security (EM+S). Vous pouvez voir la nouvelle icône de Managed Browser sur la [page Nouveautés de l’interface utilisateur des applications Intune](whats-new-in-intune-app-ui.md).

Le portail d’entreprise reçoit également des icônes mises à jour pour les versions Android, iOS et Windows de l’application, afin d’améliorer la cohérence avec d’autres applications dans EM + S. Ces icônes seront publiées progressivement sur toutes les plateformes du mois d’avril jusqu’à fin mai.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Prise en charge de l’authentification unique entre le portail d’entreprise pour iOS et Outlook pour iOS <!--834012-->

Les utilisateurs n’ont plus besoin de se connecter à l’application Outlook s’ils sont connectés à l’application Portail d’entreprise pour iOS sur le même appareil avec le même compte. Quand les utilisateurs lancent l’application Outlook, ils peuvent sélectionner leur compte et se connecter automatiquement. Nous travaillons également à l’ajout de cette fonctionnalité à d’autres applications Microsoft.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicateur de progression de connexion dans le portail d’entreprise Android <!--953374-->

Une mise à jour de l’application Portail d’entreprise Android affiche un indicateur de progression de connexion quand l’utilisateur lance l’application ou effectue une reprise. L’indicateur affiche successivement les nouveaux états, en commençant par « Connexion... », puis « Connexion en cours », puis « Vérification des exigences de sécurité... », avant d’autoriser l’utilisateur à accéder à l’application. Vous pouvez voir les nouveaux écrans de l’application Portail d’entreprise pour Android sur la [page Nouveautés de l’interface utilisateur des applications Intune](whats-new-in-intune-app-ui.md). 


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

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?

Cela n’affecte aucun de vos déploiements existants vers des appareils qui sont gérés par l’intermédiaire de l’agent de PC Intune. Toutefois, après la migration, vous ne pourrez pas déployer ces appxs migrés vers de nouveaux appareils gérés par l’intermédiaire de l’agent de PC Intune qui n’étaient pas précédemment ciblés.

#### <a name="what-action-do-i-need-to-take"></a>Que dois-je faire ?

Après la migration, vous devez retélécharger l’appx en tant qu’appx PC si vous voulez effectuer de nouveaux déploiements de PC. Pour en savoir plus, consultez [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Changement relatif aux appx dans Intune sur Azure) sur le blog de l’équipe de support technique Intune.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Préversion publique de la nouvelle expérience d’administrateur Intune sur Azure <!--736542-->

Début 2017, nous migrerons l’intégralité de notre expérience administrateur vers Azure, permettant ainsi une gestion puissante et intégrée des principaux flux de travail EMS sur une plateforme de services moderne et extensible à l’aide des API Graph.

Les nouveaux locataires de test pourront accéder à la préversion publique de la nouvelle expérience administrateur dans le portail Azure ce mois-ci. Dans un état d’aperçu, les fonctionnalités et la parité avec la console Intune existante seront remises en mode itératif.

L’expérience administrateur dans le portail Azure utilisera la nouvelle fonctionnalité de regroupement et de ciblage précédemment annoncée ; lorsque votre client existant est migré vers la nouvelle expérience de regroupement, vous le serez également afin d’afficher un aperçu de la nouvelle expérience administrateur sur votre client. En attendant, si vous souhaitez tester ou examiner toute nouvelle fonctionnalité avant la migration du client, inscrivez-vous à un nouveau compte d’évaluation Intune ou consultez la [nouvelle documentation](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune).

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Prise en charge des options de configuration gérées pour les applications Android <!-- 621621 -->

Les applications Android dans le Play Store qui prennent en charge les options de configuration gérées peuvent être configurées par Intune.  Cette fonctionnalité permet au personnel informatique d’afficher la liste des valeurs de configuration prises en charge par une application, et fournit une interface interactive et guidée de premier plan pour lui permettre de configurer ces valeurs.

### <a name="remote-assistance-for-android-devices----675418---"></a>Assistance à distance pour les appareils Android <!-- 675418 -->

Intune utilise le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs qui utilisent des appareils Android.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nouvelle stratégie Android pour les codes PIN complexes <!-- 722069 -->

Vous pouvez définir un type de mot de passe requis « Chiffres complexes » dans un profil d’appareil Android pour les appareils qui exécutent Android 5.0 et versions ultérieures.  Utilisez ce paramètre pour empêcher les utilisateurs d’appareils de créer un code PIN qui contient des nombres répétés ou consécutifs, tel que 1111 ou 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Prise en charge supplémentaire des appareils Android for Work

- **Gérer les paramètres de profil professionnel et de mot de passe** <!-- 612808 -->

  Nous avons ajouté une nouvelle stratégie de restriction d’appareil Android for Work qui vous permet de gérer les paramètres de profil professionnel et de mot de passe sur les appareils Android for Work que vous gérez.

- **Autoriser le partage de données entre profils professionnels et personnels** <!-- 1045102 -->

  Nous avons mis à jour le paramètre **Partage des données entre les profils professionnels et personnels** dans un profil de restriction d’appareil Android for Work avec de nouvelles options pour vous aider à configurer le partage de données entre des profils professionnels et personnels.

- **Limiter la copie et le collage entre profils professionnels et personnels** <!-- 1046094 -->

  Quand vous gérez des appareils Android for Work avec Intune, les actions Copier et Coller entre applications professionnelles et personnelles sont autorisées. Nous avons maintenant ajouté un profil d’appareil personnalisé pour les appareils Android for Work, qui vous permet de limiter les actions Copier et Coller entre applications professionnelles et personnelles.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>Affecter des applications métier aux appareils iOS et Android <!-- 1057568 -->

Vous pouvez affecter des applications métier pour iOS (fichiers .ipa) et Android (fichiers .apk) à des utilisateurs ou des appareils.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>Nouvelles stratégies pour les appareils iOS <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Applications dans l’écran d’accueil** - Vous pouvez utiliser une stratégie d’appareil pour contrôler quelles applications sont affichées dans l’écran d’accueil de l’appareil iOS d’un utilisateur. Cette stratégie change la disposition de l’écran d’accueil, mais ne déploie aucune application que vous avez spécifiée si elle n’est pas installée.

- **Connexions aux appareils AirPrint** - Vous pouvez utiliser une stratégie d’appareil Intune pour contrôler à quels appareils AirPrint (imprimantes réseau) les utilisateurs finaux d’appareils iOS peuvent se connecter.

- **Connexions aux appareils AirPlay** - Vous pouvez utiliser une stratégie d’appareil Intune pour déterminer à quels appareils AirPlay (comme Apple TV) les utilisateurs finaux d’appareils iOS peuvent se connecter.

- **Message d’écran de verrouillage personnalisé** - Vous pouvez configurer un message personnalisé qui s’affiche sur l’écran de verrouillage des appareils iOS à la place du message d’écran de verrouillage par défaut.

- **Filtrage de contenu web** - Vous pouvez contrôler les sites web auxquels les utilisateurs d’appareils iOS peuvent accéder à l’aide de l’une des deux méthodes suivantes :

  - Ajouter des URL autorisées et bloquées à l’aide du filtrage de contenu web intégré d’Apple.
  - Autoriser uniquement l’accès aux sites web spécifiés par le navigateur Safari. Des signets seront créés dans Safari pour chaque site que vous spécifiez.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Restreindre les notifications Push pour les applications iOS <!-- 723767 -->

Dans un profil de restriction d’appareil Intune, vous pouvez configurer les paramètres de notification suivants pour les appareils iOS :

- Activer ou désactiver entièrement la notification pour une application spécifiée.
- Activer ou désactiver la notification dans le Centre de notification pour une application spécifiée.
- Spécifier le type d’alerte : **Aucune**, **Bannière** ou **Alerte modale**.
- Spécifier si les badges sont autorisés pour cette application.
- Spécifier si les sons de notification sont autorisés.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>Configurer les applications iOS pour s’exécuter en mode Application unique autonome <!-- 737837 -->

Vous pouvez utiliser un profil d’appareil Intune pour configurer les appareils iOS pour qu’ils exécutent les applications spécifiées en mode Application unique autonome. Quand ce mode est configuré et que l’application est exécutée, l’appareil est verrouillé et il ne peut exécuter que cette application. Vous pouvez par exemple utiliser ce mode quand vous configurez une application qui permet aux utilisateurs d’effectuer un test sur l’appareil. Une fois les actions de l’application terminées, ou si vous supprimez cette stratégie, l’appareil retourne à son état normal.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Configurer des domaines approuvés pour la messagerie électronique et la navigation web sur des appareils iOS <!-- 723765 -->

À partir d’un profil de restriction d’appareil iOS, vous pouvez configurer les paramètres de domaine suivants :

- **Domaines d’e-mail non marqués** - Les e-mails reçus ou envoyés par l’utilisateur qui ne correspondent pas aux domaines que vous spécifiez ici sont marqués comme non approuvés.

- **Domaines web gérés** - Les documents téléchargés à partir des URL que vous spécifiez ici sont considérés comme gérés (Safari uniquement).  

- **Domaines de remplissage automatique des mots de passe Safari** - Les utilisateurs peuvent enregistrer des mots de passe dans Safari uniquement à partir des URL qui correspondent aux modèles que vous spécifiez ici. Pour utiliser ce paramètre, il faut que l’appareil soit en mode supervisé et non configuré pour plusieurs utilisateurs. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>Applications VPP disponibles dans le portail d’entreprise iOS <!-- 748782 -->

Vous pouvez affecter des applications achetées en volume (VPP) iOS comme installations **disponibles** pour les utilisateurs finaux. Ces derniers auront besoin d’un compte Apple Store pour installer l’application.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>Synchroniser des livres électroniques à partir de l’Apple VPP Store <!-- 800878 -->

Vous pouvez synchroniser les livres que vous avez achetés dans la boutique VPP (Programme d’achat en volume) d’Apple avec Intune, et les attribuer à des utilisateurs.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Gestion des utilisateurs multiples pour les appareils Samsung KNOX Standard <!-- 971988 -->

Les appareils qui exécutent Samsung KNOX Standard sont désormais pris en charge pour la gestion des utilisateurs multiples par Intune. Cela signifie que les utilisateurs finaux peuvent se connecter et se déconnecter de l’appareil avec leurs informations d’identification Azure Active Directory, et que l’appareil est géré de façon centralisée qu’il soit en cours d’utilisation ou non.  Quand les utilisateurs finaux se connectent, ils ont accès aux applications et les éventuelles stratégies sont appliquées à ces applications. Quand les utilisateurs se déconnectent, toutes les données d’application sont effacées.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Paramètres supplémentaires de restriction d’appareil Windows <!-- 818566 -->

Nous avons ajouté la prise en charge de paramètres supplémentaires de restriction d’appareil Windows, comme une prise en charge supplémentaire du navigateur Edge, la personnalisation de l’écran de verrouillage d’appareil, la personnalisation du menu Démarrer, les papiers peints Windows à la une et les paramètres de proxy.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Prise en charge multi-utilisateur pour Windows 10 Creators Update <!-- 822547 -->

Nous avons ajouté la prise en charge de la gestion des utilisateurs multiples pour les appareils qui exécutent Windows 10 Creators Update et sont joints à un domaine Azure Active Directory. Cela signifie que quand différents utilisateurs ouvrent une session sur l’appareil avec leurs informations d’identification AAD, ils reçoivent les applications et les stratégies qui ont été affectées à leur nom d’utilisateur.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start pour les PC Windows 10<!-- 1004830 -->

Dans cette version, nous avons ajouté une nouvelle action d’appareil Fresh Start pour les PC Windows 10.  Quand vous exécutez cette action, les applications qui ont été installées sur l’ordinateur sont supprimées, et le PC est automatiquement mis à jour vers la dernière version de Windows. Vous pouvez ainsi supprimer des applications OEM préinstallées, comme celles qui sont souvent fournies avec un nouveau PC. Vous pouvez configurer si les données utilisateur sont conservées quand cette action est exécutée sur l’appareil.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Chemins de mise à niveau Windows 10 supplémentaires <!-- 903672 -->

Vous pouvez désormais créer une stratégie de mise à niveau d’édition pour mettre à niveau les appareils vers les éditions Windows 10 supplémentaires suivantes :

- Windows 10 Professionnel
- Windows 10 Professionnel N
- Windows 10 Professionnel Éducation
- Windows 10 Professionnel Éducation N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Inscription en bloc des appareils Windows 10 <!-- 747607 -->

Vous pouvez joindre un grand nombre d’appareils Windows 10 à Azure Active Directory et Intune avec les outils d’automatisation informatique. Pour activer l’inscription MDM automatique pour votre locataire Azure AD, créez un package de mise en service qui joint l’appareil à votre locataire Azure AD à l’aide du Concepteur de configuration Windows. Appliquez ce package aux appareils d’entreprise que vous souhaitez inscrire et gérer en bloc.  Une fois le package appliqué, les appareils se connectent à Azure AD et s’inscrivent dans Intune. Ils sont alors prêts pour que vos utilisateurs Azure AD s’y connectent.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>Nouveaux paramètres GAM pour les codes PIN et les emplacements de stockage géré <!-- 58112, 736644 -->

Deux nouveaux paramètres d’application sont disponibles pour vous aider dans les scénarios de gestion des applications mobiles (GAM) :

- **Désactiver le code PIN de l’application quand le code PIN de l’appareil est géré** - Détecte si un code PIN d’appareil est présent sur l’appareil inscrit et, si c’est le cas, contourne le code PIN de l’application déclenché par les stratégies de protection des applications. Ce paramètre permet de réduire le nombre d’invites de code PIN pour les utilisateurs ouvrant une application GAM sur un appareil inscrit. Cette fonctionnalité est disponible pour iOS et Android.

- **Sélectionnez dans quels services de stockage les données d’entreprise peuvent être enregistrées** - Permet de spécifier les emplacements de stockage où enregistrer les données d’entreprise. Les utilisateurs peuvent enregistrer dans les services d’emplacement de stockage sélectionnés, ce qui signifie que tous les autres services d’emplacement de stockage non répertoriés seront bloqués.

  Liste des services d’emplacement de stockage pris en charge :

  - OneDrive Entreprise
  - SharePoint Online
  - Stockage local


### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.

