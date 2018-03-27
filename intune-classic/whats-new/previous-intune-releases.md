---
title: Versions précédentes
description: ''
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 45dad14a-d412-488d-bb1e-ad990ea503df
ROBOTS: NOINDEX,NOFOLLOW
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 76e53cabba9b684170d659ae5b8ef884bfe9abaa
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="previous-intune-releases"></a>Versions précédentes d’Intune

Cette page contient une liste des annonces publiées dans [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/whats-new-last-six-months.md)]

## <a name="july-2016"></a>Juillet 2016

### <a name="app-management"></a>Gestion d'applications

__Améliorer l’expérience de mise à jour de profil d’approvisionnement d’application__ Les applications mobiles métier Apple iOS intègrent un profil d’approvisionnement et du code signé avec un certificat. Lorsque l’application s’exécute sur un appareil iOS, iOS confirme l’intégrité de l’application iOS et applique les stratégies définies par le profil de configuration.

Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement 3 ans. Toutefois, le profil de configuration expire au bout d’1 an. Grâce à cette mise à jour, Intune vous offre les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration alors que le certificat est toujours valide. Pour plus d’informations, consultez [Utiliser des stratégies de profil de provisionnement d’applications mobiles iOS pour maintenir vos applications métier à jour](/intune-classic/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Disponibilité du Xamarin SDK pour applications Intune__ Le composant Xamarin SDK pour applications Intune vous permet d’activer les fonctionnalités de gestion des applications mobiles Intune dans vos applications Android et iOS mobiles développées avec Xamarin. Ce composant est disponible dans le [Store Xamarin](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou dans la [page Github Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Gestion des périphériques
__Augmentation du nombre d’inscriptions d’appareils__ Intune augmente le nombre maximal d’inscriptions d’appareils configurables en repoussant leur limite de 5 appareils par utilisateur à 15.
<!---TFS 1289896 --->

__Intégration de TeamViewer sur les PC Windows exécutant le logiciel client Intune__
[TeamViewer](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise

__Site web Portail d’entreprise__
- **Amélioration de l’interface d’inscription d’appareils Windows**<br/>
Quand vous utilisez l’accès conditionnel, les étapes d’inscription pour Windows 8.1, Windows 10 Desktop et Windows 10 Mobile ont été clarifiées dans le site web Portail d’entreprise. Les utilisateurs peuvent à présent voir deux étapes distinctes, « Inscription de l’appareil » et « Jonction au lieu de travail », ce qui leur permet de consulter plus facilement l’état de leur appareil et de terminer le processus en cas d’échec de l’outil Workplace Join (WPJ). Ces différentes étapes sont également censées simplifier le processus de résolution des problèmes pour les administrateurs. Auparavant, quand les utilisateurs finaux tentaient d’effectuer une inscription et que toutes les étapes d’inscription réussissaient à l’exception de la jonction d’espace de travail, l’appareil inscrit n’apparaissait pas dans la liste des appareils pour être identifiés par les utilisateurs, ce qui est une source de confusion pour les utilisateurs.

__Android__
- **Application Portail d’entreprise Android**<br/>
Si les utilisateurs finaux Android voient un message d’erreur leur indiquant qu’il manque un certificat nécessaire à leur appareil, ils peuvent appuyer sur un bouton « Comment résoudre ce problème » pour consulter les [étapes](/intune-classic/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues) que les administrateurs informatiques peuvent utiliser pour résoudre le problème de certificat.

- **Limiter les installations d’applications à chargement indépendant sur les appareils inscrits**<br/>
Les appareils Android ne peuvent plus installer d’applications par le biais du site web du portail d’entreprise, sauf s’ils ont été inscrits dans Intune à l’aide de l’application portail d’entreprise Intune pour Android.
<!---TFS 1299082--->

__iOS__
- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS**<br/>
Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet **Mes appareils** de l’application Portail d’entreprise pour iOS. Seul l’appareil local exécutant l’application est affiché, et uniquement s’il est inscrit à l’aide de l’application Portail d’entreprise.

L’utilisateur d’un gestionnaire d’inscription d’appareil peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée qu’à partir de la console d’administration Intune. De plus, Intune déprécie l’utilisation de comptes gestionnaires d’inscription d’appareil avec le programme d’inscription des appareils Apple ou l’outil Configurateur Apple. Ces deux méthodes d’inscription prennent déjà en charge l’inscription sans utilisateur pour les appareils iOS partagés.

Utilisez uniquement des comptes gestionnaires d’inscription d’appareil quand l’inscription sans utilisateur pour les appareils partagés n’est pas disponible. Pour plus d’informations, consultez [Inscrire des appareils d’entreprise avec le Gestionnaire d’inscription d’appareil dans Microsoft Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Modification des noms de fonctionnalités Windows
- [Microsoft Passport pour Windows](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) se nomme maintenant **Windows Hello Entreprise**.
- [Protection des données d’entreprise](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) est maintenant appelé **Protection des informations Windows**.


## <a name="june-2016"></a>Juin 2016
### <a name="intune-service-health"></a>État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Ces informations sont désormais disponibles sur le portail de gestion Office 365 sous État du service. Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gestion d'applications
- **Amélioration de la configuration des stratégies de données d’entreprise Windows 10.** Nous avons amélioré la configuration des stratégies de protection des données d’entreprise Windows 10 au niveau de la création des règles d’application, de la définition des limites du réseau et d’autres paramètres de protection des données d’entreprise. Pour plus d’informations, consultez la rubrique [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Gestion des périphériques
- **Paramètre de stratégie Windows Defender pour une protection contre les applications potentiellement indésirables.** Un nouveau paramètre Windows Defender nommé **Potentially Unwanted Application Detection** (Détection des applications potentiellement indésirables) a été ajouté à la stratégie de configuration générale pour Windows 10 Desktop et Mobile. Vous pouvez utiliser ce paramètre pour empêcher les postes de travail Windows inscrits d’exécuter des logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée. Pour plus d’informations, consultez [Paramètres de la stratégie Windows 10 dans Microsoft Intune](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Accès conditionnel
- **Stratégie de contrôle d’accès au réseau Cisco ISE pour Intune.**  Les clients qui utilisent Cisco Identity Service Engine (ISE) 2.1 et Microsoft Intune peuvent définir une stratégie de contrôle d’accès au réseau dans ISE.

    Quand vous utilisez cette stratégie, les appareils qui doivent se connecter au réseau Wi-Fi ou VPN doivent respecter les conditions suivantes avant d’obtenir l’autorisation d’accès :

    * Ils doivent être gérés par Intune
    * Ils doivent être conformes à toutes les stratégies de conformité Intune déployées

 Les utilisateurs finaux d’appareils non conformes sont invités à les inscrire et corriger tout problème de conformité pour obtenir l’accès.
- **Accès conditionnel pour le navigateur.** Vous pouvez définir une stratégie d’accès conditionnel pour [Exchange Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) afin que ces applications soient uniquement accessibles à partir de navigateurs web pris en charge sur des appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android sont invités à inscrire leur appareil dans Intune, et à résoudre les problèmes de non conformité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **Dynamics CRM Online prend en charge l’accès conditionnel.** Vous pouvez définir une stratégie d’accès conditionnel pour [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Dynamics CRM sur un appareil iOS ou Android seront invités à s’inscrire à Intune et à résoudre les éventuels problèmes de non conformité avant de finaliser la connexion.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Mises à jour du Portail d’entreprise Intune

__Application Portail d’entreprise Android__

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils interdisent l’installation d’applications à partir de sources inconnues (Android 4.0+) », le message « L’installation à partir de sources inconnues doit être désactivée » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Sécurité**, puis désactiver **Sources inconnues**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/intune-user-help/you-are-asked-to-turn-off-unknown-sources-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils recherchent les menaces de sécurité (Android 4.0+) », le message « Rechercher les menaces de sécurité sur l’appareil » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Google** > **Sécurité**, puis activer **Rechercher les menaces de sécurité sur l’appareil**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) supplémentaires sur le message et la raison pour laquelle ils doivent activer le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger la désactivation du débogage USB (Android 4.2+) », le message « Le débogage USB doit être désactivé » s’affiche aux utilisateurs finaux d’appareils Android 4.2 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Options pour développeurs**, puis désactiver **Débogage USB**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/intune-user-help/you-are-asked-to-turn-off-usb-debugging-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie « Niveau minimal du correctif de sécurité Android (Android 6.0+), le message « Cet appareil n’est pas au niveau minimal du correctif de sécurité Android » s’affiche aux utilisateurs finaux d’appareils Android 6.0 ou version ultérieure. Les utilisateurs doivent installer le correctif de sécurité demandé. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/intune-user-help/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sur la façon d’installer le correctif de sécurité demandé et de voir quel correctif de sécurité est actuellement installé.

__Application Portail d’entreprise iOS__

- Lorsque les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l’installation de l’application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour consulter les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement](/intune-user-help/sync-your-device-manually-ios).

- L’application Portail d’entreprise Microsoft Intune pour iOS a été mise à jour pour prendre en charge iOS 8.0 et version ultérieure. Cette mise à jour signifie que les utilisateurs finaux peuvent installer l’application Portail d’entreprise et inscrire de nouveaux appareils dans Intune uniquement si l’appareil exécute iOS version 8.0 ou ultérieure. Les utilisateurs qui ont déjà inscrit des appareils exécutant une version non prise en charge d'iOS peuvent continuer à utiliser l'application Portail d'entreprise qui figure sur leur appareil.

## <a name="may-2016"></a>Mai 2016
Toutes ces fonctionnalités sont également prises en charge pour les déploiements hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez la page [Nouveautés hybrides](https://technet.microsoft.com/library/mt718155.aspx).

### <a name="documentation"></a>Documentation
Bienvenue dans la préversion de [docs.microsoft.com](https://docs.microsoft.com/intune).
Il s’agit d’une plateforme de contenu moderne, entièrement nouvelle, conçue pour permettre à nos clients de comprendre et d’utiliser plus aisément Intune.
Pour découvrir toutes les nouvelles fonctionnalités, consultez [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Présentation de docs.microsoft.com).

### <a name="intune-service-health"></a>État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Vous trouvez désormais ces informations sur le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) sous **État du service**.
Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gestion d'applications
- **SDK GAM : prise en charge de la configuration de longueur de code confidentiel.** Vous pourrez spécifier la longueur du code confidentiel des applications MAM comme s’il s’agissait du code confidentiel d’un appareil. Cette opération obligera les utilisateurs finaux à respecter les nouvelles restrictions que vous définissez. Ils verront un écran légèrement différent pour prendre en compte la saisie d’un code confidentiel plus long. Pour plus d’informations, consultez [Paramètres de stratégie MAM pour Android](/intune-classic/deploy-use/ios-mam-policy-settings).

- **Skype Entreprise pour iOS et Android.** Vous pouvez maintenant cibler Skype Entreprise avec [MAM sans stratégie d’inscription](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Une fois les utilisateurs connectés, les stratégies GAM sont appliquées.

- **Nouvelles applications disponibles pour la gestion avec les stratégies GAM.** Les applications Microsoft Word, Excel et PowerPoint pour Android peuvent désormais être associées avec des stratégies MAM sur des appareils qui ne sont pas inscrits auprès d’Intune. Pour obtenir la liste complète des applications prises en charge, accédez à la galerie d’applications mobiles Microsoft Intune sur la page des [partenaires de l’application Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise

#### <a name="android-company-portal-app"></a>Application Portail d’entreprise Android
- **Notifications toast pour l’utilisateur final** : les utilisateurs finaux voient à présent des notifications toast provenant de l’application Portail d’entreprise Android quand ils inscrivent leurs appareils ou suppriment leurs appareils sur le portail d’entreprise.

- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise Android.** Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise Android. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune.

#### <a name="company-portal-website"></a>site web Portail d’entreprise
- **Site web Portail d’entreprise : une bannière d’identification de l’appareil fournit d’autres informations aux utilisateurs finaux.** Désormais, les utilisateurs finaux peuvent facilement identifier l’appareil qu’ils ont sélectionné lorsqu’ils utilisent le site web Portail d’entreprise. Si un appareil incorrect est sélectionné, ils peuvent sélectionner l’appareil approprié en cliquant sur le lien **Tap here** (Appuyer ici) dans la bannière de la page d’accueil.

### <a name="service-deprecation"></a>Désapprobation du service
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


## <a name="april-2016"></a>Avril 2016
Toutes ces fonctionnalités sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune).

### <a name="app-management"></a>Gestion d'applications
- **Conformité GAM de l’utilisateur.**
Vous pouvez désormais afficher l’[état](/intune-classic/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) de vos stratégies de gestion d’applications pour n'importe quel utilisateur dans votre client Azure Active Directory (AAD). Les opérations à effectuer sont les suivantes :
   - Appareils
   - Applications sur l’appareil

   Valeurs d'état :

   **Activé** : indique que la stratégie a été déployée pour l'utilisateur, que l’application a été utilisée dans un contexte professionnel et qu’elle a reçu avec succès la stratégie.

    **Non activé :** indique que la stratégie a été déployée pour l’utilisateur, mais que l’application n’a pas été utilisée au moins une fois dans un contexte professionnel depuis.


- **Contrôles GAM pour empêcher la synchronisation des contacts Outlook (Android).**
Un nouveau paramètre est disponible pour la [gestion des applications mobiles](/intune-classic/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), les contacts qui ont déjà été enregistrés dans le carnet d’adresses natif seront supprimés. Ce nouveau paramètre est initialement pris en charge par l’application Outlook sur les appareils Android.

### <a name="device-management"></a>Gestion des périphériques
- **Identification de numéros de téléphone pour les appareils appartenant à l’entreprise.** Les téléphones classés comme « appartenant à l’entreprise » sont identifiés avec leur numéro de téléphone complet, par exemple, lorsque vous exécutez un rapport d’inventaire des appareils mobiles. Les numéros de téléphone de type « BYOD » continuent d’être masqués avec **** ; seuls les 4 derniers chiffres s’affichent.


### <a name="company-portal-updates"></a>Mises à jour de Portail d'entreprise
**Application Portail d’entreprise Android** Les utilisateurs qui n’ont pas inscrit leur appareil dans Intune et qui n’ont pas le bon certificat installé ne peuvent pas se connecter à l’application Portail d’entreprise Android. Le message suivant s’affiche : « Vous ne pouvez pas vous connecter, car il manque un certificat obligatoire à votre appareil ». Le message inclut un lien « Comment résoudre ce problème » sur lequel les utilisateurs peuvent appuyer pour afficher des instructions sur l’installation du certificat. Pour connaître les étapes que les utilisateurs finaux doivent suivre pour résoudre ce problème, consultez [Un certificat obligatoire est manquant sur votre appareil](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Application Portail d’entreprise iOS** Une prise en charge a été ajoutée pour l’action Tirer pour actualiser permettant d’actualiser le contenu sur l’écran d’accueil, notamment les applications répertoriées, les appareils répertoriés et les informations sur les contacts informatiques. L'action Tirer pour actualiser ne vérifie pas les informations de conformité ou de stratégie, opération qui peut être effectuée en sélectionnant la vignette correspondant à votre appareil puis en appuyant sur le bouton **Sync**.

**Application Portail d’entreprise Windows 10 Mobile et Windows Phone 8.1** Quand les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour obtenir les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement pour accélérer l’installation des applications](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Site web du portail d’entreprise** Quand les utilisateurs Windows 10 Mobile et Windows Phone 8.1 installent des applications métier, les nouveaux états suivants apparaissent et leur fournissent plus de détails sur l’état de leur installation :

* **En attente de la synchronisation de l’appareil** : l'utilisateur a appuyé sur « Installer » et l'appareil tente à présent de se synchroniser avec l'infrastructure Intune. La synchronisation est nécessaire pour pouvoir finaliser l'installation. Le message « En attente de la synchronisation de l’appareil » contient également un lien sur lequel les utilisateurs peuvent cliquer pour obtenir des [instructions](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) sur la synchronisation manuelle de leur appareil avec Intune si le processus de synchronisation prend beaucoup de temps ou se bloque.
* **Téléchargement** : la demande de téléchargement de l'utilisateur est en cours de traitement et l’appareil télécharge et installe l'application.

Avant l'ajout de ces états, les utilisateurs étaient désorientés lorsque l’installation de l'application prenait beaucoup de temps car seul l’état « Installation » s’affichait à l'écran, parfois pendant des heures. Grâce à l’ajout de ces nouveaux états, au lieu d'appeler le support technique, les utilisateurs peuvent désormais appuyer sur le lien « En attente de la synchronisation de l’appareil » et suivre les instructions pour forcer la reprise du processus de synchronisation.

>[!div class="step-by-step"]

>[&larr; **Nouveautés d’Intune**](whats-new-in-microsoft-intune.md)    
