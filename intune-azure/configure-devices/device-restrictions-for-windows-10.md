---
title: "Paramètres de restriction d’appareils Intune pour Windows 10 | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6e0540acd5488077ae5217f8862e3bc5462ed71
ms.openlocfilehash: 422826ded029eb8f17856e47e98f5a09dc36bc08


---

# <a name="windows-10-and-later-device-restriction-settings-in-intune-azure-preview"></a>Paramètres de restriction des appareils Windows 10 et versions ultérieures dans la version préliminaire d'Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Général
-   **Capture d’écran** - Autorise l’utilisateur à capturer le contenu de l’écran d’appareil en tant qu’image. (Windows 10 Mobile uniquement)
-   **Copier et coller (mobile uniquement)** - Autorise les actions copier-coller entre les applications sur l’appareil.
-   **Inscription manuelle** - Permet à l’utilisateur de supprimer manuellement le compte d’espace de travail de l’appareil.
-   **Installation manuelle du certificat racine** -  
-   **Envoi des données de diagnostic** - Les valeurs possibles sont les suivantes :
    -       **Aucun** - Aucune donnée n’est envoyée à Microsoft
    -       **Basique** - Une quantité limitée d’informations est envoyée à Microsoft
    -       **Amélioré** - Des données de diagnostic avancées sont envoyées à Microsoft
    -       **Complète** - Envoie les mêmes données que Amélioré, ainsi que des données supplémentaires sur l'état de l’appareil
-   **Appareil photo** - Autorise ou bloque l’utilisation de l’appareil photo sur l’appareil.
-   **Stockage amovible** - Spécifie si des appareils de stockage externe comme une carte SD peuvent être utilisés avec l’appareil.
-   **Géolocalisation** - Spécifie si l’appareil peut utiliser les informations des services d’emplacement.
-   **Partage Internet** - Autorise l’utilisation du partage de connexion Internet sur l’appareil.
-   **Réinitialisation du téléphone** - Détermine si l’utilisateur peut rétablir les paramètres d’usine de son appareil.
-   **Connexion USB** - Détermine si les appareils peuvent accéder à des appareils de stockage externe par le biais d’une connexion USB.
-   **Mode antivol** - Détermine si le mode antivol Windows est activé.
-   **Notifications du centre de notifications** - Active ou désactive les notifications de centre de notifications sur l’écran de verrouillage de l’appareil (Windows 10 Mobile uniquement).
-   **Cortana** - Active ou désactive l’assistant vocal Cortana.
-   **Enregistrement vocal** - Autorise ou bloque l’utilisation de l’enregistreur vocal de l’appareil.

## <a name="password"></a>Mot de passe
-   **Mot de passe requis** - Oblige l’utilisateur final à saisir un mot de passe pour accéder à l’appareil.
-   **Type de mot de passe requis** - Spécifie si le mot de passe doit être numérique uniquement ou alphanumérique.
-   **Longueur minimale du mot de passe** - S’applique à Windows 10 Mobile uniquement.
-   **Nombre d'échecs de connexion avant réinitialisation de l'appareil** - Pour les appareils exécutant Windows 10 : si BitLocker est activé sur l’appareil, ce dernier passe en mode de récupération BitLocker après le nombre d’échecs de connexion que vous avez spécifié. Si BitLocker n’est pas activé sur l’appareil, alors ce paramètre ne s’applique pas.
Pour les appareils exécutant Windows 10 Mobile : après le nombre d’échecs de connexion que vous spécifiez, l’appareil est réinitialisé.
-   **Nombre maximal de minutes d'inactivité avant le verrouillage de l'appareil** - Spécifie la durée pendant laquelle l’appareil doit être inactif avant le verrouillage de l’écran.
-   **Expiration du mot de passe (jours)** - Spécifie la durée après laquelle le mot de passe d’un appareil doit être modifié.
-   **Empêcher la réutilisation des mots de passe précédents** - Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.
-   **Exiger un mot de passe quand l'appareil sort d'un état d'inactivité** - Spécifie que l’utilisateur doit entrer un mot de passe pour déverrouiller l’appareil (Windows 10 Mobile uniquement).
-   **Chiffrement** - Active le chiffrement sur les appareils ciblés (Windows 10 Mobile uniquement).
## <a name="app-store"></a>App Store

