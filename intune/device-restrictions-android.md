---
title: "Paramètres de restriction d’appareil Intune pour Android"
titleSuffix: Intune Azure preview
description: "Version préliminaire d&quot;Intune Azure : découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Android."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3627b28b60908c225ce1797968123ce854a70a8b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Android et Samsung KNOX Standard dans Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="general"></a>Général

|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Appareil photo**|Autorise l’utilisation de l’appareil photo de l’appareil.|Oui|Oui|
|**Copier et coller**|Autorise les fonctions Copier et Coller sur l’appareil.|Non|Oui|
|**Partage du Presse-papiers entre applications**|Autorise l’utilisation du Presse-papiers pour copier-coller entre les applications.|Non|Oui|
|**Envoi des données de diagnostic**|Empêche l’utilisateur d’envoyer des données de diagnostic depuis l’appareil.|Non|Oui|
|**Réinitialisation aux paramètres d’usine**|Autorise l’utilisateur à rétablir les paramètres d’usine sur l’appareil.|Non|Oui|
|**Géolocalisation**|Permet à l’appareil d’utiliser les informations de localisation (Samsung KNOX Standard uniquement).|Non|Oui|
|**Mise hors tension**|Autorise l’utilisateur à mettre l’appareil hors tension.<br>Si ce paramètre est désactivé, le paramètre **Nombre d'échecs de connexion avant réinitialisation de l'appareil** pour les appareils Samsung KNOX Standard ne fonctionne pas.|Non|Oui|
|**Capture d'écran**|Autorise l’utilisateur à capturer le contenu de l’écran comme image.|Non|Oui|
|**Assistant vocal**|Autorise l’utilisation du logiciel Assistant vocal sur l’appareil.|Non|Oui|
|**YouTube**|Autorise l’utilisation de l’application YouTube sur l’appareil.|Non|Oui|
|**Appareils partagés**|Configurer un appareil Samsung KNOX standard géré en tant qu’appareil partagé. Dans ce mode, les utilisateurs finaux peuvent se connecter et se déconnecter de l’appareil avec leurs informations d’identification Azure AD, et l’appareil est géré de façon centralisée qu’il soit en cours d’utilisation ou non.<br>Quand les utilisateurs finaux se connectent, ils ont accès aux applications et les éventuelles stratégies sont appliquées à ces applications. Quand les utilisateurs se déconnectent, toutes les données d’application sont effacées.|Non|Oui|

## <a name="password"></a>Mot de passe

|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Mot de passe**|Demande à l’utilisateur final de saisir un mot de passe pour pouvoir accéder à l’appareil.|Oui|Oui|
|**Longueur minimale du mot de passe**|Saisissez la longueur minimale du mot de passe qu’un utilisateur doit configurer (entre 4 et 16 caractères).|Oui|Oui|
|**Nombre maximal de minutes d’inactivité avant le verrouillage de l’appareil**|Spécifie le nombre de minutes d’inactivité avant verrouillage automatique de l’appareil.|Oui|Oui|
|**Nombre d’échecs de connexion avant réinitialisation de l’appareil**|Spécifie le nombre d’échecs de connexion à autoriser avant réinitialisation de l’appareil.|Oui|Oui|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant de devoir modifier le mot de passe de l’appareil.|Oui|Oui|
|**Type de mot de passe requis**|Spécifie le niveau de complexité du mot de passe exigé et si les appareils biométriques peuvent être utilisés. Choisissez parmi :<br><br>    -     **Paramètre par défaut de l’appareil**<br>-     **Sécurité biométrique faible**<br>    -     **Au moins numérique**<br>    -     **Chiffres complexes** (les chiffres répétés ou consécutifs tels que « 1111 » ou « 1234 » ne sont pas autorisés)<sup>1</sup><br>    -     **Au moins alphabétique**<br>    -     **Au moins alphanumérique**<br>    -     **Au moins alphanumérique avec des symboles**|Oui|Oui|
|**Empêcher la réutilisation des mots de passe précédents**|Empêche l’utilisateur final de créer un mot de passe qu’il a déjà utilisé.|Oui|Oui|
|**Déverrouillage par empreinte digitale**|Permet l’utilisation d’une empreinte digitale pour déverrouiller les appareils pris en charge.|Non|Oui|
|**Smart Lock et autres agents de confiance**|Vous permet de contrôler la fonctionnalité Smart Lock sur les appareils Android compatibles (Samsung KNOX Standard 5.0 et plus). Cette fonctionnalité du téléphone, parfois appelée agent de confiance, vous permet de désactiver ou de contourner le mot de passe de l’écran de verrouillage de l’appareil si celui-ci se trouve dans un emplacement fiable (par exemple, quand il est connecté à un appareil Bluetooth spécifique ou qu’il se trouve à proximité d’une balise NFC). Vous pouvez utiliser ce paramètre pour empêcher les utilisateurs de configurer Smart Lock.|Oui (versions 5.0 et plus)|Oui|
|**Chiffrement**|Exige que les fichiers soient chiffrés sur le périphérique.|Oui|Oui|

<sup>1</sup>avant d’affecter ce paramètre à des appareils, assurez-vous que l’application Portail d’entreprise a été mise à jour vers la dernière version sur les appareils ciblés.

