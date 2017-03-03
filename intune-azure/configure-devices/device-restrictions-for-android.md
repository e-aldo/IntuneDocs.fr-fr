---
title: "Paramètres de restriction d’appareils Intune pour Android | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: a003b2b16e05c2d071bb7dbaaf564e24d0cf5823
ms.lasthandoff: 02/16/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Android et Samsung KNOX Standard dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Général
-     **Appareil photo** - Autorise l’utilisation de l’appareil photo de l’appareil.
-     **Copier et coller** - Autorise les fonctions Copier et Coller sur l’appareil.
-     **Partage du Presse-papiers entre applications** - Autorise l’utilisation du Presse-papiers pour copier-coller entre les applications (Samsung KNOX Standard uniquement).
-     **Envoi des données de diagnostic** - Empêche l’utilisateur d’envoyer des données de diagnostic depuis l’appareil.    
-     **Réinitialisation aux paramètres d’usine** - Autorise l’utilisateur à rétablir les paramètres d’usine sur l’appareil.
-     **Géolocalisation** - Permet à l’appareil d’utiliser les informations de localisation (Samsung KNOX Standard uniquement).
-     **Mise hors tension** - Autorise l’utilisateur à mettre l’appareil hors tension.<br>Si ce paramètre est désactivé, le paramètre **Nombre d'échecs de connexion avant réinitialisation de l'appareil** pour les appareils Samsung KNOX Standard ne fonctionne pas.
-     **Capture d'écran** - Autorise l’utilisateur à capturer le contenu de l’écran comme image.
-     **Assistant vocal** - Autorise l’utilisation du logiciel Assistant vocal sur l’appareil (Samsung KNOX Standard uniquement).
-     **YouTube** - Autorise l’utilisation de l’application YouTube sur l’appareil (Samsung KNOX Standard uniquement).

## <a name="password"></a>Mot de passe
-     **Mot de passe requis** - Oblige l’utilisateur final à saisir un mot de passe pour accéder à l’appareil.
-     **Longueur minimale du mot de passe** - Entrez la longueur minimale du mot de passe qu’un utilisateur doit configurer (entre 4 et 16 caractères).
-     **Nombre maximal de minutes d'inactivité avant le verrouillage de l'appareil** - Spécifie le nombre de minutes d’inactivité avant verrouillage automatique de l’appareil.
-     **Nombre d'échecs de connexion avant réinitialisation de l'appareil** - Spécifie le nombre d’échecs de connexion à autoriser avant réinitialisation de l’appareil.
-     **Expiration du mot de passe (jours)** - Spécifie le nombre de jours avant que l’utilisateur ne doive modifier le mot de passe de l’appareil.
-     **Type de mot de passe requis** - Spécifie le niveau de complexité du mot de passe exigé et si les appareils biométriques peuvent être utilisés.
-     **Empêcher la réutilisation des mots de passe précédents** - Empêche l’utilisateur final de créer un mot de passe qu’il a déjà utilisé.
-     **Déverrouillage par empreinte digitale** - Permet l’utilisation d’une empreinte digitale pour déverrouiller les appareils pris en charge.
-     **Smart Lock et autres agents de confiance** - Vous permet de contrôler la fonctionnalité Smart Lock sur les appareils Android compatibles (Samsung KNOX Standard 5.0 et modèles ultérieurs). Cette fonctionnalité du téléphone, parfois appelée agent de confiance, vous permet de désactiver ou de contourner le mot de passe de l’écran de verrouillage de l’appareil si celui-ci se trouve dans un emplacement fiable (par exemple, quand il est connecté à un appareil Bluetooth spécifique ou qu’il se trouve à proximité d’une balise NFC). Vous pouvez utiliser ce paramètre pour empêcher les utilisateurs de configurer Smart Lock.
-     **Chiffrement** - Exige que les fichiers soient chiffrés sur l’appareil.

## <a name="google-play-store"></a>Google Play Store

-     **Google Play Store** - Permet à l’utilisateur d’accéder à Google Play Store sur l’appareil (Samsung KNOX Standard uniquement).

## <a name="restricted-apps"></a>Applications restreintes

Dans la liste des applications restreintes, vous pouvez configurer une des listes suivantes :

