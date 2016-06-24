---
# required metadata

experiment_id: lindavr-abtest-20160527
title: Nouveautés | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nouveautés de Microsoft Intune
## Juin 2016

### Mises à jour de Portail d'entreprise

#### Application Portail d’entreprise iOS

- Lorsque les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour lire les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement pour accélérer l’installation des applications](/Intune/EndUser/sync-your-device-manually-ios.md).

- L’application Portail d’entreprise Microsoft Intune pour iOS a été mise à jour pour prendre en charge iOS 8.0 et version ultérieure. Cette mise à jour signifie que les utilisateurs finaux ne peuvent installer l’application Portail d’entreprise et inscrire de nouveaux appareils dans Intune que si l’appareil exécute iOS 8.0 ou version ultérieure. Les utilisateurs qui ont déjà inscrit des appareils exécutant une version non prise en charge d'iOS peuvent continuer à utiliser l'application Portail d'entreprise qui figure sur leur appareil.

## Mai 2016


Toutes ces fonctionnalités sont également prises en charge pour les déploiements hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez la page [Nouveautés hybrides](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### Documentation

Bienvenue dans la préversion de [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Il s’agit d’une plateforme de contenu moderne, entièrement nouvelle, conçue pour permettre à nos clients de comprendre et d’utiliser plus aisément Intune.
Pour découvrir toutes les nouvelles fonctionnalités, consultez [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Présentation de docs.microsoft.com).

### État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Vous trouvez désormais ces informations sur le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) sous **État du service**.
Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### Gestion d'applications

- **SDK MAM : prise en charge de la configuration de longueur de code confidentiel.** Vous pourrez spécifier la longueur du code confidentiel des applications MAM comme s’il s’agissait du code confidentiel d’un appareil. Cette opération obligera les utilisateurs finaux à respecter les nouvelles restrictions que vous définissez. Ils verront un écran légèrement différent pour prendre en compte la saisie d’un code confidentiel plus long. Pour plus d’informations, consultez [MAM policy settings for Android](/intune/deploy-use/android-mam-policy-settings) (Paramètres de stratégie MAM pour Android) et [MAM policy settings for iOS](/intune/deploy-use/ios-mam-policy-settings) (Paramètres de stratégie MAM pour iOS).

- **Skype Entreprise pour iOS et Android.** Vous pouvez maintenant cibler Skype Entreprise avec [MAM sans stratégie d’inscription](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Une fois les utilisateurs connectés, les stratégies MAM sont appliquées.

- **Nouvelles applications disponibles pour la gestion avec les stratégies MAM.** Les applications Microsoft Word, Excel et PowerPoint pour Android peuvent désormais être associées avec des stratégies MAM sur des appareils qui ne sont pas inscrits auprès d’Intune. Pour obtenir la liste complète des applications prises en charge, accédez à la galerie d’applications mobiles Microsoft Intune sur la page des [partenaires de l’application Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).



### Mises à jour de Portail d'entreprise

#### Application Portail d’entreprise Android

- **Notifications toast pour l’utilisateur final** : les utilisateurs finaux voient à présent des notifications toast provenant de l’application Portail d’entreprise Android quand ils inscrivent leurs appareils ou suppriment leurs appareils sur le portail d’entreprise.

- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise Android.** Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise Android. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune.
-
#### Site web Portail d’entreprise

**Site web Portail d’entreprise : Une bannière d’identification de l’appareil fournit d’autres informations aux utilisateurs finaux.** Désormais, les utilisateurs finaux peuvent facilement identifier l’appareil qu’ils ont sélectionné lorsqu’ils utilisent le site web Portail d’entreprise. Si un appareil incorrect est sélectionné, ils peuvent sélectionner l’appareil approprié en cliquant sur le lien **Tap here** (Appuyer ici) dans la bannière de la page d’accueil.


## Nouveautés à venir

- **Intégration de l’interface utilisateur du Centre de messages**. Dans le cadre de la migration d’Intune vers le [portail de gestion Office 365](https://portal.office.com/), nous allons commencer par tirer parti du centre de messages pour communiquer les nouvelles fonctionnalités et autres notifications. En outre, en installant l'application mobile d’administration Office 365, vous pouvez recevoir des notifications sur votre téléphone mobile et transférer facilement des messages à des utilisateurs ou à un alias de distribution.
Nous allons commencer en utilisant le centre de messages avec la version de mai, qui vous avertira lorsque des mises à jour seront terminées et inclura des informations sur les nouvelles fonctionnalités Intune. Consultez dès aujourd’hui le Centre des messages en vous connectant au [portail de gestion Office 365](https://portal.office.com/) et en choisissant l’option CENTRE DES MESSAGES dans le volet de navigation gauche.

- **Modifications apportées aux comptes de gestionnaires d’inscription d’appareils**. Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus **tous** les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet **Mes appareils** de l’application Portail d’entreprise iOS. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune. En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés. Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible.

### Feuille de route du cloud
Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Désapprobation du service
- **Applications de visionneuse Intune.** Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pour Android depuis Google Play

  Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle application de gestion des droits (partage RMS) pour Android, qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. En savoir plus sur l’application de partage RMS (avec un lien vers la documentation).

- **Ciblage de groupe personnalisé de suppression des règles de notification.**
Les règles de notification Intune définissent les destinataires d’une alerte par e-mail envoyée par Intune. Actuellement, vous pouvez configurer des règles de notification pour envoyer des e-mails à tous les utilisateurs d’appareils d’un groupe d’appareils Intune que vous avez créé. Aux alentours du 1er juin 2016, le ciblage des groupes créés par l’utilisateur n’est plus pris en charge.

    Aujourd’hui, pour cibler une règle de notification sur un groupe que vous avez créé à partir de la console d’administration Microsoft Intune, procédez comme suit :

    Dans l’espace de travail **Administration**, cliquez sur **Règles de notification** > **Créer une règle**.

    À l’étape 2 de l’Assistant Créer règle de notification, sélectionnez les groupes d’appareils que la règle doit cibler. Cette étape, « Sélection de groupes d’appareils », est actuellement supprimée de la console Intune.

    Le calendrier relatif à cette modification est le suivant :
    - En juin 2016, les nouveaux clients ne verront pas l’étape 2 de l’Assistant Créer règle de notification. Les clients existants ne sont pas affectés.
    - Vers le mois d’aout 2016, certains clients existants ne verront pas l’étape « Sélection de groupes d’appareils » dans l’Assistant.
    - Vers le mois d’octobre 2016, nous prévoyons qu’aucun client ne voie plus l’étape « Sélection de groupes d’appareils » dans l’Assistant.


- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**. Au cours des prochains mois, une mise à jour sera publiée pour l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 8.0 ou ultérieure. Les utilisateurs ne pourront pas inscrire de nouveaux appareils exécutant des versions d’iOS inférieures à 8.0. Les appareils inscrits qui exécutent des versions d’iOS inférieures à 8.0 continueront d’être gérés et pourront continuer à utiliser l’application Portail d’entreprise pour une durée limitée. Toutefois, les appareils doivent utiliser iOS version 8.0 ou ultérieure pour accéder aux versions les plus récentes de l’application Portail d’entreprise. Nous vous encourageons à informer les utilisateurs de mettre à jour leur système d’exploitation vers iOS version 8.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.



## Versions précédentes d’Intune
Les dernières améliorations apportées à Intune au cours des six derniers mois sont répertoriées dans l’article [Versions précédentes d’Intune](previous-intune-releases.md).
> [!div class="op_single_selector"]
- [Avril 2016](previous-intune-releases.md)
- [Mars 2016](previous-intune-releases.md)
- [Février 2016](previous-intune-releases.md)
- [Janvier 2016](previous-intune-releases.md)
- [Décembre 2015](previous-intune-releases.md)
- [Novembre 2015](previous-intune-releases.md)




### Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)


<!--HONumber=Jun16_HO2-->


