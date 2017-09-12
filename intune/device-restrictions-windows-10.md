---
title: "Paramètres de restriction d’appareil Intune pour Windows 10"
titlesuffix: Azure portal
description: "Découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 182088fa7c99f9f933d2228c0cdcf6a29aa4d727
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Windows 10 et versions ultérieures dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Général
-   **Capture d’écran (mobile uniquement)** - Autorise l’utilisateur à capturer le contenu de l’écran d’appareil en tant qu’image.
-   **Copier et coller (mobile uniquement)** - Autorise les actions copier-coller entre les applications sur l’appareil.
-   **Inscription manuelle** - Permet à l’utilisateur de supprimer manuellement le compte d’espace de travail de l’appareil.
-   **Installation manuelle du certificat racine (mobile uniquement)** -Empêche l’utilisateur d’installer manuellement les certificats racines et les certificats CAP intermédiaires.
-   **Envoi des données de diagnostic** - Les valeurs possibles sont les suivantes :
    -       **Aucun** - Aucune donnée n’est envoyée à Microsoft
    -       **Basique** - Une quantité limitée d’informations est envoyée à Microsoft
    -       **Amélioré** - Des données de diagnostic avancées sont envoyées à Microsoft
    -       **Complète** - Envoie les mêmes données que Amélioré, ainsi que des données supplémentaires sur l'état de l’appareil
-   **Appareil photo** - Autorise ou bloque l’utilisation de l’appareil photo sur l’appareil.
-   **Synchronisation des fichiers OneDrive** -Empêche l’appareil de synchroniser des fichiers avec OneDrive.
-   **Stockage amovible** - Spécifie si des appareils de stockage externe comme une carte SD peuvent être utilisés avec l’appareil.
-   **Géolocalisation** - Spécifie si l’appareil peut utiliser les informations des services d’emplacement.
-   **Partage Internet** - Autorise l’utilisation du partage de connexion Internet sur l’appareil.
-   **Réinitialisation du téléphone** - Détermine si l’utilisateur peut rétablir les paramètres d’usine de son appareil.
-   **Connexion USB (mobile uniquement)** - Détermine si les appareils peuvent accéder à des appareils de stockage externe par le biais d’une connexion USB.
-   **Mode antivol (mobile uniquement)** - Détermine si le mode antivol Windows est activé.
-   **Cortana** - Active ou désactive l’assistant vocal Cortana.
-   **Enregistrement vocal (mobile uniquement)** - Autorise ou bloque l’utilisation de l’enregistreur vocal de l’appareil.
-   **Modification du nom de l’appareil** - Empêche l’utilisateur final de modifier le nom de l’appareil (Windows 10 Mobile uniquement).
-   **Ajouter des packages de configuration** - Bloque l’agent de configuration du runtime qui installe les packages de configuration.
-   **Supprimer les packages de configuration** - Bloque l’agent de configuration du runtime qui supprime les packages de configuration.
-   **Découverte d’appareil** - Empêche un appareil d’être détecté par d’autres appareils.
-   **Sélecteur de tâches (mobile uniquement)** - Bloque le sélecteur de tâches sur l’appareil.
-   **Boîte de dialogue d’erreur de carte SIM (mobile uniquement)** - Empêche un message d’erreur de s’afficher sur l’appareil si aucune carte SIM n’est détectée.


## <a name="password"></a>Mot de passe
-   **Mot de passe** - Demande à l’utilisateur final d’entrer un mot de passe pour accéder à l’appareil.
    -   **Type de mot de passe requis** - Spécifie si le mot de passe doit être numérique uniquement ou alphanumérique.
    -   **Longueur minimale du mot de passe** - S’applique à Windows 10 Mobile uniquement.
    -   **Nombre d'échecs de connexion avant réinitialisation de l'appareil** - Pour les appareils exécutant Windows 10 : si BitLocker est activé sur l’appareil, ce dernier passe en mode de récupération BitLocker après le nombre d’échecs de connexion que vous avez spécifié. Si BitLocker n’est pas activé sur l’appareil, alors ce paramètre ne s’applique pas.
