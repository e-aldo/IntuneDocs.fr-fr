---
title: "Nouveautés à venir | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 9b536372623632b609433c49991a8bdc70e6da49


---

# Nouveautés à venir de Microsoft Intune : juillet
Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Vérifiez régulièrement les mises à jour Nouveautés à venir.

Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Gestion d'applications
### Améliorer l’expérience de mise à jour de profil d’approvisionnement d’application
Les applications mobiles métier Apple iOS intègrent un profil d’approvisionnement et du code signé avec un certificat. Lorsque l’application s’exécute sur un appareil iOS, iOS confirme l’intégrité de l’application et applique les stratégies définies par le profil de configuration.

Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement 3 ans. Toutefois, le profil de configuration expire au bout d’1 an. Grâce à cette mise à jour, Intune vous fournira les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration alors que le certificat est toujours valide.
<!--- TFS 1280247--->

### Prise en charge de Xamarin
Le SDK d’application Microsoft Intune prend en charge les applications Xamarin dans les scénarios suivants :

- Écriture de nouvelles applications ou modification des applications métier existantes à l'aide du kit de développement logiciel (SDK) Intune. Vous pouvez obtenir le plug-in sur la page [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Ajout de la prise en charge MAM aux applications métier existantes à l'aide de l'outil de création de package de restrictions d'application Intune

Pour faciliter le choix de la méthode à utiliser, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).

<!--- TFS 1061478 & TFS 1152340--->

## Gestion des appareils
### Augmentation du nombre d’inscriptions d’appareils
Intune augmentera le nombre maximal d’inscriptions d’appareils configurables en repoussant leur limite de 5 appareils par utilisateur à 15.
<!---TFS 1289896 --->

## Gestion des groupes
### Début de la transition des groupes Intune vers les groupes Azure Active Directory en août 2016
Intune crée une nouvelle expérience de gestion de groupe qui utilise les groupes de sécurité Azure Active Directory (AAD) en tant que groupes d’utilisateurs et d’appareils dans Intune. Ces groupes seront utilisés pour la gestion, le déploiement de stratégies et de profils de tous les groupes **lorsque nous introduirons le nouveau portail d’administration Intune basé sur Azure**.

Grâce à cette nouvelle expérience, vous n’aurez plus besoin de dupliquer des groupes entre des services, **ce qui vous permet d’accéder à certaines fonctionnalités de groupes Azure Active Directory Premium (AADP)**, tout en bénéficiant d’une extensibilité lors de l’utilisation de PowerShell et Graph. La gestion des groupes sera également unifiée lors de la gestion de la mobilité d’entreprise.

Pour activer la transition vers les groupes de sécurité, nous allons devoir modifier la **console d’administration actuelle**. **Ces modifications et l’utilisation des groupes de sécurité Azure AD seront consignées dans la documentation d’Intune**.

Les clients qui ne connaissent pas Intune constateront **certaines modifications du groupe de sécurité avant les clients actuels**.

Outre les modifications dans la gestion de groupe, **les fonctionnalités suivantes deviendront obsolètes** :
- Exclusion de membres ou de groupes lors de la création d’un groupe
- « Gérer des groupes » dans le rôle d’administrateur de service
- Alertes personnalisées basées sur le groupe pour les règles de notification
- Glissement des groupes dans les rapports


## Portail d'entreprise

### Ajout de « Notifications » sur le portail d’entreprise pour Android
En août, nous publierons une mise à jour du portail d’entreprise pour Android qui présente une nouvelle icône **Notifications** sur la page d’accueil. En appuyant sur cette icône, vous pourrez accéder à la page **Notifications** qui indiquera à votre utilisateur final tous les éléments qui nécessitent son attention particulière dans l’application de portail d’entreprise, tels que la non-conformité d’un appareil, ainsi que les mises à jour ou les activations d’inscriptions. Si vous utilisez également l’application de portail d’entreprise iOS, vous pouvez déjà utiliser ces notifications. Une fois la page **Notifications** en place, si votre appareil est déjà inscrit, vous ne verrez plus la page **Configuration de l’accès à l’entreprise** à chaque fois que vous accédez au portail d’entreprise pour Android ou que vous y revenez. Nous savons que beaucoup d’entre vous ont créé des conseils pour l’utilisateur final et que vous appréciez de recevoir des notifications avancées lorsque vos conseils/captures d’écrans doivent être mis à jour. Mettez à jour votre documentation pour refléter les modifications de l’expérience à venir. Vous trouverez des captures d’écran mises à jour ici : https://aka.ms/androidcpupdate  

