---
title: "Paramètres de restrictions d’appareil Intune pour iOS"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: a062b92cba0042153ffe22b949ce8a3b7b740b3f
ms.lasthandoff: 02/18/2017


---

# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils iOS dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Général
-     **Appareil photo** : spécifie si l’appareil photo de l’appareil peut être utilisé.     
-     **Envoi des données de diagnostic** : autoriser ou bloquer l’envoi de données de diagnostic à Apple depuis l’appareil.
-     **FaceTime** : autorisez l’utilisation de l’application FaceTime.
-     **Capture d'écran** : permet à l’utilisateur de capturer le contenu de l’écran en tant qu’image.
-     **Siri** : autoriser l’utilisation de l’assistant vocal Siri sur l’appareil.
    -     **Siri quand l'appareil est verrouillé** : autoriser l’utilisation de l’assistant vocal Siri sur l’appareil lorsqu’il est verrouillé.
    -     **Filtre d’obscénités de Siri (en mode supervisé uniquement)** : empêche Siri de dicter ou d’employer un langage obscène.
    -     **Siri à consulter le contenu généré par les utilisateurs depuis Internet (mode supervisé uniquement)** : autorisez Siri à accéder aux sites web pour répondre aux questions.
-     **Certificats TLS non approuvés** : autoriser les certificats Transport Layer Security non autorisés sur l’appareil.
-     **Accès au centre de contrôle quand l'appareil est verrouillé** : autorise l’utilisateur à accéder à l’application du centre de contrôle lorsque l’appareil est verrouillé.
-     **Notifications lorsque l’appareil est verrouillé** : autorisez l’utilisateur à accéder à l’affichage des notifications sans déverrouiller l’appareil.
-     **Livret lors du verrouillage de l’appareil** : autoriser l’utilisateur à accéder à l’application de livret lorsque l’appareil est verrouillé.
-     **Vue Aujourd'hui lors du verrouillage de l’appareil** : autorisez l’utilisateur à afficher la vue Aujourd'hui lorsque l’appareil est verrouillé.
-     **Approbation des applications d’entreprise** : permet à l’utilisateur de choisir de faire confiance aux applications qui n’ont pas été téléchargées à partir de l’App Store.
-     **AirDrop (en mode supervisé uniquement)** : autorise l’utilisation de la fonctionnalité AirDrop pour échanger du contenu avec des appareils proches.
-     **Recherche Spotlight pour renvoyer des résultats à partir d’Internet (mode supervisé uniquement)** : laissez la recherche Spotlight se connecter à Internet pour fournir des résultats.
-     **Recherche de définition des mots (en mode supervisé uniquement)** : autorise la fonctionnalité iOS qui vous permet de sélectionner un mot et de rechercher sa définition.
-     **Claviers prédictifs (en mode supervisé uniquement)** : autorise l’utilisation de claviers prédictifs qui suggèrent des mots que l’utilisateur pourrait vouloir utiliser.
-     **Correction automatique (en mode supervisé uniquement)** : permet à l’appareil de corriger automatiquement les mots mal orthographiés.
-     **Vérification orthographique du clavier (mode supervisé uniquement)** : active l’outil de vérification orthographique de l’appareil.
-     **Raccourcis clavier (mode supervisé uniquement)** : permet d’utiliser les raccourcis clavier.
-     **Détection du poignet pour une Apple Watch appairée** : quand elle est activée, l’Apple Watch n’affiche pas de notification si elle n’est pas portée.
- **Exiger un mot de passe associé pour les demandes AirPlay sortantes** : nécessite un mot de passe de jumelage lorsque l’utilisateur a recours à AirPlay pour diffuser le contenu vers d’autres appareils Apple.
- **Modification de compte (en mode supervisé uniquement)** : autorisez l’utilisateur à modifier les paramètres de compte tels que les configurations des e-mails.
- **Appariement Apple Watch (mode supervisé uniquement)** : autorise l’appareil à s’associer avec une Apple Watch.
- **Modification Bluetooth (mode supervisé uniquement)** : empêche l’utilisateur final de modifier les paramètres Bluetooth sur l’appareil.
- **Observation de l’écran à distance avec l’application Classroom (mode supervisé uniquement)** : autorisez ou bloquez l’application Classroom pour l’observation de l’écran sur des appareils distants.
- **Activation des restrictions dans les paramètres de l’appareil (appareils supervisés uniquement)** : autorisez l’utilisateur à configurer les restrictions d'appareil (contrôle parental) sur l’appareil.
- **Utiliser la réinitialisation de tous les paramètres et du contenu sur l’appareil (mode supervisé uniquement)** : autorisez l’utilisateur à utiliser l’option de réinitialisation de tout le contenu et de tous les paramètres sur l’appareil.
- **Modification du nom de l'appareil (mode supervisé uniquement)** : autorise l’utilisateur à modifier le nom de l’appareil.
- **Modification des paramètres d’envoi de diagnostics (mode supervisé uniquement)** : autorisez ou bloquez l’envoi de données de diagnostics de l’appareil à Apple.
- **Appariement d’hôtes pour contrôler les appareils avec lesquels un appareil iOS peut s’apparier (mode supervisé uniquement)** : autorisez l’appariement d’hôtes à permettre à l’administrateur de déterminer les appareils avec lesquels un appareil iOS peut s’apparier.
- **Modification des paramètres de notification (mode supervisé uniquement)** : autorisez l’utilisateur à modifier les paramètres de notification de l'appareil.
- **Modification du mot de passe (mode supervisé uniquement)** : autorisez l’ajout, la suppression ou la modification du mot de passe de l’appareil.
- **Modification du fond d’écran (mode supervisé uniquement)** : autorisez l’utilisateur à modifier le fond d’écran de l’appareil.
- **Modification des paramètres d’approbation d’application d’entreprise (mode supervisé uniquement)** : permet à l’utilisateur de sélectionner les applications approuvées qui n’ont pas été téléchargées à partir de la boutique d’applications.
- **Installation d’applications à partir de l’App Store (mode supervisé uniquement)** : autoriser l’appareil à accéder à l’App Store et installer des applications.
- **Modifications aux paramètres de l’application Find My Friends (mode supervisé uniquement)** : autorisez l’utilisateur à modifier les paramètres de l’application Find My Friends.
- **iBooks Store (en mode supervisé uniquement)** : autorise l’utilisateur à parcourir et à acheter des livres depuis l’IBooks Store.
- **Application Messages sur l’appareil (mode supervisé uniquement)** : autorisez l’utilisation de l’application Messages pour envoyer et lire des messages texte.
- **Podcasts (mode supervisé uniquement)** : autorisez l’utilisation de l’application Podcasts.
- **Service Music (mode supervisé uniquement)** : autorisez l’utilisation de l’application Apple Music.
- **Service iTunes Radio (mode supervisé uniquement)** : autorisez l’utilisation de l’application de iTunes Radio.
- **Apple News (mode supervisé uniquement)** : autorisez l’utilisation de l’application Apple News.
- **Modifications au profil de configuration** : autoriser l’utilisateur à installer des profils de configuration.