Pour les appareils exécutant Windows 10 Mobile : après le nombre d’échecs de connexion que vous spécifiez, l’appareil est réinitialisé.
    -   **Nombre maximal de minutes d'inactivité avant le verrouillage de l'appareil** - Spécifie la durée pendant laquelle l’appareil doit être inactif avant le verrouillage de l’écran.
    -   **Expiration du mot de passe (jours)** - Spécifie la durée après laquelle le mot de passe d’un appareil doit être modifié.
    -   **Empêcher la réutilisation des mots de passe précédents** - Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.
    -   **Exiger un mot de passe quand l’appareil sort d’un état d’inactivité (Mobile uniquement)** - Spécifie que l’utilisateur doit entrer un mot de passe pour déverrouiller l’appareil (Windows 10 Mobile uniquement).
    -   **Mots de passe simples** - Permet d’utiliser des mots de passe simples, tels que 1111 ou 1234. Ce paramètre autorise ou bloque également l’utilisation des mots de passe d’image Windows.
-   **Chiffrement** - Active le chiffrement sur les appareils ciblés (Windows 10 Mobile uniquement).

## <a name="personalization"></a>Personalization

-   **URL de l’image d’arrière-plan du poste de travail (Desktop uniquement)** - Spécifie l’URL d’une image au format JPEG, JPG ou PNG que vous souhaitez utiliser comme papier peint du Bureau Windows. Les utilisateurs ne peuvent pas modifier ce paramètre.

## <a name="privacy"></a>Confidentialité

-   **Personnalisation des entrées** – Ne pas autoriser l’utilisation des services cloud de reconnaissance vocale pour les applications du Microsoft Store, la dictée ou Cortana. Si vous autorisez ces services, Microsoft peut collecter des données vocales pour améliorer le service.
-   **Acceptation automatique des invites de consentement de l’utilisateur pour le couplage et la confidentialité** – Autoriser Windows à accepter automatiquement les messages de consentement de couplage et de confidentialité lors de l’exécution des applications.


## <a name="locked-screen-experience"></a>Expérience d’écran de verrouillage


-   **Notifications du centre de notifications (mobile uniquement)** - Active les notifications du Centre de notifications sur l’écran de verrouillage de l’appareil (Windows 10 Mobile uniquement).
-   **URL de l'image de l'écran verrouillé (Desktop uniquement)** - Spécifie l’URL d’une image au format JPEG, JPG ou PNG qui sera utilisée comme papier peint de l’écran de verrouillage Windows. Les utilisateurs ne peuvent pas modifier ce paramètre.
-   **Délai d’expiration de l’écran configurable par l’utilisateur (mobile uniquement)** – Permet aux utilisateurs de configurer la durée 
-   **Cortana sur écran verrouillé (poste de travail uniquement)** – Ne pas autoriser l’utilisateur à interagir avec Cortana quand l’appareil est sur l’écran de verrouillage (Windows 10 Desktop uniquement).
-   **Notifications toast sur écran verrouillé** – Bloquer l’affichage des messages d’alerte sur l’écran de verrouillage de l’appareil.
-   **Délai d’expiration de l’écran (mobile uniquement)** - Spécifie la durée (en secondes) au bout de laquelle l’écran s’éteint après le verrouillage.



## <a name="app-store"></a>App Store

-   **App store (mobile uniquement)** - Active ou bloque l’utilisation de l’App Store sur les appareils Windows 10 Mobile.
-   **Mettre à jour automatiquement les applications du Windows store** - Permet aux applications installées à partir du Microsoft Store d’être automatiquement mises à jour.
-   **Installation d’applications approuvées** - Permet de charger indépendamment les applications signées avec un certificat approuvé.
-   **Déverrouillage de développement** - Autorise les paramètres de développement Windows, par exemple pour autoriser l’utilisateur à modifier des applications qui ont été chargées indépendamment.
-   **Données d'application utilisateur partagées** - Permet aux applications de partager des données entre différents utilisateurs sur le même appareil.
-   **Utiliser uniquement un store privé** - Activez cette option pour autoriser les utilisateurs à télécharger uniquement des applications à partir de votre Store privé.
-   **Lancement des applications du Windows Store** - Permet de désactiver toutes les applications qui ont été préalablement installées sur l’appareil ou qui ont été téléchargées à partir du Microsoft Store.
-   **Installer des données d'application sur le volume système** - Empêche les applications de stocker des données sur le volume système de l’appareil.
-   **Installer des données d'application sur le lecteur système** - Empêche les applications de stocker des données sur le lecteur système de l’appareil.
-   **Jeux DVR (Desktop uniquement)** - Détermine si l’enregistrement et la diffusion des jeux sont autorisés ou non.
-   **Applications du Store uniquement** -Détermine si les utilisateurs peuvent installer des applications à partir d’emplacements autres que l’App Store.



