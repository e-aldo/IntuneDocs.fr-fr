---
# required metadata

title: Nouveautés à venir | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 06/10/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: mamoriss
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Nouveautés à venir de Microsoft Intune
Ces informations sont fournies de manière très limitée dans le cadre d’un accord de confidentialité et sont susceptibles de changer. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Veuillez contacter votre responsable Intune ou votre chef de projet si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Vérifiez régulièrement les mises à jour Nouveautés à venir.

Les modifications suivantes sont en cours de développement pour Intune. Toutes ces fonctionnalités seront également prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).


## Gestion d'applications
- **Amélioration de la configuration des stratégies de données d’entreprise Windows 10.** Nous avons amélioré la configuration des stratégies de protection des données d’entreprise Windows 10 au niveau de la création des règles d’application, de la définition des limites du réseau et d’autres paramètres de protection des données entreprise.
<!---TFS 1303011--->

- **Accès conditionnel pour le navigateur.** Vous ne pourrez pas définir une stratégie d'accès conditionnel pour Exchange Online et SharePoint Online afin que ces applications soient uniquement accessibles aux appareils iOS et Android gérés et compatibles. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android seront invités à inscrire leurs appareils avec Intune, et à résoudre les problèmes d'incompatibilité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **Dynamics CRM Online prend en charge l’accès conditionnel.** Les utilisateurs pourront définir une stratégie d’accès conditionnel pour Dynamics CRM Online afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Dynamics CRM sur un appareil iOS ou Android seront invités à s’inscrire à Intune et à résoudre les éventuels problèmes de non conformité avant de finaliser la connexion.
<!---TFS1295358--->

### Prise en charge de Xamarin
Le SDK d’application Microsoft Intune prend en charge les applications Xamarin dans les scénarios suivants :

- Écriture de nouvelles applications ou modification des applications métier existantes à l'aide du kit de développement logiciel (SDK) Intune. Vous pouvez obtenir le plug-in sur la page [Microsoft Intune Github](https://github.com/msintuneappsdk).
- Ajout de la prise en charge MAM aux applications métier existantes à l'aide de l'outil de création de package de restrictions d'application Intune

Pour faciliter le choix de la méthode à utiliser, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune).
<!--- TFS 1061478 & TFS 1152340--->

## Gestion des appareils
- **Paramètre de stratégie Windows Defender pour une protection contre les applications potentiellement indésirables.** Un nouveau paramètre Windows Defender nommé **Potentially Unwanted Application Detection** (Détection des applications potentiellement indésirables) a été ajouté à la stratégie de configuration générale pour Windows 10 Desktop et Mobile. Vous pouvez utiliser ce paramètre pour empêcher les postes de travail Windows inscrits d’exécuter des logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée.
<!---TFS 1244478--->

## Accès conditionnel
**Stratégie de contrôle d’accès au réseau Cisco ISE pour Intune.**  Les clients qui utilisent Cisco Identity Service Engine (ISE) 2.1 et Microsoft Intune peuvent définir une stratégie de contrôle d’accès au réseau dans ISE.

Quand vous utilisez cette stratégie, les appareils qui doivent se connecter au réseau Wi-Fi ou VPN doivent respecter les conditions suivantes avant d’obtenir l’autorisation d’accès :

* Ils doivent être gérés par Intune
* Ils doivent être conformes à toutes les stratégies de conformité Intune déployées

Les utilisateurs finaux d’appareils non conformes sont invités à s’inscrire et à résoudre les problèmes de conformité pour obtenir l’autorisation d’accès.
<!---TFS 1299144--->

## Portail d'entreprise
**Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS.** Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise pour iOS. Seul l’appareil local qui exécute l’application sera affiché et uniquement s’il est inscrit via l’application Portail d’entreprise. L’utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut pas être effectuée à partir de la console d’administration Intune.  En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés. Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible.
<!---TFS 1233681--->

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


<!--HONumber=Jun16_HO3-->