-   **App store (mobile uniquement)** - Active ou bloque l’utilisation de l’App Store sur les appareils Windows 10 Mobile.
## <a name="edge-browser"></a>Navigateur Edge
-   **Navigateur Microsoft Edge (mobile uniquement)** - autorise l’utilisation du navigateur web Edge sur l’appareil.
-   **SmartScreen** - Active ou désactive la fonctionnalité SmartScreen qui bloque les sites web frauduleux.
-   **Envoyer un en-tête Do Not Track** - Configure le navigateur Microsoft Edge pour envoyer des en-êtes Do Not Track aux sites web que les utilisateurs visitent.
-   **Cookies** - Permet au navigateur d’enregistrer les cookies internet sur l’appareil.
-   **JavaScript** - Autorise l’exécution de scripts, tels que JavaScript, dans le navigateur Microsoft Edge.
-   **Fenêtres publicitaires** - Bloque les fenêtres publicitaires dans le navigateur.<br>(S’applique à Windows 10 Desktop uniquement).
-   **Suggestions de recherche** - Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche.
-   **Envoyer le trafic intranet vers Internet Explorer** - Permet aux utilisateurs d’ouvrir des sites web intranet dans Internet Explorer. <br>(Windows 10 Desktop uniquement).
-   **Remplissage automatique** - Autoriser les utilisateurs à modifier les paramètres de saisie semi-automatique dans le navigateur.<br>(Windows 10 Desktop uniquement)
-   **Gestionnaire de mots de passe** - Activer ou désactiver la fonctionnalité Gestionnaire de mots de passe Microsoft Edge.
-   **Emplacement de la liste des sites en mode entreprise** - Indique où trouver la liste des sites web qui s’ouvrent en Mode entreprise. Les utilisateurs ne peuvent pas modifier cette liste.<br>(Windows 10 Desktop uniquement).
## <a name="cloud-and-storage"></a>Cloud et stockage
-   **Compte Microsoft** - Permet à l’utilisateur d’associer un compte Microsoft à l’appareil.
-   **Compte non-Microsoft** - Permet à l’utilisateur d’ajouter des comptes de messagerie à l’appareil qui ne sont pas associés à un compte Microsoft.
-   **Synchronisation des paramètres du compte Microsoft** - Permet aux paramètres d’appareil et d’application associés à un compte Microsoft de se synchroniser entre les appareils.
## <a name="cellular-and-connectivity"></a>Cellulaire et connectivité
-   **Itinérance des données** - Autorise l’itinérance entre réseaux lors de l’accès aux données.
-   **VPN sur le réseau de téléphonie mobile** - Détermine si l’appareil peut accéder aux connexions VPN quand il est connecté à un réseau cellulaire.
-   **Itinérance VPN sur le réseau de téléphonie mobile** - Détermine si l’appareil peut accéder aux connexions VPN quand il est en itinérance sur un réseau cellulaire.
-   **Bluetooth** - Contrôle si l’utilisateur peut activer et configurer la fonction Bluetooth sur l’appareil.
-   **Détectabilité de Bluetooth** - Permet à cet appareil d’être découvert par d’autres appareils Bluetooth.
-   **Publicité Bluetooth** - Permet à l’appareil de recevoir des publications via Bluetooth.
-   **NFC** - Permet à l’utilisateur d’activer et de configurer les fonctionnalités Near Field Communications sur l’appareil.
-   **Wi-Fi** - Permet à l’utilisateur d’activer et de configurer le Wi-Fi sur l’appareil (Windows 10 Mobile uniquement).
-   **Se connecter automatiquement aux points d'accès Wi-Fi** - Permet à l’appareil de se connecter automatiquement aux points d’accès Wi-Fi gratuits et d’accepter automatiquement les termes et conditions de la connexion.
-   **Configuration manuelle du Wi-Fi** - Détermine si les utilisateurs peuvent configurer leurs propres connexions Wi-Fi ou s’ils peuvent uniquement utiliser les connexions configurées par un profil Wi-Fi (Windows 10 Mobile uniquement).
## <a name="defender"></a>Defender