## <a name="edge-browser"></a>Navigateur Edge
-   **Navigateur Microsoft Edge (mobile uniquement)** - autorise l’utilisation du navigateur web Edge sur l’appareil.
-   **Liste déroulante des barres d’adresse (Desktop uniquement)** – Permet d’empêcher Edge d’afficher une liste de suggestions dans une liste déroulante quand vous tapez. Cela aide à réduire l’utilisation de la bande passante réseau entre Edge et les services Microsoft.
-   **Synchroniser les favoris entre les navigateurs Microsoft (Desktop uniquement)** – Permet à Windows de synchroniser les Favoris entre Internet Explorer et Edge.
-   **Envoyer un en-tête Do Not Track** - Configure le navigateur Microsoft Edge pour envoyer des en-êtes Do Not Track aux sites web que les utilisateurs visitent.
-   **Cookies** - Permet au navigateur d’enregistrer les cookies internet sur l’appareil.
-   **JavaScript** - Autorise l’exécution de scripts, tels que JavaScript, dans le navigateur Microsoft Edge.
-   **Fenêtres contextuelles** - Bloque les fenêtres publicitaires dans le navigateur (s’applique à Windows 10 Desktop uniquement).
-   **Suggestions de recherche** - Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche.
-   **Envoyer le trafic intranet vers Internet Explorer** - Permet aux utilisateurs d’ouvrir des sites web intranet dans Internet Explorer (Windows 10 Desktop uniquement).
-   **Remplissage automatique** - Autoriser les utilisateurs à modifier les paramètres de saisie semi-automatique dans le navigateur (Windows 10 Desktop uniquement).
-   **Gestionnaire de mots de passe** - Activer ou désactiver la fonctionnalité Gestionnaire de mots de passe Microsoft Edge.
-   **Emplacement de la liste des sites en mode entreprise** - Indique où trouver la liste des sites web qui s’ouvrent en Mode entreprise. Les utilisateurs ne peuvent pas modifier cette liste.<br>(Windows 10 Desktop uniquement).
-   **Outils de développement** - Empêche l’utilisateur final d’ouvrir les outils de développement Edge.
-   **Extensions** - Autoriser l’utilisateur final à installer des extensions Edge sur l’appareil.
-   **Navigation inPrivate** - Empêche l’utilisateur final d’ouvrir des sessions de navigation InPrivate.
-   **Afficher la page de la première exécution** – Empêche l’affichage de la page d’introduction lors de la première exécution d’Edge.
    -   **URL de la première exécution** – Spécifie l’URL d’une page qui s’affiche la première fois qu’un utilisateur exécute Edge (Windows 10 Mobile uniquement).
-   **Pages d’accueil** - Ajoute une liste de sites que vous souhaitez utiliser comme pages d’accueil dans le navigateur Edge (poste de travail uniquement).
-   **Changement des pages de démarrage** – Permet aux utilisateurs de changer les pages de démarrage affichées quand Edge est ouvert. Utilisez le paramètre Pages d’accueil pour créer la page, ou liste de pages, qui est ouverte quand Edge démarre.
-   **Bloquer l'accès aux indicateurs about** - Empêche l’utilisateur final d’accéder à la page des indicateurs about: dans Edge, qui contient les paramètres expérimentaux et de développement.
-   **Adresse IP localhost WebRTC** - Bloque l’affichage de l’adresse IP localhost des utilisateurs lors d’appels téléphoniques effectués à l’aide du protocole RTC web.
-   **Moteur de recherche par défaut** - Spécifie le moteur de recherche par défaut à utiliser. Les utilisateurs finaux peuvent modifier cette valeur à tout moment.
-   **Effacer les données de navigation à la sortie** – Efface l’historique et les données de navigation quand l’utilisateur quitte Edge.
-   **Collecte de données pour les vignettes dynamiques** – Empêche Windows de collecter des informations sur la vignette dynamique quand les utilisateurs épinglent un site au menu Démarrer à partir d’Edge.

