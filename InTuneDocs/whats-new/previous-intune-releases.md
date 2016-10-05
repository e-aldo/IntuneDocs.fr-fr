---
title: "Versions précédentes | Microsoft Intune"
description: 
keywords: 
author: Lindavr
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3206634884807743576f2d9dc1ca17b6bbbc9cc6
ms.openlocfilehash: 996198a2525dc830d229e7143afda3c71f4276b8


---

# Versions précédentes d’Intune
## Août 2016
## Août 2016
## Gestion d'applications
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

### Applications affichées et masquées dans iOS 9.3
Pour les appareils supervisés exécutant iOS 9.3 ou une version ultérieure, vous pouvez utiliser la liste des applications affichées et masquées dans la stratégie de configuration générale d’iOS pour :
- Spécifier une liste d’applications à masquer aux utilisateurs. Les utilisateurs ne peuvent pas afficher ou lancer ces applications.
- Spécifier une liste d’applications que les utilisateurs peuvent afficher et lancer. Aucune autre application ne peut être affichée ou lancée.

Les applications que vous pouvez spécifier incluent celles que vous avez déployées, ainsi que les applications iOS intégrées telles que Messages et Notes. Pour plus d’informations, consultez [Paramètres de la stratégie iOS dans Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
### Stratégie des applications autorisées et bloquées pour les appareils dotés de Samsung KNOX
Vous pouvez désormais configurer une stratégie personnalisée pour les appareils dotés de Samsung KNOX, qui vous permet de créer l’un des éléments suivants :
- Une liste d’applications qui sont bloquées sur l’appareil. Même si elle est installée, une application incluse dans la liste d’applications bloquées ne peut pas être activée sur l’appareil.
- Une liste d’applications que les utilisateurs de l’appareil sont autorisés à installer à partir du magasin Google Play. Aucune autre application ne peut être installée à partir de ce magasin.

Ces paramètres peuvent uniquement être utilisés par les appareils qui exécutent Samsung KNOX.
Pour plus d’informations, consultez [Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
### Nouvelles applications compatibles avec les stratégies de gestion des applications mobiles (MAM)
L’application Yammer pour [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) et [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) est désormais compatible avec les [stratégies de gestion des applications mobiles (MAM) Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), que l’appareil soit inscrit ou non.

Pour obtenir la liste complète des applications MAM compatibles, consultez le site des [partenaires des applications Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

### Applications de visionneuse Intune
Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pour Android depuis Google Play

Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle [application Rights Management (partage RMS) pour Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. Quand l’application de visionneuse Intune ne sera plus prise en charge, elle sera supprimée du Google Store et ne sera plus disponible pour une utilisation ultérieure.

## Gestion des appareils
### Prise en charge d’Android 7.0
Intune assure la prise en charge dès le premier jour du système d’exploitation Android 7.0 pour les appareils mobiles, bientôt disponible.
<!---TFS 1262053--->
### Suppression par Google de la fonctionnalité de réinitialisation à distance du code secret sur les appareils Android 7.0
Google supprime la fonctionnalité permettant aux utilisateurs finaux et aux administrateurs informatiques de réinitialiser à distance le code secret de leurs appareils Android 7.0. Auparavant, les administrateurs informatiques pouvaient réinitialiser à distance le code secret d’un utilisateur, et les utilisateurs finaux pouvaient réinitialiser leur code secret depuis le site web du Portail d’entreprise.



## Mises à jour du Portail d’entreprise
### Site web Portail d’entreprise
- **Lien des commentaires sur le Portail d’entreprise à l’attention de Microsoft** <br/>
Le site web du Portail d’entreprise permet aux utilisateurs finaux de sélectionner un nouveau lien « Commentaires », en bas de la page, pour envoyer des commentaires à Microsoft concernant leur expérience d’utilisation du site. Les commentaires regroupés sont anonymes et permettent à Microsoft d’améliorer le site web du Portail d’entreprise, afin d’optimiser cette expérience.
<!--- TFS 1313657 checked--->

### iOS
- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
L’application Microsoft Intune Managed Browser pour iOS a été mise à jour pour prendre en charge les appareils exécutant iOS 8.0 ou version ultérieure. Même si les appareils iOS 7.1 peuvent toujours utiliser l’application Managed Browser existante, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou version ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253 checked--->

## Nouveautés à venir

### Prise en charge d’iOS 10
Intune prendra entièrement en charge iOS 10. D’autres informations seront fournies au moment du lancement de la version publique d’iOS 10.

### Début de la transition des groupes Intune vers les groupes Azure Active Directory dès septembre 2016
Intune crée une nouvelle expérience de gestion de groupe qui utilise les groupes de sécurité Azure Active Directory (AAD) en tant que groupes d’utilisateurs et d’appareils dans Intune. Ces groupes seront utilisés pour la gestion, le déploiement de stratégies et de profils de tous les groupes **lorsque nous introduirons le nouveau portail d’administration Intune basé sur Azure**.

Grâce à cette nouvelle expérience, vous n’aurez plus besoin de dupliquer des groupes entre des services, **ce qui vous permet d’accéder à certaines fonctionnalités de groupes Azure Active Directory Premium (AADP)**, tout en bénéficiant d’une extensibilité lors de l’utilisation de PowerShell et Graph. La gestion des groupes sera également unifiée lors de la gestion de la mobilité d’entreprise.

Pour activer la transition vers les groupes de sécurité, nous allons devoir modifier la **console d’administration actuelle**. **Ces modifications et l’utilisation des groupes de sécurité Azure AD seront consignées dans la documentation d’Intune**.

Les clients qui ne connaissent pas Intune constateront **certaines modifications du groupe de sécurité avant les clients actuels**.

Outre les modifications dans la gestion de groupe, **les fonctionnalités suivantes deviendront obsolètes** :
- Exclusion de membres ou de groupes lors de la création d’un groupe
- Groupes **Utilisateurs non groupés** et **Appareils non groupés**
- **Gérer des groupes** dans le rôle d’administrateur de service
- Alertes personnalisées basées sur le groupe pour les règles de notification
- Glissement des groupes dans les rapports
<!--- TFS 1295329--->

### Ajout de « Notifications » sur le portail d’entreprise pour Android
En septembre, nous publierons une mise à jour du Portail d’entreprise pour Android, qui présentera la nouvelle icône **Notifications** de la page d’accueil. En appuyant sur cette icône, vous pourrez accéder à la page **Notifications** qui indiquera à votre utilisateur final tous les éléments qui nécessitent son attention particulière dans l’application de portail d’entreprise, tels que la non-conformité d’un appareil, ainsi que les mises à jour ou les activations d’inscriptions. Si vous utilisez également l’application de portail d’entreprise iOS, vous pouvez déjà utiliser ces notifications. Une fois la page **Notifications** en place, si votre appareil est déjà inscrit, vous ne verrez plus la page **Configuration de l’accès à l’entreprise** à chaque fois que vous accédez au portail d’entreprise pour Android ou que vous y revenez. Nous savons que beaucoup d’entre vous ont créé des conseils pour l’utilisateur final et que vous appréciez de recevoir des notifications avancées lorsque vos conseils/captures d’écrans doivent être mis à jour. Mettez à jour votre documentation pour refléter les modifications de l’expérience à venir. Vous trouverez des captures d’écran mises à jour ici : https://aka.ms/androidcpupdate.  

### Améliorations apportées à l’accès des utilisateurs finaux iOS à leurs applications
Les modifications suivantes seront appliquées en septembre pour les mosaïques d’applications de l’application Portail d’entreprise : iOS pointera les utilisateurs vers différentes vues dans un emplacement unique, le site Web de Portail d’entreprise, pour toutes leurs applications. Actuellement, les restrictions d’Apple n’autorisent pas les applications métier et gérées de l’App store à être répertoriées dans l’application Portail d’entreprise et obligent les utilisateurs à consulter différentes vues pour rechercher toutes leurs applications.

- La mosaïque **Applications d’entreprise** pointe actuellement vers une liste de toutes les applications dans l’onglet TOUT du site Web Portail d’entreprise, et elle continuera de fonctionner de la même manière. Le nom de la mosaïque est modifié en **Toutes les applications**.
- La mosaïque **Autres applications** pointe actuellement vers une vue située à l’intérieur de l’application Portail d’entreprise, qui répertorie toutes les applications que le Portail d’entreprise est autorisé à afficher par Apple. Le nom de la mosaïque est modifié en **Applications proposées**, et la sélection de cette mosaïque ouvre l’onglet SÉLECTION du site Web Portail d’entreprise.
-  La mosaïque **Catégories** pointe actuellement vers une vue située à l’intérieur de l’application Portail d’entreprise, qui répertorie les catégories d’applications. Le nom de la mosaïque ne change pas, mais elle pointe maintenant sur l’onglet CATÉGORIES du site Web Portail d’entreprise. Vous trouverez des captures d’écran mises à jour [ici](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

### Feuille de route du cloud
Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).

### Désapprobation du service
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
En septembre, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.  

- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
En août, Intune publiera une mise à jour de l’application Microsoft Intune Managed Browser pour iOS qui prendra uniquement en charge les appareils exécutant iOS version 8.0 ou ultérieure. Même si les appareils iOS 7.1 pourront toujours utiliser l’application Managed Browser, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253--->

- **Les applications du portail d’entreprise pour Windows 8 et Windows Phone 8 sont obsolètes** <br/>
À partir d’octobre 2016, Microsoft Intune ne prendra plus en charge les applications Portail d’entreprise Windows 8 et Windows Phone 8. Microsoft Intune cessera également de prendre en charge la plateforme Windows Phone 8. Ainsi, vous ne pourrez plus inscrire ni mettre à jour des appareils Windows Phone 8. Néanmoins, vous pourrez continuer à gérer les appareils Windows Phone 8 et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## Juillet 2016
### Gestion d'applications
#### Améliorer l’expérience de mise à jour de profil d’approvisionnement d’application
Les applications mobiles métier Apple iOS intègrent un profil d’approvisionnement et du code signé avec un certificat. Lorsque l’application s’exécute sur un appareil iOS, iOS confirme l’intégrité de l’application iOS et applique les stratégies définies par le profil de configuration.

Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement 3 ans. Toutefois, le profil de configuration expire au bout d’1 an. Grâce à cette mise à jour, Intune vous offre les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration alors que le certificat est toujours valide. Pour plus d’informations, consultez [Utilisation de stratégies de profil de configuration d’applications mobiles iOS pour maintenir vos applications métier à jour](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->
#### Disponibilité du Xamarin SDK pour applications Intune
Le composant Xamarin SDK pour applications Intune vous permet d’activer les fonctionnalités de gestion des applications mobiles Intune dans vos applications Android et iOS mobiles développées avec Xamarin. Le composant est disponible dans le [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou sur la [page Github de Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### Gestion des appareils
#### Augmentation du nombre d’inscriptions d’appareils
Intune augmente le nombre maximal d’inscriptions d’appareils configurables en repoussant leur limite de 5 appareils par utilisateur à 15.
<!---TFS 1289896 --->

#### Intégration de TeamViewer sur les PC Windows exécutant le logiciel client Intune
L’intégration de [TeamViewer](https://www.teamviewer.com) sur les PC Windows exécutant le client Intune vous permet d’établir des sessions d’assistance à distance avec des PC Windows, afin d’aider les départements de support technique des utilisateurs finaux. Cela inclut Windows 7, 8, 8.1 et Windows 10. Pour plus d’informations, consultez [Tâches courantes de gestion des PC Windows avec le client Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).
<!---TFS 1284856--->

### Mises à jour du Portail d’entreprise
#### Site web Portail d’entreprise
- **Amélioration de l’interface d’inscription d’appareils Windows**<br/>
Lorsque vous utilisez l’accès conditionnel, les étapes d’inscription pour Windows 8.1, Windows 10 Desktop et Windows 10 Mobile ont été précisées dans le site web du portail d’entreprise. Les utilisateurs peuvent à présent voir deux étapes distinctes, « Inscription de l’appareil » et « Jonction au lieu de travail », ce qui leur permet de consulter plus facilement l’état de leur appareil et de terminer le processus en cas d’échec de l’outil Workplace Join (WPJ). Ces différentes étapes sont également censées simplifier le processus de résolution des problèmes pour les administrateurs. Auparavant, lorsque les utilisateurs finaux inscrivaient un appareil et que toutes les étapes de l’inscription réussissaient à l’exception de la jonction au lieu de travail, l’appareil inscrit n’apparaissait pas dans la liste des appareils identifiables par les utilisateurs, ce qui pouvait s’avérer déroutant.

#### Android
- **Application Portail d’entreprise Android**<br/>
Si un message d’erreur s’affiche pour les utilisateurs finaux Android en leur indiquant qu’il manque un certificat requis pour leur appareil, ils peuvent appuyer sur un bouton « Comment résoudre ce problème » pour consulter les [étapes](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) à suivre afin d’installer le certificat manquant. Si les utilisateurs suivent ces étapes, mais qu’un autre message d’erreur indique « Certificat manquant », ils sont invités à contacter leur administrateur et à fournir ce [lien](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), qui mène vers les étapes à suivre pour résoudre ce problème de certificat.

- **Limiter les installations d’applications à chargement indépendant sur les appareils inscrits**<br/>
Les appareils Android ne peuvent plus installer d’applications par le biais du site web du portail d’entreprise, sauf s’ils ont été inscrits dans Intune à l’aide de l’application portail d’entreprise Intune pour Android.
<!---TFS 1299082--->

#### iOS
- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS**<br/>
Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet **Mes appareils** de l’application Portail d’entreprise pour iOS. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise.

L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune. En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés.

Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible. Pour plus d’informations, consultez [Inscrire des appareils d’entreprise avec le Gestionnaire d’inscription d’appareil dans Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### Modification des noms de fonctionnalités Windows
- [Microsoft Passport pour Windows](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) se nomme maintenant **Windows Hello Entreprise**.
- [Protection des données d’entreprise](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) est maintenant appelé **Protection des informations Windows**.

## Juin 2016
### État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Ces informations sont désormais disponibles sur le portail de gestion Office 365 sous État du service. Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### Gestion d'applications
- **Amélioration de la configuration des stratégies de données d’entreprise Windows 10.** Nous avons amélioré la configuration des stratégies de protection des données d’entreprise Windows 10 au niveau de la création des règles d’application, de la définition des limites du réseau et d’autres paramètres de protection des données d’entreprise. Pour plus d’informations, consultez la rubrique [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### Gestion des appareils
- **Paramètre de stratégie Windows Defender pour une protection contre les applications potentiellement indésirables.** Un nouveau paramètre Windows Defender nommé **Potentially Unwanted Application Detection** (Détection des applications potentiellement indésirables) a été ajouté à la stratégie de configuration générale pour Windows 10 Desktop et Mobile. Vous pouvez utiliser ce paramètre pour empêcher les postes de travail Windows inscrits d’exécuter des logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée. Pour plus d’informations, consultez [Paramètres de la stratégie Windows 10 dans Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### Accès conditionnel
- **Stratégie de contrôle d’accès au réseau Cisco ISE pour Intune.**  Les clients qui utilisent Cisco Identity Service Engine (ISE) 2.1 et Microsoft Intune peuvent définir une stratégie de contrôle d’accès au réseau dans ISE.

    Quand vous utilisez cette stratégie, les appareils qui doivent se connecter au réseau Wi-Fi ou VPN doivent respecter les conditions suivantes avant d’obtenir l’autorisation d’accès :

    * Ils doivent être gérés par Intune
    * Ils doivent être conformes à toutes les stratégies de conformité Intune déployées

 Les utilisateurs finaux d’appareils non conformes sont invités à s’inscrire et à résoudre les problèmes de conformité pour obtenir l’autorisation d’accès.
- **Accès conditionnel pour le navigateur.** Vous ne pourrez pas définir une stratégie d’accès conditionnel pour [Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md) et [SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md) afin que ces applications soient uniquement accessibles à partir de navigateurs web pris en charge sur des appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android seront invités à inscrire leurs appareils avec Intune, et à résoudre les problèmes d'incompatibilité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **Dynamics CRM Online prend en charge l’accès conditionnel.** Vous pouvez définir une stratégie d’accès conditionnel pour [Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md) afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Dynamics CRM sur un appareil iOS ou Android seront invités à s’inscrire à Intune et à résoudre les éventuels problèmes de non conformité avant de finaliser la connexion.
<!---TFS1295358--->

##Mises à jour du Portail d’entreprise

#### Application Portail d’entreprise Android

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils interdisent l’installation d’applications à partir de sources inconnues (Android 4.0+) », le message « L’installation à partir de sources inconnues doit être désactivée » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Sécurité**, puis désactiver **Sources inconnues**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils recherchent les menaces de sécurité (Android 4.0+) », le message « Rechercher les menaces de sécurité sur l’appareil » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Google** > **Sécurité**, puis activer **Rechercher les menaces de sécurité sur l’appareil**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) supplémentaires sur le message et la raison pour laquelle ils doivent activer le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger la désactivation du débogage USB (Android 4.2+) », le message « Le débogage USB doit être désactivé » s’affiche aux utilisateurs finaux d’appareils Android 4.2 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Options pour développeurs**, puis désactiver **Débogage USB**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie « Niveau minimal du correctif de sécurité Android (Android 6.0+), le message « Cet appareil n’est pas au niveau minimal du correctif de sécurité Android » s’affiche aux utilisateurs finaux d’appareils Android 6.0 ou version ultérieure. Les utilisateurs doivent installer le correctif de sécurité demandé. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sur la façon d’installer le correctif de sécurité demandé et de voir quel correctif de sécurité est actuellement installé.

#### Application Portail d’entreprise iOS

- Lorsque les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour consulter les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement](/Intune/EndUser/sync-your-device-manually-ios).

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
- **SDK MAM : prise en charge de la configuration de longueur de code confidentiel.** Vous pourrez spécifier la longueur du code confidentiel des applications MAM comme s’il s’agissait du code confidentiel d’un appareil. Cette opération obligera les utilisateurs finaux à respecter les nouvelles restrictions que vous définissez. Ils verront un écran légèrement différent pour prendre en compte la saisie d’un code confidentiel plus long. Pour plus d’informations, consultez [Paramètres de stratégie MAM pour Android](android-mam-policy-settings.md) et [Paramètres de stratégie MAM pour iOS](ios-mam-policy-settings.md).

- **Skype Entreprise pour iOS et Android.** Vous pouvez maintenant cibler Skype Entreprise avec [MAM sans stratégie d’inscription](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md). Une fois les utilisateurs connectés, les stratégies MAM sont appliquées.

- **Nouvelles applications disponibles pour la gestion avec les stratégies MAM.** Les applications Microsoft Word, Excel et PowerPoint pour Android peuvent désormais être associées avec des stratégies MAM sur des appareils qui ne sont pas inscrits auprès d’Intune. Pour obtenir la liste complète des applications prises en charge, accédez à la galerie d’applications mobiles Microsoft Intune sur la page des [partenaires de l’application Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### Mises à jour du Portail d’entreprise

#### Application Portail d’entreprise Android
- **Notifications toast pour l’utilisateur final** : les utilisateurs finaux voient à présent des notifications toast provenant de l’application Portail d’entreprise Android quand ils inscrivent leurs appareils ou suppriment leurs appareils sur le portail d’entreprise.

- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise Android.** Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise Android. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune.

#### Site web Portail d’entreprise
- **Site web Portail d’entreprise : Une bannière d’identification de l’appareil fournit d’autres informations aux utilisateurs finaux.** Désormais, les utilisateurs finaux peuvent facilement identifier l’appareil qu’ils ont sélectionné lorsqu’ils utilisent le site web Portail d’entreprise. Si un appareil incorrect est sélectionné, ils peuvent sélectionner l’appareil approprié en cliquant sur le lien **Tap here** (Appuyer ici) dans la bannière de la page d’accueil.

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

  Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle application de gestion des droits (partage RMS) pour Android, qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. En savoir plus sur l’application de partage RMS (avec un lien vers la documentation).

- **Ciblage de groupe personnalisé de suppression des règles de notification.**
Les règles de notification Intune définissent les destinataires d’une alerte par e-mail envoyée par Intune. Actuellement, vous pouvez configurer des règles de notification pour envoyer des e-mails à tous les utilisateurs d’appareils d’un groupe d’appareils Intune que vous avez créé. Aux alentours du 1er juin 2016, le ciblage des groupes créés par l’utilisateur n’est plus pris en charge.

    Aujourd’hui, pour cibler une règle de notification sur un groupe que vous avez créé à partir de la console d’administration Microsoft Intune, procédez comme suit :

    Dans l’espace de travail **Administration**, cliquez sur **Règles de notification** > **Créer une règle**.

    À l’étape 2 de l’Assistant Créer règle de notification, sélectionnez les groupes d’appareils que la règle doit cibler. Cette étape, « Sélection de groupes d’appareils », va être supprimée de la console Intune.

    Le calendrier relatif à cette modification est le suivant :
    - En juin 2016, les nouveaux clients ne verront pas l’étape 2 de l’Assistant Créer règle de notification. Les clients existants ne sont pas affectés.
    - Vers le mois d’aout 2016, certains clients existants ne verront pas l’étape « Sélection de groupes d’appareils » dans l’Assistant.
    - Vers le mois d’octobre 2016, nous prévoyons qu’aucun client ne voie plus l’étape « Sélection de groupes d’appareils » dans l’Assistant.


- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**. Au cours des prochains mois, une mise à jour sera publiée pour l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 8.0 ou ultérieure. Les utilisateurs ne pourront pas inscrire de nouveaux appareils exécutant des versions d’iOS inférieures à 8.0. Les appareils inscrits qui exécutent des versions d’iOS inférieures à 8.0 continueront d’être gérés et pourront continuer à utiliser l’application Portail d’entreprise pour une durée limitée. Toutefois, les appareils doivent utiliser iOS version 8.0 ou ultérieure pour accéder aux versions les plus récentes de l’application Portail d’entreprise. Nous vous encourageons à informer les utilisateurs de mettre à jour leur système d’exploitation vers iOS version 8.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  


## Avril 2016
Toutes ces fonctionnalités sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune).
### Gestion d'applications
- **Conformité MAM de l’utilisateur.**
Vous pouvez désormais afficher l’[état](monitor-mobile-app-management-policies-with-Microsoft-Intune.md) de vos stratégies de gestion d’applications pour n'importe quel utilisateur dans votre client Azure Active Directory (AAD). Les opérations à effectuer sont les suivantes :
   - Appareils
   - Applications sur l’appareil

   Valeurs d'état :

   **Activé** : indique que la stratégie a été déployée pour l'utilisateur, que l’application a été utilisée dans un contexte professionnel et qu’elle a reçu avec succès la stratégie.

    **Non activé :** indique que la stratégie a été déployée pour l’utilisateur, mais que l’application n’a pas été utilisée au moins une fois dans un contexte professionnel depuis.


- **Contrôles MAM pour empêcher la synchronisation des contacts Outlook (Android).**
Un nouveau paramètre est disponible pour la [gestion des applications mobiles](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) sans inscription de l'appareil. Ce paramètre vous permet d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils Android. Si ce paramètre est activé, les applications ciblées ne pourront plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, les applications ciblées pourront enregistrer les contacts dans le carnet d'adresses natif. Lorsque vous [réinitialisez de façon sélective un appareil ou une application](wipe-managed-company-app-data-with-Microsoft-Intune.md), les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est initialement pris en charge par l'application Outlook sur les appareils Android.

### Gestion des appareils
- **Identification de numéros de téléphone pour les appareils appartenant à l'entreprise.** Les téléphones classés comme « appartenant à l’entreprise » sont identifiés avec leur numéro de téléphone complet, par exemple, lorsque vous exécutez un rapport d’inventaire des appareils mobiles. Les numéros de téléphone de type « BYOD » continuent d’être masqués avec **** ; seuls les 4 derniers chiffres s’affichent.


### Mises à jour de Portail d'entreprise
**Application Portail d’entreprise Android** Les utilisateurs qui n’ont pas inscrit leur appareil dans Intune et qui n’ont pas le bon certificat installé ne peuvent pas se connecter à l’application Portail d’entreprise Android. Le message suivant s’affiche : « Vous ne pouvez pas vous connecter, car il manque un certificat obligatoire à votre appareil ». Le message inclut un lien « Comment résoudre ce problème » permettant aux utilisateurs d’obtenir des instructions pour installer le certificat. Pour connaître les étapes que les utilisateurs finaux doivent suivre pour résoudre ce problème, consultez [Un certificat obligatoire est manquant sur votre appareil](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Application Portail d’entreprise iOS** Une prise en charge a été ajoutée pour l’action Tirer pour actualiser permettant d’actualiser le contenu sur l’écran d’accueil, notamment les applications répertoriées, les appareils répertoriés et les informations sur les contacts informatiques. L'action Tirer pour actualiser ne vérifie pas les informations de conformité ou de stratégie, opération qui peut être effectuée en sélectionnant la vignette correspondant à votre appareil puis en appuyant sur le bouton **Sync**.

**Application Portail d’entreprise Windows 10 Mobile et Windows Phone 8.1** Quand les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour obtenir les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement pour accélérer l’installation des applications](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Site web du portail d’entreprise** Quand les utilisateurs Windows 10 Mobile et Windows Phone 8.1 installent des applications métier, les nouveaux états suivants apparaissent et leur fournissent plus de détails sur l’état de leur installation :

* **En attente de la synchronisation de l’appareil** : l'utilisateur a appuyé sur « Installer » et l'appareil tente à présent de se synchroniser avec l'infrastructure Intune. La synchronisation est nécessaire pour pouvoir finaliser l'installation. Le message « En attente de la synchronisation de l’appareil » contient également un lien sur lequel les utilisateurs peuvent cliquer pour obtenir des [instructions](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) sur la synchronisation manuelle de leur appareil avec Intune si le processus de synchronisation prend beaucoup de temps ou se bloque.
* **Téléchargement** : la demande de téléchargement de l'utilisateur est en cours de traitement et l’appareil télécharge et installe l'application.

Avant l'ajout de ces états, les utilisateurs étaient désorientés lorsque l’installation de l'application prenait beaucoup de temps car seul l’état « Installation » s’affichait à l'écran, parfois pendant des heures. Grâce à l’ajout de ces nouveaux états, au lieu d'appeler le support technique, les utilisateurs peuvent désormais appuyer sur le lien « En attente de la synchronisation de l’appareil » et suivre les instructions pour forcer la reprise du processus de synchronisation.


## Mars 2016
### Nouveautés au 29 mars 2016
À l’exception de la mise à jour de la stratégie de configuration générale Windows 10, toutes les fonctionnalités publiées le 29 mars 2016, sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune). La prise en charge d’un environnement hybride pour la mise à jour de la stratégie de configuration générale Windows 10 sera bientôt disponible. Veuillez noter que certaines de ces fonctionnalités peuvent nécessiter la dernière version du Configuration Manager.

### Gestion d'applications
- **Contrôles MAM pour empêcher la synchronisation des contacts Outlook (iOS).** Un nouveau paramètre est disponible pour la gestion des applications mobiles sans inscription de l'appareil. Ce paramètre vous permet d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils iOS. Si ce paramètre est activé, l'application ne pourra plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, l'application pourra enregistrer les contacts dans le carnet d'adresses natif. Lorsque vous réinitialisez de façon sélective un appareil ou une application, tous les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est pris en charge par l'application Outlook sur les appareils iOS. Pour plus d’informations à ce sujet et sur d’autres paramètres, consultez [Créer et déployer des stratégies de gestion des appareils mobiles](https://technet.microsoft.com/en-us/library/dn292747.aspx).

### Contrôle d'accès
- **Skype Entreprise Online prend en charge l'accès conditionnel.** Vous pouvez définir une stratégie d'accès conditionnel pour Skype Entreprise Online afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et compatibles. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Skype Entreprise sur un appareil iOS et Android seront invités à s'inscrire auprès d’Intune et à résoudre les éventuels problèmes d'incompatibilité avant de finaliser la connexion. Pour plus d’informations, consultez [Manage access to Skype for Business Online](https://technet.microsoft.com/en-us/library/mt695297.aspx) (Gestion de l’accès à Skype Entreprise Online).

### Gestion des appareils
- **Prise en charge d’Intune pour iOS 9.3.** Le Lundi 21 mars, Apple a annoncé la mise sur le marché d’iOS 9.3. Nous avons travaillé à assurer la compatibilité de Microsoft Intune avec la dernière version du système d’exploitation mobile Apple et [nous avons le plaisir d’annoncer qu’Intune prend en charge la gestion des appareils iOS 9.3](https://blogs.technet.microsoft.com/microsoftintune/2016/03/23/microsoft-intune-provides-support-for-ios-9-3/).

  Toutes les fonctionnalités Intune existantes actuellement disponibles pour la gestion des appareils iOS continue de fonctionner en toute transparence lorsque les utilisateurs migrent leurs appareils vers iOS 9.3. iOS 9.3 est également pris en charge aujourd’hui pour les clients hybrides (Configuration Manager intégré à Intune).

- **La stratégie de configuration générale Windows 10 contient maintenant des paramètres pour gérer Windows Defender sur des PC Windows 10 inscrits.** Pour plus d’informations, consultez [Paramètres de la stratégie de configuration Windows 10 dans Microsoft Intune](https://technet.microsoft.com/en-us/library/mt404697.aspx).


### Portail d'entreprise

- **Packages d’applications Windows disponibles directement accessibles depuis le portail d’entreprise.** Les utilisateurs de PC sous Windows 8, Windows 8.1 et Windows RT peuvent désormais installer des packages d'applications Windows (avec l'extension .aspx) directement depuis le site Web du portail d'entreprise. Auparavant, vous deviez effectuer le déploiement, ou les utilisateurs devaient installer l'application Portail d'entreprise sur leurs appareils pour installer des applications.

- **Les utilisateurs peuvent verrouiller à distance leurs appareils depuis le portail d’entreprise** Une nouvelle option de verrouillage à distance a été ajoutée au site Web du portail d'entreprise pour permettre aux utilisateurs de verrouiller à distance leurs appareils depuis le portail si leur appareil est égaré ou volé. Consultez les [instructions pour l’utilisateur final](https://technet.microsoft.com/library/mt590895.aspx/?wt.mc_id=ui#BKMK_iwp_remote_lock). Le tableau suivant répertorie les plates-formes prises en charge pour le verrouillage à distance avec Intune en mode autonome et Intune avec Configuration Manager.

|Plate-forme | Détails de la prise en charge|
|---------|----------------|
|Android |Pris en charge|
|iOS |Pris en charge|
|Windows 10 Mobile |Pris en charge uniquement si le téléphone dispose d’un code secret|
|Windows 10 Desktop |Non prise en charge|
|Windows Phone 8.1 |Pris en charge uniquement si le téléphone dispose d’un code secret|
|Windows Phone 8.0 |Non prise en charge|
|PC (Windows 8.0 et versions antérieures) |Non prise en charge|
|PC (Windows 8.1) |Non pris en charge|

### Nouveautés au 10 mars 2016

### Gestion d'applications

- **Tirer parti de la gestion « Open-in » d’iOS pour les appareils qui sont inscrits dans une solution tierce de gestion des appareils mobiles** Vous pouvez utiliser votre fournisseur tiers de gestion des appareils mobiles pour tirer parti de la gestion « Open-In » d’iOS. Vous pouvez définir des restrictions dans les paramètres de profil de configuration et déployer l’application à l’aide des informations contenues dans [Gérer les transferts de données entre applications iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

     Cette approche présente deux avantages principaux :

     1. Les utilisateurs doivent se connecter avec leur compte professionnel avant de pouvoir accéder à des données d’entreprise à partir des services cloud ou d’autres applications. Cela permet de s’assurer que les stratégies de gestion des applications mobiles sont en place lors de l’accès aux données.

     2. Les profils de messagerie gérés et d’autres applications gérées déployées par le biais d’une solution de gestion des appareils mobiles tierce peuvent partager des fichiers et des données avec les applications qui ont des stratégies MAM Intune.

- **Gérer l’application Microsoft Outlook avec des stratégies GAM pour les appareils non inscrits dans Intune** Vous pouvez désormais gérer l’application Microsoft Outlook sur les appareils qui ne sont pas inscrits dans Intune avec la stratégie de gestion des applications mobiles Intune. L’application Microsoft Outlook mise à jour avec les fonctionnalités MAM est disponible pour les appareils [iOS](https://itunes.apple.com/us/app/microsoft-outlook-email-calendar/id951937596?mt=8) et [Android](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook). Suivez les instructions de la rubrique [Créer et déployer des stratégies de gestion des applications mobiles](https://technet.microsoft.com/library/mt627829.aspx) pour créer une stratégie MAM.  


- **Les stratégies de configuration des applications mobiles offrent plus de souplesse pour spécifier les détails de l’utilisateur pour les applications iOS** Vous pouvez fournir des paramètres utilisateur dont une application iOS peut avoir besoin quand elle est ouverte. Par exemple, vous pouvez fournir un port réseau ou un nom d’utilisateur. Pour plus d’informations, consultez [Configurer des applications iOS avec des stratégies de configuration des applications mobiles dans Microsoft Intune](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md).


- **Déployer Adobe Reader pour Microsoft Intune sur des appareils iOS gérés par Intune dans votre entreprise** L’application Adobe Reader pour iOS peut maintenant être gérée sur les appareils inscrits avec la stratégie de gestion des applications mobiles Intune.

- **Vérifiez que les clips web déployés sont ouverts dans Managed Browser** Vous pouvez déployer des clips web ciblés qui peuvent uniquement être ouverts à l’aide de Managed Browser sur des appareils iOS et Android. Par exemple, vous déployez des liens vers des ressources d’entreprise par le biais du portail d’entreprise et, quand les utilisateurs accèdent aux liens, ils s’ouvrent directement dans Managed Browser où ils peuvent être protégés par une stratégie de gestion des applications mobiles. Pour plus d’informations, consultez [Déployer des applications](deploy-apps.md).


- **Rechercher, gérer et distribuer des applications Windows Store pour Entreprises pour les appareils Windows 10 à partir de la console d’administration Intune** La prise en charge du Windows Store pour Entreprises est disponible dans Intune pour vous aider à rechercher, gérer et distribuer des applications sur les appareils Windows 10 que vous gérez. Le Windows Store pour Entreprises vous permet de gérer le processus de déploiement et de surveillance de ces applications à partir de la console Administrateur Intune, la même console que vous utilisez pour gérer vos autres applications. Plus précisément, le Windows Store pour Entreprises gère le contenu et les licences des « applications sous licence en ligne ». Pour plus d’informations, consultez [Gérer les applications que vous avez achetées dans Windows Store pour Entreprises](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).


### Gestion des appareils
- **Distribution de certificats PFX pour les appareils iOS** Les administrateurs Intune peuvent créer et déployer des certificats PFX iOS pour l’authentification Wi-Fi, e-mail et VPN sur les appareils iOS. Cette fonctionnalité est déjà disponible pour les appareils Android et Windows 10. Pour plus d’informations, consultez [Activer l’accès aux ressources d’entreprise à l’aide de profils de certificat](secure-resource-access-with-certificate-profiles.md).


- **Appliquer des applications et des stratégies à différents groupes d’appareils en fonction de la sélection de catégorie de l’utilisateur** Les administrateurs Intune peuvent maintenant définir des catégories d’appareils personnalisées que les utilisateurs peuvent sélectionner pendant l’inscription. Par exemple, les administrateurs peuvent souhaiter que les utilisateurs spécifient s’ils inscrivent un appareil utilisé pour « Caisse enregistreuse », « Camion de livraison » ou « Salle des inventaires ». La catégorie sélectionnée fait que l’appareil devient membre d’un groupe d’appareils Intune, qui peut être utilisé pour le déploiement de différentes stratégies et applications sur l’appareil inscrit. Pour plus d’informations, consultez [Catégoriser les appareils avec le mappage de groupe d’appareils](categorize-devices-with-device-group-mapping-in-microsoft-intune.md).

### Modifications et mises à jour du portail d’entreprise Microsoft
Les modifications suivantes ont été apportées au portail d’entreprise dans cette version.

**Application Portail d’entreprise Android**

* Quand vos utilisateurs lancent une application gérée par la gestion des applications mobiles (MAM), un message les avertit que l’application est gérée par leur société. Les utilisateurs peuvent désormais appuyer sur un lien « En savoir plus » pour obtenir des [informations supplémentaires](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_use_mgd_apps) sur ce que signifie le terme « applications gérées ». Ils peuvent aussi appuyer sur « Ne plus afficher » pour que le message n’apparaisse plus lors du lancement de l’application.
* De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
* Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.


**Application Portail d’entreprise iOS**
* Quand vos utilisateurs lancent une application gérée par la gestion des applications mobiles (MAM), un message les avertit que l’application est gérée par leur société. Les utilisateurs peuvent désormais appuyer sur un lien « En savoir plus » pour obtenir des [informations supplémentaires](https://technet.microsoft.com/library/mt598622.aspx#BKMK_ios_use_mgd_apps) sur ce que signifie le terme « applications gérées ». Ils peuvent aussi appuyer sur « Ne plus afficher » pour que le message n’apparaisse plus lors du lancement de l’application.
* De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).
* Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.




## Février 2016
### Modifications et mises à jour du portail d’entreprise Microsoft

Les modifications suivantes ont été apportées au portail d’entreprise dans cette version.

#### Application Portail d’entreprise Android
- De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_enroll_devc).
- Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.

#### Application Portail d’entreprise iOS
 - De nouveaux écrans ont été ajoutés pour guider les utilisateurs lors du processus d’inscription, et pour fournir des informations supplémentaires sur la raison pour laquelle ils doivent s’inscrire et sur ce que les administrateurs informatiques peuvent et ne peuvent pas voir sur leurs appareils inscrits. Pour plus d’informations, consultez les [instructions d’inscription](https://technet.microsoft.com/library/mt598622.aspx#BKMK_enroll_ios_device).

 - Les messages d’erreur d’inscription sont maintenant affichés dans l’application Portail d’entreprise. Auparavant, ces messages étaient affichés sur le site web du portail d’entreprise. Cette modification signifie que tous les messages d’erreur apparaissent maintenant à un seul endroit, plutôt qu’à deux emplacements différents.


## Janvier 2016

### Tirer parti des fonctionnalités de Windows 10
* **Accès conditionnel avec le service d’attestation de l’intégrité** Les administrateurs Intune peuvent désormais afficher l’état de l’attestation de l’intégrité des appareils Windows 10 dans la console d’administration Intune. L’attestation de l’intégrité des appareils permet à l’administrateur de s’assurer que les ordinateurs clients ont des configurations de BIOS, de Module de plateforme sécurisée (TPM) et de logiciel de démarrage dignes de confiance. Pour prendre en charge l’attestation de l’intégrité des appareils, les appareils clients doivent exécuter Windows 10 avec le Module de plateforme sécurisée (TPM) 2 activé. L’attestation de l’intégrité des appareils affiche le nombre d’appareils activés pour chacun des éléments suivants :
    * Logiciel anti-programme malveillant à lancement anticipé
    * BitLocker
    * Démarrage sécurisé
    * Intégrité du code

    Pour plus d’informations sur le paramètre d’intégrité des appareils, sur les points de données recueillis et sur le rapport d’attestation d’intégrité, consultez [Introduction aux stratégies de conformité des appareils pour Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md). Pour en savoir plus, référez-vous aux [détails du service HAS](https://msdn.microsoft.com/en-us/library/dn934876.aspx).

* [Stratégie Windows 10 Passport for Work et gestion des certificats](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) Avec Intune, vous pouvez **intégrer Microsoft Passport for Work** et disposer ainsi d’une méthode de connexion alternative pour Windows 10 qui utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle. Passport vous permet d’utiliser un mouvement utilisateur pour vous connecter, au lieu d’un mot de passe. Un mouvement utilisateur peut être un simple code confidentiel, une authentification biométrique telle que Windows Hello ou un appareil externe tel qu’un lecteur d’empreintes digitales.

* **VPN pour des applications spécifiques** Vous pouvez sélectionner les applications qui se connectent automatiquement à votre réseau d’entreprise par le biais du VPN. Créez la liste des applications quand vous configurez le profil VPN, comme décrit dans Aider les utilisateurs à se connecter à leur travail à l’aide de profils VPN avec Microsoft Intune.

* **Prise en charge de la réinitialisation complète de Windows 10** Vous pouvez maintenant effectuer une réinitialisation complète à distance d’appareils Windows 10 Desktop inscrits dans Intune par le biais de la console d’administration Intune. La réinitialisation complète de Windows 10 effectue une réinitialisation aux paramètres d’usine de l’appareil.


### Mise à jour du programme VPP (Volume Purchase Program) d’Apple
Intune peut maintenant vous aider à [gérer les applications que vous avez achetées par le biais du programme VPP (Volume Purchase Program) d’Apple pour les entreprises](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md). Cela comprend la synchronisation des informations de licence entre Apple et Intune, et le suivi du nombre de copies de chaque application que vous avez déployées.

### Utiliser des numéros IMEI pour identifier les appareils appartenant à l’entreprise
Vous pouvez désormais [importer des numéros IMEI (international mobile equipment identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) pour les plates-formes d’appareils mobiles ayant ce type de numéro, afin de faciliter l’identification des appareils mobiles appartenant à l’entreprise. Une fois inscrit dans Intune, les appareils avec des numéros IMEI importés sont marqués comme appareils d’entreprise, ce qui peut être utilisé pour appliquer des stratégies différentes de celles appliquées aux appareils personnels.

### Davantage d’applications sont désormais compatibles avec les stratégies MAM Intune
Des applications supplémentaires de partenaires de Microsoft sont désormais compatibles avec les stratégies de gestion des applications mobiles (MAM) Intune (pour les appareils gérés par Intune) :
* Box for EMM (de Box Inc) : iOS uniquement
* Adobe Reader (d’Adobe) : Android uniquement
* Foxit PDF Reader (de Foxit Corporation) : iOS et Android


### La prise en charge d’IE9 cesse en janvier
Le support d’Internet Explorer 9 prend fin dès le mois de février 2016. Dès lors, ce ne sera plus le navigateur officiel pour accéder au site web Portail d’entreprise Microsoft Intune, au portail de compte Intune et à la console d’administration Intune. Vous devrez migrer vers Internet Explorer 10 ou version ultérieure.


>[!div class="step-by-step"]

>[&larr; **Nouveautés d'Intune**](whats-new-in-microsoft-intune.md)    



<!--HONumber=Sep16_HO2-->