-   **Surveillance en temps réel** - Active la recherche en temps réel des logiciels malveillants, logiciels espions et autres logiciels indésirables.
-   **Analyse du comportement** - Permet à Defender de rechercher certains modèles connus d’activité suspecte sur les appareils.
-   **Network Inspection System (NIS)** - Le système NIS (Network Inspection System) vous aide à protéger les appareils contre les attaques réseau à l’aide de signatures de vulnérabilités connues fournies par le Microsoft Endpoint Protection Center afin de détecter et de bloquer tout trafic malveillant.
-   **Analyser tous les téléchargements** - Contrôle si Defender analyse tous les fichiers téléchargés depuis Internet.
-   **Analyser les scripts chargés dans les navigateurs web Microsoft** - Permet à Defender d’analyser les scripts utilisés dans Internet Explorer.
-   **Accès de l'utilisateur final à Defender** - Détermine si l'interface utilisateur de Windows Defender est masquée aux utilisateurs finaux.
Lorsque ce paramètre est modifié, le changement est appliqué au prochain redémarrage de l'ordinateur de l'utilisateur final.
-   **Intervalle de mise à jour des signatures (en heures)** - Spécifie l'intervalle auquel Defender vérifie les nouveaux fichiers de signatures.
-   **Surveiller l’activité des fichiers et des programmes** - Autorise Defender à surveiller l’activité des fichiers et des programmes sur des appareils.
-   **Nombre de jours avant la suppression des programmes malveillants en quarantaine** - Permet à Defender de continuer à suivre les logiciels malveillants résolus pendant un certain nombre de jours que vous spécifiez, pour vous permettre de vérifier manuellement les appareils affectés. Si vous définissez le nombre de jours du suivi sur **0**, les logiciels malveillants restent dans le dossier de quarantaine et ne sont pas automatiquement supprimés.
-   **Limite de l'utilisation du processeur pendant une analyse** - Vous permet de limiter la quantité de ressources du processeur que les analyses sont autorisées à utiliser (de **1** à **100**).
-   **Analyser les fichiers d’archive** - Permet à Defender d’analyser les fichiers archivés tels que les archives .zip ou .cab.
-   **Analyser les e-mails entrants** - Permet à Defender d’analyser les e-mails quand ils arrivent sur l’appareil.
-   **Analyser les disques amovibles lors d'une analyse complète** - Permet à Defender d'analyser les lecteurs amovibles tels que les clés USB.
-   **Analyser les lecteurs réseau mappés lors d'une analyse complète** - Permet à Defender d’analyser les fichiers sur un lecteur réseau mappé.<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.
-   **Analyser les fichiers ouverts à partir de dossiers réseau** - Permet à Defender d’analyser les fichiers sur des lecteurs réseau partagés (par exemple, les lecteurs accessibles à partir d’un chemin UNC).
Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.
-   **Protection du cloud** - Autorise ou empêche Microsoft Active Protection Service de recevoir des informations sur l’activité des logiciels malveillants en provenance des appareils que vous gérez. Ces informations serviront à améliorer le service.
-   **Demander confirmation aux utilisateurs avant l'envoi d'un échantillon** - Contrôle si les fichiers susceptibles de nécessiter une analyse plus approfondie de la part de Microsoft pour déterminer s’il s’agit de logiciels malveillants sont automatiquement envoyés à Microsoft.
-   **Heure de l'analyse rapide quotidienne** - Permet de planifier une analyse rapide exécutée tous les jours à l’heure de votre choix.
-   **Type d’analyse système à effectuer** - Vous permet de spécifier le niveau d’analyse à effectuer lorsque vous planifiez une analyse système.
## <a name="defender-exclusions"></a>Exclusions de Defender

-   **Fichiers et dossiers à exclure des analyses et de la protection en temps réel** - Ajoute un ou plusieurs fichiers et dossiers comme **C:\Chemin** ou **%ProgramFiles%\Chemin\NomFichier.exe** à la liste des exclusions. Ces fichiers et dossiers ne sont pas inclus dans les analyses en temps réel ou planifiées.
-   **Extensions de fichier à exclure des analyses et de la protection en temps réel** - Ajoute une ou plusieurs extensions de fichier comme **jpg** ou **txt** à la liste des exclusions. Tous les fichiers avec ces extensions ne sont pas inclus dans les analyses en temps réel ou planifiées.
-   **Processus à exclure des analyses et de la protection en temps réel** - Ajoute un ou plusieurs processus de type **.exe**, **.com** ou **.scr** à la liste des exclusions. Ces processus ne seront pas inclus dans les analyses en temps réel ou planifiées.



<!--HONumber=Feb17_HO1-->