## <a name="edge-browser-smartscreen"></a>SmartScreen du navigateur Edge

-   **SmartScreen** - Active ou désactive la fonctionnalité SmartScreen qui bloque les sites web frauduleux.
-   **Ignorer les invites SmartScreen** - Autorise l’utilisateur final à ignorer les avertissements du filtre SmartScreen sur les sites web potentiellement malveillants.
-   **Annuler les invites SmartScreen concernant les fichiers** - Autorise l’utilisateur final à ignorer les avertissements du filtre SmartScreen sur le téléchargement de fichiers potentiellement malveillants.

## <a name="search"></a>Recherche
- **Recherche sécurisée (appareils mobiles uniquement)** - Contrôle la manière dont Cortana filtre les contenus pour adultes dans les résultats de la recherche. Vous pouvez sélectionner **Strict** ou **Modéré**, ou encore autoriser l’utilisateur à choisir ses propres paramètres.

## <a name="cloud-and-storage"></a>Cloud et stockage
-   **Compte Microsoft** - Permet à l’utilisateur d’associer un compte Microsoft à l’appareil.
-   **Compte non-Microsoft** - Permet à l’utilisateur d’ajouter des comptes de messagerie à l’appareil qui ne sont pas associés à un compte Microsoft.
-   **Synchronisation des paramètres du compte Microsoft** - Permet aux paramètres d’appareil et d’application associés à un compte Microsoft de se synchroniser entre les appareils.

## <a name="cellular-and-connectivity"></a>Cellulaire et connectivité

-   **Canal de données mobiles** – Empêche les utilisateurs d’utiliser des données, par exemple de naviguer sur le web, quand ils sont connectés à un réseau cellulaire. 
-   **Itinérance des données** - Autorise l’itinérance entre réseaux lors de l’accès aux données.
-   **VPN sur le réseau de téléphonie mobile** - Détermine si l’appareil peut accéder aux connexions VPN quand il est connecté à un réseau cellulaire.
-   **Itinérance VPN sur le réseau de téléphonie mobile** - Détermine si l’appareil peut accéder aux connexions VPN quand il est en itinérance sur un réseau cellulaire.
-   **Bluetooth** - Contrôle si l’utilisateur peut activer et configurer la fonction Bluetooth sur l’appareil.
-   **Détectabilité de Bluetooth** - Permet à cet appareil d’être découvert par d’autres appareils Bluetooth.
-   **Précouplage Bluetooth** – Permet de configurer des appareils Bluetooth spécifiques pour qu’ils soient couplés automatiquement à un appareil hôte.
-   **Publicité Bluetooth** - Permet à l’appareil de recevoir des publications via Bluetooth.
-   **Service d’appareils connectés** – Permet de choisir s’il faut autoriser le service d’appareils connectés, qui active la découverte et la connexion à d’autres appareils Bluetooth.
-   **NFC** - Permet à l’utilisateur d’activer et de configurer les fonctionnalités Near Field Communications sur l’appareil.
-   **Wi-Fi** - Permet à l’utilisateur d’activer et de configurer le Wi-Fi sur l’appareil (Windows 10 Mobile uniquement).
-   **Se connecter automatiquement aux points d'accès Wi-Fi** - Permet à l’appareil de se connecter automatiquement aux points d’accès Wi-Fi gratuits et d’accepter automatiquement les termes et conditions de la connexion.
-   **Configuration manuelle du Wi-Fi** - Détermine si les utilisateurs peuvent configurer leurs propres connexions Wi-Fi ou s’ils peuvent uniquement utiliser les connexions configurées par un profil Wi-Fi (Windows 10 Mobile uniquement).
-   **Intervalle de recherche de Wi-Fi** - Spécifiez la fréquence à laquelle les appareils recherchent des réseaux Wi-Fi. Spécifiez une valeur comprise entre 1 (plus fréquent) et 500 (moins fréquent).
-   **Services Bluetooth autorisés** – Spécifiez (sous forme de chaînes hexadécimales) une liste de services et de profils Bluetooth autorisés.