## <a name="password"></a>Mot de passe
-     **Mot de passe requis** : demande à l’utilisateur final d’entrer un mot de passe pour accéder à l’appareil.
-     **Mots de passe simples** : autorise des mots de passe simples, comme 0000 et 1234.
-     **Type de mot de passe requis** : spécifiez le type de mot de passe requis, par exemple une valeur numérique uniquement, ou alphanumérique.
-     **Nombre de caractères non alphanumériques dans le mot de passe** : spécifie le nombre de caractères de symbole (comme **#** ou **@**) devant être inclus dans le mot de passe.
-     **Longueur minimale du mot de passe** : spécifie le nombre minimal de caractères à inclure dans le mot de passe.
-     **Nombre d'échecs de connexion avant réinitialisation de l'appareil** : spécifie le nombre de tentatives de connexion ayant échoué que le paramètre système autorise avant d’effacer le contenu de l’appareil.
-     **Nombre maximal de minutes après verrouillage de l’écran avant de demander un mot de passe**<sup>1</sup> : spécifiez la durée pendant laquelle l’appareil peut rester inactif avant que l’utilisateur doive entrer à nouveau son mot de passe.
-     **Nombre maximal de minutes d’inactivité avant verrouillage de l’écran**<sup>1</sup> : spécifiez le nombre de minutes avant que l’écran de l’appareil s’éteigne.
-     **Expiration du mot de passe (jours)** : spécifie le nombre de jours avant que l’utilisateur ne doive modifier le mot de passe de l’appareil.
-     **Empêcher la réutilisation des mots de passe précédents** : spécifiez le nombre de mots de passe précédemment utilisés conservés par l’appareil.
-     **Déverrouillage par empreinte digitale** : autorisez l’utilisation d’une empreinte digitale pour déverrouiller les appareils compatibles.

<sup>1</sup> Lorsque vous configurez les paramètres **Nombre maximal de minutes d'inactivité avant le verrouillage de l'appareil** et **Nombre maximal de minutes entre le verrouillage de l'écran et la demande du mot de passe**, ceux-ci sont appliqués de manière séquentielle. Par exemple, si vous affectez aux deux paramètres la valeur **5** minutes, l'écran s'éteint automatiquement après 5 minutes, et l'appareil se verrouille après 5 minutes de plus. Toutefois, si l'utilisateur désactive manuellement l'écran, le second paramètre est immédiatement appliqué. Dans le même exemple, une fois que l'utilisateur a désactivé l'écran, l'appareil se verrouille 5 minutes plus tard.

## <a name="app-store-doc-viewing-gaming"></a>App Store, affichage de document, jeux


-   **App Store (mode supervisé uniquement)** : bloquez l’accès à l’App Store sur les appareils supervisés.
-     **Mot de passe pour accéder à l'App Store** : oblige l’utilisateur à saisir un mot de passe pour pouvoir visiter l’App Store.
-     **Achats dans l'application** : autoriser les achats depuis une application en cours d’exécution.
-     **Téléchargements d’application automatiques (mode supervisé uniquement)** -
-     **Contenu explicite dans les musiques, podcasts et actualités sur iTunes (mode supervisé uniquement)** : autorisez l’appareil à accéder au contenu adulte à partir de la boutique.
-     **Télécharger du contenu de l'iBook Store indiqué comme étant de la « Littérature érotique »** : autorisez l’utilisateur à télécharger des livres de la catégorie « Littérature érotique ».
-     **Affichage de documents d’entreprise dans les applications non gérées** : autorisez l’affichage des documents d’entreprise dans n’importe quelle application.<br>**Exemple** : Vous voulez empêcher les utilisateurs d’enregistrer des fichiers de OneDrive dans Dropbox. Attribuez la valeur Non à ce paramètre. Une fois que l’appareil a reçu la stratégie (par exemple, après un redémarrage), il cesse d’autoriser l’enregistrement.
-     **Affichage des documents autres que ceux d’entreprise dans les applications d’entreprise** : autorisez l’affichage de tous les documents dans les applications d’entreprise gérées.
-     **Traiter AirDrop comme une destination non gérée** : empêche les applications gérées de pouvoir envoyer des données via AirDrop. AirDrop.
-     **Ajout d’amis Game Center (mode supervisé uniquement)** : autorisez l’utilisateur à ajouter des amis dans Game Center.
-     **Game Center (mode supervisé uniquement)** : bloquez ou activez l’utilisation de l’application Game Center.
-     **Jeux multijoueur (en mode supervisé uniquement)** autorisez l’utilisateur à jouer à des jeux multijoueur sur l’appareil.
-     **Plage de classifications** : choisissez la plage de classifications pour laquelle vous souhaitez configurer les téléchargements autorisés, puis cliquez sur les évaluations autorisées pour **Films** et **Émissions TV**.
-     **Applications** : choisissez la catégorie d’âge autorisée pour les applications que les utilisateurs pourront télécharger, ou choisissez **Autoriser toutes les applications**.

## <a name="restricted-apps"></a>Applications restreintes

Dans la liste des applications restreintes, vous pouvez configurer une des listes suivantes :

Une liste **Applications interdites** : répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.
Une liste **Applications approuvées** : répertorie les applications que les utilisateurs sont autorisés à installer. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.

Pour configurer la liste, cliquez sur **Ajouter**, puis spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Comment spécifier l’URL vers une application dans l’App Store

Pour insérer une URL d’application dans la liste des applications, utilisez le format suivant :

À l’aide d’un moteur de recherche, recherchez l’application à utiliser dans l’App Store iTunes, puis ouvrez la page de l’application.
Copiez l’URL de la page et utilisez-la en tant qu’adresse permettant de configurer la liste des applications autorisées ou interdites, ou une application à exécuter en mode plein écran.
Les profils d'appareil qui contiennent des paramètres d’applications restreintes doivent être déployés sur des groupes d’utilisateurs.

Exemple : rechercher Microsoft Word pour iPad. L’URL que vous utilisez est la suivante : https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Vous pouvez également utiliser le logiciel iTunes pour rechercher l'application, puis la commande **Copier le lien** pour obtenir l'URL de l'application.



### <a name="additional-options"></a>Options supplémentaires

Vous pouvez également cliquer sur **Importer** pour remplir la liste à partir d’un fichier csv au format <*URL de l’application*>, <*Nom de l’application*>, <*Développeur de l’application*>, ou cliquer sur **Exporter** pour créer un fichier csv contenant le contenu de la liste des applications restreintes dans le même format.

## <a name="show-or-hide-apps"></a>Afficher ou masquer des applications

Dans la liste des applications affichées ou masquées, vous pouvez configurer une des listes suivantes (nécessite des appareils supervisés tournant sous iOS 9.3 ou version ultérieure).

Une liste **Applications masquées** : spécifier une liste d’applications à masquer aux utilisateurs. Les utilisateurs ne peuvent pas afficher ou lancer ces applications.
Une liste **Applications visibles** : spécifier une liste d’applications que les utilisateurs peuvent afficher et lancer. Aucune autre application ne peut être affichée ou lancée.

Pour configurer la liste, cliquez sur **Ajouter**, puis spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Comment spécifier l’URL vers une application dans l’App Store

Pour insérer une URL d’application dans la liste des applications, utilisez le format suivant :

À l’aide d’un moteur de recherche, recherchez l’application à utiliser dans l’App Store iTunes, puis ouvrez la page de l’application.
Copiez l’URL de la page et utilisez-la en tant qu’adresse permettant de configurer la liste des applications autorisées ou interdites, ou une application à exécuter en mode plein écran.

Exemple : rechercher Microsoft Word pour iPad. L’URL que vous utilisez est la suivante : https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> Vous pouvez également utiliser le logiciel iTunes pour rechercher l'application, puis la commande **Copier le lien** pour obtenir l'URL de l'application.

### <a name="additional-options"></a>Options supplémentaires

Vous pouvez également cliquer sur **Importer** pour remplir la liste à partir d’un fichier csv au format <*URL de l’application*>, <*Nom de l’application*>, <*Développeur de l’application*>, ou cliquer sur **Exporter** pour créer un fichier csv contenant le contenu de la liste des applications affichées ou masquées dans le même format.

### <a name="app-information-for-built-in-ios-apps"></a>Informations sur les applications iOS intégrées
Utilisez les informations de cette liste pour identifier le nom, l’éditeur et l’ID de lot des applications iOS intégrées que vous pouvez afficher ou masquer. Si vous souhaitez afficher ou masquer toutes les applications de la liste, vous pouvez copier les données ci-dessous dans un fichier texte avec l’extension **.csv**, puis utiliser l’option **Importer** pour importer toutes les applications simultanément.


    App Store,Apple,com.apple.AppStore
    Calculator,Apple,com.apple.calculator
    Calendar,Apple,com.apple.mobilecal
    Camera,Apple,com.apple.camera
    Clock,Apple,com.apple.mobiletimer
    Compass,Apple,com.apple.compass
    Contacts,Apple,com.apple.MobileAddressBook
    FaceTime,Apple,com.apple.facetime
    Find Friends,Apple,com.apple.mobileme.fmf1
    Find iPhone,Apple,com.apple.mobileme.fmip1
    Game Center,Apple,com.apple.gamecenter
    GarageBand,Apple,com.apple.mobilegarageband
    Health,Apple,com.apple.Health
    iBooks,Apple,com.apple.iBooks
    iTunes Store,Apple,com.apple.MobileStore
    iTunes U,Apple,com.apple.itunesu
    Keynote,Apple,com.apple.Keynote
    Mail,Apple,com.apple.mobilemail
    Maps,Apple,com.apple.Maps
    Messages,Apple,com.apple.MobileSMS
    Music,Apple,com.apple.Music
    News,Apple,com.apple.news
    Notes,Apple,com.apple.mobilenotes
    Numbers,Apple,com.apple.Numbers
    Pages,Apple,com.apple.Pages
    Photo Booth,Apple,com.apple.Photo-Booth
    Photos,Apple,com.apple.mobileslideshow
    Podcasts,Apple,com.apple.podcasts
    Reminders,Apple,com.apple.reminders
    Safari,Apple,com.apple.mobilesafari
    Settings,Apple,com.apple.Preferences
    Stocks,Apple,com.apple.stocks
    Tips,Apple,com.apple.tips
    Videos,Apple,com.apple.videos
    VoiceMemos,Apple,com.apple.VoiceMemos
    Wallet,Apple,com.apple.Passbook
    Watch,Apple,com.apple.Bridge
    Weather,Apple,com.apple.weather





## <a name="cellular"></a>Cellulaire
-     **Itinérance des données** : autoriser l’itinérance des données quand l’appareil se trouve sur un réseau cellulaire.
-     **Récupération en arrière-plan globale en cas d'itinérance** : autoriser l’appareil à récupérer des données comme les courriers électroniques lorsqu’il est en mode itinérance sur un réseau cellulaire.
-     **Numérotation vocale** : autoriser l’utilisation de la fonctionnalité de numérotation vocale sur l’appareil.
-     **Itinérance vocale** : autoriser l’itinérance vocale quand l’appareil se trouve sur un réseau cellulaire.
-     **Modifications apportées aux paramètres d’utilisation des données cellulaires des applications (mode supervisé uniquement)** : autorisez l’utilisateur à contrôler les applications qui sont autorisées à utiliser des données cellulaires.

## <a name="cloud-and-storage"></a>Cloud et stockage
-     **Sauvegarder sur iCloud** : autorise l’utilisateur à sauvegarder les données de l’appareil dans iCloud.
-     **Synchronisation de documents sur iCloud (en mode supervisé uniquement)** : autorisez la synchronisation des documents et des clés-valeurs sur votre espace de stockage iCloud.
-     **Synchronisation du flux de photos sur iCloud** : permet aux utilisateurs d’activer **Mon flux de photos** sur leur appareil afin de synchroniser les photos avec iCloud et de les mettre à la disposition de tous les appareils des utilisateurs.
-     **Sauvegarde chiffrée** : exiger le chiffrement des sauvegardes d’appareil.
-     **Photothèque iCloud** : si définie sur **Non**, désactive l’utilisation de la photothèque iCloud qui permet aux utilisateurs de stocker des photos et des vidéos dans le cloud.    Toutes les photos qui ne sont pas entièrement téléchargées de la Photothèque iCloud sur l'appareil seront supprimées de l'appareil si cette valeur est définie sur **Non**.
-     **Applications gérées synchronisées avec le cloud** : autorisez les applications que vous gérez avec Intune à synchroniser les données sur le compte iCloud de l’utilisateur.
-     **Flux de photos partagé** : choisissez **Non** pour désactiver le **partage de photos iCloud** sur l'appareil.
-     **Continuation d’activité** : autorise l’utilisateur à reprendre le travail qu’il a commencé sur un appareil iOS, sur un autre appareil iOS ou Mac OS X (transfert).

## <a name="kiosk"></a>Kiosque
-     **Verrou d’activation** : active le verrou d’activation sur des appareils iOS supervisés.
-     **Application s’exécutant en mode kiosque** : choisissez **Application gérée** pour sélectionner une application que vous avez ajoutée à Intune, ou **Application de boutique** pour spécifier l’URL d’une application dans la boutique. Aucune autre application ne pourra s'exécuter sur l'appareil. Pour obtenir de l’aide, consultez la section « Comment spécifier des URL de magasins d’applications » de la présente rubrique.
-     **Assistance tactile** : active ou désactive le paramètre d’accessibilité **Assistance tactile**, qui permet à l’utilisateur d’effectuer des mouvements à l’écran pouvant être difficiles à effectuer.
-     **Inverser les couleurs** - Active ou désactive le paramètre d’accessibilité Inverser les couleurs qui ajuste l’affichage pour aider les utilisateurs ayant des troubles visuels.
-     **Audio mono** : active ou désactive le paramètre d’accessibilité Audio mono.
-     **VoiceOver** : activez ou désactivez le paramètre d’accessibilité **VoiceOver**, qui lit à haute voix le texte affiché à l’appareil.
-     **Zoom** : active ou désactive le paramètre d’accessibilité **Zoom**, qui vous permet d’utiliser la fonctionnalité tactile pour agrandir l’affichage de l’appareil.
-     **Verrouillage automatique** : active ou désactive le verrouillage automatique de l’appareil.
-     **Fonction de sonnerie** - Active ou désactive le commutateur de sonnerie (désactivation du son) sur l’appareil.
-     **Rotation d’écran** : active ou désactive la modification de l’orientation de l’écran lorsque l’utilisateur fait pivoter l’appareil.
-     **Bouton de mise en veille de l’écran** : active ou désactive le bouton Veille/sortie de veille de l’écran sur l’appareil.
-     **Tactile** : active ou désactive l’écran tactile sur l’appareil.
-     **Boutons de volume** - Active ou désactive l’utilisation des boutons de volume sur l’appareil.
-     **Assistance tactile** : active ou désactive les réglages d’assistance tactile, qui permettent à l’utilisateur de régler la fonction d’assistance tactile.
-     **Réglages de couleurs inversées** : active ou désactive les réglages de couleurs inversées, qui permettent à l’utilisateur d’ajuster la fonction de couleurs inversées.
-     **Lire le texte sélectionné** : active ou désactive les paramètres d’accessibilité Sélection Speak, qui peuvent lire à haute voix le texte que l’utilisateur sélectionne.
-     **Contrôle VoiceOver** : active ou désactive les réglages VoiceOver qui vous permettent de régler la fonction VoiceOver (par exemple, la vitesse de lecture à haute voix du texte affiché à l’écran).
-     **Contrôle du zoom** : active ou désactive les réglages du zoom qui vous permettent de régler la fonction de zoom.

>[!NOTE]
> Avant de pouvoir configurer un appareil iOS pour le mode plein écran, vous devez utiliser l’outil Apple Configurator ou le Programme d’inscription des appareils Apple pour mettre l’appareil en mode supervisé. Pour en savoir plus sur l’outil Apple Configurator, consultez votre documentation Apple.
>Si l’application iOS que vous spécifiez est installée après le déploiement de la stratégie de configuration, l’appareil ne bascule en mode plein écran qu’après son redémarrage.

## <a name="safari"></a>Safari
-     **Supervisé (en mode supervisé uniquement)** : spécifier si le navigateur Safari peut être utilisé sur l’appareil.
-     **Remplissage automatique** : autorise l’utilisateur à modifier les paramètres de saisie semi-automatique dans le navigateur.
-     **Cookies** : autorise le navigateur à utiliser des cookies.
-     **JavaScript** : autoriser l’exécution des scripts Java dans le navigateur.
-     **Avertissement de fraude** : autoriser l’affichage d’avertissements antifraude dans le navigateur.
-     **Fenêtres publicitaires** : activer ou désactiver le bloqueur de fenêtres publicitaires du navigateur.

