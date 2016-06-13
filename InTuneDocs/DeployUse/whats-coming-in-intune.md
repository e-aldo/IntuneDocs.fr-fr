---
# required metadata

title: Nouveautés à venir | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 05/17/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nouveautés à venir de Microsoft Intune
Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Vérifiez régulièrement les mises à jour Nouveautés à venir.

Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront également prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Communications Intune
- **Informations d’état du service Intune.** Les informations d’état du service Intune ont été déplacées dans un endroit central avec d’autres services Microsoft. Vous trouvez à présent ces informations sur le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) sous État du service. Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

- **Intégration de l’interface utilisateur du Centre de messages.** Dans le cadre de la migration d’Intune vers le [portail de gestion Office 365](https://portal.office.com/), nous allons commencer par tirer parti du centre de messages pour communiquer les nouvelles fonctionnalités et autres notifications. En outre, en installant l'application mobile d’administration Office 365, vous pouvez recevoir des notifications sur votre téléphone mobile et transférer facilement des messages à des utilisateurs ou à un alias de distribution.
Nous allons commencer en utilisant le centre de messages avec la version de mai, qui vous avertira lorsque des mises à jour seront terminées et inclura des informations sur les nouvelles fonctionnalités Intune. Consultez dès aujourd’hui le centre des messages en vous connectant au [portail de gestion Office 365](https://portal.office.com/) et en choisissant l’option **Centre des messages** dans le volet de navigation gauche.

## Gestion d'applications
- **Nouvelles applications disponibles pour la gestion avec les stratégies MAM.** Les applications Microsoft Word, Excel et PowerPoint pour Android peuvent désormais être associées avec des stratégies MAM sur des appareils qui ne sont pas inscrits auprès d’Intune. Pour obtenir la liste complète des applications prises en charge, accédez à la galerie d’applications mobiles Microsoft Intune sur la page des partenaires de l’application [Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


- **Accès conditionnel pour le navigateur.** Vous ne pourrez pas définir une stratégie d'accès conditionnel pour Exchange Online et SharePoint Online afin que ces applications soient uniquement accessibles aux appareils iOS et Android gérés et compatibles. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android seront invités à inscrire leurs appareils avec Intune, et à résoudre les problèmes d'incompatibilité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **SDK MAM : prise en charge de la configuration de longueur de code confidentiel.** Vous pourrez spécifier la longueur du code confidentiel des applications MAM comme s’il s’agissait du code confidentiel d’un appareil. Cette opération obligera les utilisateurs finaux à respecter les nouvelles restrictions que vous définissez. Ils verront un écran légèrement différent pour prendre en compte la saisie d’un code confidentiel plus long.
<!--- TFS 1104753--->

- **Skype Entreprise pour Android.** Les administrateurs Intune peuvent maintenant cibler Skype Entreprise avec MAM sans stratégie d'inscription.  Une fois les utilisateurs connectés, les stratégies auxquelles seront appliquées.
<!--- TFS item 1248444 --->

- **Skype Entreprise pour iOS.** Les administrateurs Intune peuvent maintenant cibler Skype Entreprise avec MAM sans stratégie d'inscription.  Une fois les utilisateurs connectés, les stratégies auxquelles seront appliquées.
<!--- TFS item 1248443 --->

### Prise en charge de Xamarin
Le Kit de développement logiciel (SDK) de l'application Microsoft Intune prend désormais en charge les applications Xamarin dans ces scénarios :

- Écriture de nouvelles applications ou modification des applications métier existantes à l'aide du kit de développement logiciel (SDK) Intune. Vous pouvez obtenir le plug-in sur la page [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Ajout de la prise en charge MAM aux applications métier existantes à l'aide de l'outil de création de package de restrictions d'application Intune

Pour faciliter le choix de la méthode à utiliser, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->


## Gestion des appareils
- **Sessions d'assistance à distance pour les PC Windows.** L’intégration de TeamViewer Windows pour les PC gérés par agent vous permet d'établir des sessions d'assistance à distance avec des ordinateurs Windows gérés par agent dans le cadre du support technique de l'utilisateur final. Cela inclut Windows 7, 8, 8.1 et Windows 10.
<!--- TFS 1284856--->



## Portail d'entreprise

- **Notifications toast pour l’utilisateur final.** Les utilisateurs finaux voient à présent des notifications toast provenant de l’application Portail d’entreprise Android quand ils inscrivent leurs appareils ou suppriment leurs appareils sur le portail d’entreprise.
- **Une bannière d'identification de l’appareil fournit davantage d'informations aux utilisateurs finaux.** Les utilisateurs finaux pourront ainsi facilement identifier l’appareil qu'ils ont sélectionné lorsqu'ils utilisent le site Web du portail d'entreprise. Si un appareil incorrect est sélectionné, ils pourront sélectionner l’appareil approprié en cliquant sur le lien « Tap here » dans la bannière de la page d'accueil.
<!--- TFS 1231157--->

- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise Android.** Pour améliorer les performances et la mise à l’échelle, Intune n’affichera plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet **Mes appareils** de l’application Portail d’entreprise Android. Seul l’appareil local qui exécute l’application sera affiché et uniquement s’il est inscrit via l’application Portail d’entreprise. L’utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne pourra être effectuée qu’à partir de la console d’administration Intune.

- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS.** Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise iOS. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune.  En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés.  Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible.



## Désapprobation du service
**Ciblage de groupe personnalisé de suppression des règles de notification.**
Les règles de notification Intune définissent les destinataires d’une alerte par e-mail envoyée par Intune. Actuellement, vous pouvez configurer des règles de notification pour envoyer des e-mails à tous les utilisateurs d’appareils d’un groupe d’appareils Intune que vous avez créé. Aux alentours du 1er juin 2016, le ciblage des groupes créés par l’utilisateur n’est plus pris en charge.

Aujourd’hui, pour cibler une règle de notification sur un groupe que vous avez créé à partir de la console d’administration Microsoft Intune, procédez comme suit :

Dans l’espace de travail **Administration**, cliquez sur **Règles de notification** > **Créer une règle**.

À l’étape 2 de l’Assistant Créer règle de notification, sélectionnez les groupes d’appareils que la règle doit cibler. Cette étape, « Sélection de groupes d’appareils », est actuellement supprimée de la console Intune.

Le calendrier relatif à cette modification est le suivant :
- En juin 2016, les nouveaux clients ne verront pas l’étape 2 de l’Assistant Créer règle de notification. Les clients existants ne sont pas affectés.
- Vers le mois d’aout 2016, certains clients existants ne verront pas l’étape « Sélection de groupes d’appareils » dans l’Assistant.
- Vers le mois d’octobre 2016, nous prévoyons qu’aucun client ne voie plus l’étape « Sélection de groupes d’appareils » dans l’Assistant.

<!---   TFS 1278864--->
**Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS.**
Au cours des prochains mois, une mise à jour sera publiée pour l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 8.0 ou ultérieure. Les utilisateurs ne pourront pas inscrire de nouveaux appareils exécutant des versions d’iOS inférieures à 8.0. Les appareils inscrits qui exécutent des versions d’iOS inférieures à 8.0 continueront d’être gérés et pourront continuer à utiliser l’application Portail d’entreprise pour une durée limitée. Toutefois, les appareils doivent utiliser iOS version 8.0 ou ultérieure pour accéder aux versions les plus récentes de l’application Portail d’entreprise. Nous vous encourageons à informer les utilisateurs de mettre à jour leur système d’exploitation vers iOS version 8.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  

- **Applications de visionneuse Intune.** Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pour Android depuis Google Play

  Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle application de gestion des droits (partage RMS) pour Android, qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. En savoir plus sur l’application de partage RMS (avec un lien vers la documentation).






### Voir aussi
Consultez [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour plus de détails sur les derniers développements.


<!--HONumber=Jun16_HO1-->