## <a name="control-panel-and-settings"></a>Panneau de configuration et paramètres

-   **Application Paramètres** - Bloque l’accès à l’application Paramètres de Windows.
    -   **Système** - Bloque l’accès à la zone système de l’application Paramètres.
        -   **Modification des paramètres d'alimentation et de veille (poste de travail uniquement)** -Empêche l’utilisateur final de modifier les paramètres d’alimentation et de veille sur l’appareil.
    -   **Appareils** - Bloque l’accès à la zone des appareils de l’application Paramètres.
    -   **Réseau Internet** - Bloque l’accès à la zone réseau et internet de l’application Paramètres.
    -   **Personnalisation** - Bloque l’accès à la zone de personnalisation de l’application Paramètres.
    -   **Comptes** - Bloque l’accès à la zone des comptes de l’application Paramètres.
    -   **Heure et langue** - Bloque l’accès à la zone heure et langue de l’application Paramètres.
        -   **Modification de l’heure système** - Empêche l’utilisateur final de modifier la date et l’heure de l’appareil.
        -   **Modification des paramètres régionaux (Desktop uniquement)** -Empêche l’utilisateur final de modifier les paramètres régionaux sur l’appareil.
        -   **Modification des paramètres de langue (poste de travail uniquement)** -Empêche l’utilisateur final de modifier les paramètres linguistiques sur l’appareil.
    -   **Jeux** - Bloque l’accès à l’application Jeux dans Paramètres.
    -   **Options d’ergonomie** - Bloque l’accès à la zone d’options d’ergonomie de l’application Paramètres.
    -   **Confidentialité** - Bloque l’accès à la zone de confidentialité de l’application Paramètres.
    -   **Mise à jour et sécurité** - Bloque l’accès à la zone des mises à jour et de la sécurité dans l’application des paramètres.

## <a name="defender"></a>Defender