Si vous configurez le paramètre **Chiffres complexes** et l’affectez à un appareil qui exécute une version antérieure à la version 5.0 d’Android, le comportement suivant s’applique.
- Si l’application Portail d’entreprise exécute une version antérieure à 1704, aucune stratégie de code PIN ne sera appliquée à l’appareil et une erreur s’affichera dans le portail Intune.
- Si l’application Portail d’entreprise a été mise à jour vers la version 1704, un simple code PIN s’appliquera. Les versions d’Android antérieures à 5.0 ne gèrent pas ce paramètre. Aucune erreur ne s’affiche dans le portail Intune.


## <a name="google-play-store"></a>Google Play Store

|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Google Play Store**|Autorise l’utilisateur à accéder à l’application Google Play Store sur l’appareil.|Non|Oui|

## <a name="restricted-apps"></a>Applications restreintes

Dans la liste des applications restreintes, vous pouvez configurer une des listes suivantes :

Une liste **Applications interdites** : répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.
Une liste **Applications approuvées** : répertorie les applications que les utilisateurs sont autorisés à installer. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.
Les profils d’appareil qui contiennent des paramètres d’applications restreintes doivent être attribués à des groupes d’utilisateurs.

Pour configurer la liste, cliquez sur **Ajouter**, puis spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Comment spécifier l’URL vers une application dans l’App Store

Pour spécifier une URL d’application dans la liste des applications conformes et non conformes, procédez comme suit :

Dans la [section Applications de Google Play](https://play.google.com/store/apps), recherchez l’application à utiliser.

Ouvrez la page d’installation de l’application, puis copiez l’URL dans le Presse-papiers. Vous pouvez maintenant utiliser cette URL dans la liste des applications conformes ou non conformes.

Exemple : Recherchez Microsoft Office Mobile dans Google Play. L’URL que vous utilisez est **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Options supplémentaires

Vous pouvez également cliquer sur **Importer** pour remplir la liste à partir d’un fichier csv au format <*URL de l’application*>, <*Nom de l’application*>, <*Développeur de l’application*>, ou cliquer sur **Exporter** pour créer un fichier csv contenant le contenu de la liste des applications restreintes dans le même format.        

## <a name="browser"></a>Navigateur
|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Navigateur web**|Spécifie si le navigateur web par défaut de l’appareil peut être utilisé.|Non|Oui|
|**Remplissage automatique**|Autorise l’utilisation de la fonction de remplissage automatique du navigateur web.|Non|Oui|
|**Cookies**|Autorise le navigateur web de l’appareil à utiliser des cookies.|Non|Oui|
|**Javascript**|Permet au navigateur web de l’appareil d’exécuter des scripts Java.|Non|Oui|
|**Fenêtres contextuelles**|Autoriser l’utilisation du bloqueur de fenêtres publicitaires dans le navigateur.|Non|Oui|

## <a name="cloud-and-storage"></a>Cloud et stockage
|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Sauvegarde Google**|Autorise l’utilisation de la sauvegarde de Google.|Non|Oui|
|**Synchronisation automatique de compte Google**|Autorise la synchronisation automatique des paramètres du compte Google.|Non|Oui|
|**Stockage amovible**|Autorise l’appareil à utiliser du stockage amovible, comme une carte SD.|Non|Oui|
|**Chiffrement des cartes de stockage**|Spécifie si la carte de stockage de l’appareil doit être chiffrée.|Non|Oui|

## <a name="cellular-and-connectivity"></a>Cellulaire et connectivité
|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Itinérance des données**|Autorise l’itinérance des données lorsque l’appareil se trouve sur un réseau de téléphonie mobile.|Non|Oui|
|**Messagerie SMS et MMS**|Autorise l’utilisation de la messagerie SMS et MMS sur l’appareil.|Non|Oui|
|**Numérotation vocale**|Active ou désactive la fonctionnalité de numérotation vocale sur l’appareil.|Non|Oui|
|**Itinérance vocale**|Autorise l’itinérance vocale quand l’appareil se trouve sur un réseau de téléphonie mobile.|Non|Oui|
|**BlueTooth**|Autorise l’utilisation de la fonction Bluetooth sur l’appareil.|Non|Oui|
|**NFC**|Autorise les opérations qui utilisent la communication en champ proche si l’appareil la prend en charge.|Non|Oui|
|**Wi-Fi**|Autorise l’utilisation des fonctionnalités Wi-Fi de l’appareil.|Non|Oui|
|**Connexion Wi-Fi**|Autorise l’utilisation de la connexion Wi-Fi sur l’appareil.|Non|Oui|

## <a name="kiosk"></a>Kiosque
|||||
|-|-|-|-|
|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX Standard|
|**Sélectionner une application gérée**|Recherchez, puis choisissez une application gérée qui peut s’exécuter lorsque l’appareil est en mode plein écran (les applications spécifiées sous la forme d’un lien vers le magasin ne sont pas prises en charge actuellement). Aucune autre application ne pourra s'exécuter sur l'appareil.|Non|Oui|
|**Bouton de veille de l’écran**|Active ou désactive le bouton Veille/sortie de veille de l'écran sur l'appareil.|Non|Oui|
|**Boutons du volume**|Active ou désactive l'utilisation des boutons de volume sur l'appareil.|Non|Oui|