Une liste **Applications interdites** : répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.
Une liste **Applications approuvées** : répertorie les applications que les utilisateurs sont autorisés à installer. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.
Les profils d'appareil qui contiennent des paramètres d’applications restreintes doivent être déployés sur des groupes d’utilisateurs.

Pour configurer la liste, cliquez sur **Ajouter**, puis spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Comment spécifier l’URL vers une application dans l’App Store

Pour spécifier une URL d’application dans la liste des applications conformes et non conformes, procédez comme suit :

Dans la [section Applications de Google Play](https://play.google.com/store/apps), recherchez l’application à utiliser.

Ouvrez la page d’installation de l’application, puis copiez l’URL dans le Presse-papiers. Vous pouvez maintenant utiliser cette URL dans la liste des applications conformes ou non conformes.

Exemple : Recherchez Microsoft Office Mobile dans Google Play. L’URL que vous utilisez est **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Options supplémentaires

Vous pouvez également cliquer sur **Importer** pour remplir la liste à partir d’un fichier csv au format <*URL de l’application*>, <*Nom de l’application*>, <*Développeur de l’application*>, ou cliquer sur **Exporter** pour créer un fichier csv contenant le contenu de la liste des applications restreintes dans le même format.        

## <a name="browser"></a>Navigateur
-     **Navigateur web** - Spécifie si le navigateur web par défaut de l’appareil peut être utilisé.
-     **Remplissage automatique** - Autorise l’utilisation de la fonction de remplissage automatique du navigateur web.
-     **Cookies** - Autorise le navigateur web de l’appareil à utiliser des cookies.
-     **JavaScript** - Permet au navigateur web de l’appareil d’exécuter des scripts Java.
-     **Fenêtres publicitaires** - Autorise l’utilisation du bloqueur de fenêtres publicitaires dans le navigateur.

## <a name="cloud-and-storage"></a>Cloud et stockage
-     **Sauvegarde Google** - Autorise l’utilisation de la sauvegarde de Google.
-     **Synchronisation automatique de compte Google** - Autorise la synchronisation automatique des paramètres du compte Google.
-     **Stockage amovible** - Permet à l’appareil d’utiliser un stockage amovible, par exemple une carte SD (Samsung KNOX Standard uniquement).
-     **Chiffrement des cartes de stockage** - Spécifie si la carte de stockage de l’appareil doit être chiffrée.

## <a name="cellular-and-connectivity"></a>Cellulaire et connectivité
-     **Itinérance des données** - Autorise l’itinérance des données quand l’appareil se trouve sur un réseau cellulaire (Samsung KNOX Standard uniquement).
-     **Messagerie SMS/MMS** - Permet l’utilisation de la messagerie SMS et MMS sur l’appareil (Samsung KNOX Standard uniquement).
-     **Numérotation vocale** - Active ou désactive la fonctionnalité de numérotation vocale sur l’appareil (Samsung KNOX Standard uniquement).
-     **Itinérance vocale** - Autorise l’itinérance vocale quand l’appareil se trouve sur un réseau cellulaire (Samsung KNOX Standard uniquement).
-     **Bluetooth** - Autorise l’utilisation de la fonctionnalité Bluetooth sur l’appareil (Samsung KNOX Standard uniquement).
-     **NFC** - Autorise les opérations qui utilisent la communication en champ proche si l’appareil la prend en charge (Samsung KNOX Standard uniquement).
-     **Wi-Fi** - Autorise l’utilisation des fonctionnalités Wi-Fi de l’appareil (Samsung KNOX Standard uniquement).
-     **Connexion Wi-Fi** - Permet l’utilisation de la connexion Wi-Fi sur l’appareil (Samsung KNOX Standard uniquement).

## <a name="kiosk"></a>Kiosque
-     **Sélectionner une application gérée** - Recherchez puis choisissez une application gérée qui peut s’exécuter quand l’appareil est en mode plein écran (les applications spécifiées sous la forme d’un lien vers le magasin ne sont pas prises en charge). Aucune autre application ne pourra s'exécuter sur l'appareil.
-     **Bouton de veille de l’écran** - Active ou désactive le bouton Veille/sortie de veille de l’écran sur l’appareil.
-     **Boutons de volume** - Active ou désactive l’utilisation des boutons de volume sur l’appareil.