-   **Surveillance en temps réel** - Active la recherche en temps réel des logiciels malveillants, logiciels espions et autres logiciels indésirables.
-   **Analyse du comportement** - Permet à Defender de rechercher certains modèles connus d’activité suspecte sur les appareils.
-   **Système NIS (Network Inspection System)** - Le système NIS vous aide à vous protéger contre les attaques réseau. Il utilise les signatures de vulnérabilités connues fournies par le Microsoft Endpoint Protection Center pour faciliter la détection et le blocage du trafic malveillant.
-   **Analyser tous les téléchargements** - Contrôle si Defender analyse tous les fichiers téléchargés depuis Internet.
-   **Analyser les scripts chargés dans les navigateurs web Microsoft** - Permet à Defender d’analyser les scripts utilisés dans Internet Explorer.
-   **Accès de l'utilisateur final à Defender** - Détermine si l'interface utilisateur de Windows Defender est masquée aux utilisateurs finaux.
Quand ce paramètre est modifié, le changement est appliqué au prochain redémarrage de l’ordinateur de l’utilisateur final.
-   **Intervalle de mise à jour des signatures (en heures)** - Spécifie l’intervalle auquel Defender vérifie les nouveaux fichiers de signatures.
-   **Surveiller l’activité des fichiers et des programmes** - Autorise Defender à surveiller l’activité des fichiers et des programmes sur des appareils.
-   **Nombre de jours avant la suppression des programmes malveillants en quarantaine** - Permet à Defender de continuer à suivre les logiciels malveillants résolus pendant un certain nombre de jours que vous spécifiez, pour vous permettre de vérifier manuellement les appareils affectés. Si vous définissez le nombre de jours du suivi sur **0**, les logiciels malveillants restent dans le dossier de quarantaine et ne sont pas automatiquement supprimés.
-   **Limite de l'utilisation du processeur pendant une analyse** - Vous permet de limiter la quantité de ressources du processeur que les analyses sont autorisées à utiliser (de **1** à **100**).
-   **Analyser les fichiers d’archive** - Permet à Defender d’analyser les fichiers archivés tels que les archives .zip ou .cab.
-   **Analyser les e-mails entrants** - Permet à Defender d’analyser les e-mails quand ils arrivent sur l’appareil.
-   **Analyser les disques amovibles lors d'une analyse complète** - Permet à Defender d'analyser les lecteurs amovibles tels que les clés USB.
-   **Analyser les lecteurs réseau mappés lors d'une analyse complète** - Permet à Defender d’analyser les fichiers sur un lecteur réseau mappé.<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne peut pas supprimer les logiciels malveillants détectés dans ces fichiers.
-   **Analyser les fichiers ouverts à partir de dossiers réseau** - Permet à Defender d’analyser les fichiers sur des lecteurs réseau partagés (par exemple les fichiers accessibles à partir d’un chemin UNC).
Si les fichiers sur le lecteur sont en lecture seule, Defender ne peut pas supprimer les logiciels malveillants détectés dans ces fichiers.
-   **Protection du cloud** - Autorise ou empêche Microsoft Active Protection Service de recevoir des informations sur l’activité des logiciels malveillants en provenance des appareils que vous gérez. Ces informations serviront à améliorer le service.
-   **Demander confirmation aux utilisateurs avant l’envoi d’un échantillon** - Contrôle si les fichiers potentiellement malveillants susceptibles de nécessiter une analyse plus approfondie sont envoyés automatiquement à Microsoft.
-   **Heure de l'analyse rapide quotidienne** - Permet de planifier une analyse rapide exécutée tous les jours à l’heure de votre choix.
-   **Type d’analyse système à effectuer** - Permet de spécifier le niveau d’analyse à effectuer quand vous planifiez une analyse système.
-   **Détecter les applications potentiellement indésirables** – Choisissez le niveau de protection quand Windows détecte des applications potentiellement indésirables, parmi les niveaux suivants :
        - **Bloquer**
        - **Audit** Pour plus d’informations sur les applications potentiellement indésirables, consultez [cette rubrique](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
-   **Actions en cas de détection de menaces de programmes malveillants** – Activez cette option pour spécifier les actions que Defender doit exécuter pour chaque niveau de menace détecté (faible, modéré, élevé et grave). Les actions possibles sont les suivantes :
    -   **Nettoyer**
    -   **Quarantaine**
    -   **Supprimer**
    -   **Autoriser**
    -   **Défini par l’utilisateur**
    -   **Bloquer**



## <a name="defender-exclusions"></a>Exclusions de Defender

-   **Fichiers et dossiers à exclure des analyses et de la protection en temps réel** - Ajoute un ou plusieurs fichiers et dossiers comme **C:\Chemin** ou **%ProgramFiles%\Chemin\NomFichier.exe** à la liste des exclusions. Ces fichiers et dossiers ne sont pas inclus dans les analyses en temps réel ou planifiées.
-   **Extensions de fichier à exclure des analyses et de la protection en temps réel** - Ajoute une ou plusieurs extensions de fichier comme **jpg** ou **txt** à la liste des exclusions. Tous les fichiers avec ces extensions ne sont pas inclus dans les analyses en temps réel ou planifiées.
-   **Processus à exclure des analyses et de la protection en temps réel** - Ajoute un ou plusieurs processus de type **.exe**, **.com** ou **.scr** à la liste des exclusions. Ces processus ne sont pas inclus dans les analyses en temps réel ou planifiées.


## <a name="network-proxy"></a>Proxy réseau

-   **Détecter automatiquement les paramètres du proxy** - Quand cette option est activée, l’appareil tente de trouver le chemin d’un script PAC.
-   **Utiliser un script de proxy** - Sélectionnez cette option si vous souhaitez spécifier un chemin d’accès à un script PAC pour configurer le serveur proxy.
    -   **URL de l’adresse du script de configuration** - Entrez l’URL d’un script PAC que vous souhaitez utiliser pour configurer le serveur proxy.
-   **Utiliser un serveur proxy manuel** - Sélectionnez cette option si vous souhaitez renseigner manuellement les informations du serveur proxy.
    -   **Adresse** - Entrez le nom ou l’adresse IP du serveur proxy.
    -   **Numéro de port** - Saisissez le numéro de port de votre serveur proxy.
    -   **Exceptions du proxy** - Entrez les URL qui ne doivent pas utiliser le serveur proxy. Utilisez des points-virgules pour séparer chaque élément.
    -   **Ignorer le serveur proxy pour les adresses locales** - Si vous ne souhaitez pas utiliser le serveur proxy pour les adresses locales sur votre intranet, activez cette option.


## <a name="windows-spotlight"></a>Windows à la une


- **Windows à la une** – Utilisez ce paramètre pour bloquer toutes les fonctionnalités Windows à la une sur les appareils Windows 10. Si vous bloquez ce paramètre, les paramètres suivants ne sont pas disponibles.
    - **Windows à la une sur l’écran de verrouillage** – Empêche Windows à la une d’afficher des informations sur l’écran de verrouillage de l’appareil.
    - **Suggestions de tiers dans Windows à la une** – Empêche Windows à la une de suggérer du contenu qui n’est pas publié par Microsoft.
    - **Fonctionnalités grand public** - Permet de bloquer certaines fonctionnalités grand public, comme l’affichage de suggestions sur le menu Démarrer ou encore les notifications d’appartenance.
    - **Conseils Windows** - Permet de bloquer l’affichage des info-bulles dans Windows.
    - **Windows à la une dans le centre de notifications** – Empêche l’affichage des suggestions de Windows à la une telles que le nouveau contenu de sécurité ou d’application dans le Centre de notifications de Windows.
    - **Personnalisation de Windows à la une** – Empêche Windows à la une de personnaliser les résultats en fonction de l’utilisation d’un appareil.
    - **Écrans d’accueil de Windows** – Bloquer l’expérience d’accueil de Windows qui montre à l’utilisateur des informations sur les fonctionnalités nouvelles ou mises à jour.


## <a name="projection"></a>Projection

- **Entrées utilisateur à partir de récepteurs d'affichage sans fil** - Bloque la saisie des utilisateurs à partir de récepteurs d’affichage sans fil.
- **Projection sur ce PC** - Empêche les autres appareils de détecter le PC pour la projection.
- **Exiger un code PIN pour l'appairage** - Exige un code PIN lors de la connexion à un projecteur.

## <a name="start"></a>Démarrer

- **Désépingler les applications de la barre des tâches** - Empêche l’utilisateur de désépingler des applications à partir du menu Démarrer.
- **Documents sur Démarrer** - Permet de masquer ou d’afficher le dossier Documents dans le menu Démarrer de Windows.
- **Téléchargements sur Démarrer** - Permet de masquer ou d’afficher le dossier Téléchargements dans le menu Démarrer de Windows.
- **Explorateur de fichiers sur Démarrer** - Permet de masquer ou d’afficher l’application Explorateur de fichiers dans le menu Démarrer de Windows.
- **Groupe résidentiel sur Démarrer** - Permet de masquer ou d’afficher le dossier Groupe résidentiel dans le menu Démarrer de Windows.
- **Musique sur Démarrer** - Permet de masquer ou d’afficher le dossier Musique dans le menu Démarrer de Windows.
- **Réseau sur Démarrer** - Permet de masquer ou d’afficher le dossier Réseau dans le menu Démarrer de Windows.
- **Dossier Personnel sur Démarrer** - Permet de masquer ou d’afficher le dossier Personnel dans le menu Démarrer de Windows.
- **Images sur Démarrer** - Permet de masquer ou d’afficher le dossier Images dans le menu Démarrer de Windows.
- **Paramètres sur Démarrer** - Permet de masquer ou d’afficher le dossier Paramètres dans le menu Démarrer de Windows.
- **Vidéos sur Démarrer** - Permet de masquer ou d’afficher le dossier Vidéos dans le menu Démarrer de Windows.