### Aider les utilisateurs à résoudre les problèmes d’inscription en cas d’échec de la jonction au lieu de travail
Lorsque vous utilisez l’accès conditionnel, les étapes d’inscription pour Windows 8.1, Windows 10 Desktop et Windows 10 Mobile ont été précisées dans le site web du portail d’entreprise pour les utilisateurs finaux ayant rencontré un échec lors de la jonction au lieu de travail. Auparavant, lorsque les utilisateurs finaux inscrivaient un appareil et effectuaient une jonction au lieu de travail, et que toutes les étapes de l’inscription réussissaient à l’exception de la jonction au lieu de travail, l’appareil inscrit n’apparaissait pas dans la liste des appareils identifiables par les utilisateurs, ce qui pouvait s’avérer déroutant. Les utilisateurs peuvent à présent voir deux étapes distinctes, « Inscription de l’appareil » et « Jonction au lieu de travail », ce qui leur permet de consulter plus facilement l’état de leur appareil et de terminer le processus après l’échec de la jonction au lieu de travail. Ces différentes étapes sont également censées simplifier le processus de résolution des problèmes pour les administrateurs.

### Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS
Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise pour iOS. Seul l’appareil local qui exécute l’application sera affiché et uniquement s’il est inscrit via l’application Portail d’entreprise. L’utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut pas être effectuée à partir de la console d’administration Intune.  En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés. Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible.
<!---TFS 1233681--->
### Limiter l’installation d’applications à chargement indépendant sur les appareils Android inscrits
Les appareils Android ne peuvent plus installer d’applications par le biais du site web du portail d’entreprise, sauf s’ils ont été inscrits dans Intune à l’aide de l’application portail d’entreprise Intune pour Android.
<!---TFS 1299082--->

## Désapprobation du service
**Les applications Portail d’entreprise pour Windows 8 et Windows Phone 8 seront déconseillées à partir de septembre 2016.** À compter de septembre 2016, les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour plateformes Windows Phone 8 et Windows 8 ne pourront plus bénéficier du support Microsoft Intune. Mettez à jour vos appareils vers Windows 8.1 et Windows Phone 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer la distribution des applications sur ces appareils.
<!---TFS 1255391--->

**Ciblage de groupe personnalisé de suppression des règles de notification.**
Les règles de notification Intune définissent les destinataires d’une alerte par e-mail envoyée par Intune. Actuellement, vous pouvez configurer des règles de notification pour envoyer des e-mails à tous les utilisateurs d’appareils d’un groupe d’appareils Intune que vous avez créé. Aux alentours du 1er juin 2016, le ciblage des groupes créés par l’utilisateur cessera d’être pris en charge.

Le calendrier relatif à cette modification est le suivant :
- À partir d’août 2016, les nouveaux clients ne verront plus l’étape 2 de l’Assistant Création d’une règle de notification. Les clients existants ne sont pas affectés.
- Vers le mois de septembre 2016, certains clients existants ne verront plus l’étape « Sélection de groupes d’appareils » dans l’Assistant.
- Vers le mois de novembre 2016, plus aucun client ne verra l’étape « Sélection de groupes d’appareils » dans l’Assistant.

<!---   TFS 1278864--->

**Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS.**
En juillet, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.  

**Applications de visionneuse Intune.** Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pour Android depuis Google Play

Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle application de gestion des droits (partage RMS) pour Android, qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. En savoir plus sur l’application de partage RMS (avec un lien vers la documentation).



### Voir aussi
Consultez [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour plus de détails sur les derniers développements.



<!--HONumber=Jul16_HO4-->


