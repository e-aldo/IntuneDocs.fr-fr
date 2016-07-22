---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: Lindavr
manager: jeffgilb
ms.date: 06/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79617dd41e51402a73759da792f581028095a2f5
ms.openlocfilehash: 65e53ad6a74fbf0e9249c367f517ab52ea0efa80


---

# Nouveautés de Microsoft Intune
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

Les points suivants sont des nouveautés de cette version. À l’exception de la mise à jour du paramètre de stratégie Windows Defender, toutes ces fonctionnalités sont également prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/en-US/library/mt718155(TechNet.10).aspx).

## Juin 2016
### État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Ces informations sont désormais disponibles sur le portail de gestion Office 365 sous État du service. Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

## Gestion d'applications
- **Amélioration de la configuration des stratégies de données d’entreprise Windows 10.** Nous avons amélioré la configuration des stratégies de protection des données d’entreprise Windows 10 au niveau de la création des règles d’application, de la définition des limites du réseau et d’autres paramètres de protection des données d’entreprise. Pour plus d’informations, consultez la rubrique [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


## Gestion des appareils
- **Paramètre de stratégie Windows Defender pour une protection contre les applications potentiellement indésirables.** Un nouveau paramètre Windows Defender nommé **Potentially Unwanted Application Detection** (Détection des applications potentiellement indésirables) a été ajouté à la stratégie de configuration générale pour Windows 10 Desktop et Mobile. Vous pouvez utiliser ce paramètre pour empêcher les postes de travail Windows inscrits d’exécuter des logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée. Pour plus d’informations, consultez [Paramètres de la stratégie Windows 10 dans Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

## Accès conditionnel
- **Stratégie de contrôle d’accès au réseau Cisco ISE pour Intune.**  Les clients qui utilisent Cisco Identity Service Engine (ISE) 2.1 et Microsoft Intune peuvent définir une stratégie de contrôle d’accès au réseau dans ISE.

    Quand vous utilisez cette stratégie, les appareils qui doivent se connecter au réseau Wi-Fi ou VPN doivent respecter les conditions suivantes avant d’obtenir l’autorisation d’accès :

    * Ils doivent être gérés par Intune
    * Ils doivent être conformes à toutes les stratégies de conformité Intune déployées

 Les utilisateurs finaux d’appareils non conformes sont invités à s’inscrire et à résoudre les problèmes de conformité pour obtenir l’autorisation d’accès.
- **Accès conditionnel pour le navigateur.** Vous ne pourrez pas définir une stratégie d’accès conditionnel pour [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) et [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) afin que ces applications soient uniquement accessibles à partir de navigateurs web pris en charge sur des appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android seront invités à inscrire leurs appareils avec Intune, et à résoudre les problèmes d'incompatibilité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **Dynamics CRM Online prend en charge l’accès conditionnel.** Vous pouvez définir une stratégie d’accès conditionnel pour [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Dynamics CRM sur un appareil iOS ou Android seront invités à s’inscrire à Intune et à résoudre les éventuels problèmes de non conformité avant de finaliser la connexion.
<!---TFS1295358--->

## Mises à jour du Portail d’entreprise

### Application Portail d’entreprise Android

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils interdisent l’installation d’applications à partir de sources inconnues (Android 4.0+) », le message « L’installation à partir de sources inconnues doit être désactivée » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Sécurité**, puis désactiver **Sources inconnues**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils recherchent les menaces de sécurité (Android 4.0+) », le message « Rechercher les menaces de sécurité sur l’appareil » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Google** > **Sécurité**, puis activer **Rechercher les menaces de sécurité sur l’appareil**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) supplémentaires sur le message et la raison pour laquelle ils doivent activer le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger la désactivation du débogage USB (Android 4.2+) », le message « Le débogage USB doit être désactivé » s’affiche aux utilisateurs finaux d’appareils Android 4.2 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Options pour développeurs**, puis désactiver **Débogage USB**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie « Niveau minimal du correctif de sécurité Android (Android 6.0+), le message « Cet appareil n’est pas au niveau minimal du correctif de sécurité Android » s’affiche aux utilisateurs finaux d’appareils Android 6.0 ou version ultérieure. Les utilisateurs doivent installer le correctif de sécurité demandé. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sur la façon d’installer le correctif de sécurité demandé et de voir quel correctif de sécurité est actuellement installé.

### Application Portail d’entreprise iOS

- Lorsque les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour consulter les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement](/Intune/EndUser/sync-your-device-manually-ios).

- L’application Portail d’entreprise Microsoft Intune pour iOS a été mise à jour pour prendre en charge iOS 8.0 et version ultérieure. Cette mise à jour signifie que les utilisateurs finaux ne peuvent installer l’application Portail d’entreprise et inscrire de nouveaux appareils dans Intune que si l’appareil exécute iOS 8.0 ou version ultérieure. Les utilisateurs qui ont déjà inscrit des appareils exécutant une version non prise en charge d'iOS peuvent continuer à utiliser l'application Portail d'entreprise qui figure sur leur appareil.


## Nouveautés à venir

### Feuille de route du cloud
Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Désapprobation du service
- **Applications de visionneuse Intune.** Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pour Android depuis Google Play

  Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle application de gestion des droits (partage RMS) pour Android, qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android.

- **Ciblage de groupe personnalisé de suppression des règles de notification.**
Les règles de notification Intune définissent les destinataires d’une alerte par e-mail envoyée par Intune. Actuellement, vous pouvez configurer des règles de notification pour envoyer des e-mails à tous les utilisateurs d’appareils d’un groupe d’appareils Intune que vous avez créé. Aux alentours du 1er juin 2016, le ciblage des groupes créés par l’utilisateur n’est plus pris en charge.

    Aujourd’hui, pour cibler une règle de notification sur un groupe que vous avez créé à partir de la console d’administration Microsoft Intune, procédez comme suit :

    Dans l’espace de travail **Administration**, cliquez sur **Règles de notification** > **Créer une règle**.

    À l’étape 2 de l’Assistant Créer règle de notification, sélectionnez les groupes d’appareils que la règle doit cibler. Cette étape, « Sélection de groupes d’appareils », va être supprimée de la console Intune.

    Le calendrier relatif à cette modification est le suivant :
    - À partir d’août 2016, les nouveaux clients ne verront plus l’étape 2 de l’Assistant Création d’une règle de notification. Les clients existants ne sont pas affectés.
    - Vers le mois de septembre 2016, certains clients existants ne verront plus l’étape « Sélection de groupes d’appareils » dans l’Assistant.
    - Vers le mois de novembre 2016, plus aucun client ne verra l’étape « Sélection de groupes d’appareils » dans l’Assistant.


- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**. En juillet, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.





## Versions précédentes d’Intune
Les dernières améliorations apportées à Intune au cours des six derniers mois sont répertoriées dans l’article [Versions précédentes d’Intune](previous-intune-releases.md).



### Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Jul16_HO1-->


