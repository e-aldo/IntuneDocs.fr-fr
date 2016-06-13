---
# required metadata

title: Paramètres de la stratégie dans Windows 10 | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie dans Windows 10

Utilisez les paramètres de la stratégie de cette rubrique pour configurer les paramètres des appareils Windows 10 Mobile et Windows 10 Desktop inscrits.

## Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale** Microsoft Intune pour Windows 10 afin de configurer les paramètres généraux des appareils Windows 10 Mobile et Windows 10 Desktop inscrits :


### Mot de passe

|Nom du paramètre|Détails|
|----------------|----------------------|
|**Exiger un mot de passe pour déverrouiller des appareils**|Exigez un mot de passe sur les appareils pris en charge.|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple, numérique uniquement ou alphanumérique|
|**Type de mot de passe requis** - **Nombre minimum de jeux de caractères**|Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe.|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères que le mot de passe de l’appareil doit contenir.<br>(Windows 10 Mobile uniquement)|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Réinitialise l'appareil si le nombre d'échecs de tentative de est atteint.|
|**Minutes d'inactivité avant arrêt de l'écran**|Spécifie la durée pendant laquelle l’appareil doit être inactif avant que l’écran de veille se verrouille.|
|**Expiration du mot de passe (jours)**|Spécifie la durée après laquelle le mot de passe d'un appareil doit être modifié.|
|**Mémoriser l'historique des mots de passe**|Spécifie si vous souhaitez empêcher l'utilisateur final de créer des mots de passe utilisés précédemment.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.|
|**Autoriser un mot de passe image et un code confidentiel**|Vous permet d'utiliser des gestes simples sur une image ou un code confidentiel simple pour vous connecter.<br>(Windows 10 Desktop uniquement)|
|**Exiger un mot de passe quand l'appareil quitte un état inactif**|Si cette option est activée, l'utilisateur doit entrer un mot de passe pour déverrouiller l’appareil pour qu’il quitte l’état inactif.<br>(Windows 10 Mobile uniquement)|

### Chiffrement

|Nom du paramètre|Détails|
|----------------|----------------------|
|**Exiger le chiffrement sur l'appareil mobile**|Active le chiffrement sur les appareils ciblés.<br>(Windows 10 Mobile uniquement)|

### Système

|Nom du paramètre|Détails|
|----------------|----------------------|
|**Autoriser la capture d'écran**|Autorise l’utilisateur à capturer le contenu de l’écran d’appareil en tant qu’image.<br>(Windows 10 Mobile uniquement)|
|**Autoriser la désinscription manuelle**|Permet à l'utilisateur de supprimer manuellement le compte d'espace de travail de l'appareil|
|**Autoriser l'installation manuelle de certificats racines**|Spécifie si l’utilisateur peut installer des certificats racines manuellement.<br>(Windows 10 Mobile uniquement)|
|**Autoriser l'envoi des données de diagnostic et d'utilisation à Microsoft**|Détermine la quantité de données de diagnostic et d'utilisation envoyées à Microsoft à partir des appareils.<br><br>**Non** - Aucune donnée n’est envoyée à Microsoft<br>**De Base** - L'appareil envoie uniquement des informations limitées à Microsoft<br>**Amélioré** - Envoie des données de diagnostic améliorées à Microsoft<br>**Complète (recommandée)** - envoie les mêmes données que **Amélioré**, ainsi que des données supplémentaires sur l'état de l’appareil|


### Compte et synchronisation

|Nom du paramètre|Détails|
|----------------|----------------------|---------------------|
|**Autoriser le compte Microsoft**|Permet à l'utilisateur d'associer un compte Microsoft à l’appareil.|
|**Autoriser l'ajout manuel de comptes non-Microsoft**|Permet à l'utilisateur d'ajouter des comptes de messagerie à l'appareil qui ne sont pas associés à un compte Microsoft.|
|**Autoriser la synchronisation des paramètres pour les comptes Microsoft**|Permet aux paramètres d’appareil et d'application associés à un compte Microsoft de se synchroniser entre les appareils.|

### Paramètres de messagerie

|Nom du paramètre|Détails|
|----------------|----------------------|---------------------|
|**Rendre le compte Microsoft facultatif dans l'application Windows Mail**|Configurez cette option pour supprimer l'obligation d’utiliser un compte Microsoft dans Windows Mail.<br>Windows 10 Desktop uniquement|



### Microsoft Edge

|Nom du paramètre|Détails|
|----------------|----------------------|
|**Autoriser le navigateur web**|Permet d’utiliser le navigateur web Edge sur l’appareil.<br>(Windows 10 Mobile uniquement)|
|**Autoriser les suggestions de recherche dans la barre d'adresse**|Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche.|
|**Autoriser l'envoi du trafic intranet vers Internet Explorer**|Permet aux utilisateurs d’ouvrir des sites web intranet dans Internet Explorer.<br>(Windows 10 Desktop uniquement)|
|**Autoriser Do Not Track**|Configure le navigateur Edge pour envoyer des en-êtes Do Not Track aux sites Web que les utilisateurs visitent.|
|**Activer SmartScreen**|Active le paramètre de navigateur SmartScreen sur les appareils.|
|**Autoriser les scripts actifs**|Autoriser l'exécution de scripts, tels que JavaScript, dans le navigateur Edge.|
|**Autoriser les fenêtres contextuelles**|Active ou désactive le bloqueur de fenêtres publicitaires du navigateur.<br>(Windows 10 Desktop uniquement)|
|**Autoriser les cookies**|Autoriser ou désactiver les cookies.|
|**Autoriser le remplissage automatique**|Autoriser les utilisateurs à modifier les paramètres de saisie semi-automatique dans le navigateur.<br>(Windows 10 Desktop uniquement)|
|**Autoriser le gestionnaire de mots de passe**|Activer ou désactiver la fonctionnalité Gestionnaire de mots de passe Edge.|
|**Emplacement de la liste des sites en mode entreprise**|Indique où trouver la liste des sites web qui s'ouvrent en Mode entreprise. Les utilisateurs ne peuvent pas modifier cette liste.<br>(Windows 10 Desktop uniquement)|

### Applications

|Nom du paramètre|Détails|
|----------------|----------------------|---------------------|
|**Autoriser la boutique d'applications**|Autoriser l’utilisateur à accéder à l’App Store sur l’appareil.<br>(Windows 10 Mobile uniquement)|



### Cellulaire

|Nom du paramètre|Détails|
|----------------|----------------------|---------------------|
|**Autoriser l'itinérance des données**|Autorisez l'itinérance entre réseaux lors de l'accès aux données.|
|**Autoriser une connexion VPN sur un réseau cellulaire**|Contrôle si l’appareil peut accéder aux connexions VPN lorsqu'il est connecté à un réseau cellulaire.|
|**Autoriser l'itinérance VPN sur un réseau cellulaire**|Contrôle si l’appareil peut accéder aux connexions VPN lorsqu'il est en itinérance sur un réseau cellulaire.|

### Matériel

|Nom du paramètre|Détails|
|----------------|----------------------|
|**Autoriser l'appareil photo**|Spécifie si l’appareil photo de l’appareil peut être utilisé.|
|**Autoriser le stockage amovible**|Spécifie si des périphériques de stockage externe telle une carte SD peuvent être utilisés avec l'appareil.|
|**Autoriser le Wi-Fi**|Autorise l’utilisation des fonctionnalités Wi-Fi de l’appareil.<br>(Windows 10 Mobile uniquement)|
|**Autoriser le partage Internet**|Autorise l'utilisation du partage de connexion Internet sur l'appareil.|
|**Autoriser la configuration manuelle du Wi-Fi**|Détermine si les utilisateurs peuvent configurer leurs propres connexions Wi-Fi ou s'ils peuvent uniquement utiliser les connexions configurées par un profil Wi-Fi.<br>(Windows 10 Mobile uniquement)|
|**Autoriser la connexion automatique aux points d'accès Wi-Fi gratuits**|Permet à l’appareil de se connecter automatiquement aux points d'accès Wi-Fi gratuits et d’accepter automatiquement les termes et conditions de la connexion.|
|**Autoriser la géolocalisation**|Spécifie si l'appareil peut utiliser les informations des services d'emplacement.|
|**Autoriser NFC**|Permet à l’appareil d’utiliser ses fonctionnalités NFC (Near Field Communications).|
|**Autoriser Bluetooth**|Permet d'utiliser les fonctionnalités Bluetooth de l'appareil.|
|**Autoriser le mode découvrable Bluetooth**|Permet à cet appareil d’être découvert par d'autres appareils Bluetooth.|
|**Autoriser la publicité Bluetooth**|Permet aux appareils de recevoir des publicités par Bluetooth.|
|**Autoriser le mode connectable Bluetooth**|**Important :** Ce paramètre n’est plus pris en charge par Windows 10 et sera supprimé.|
|**Autoriser la réinitialisation du téléphone**|Détermine si l'utilisateur peut rétablir les paramètres d'usine de son appareil.|
|**Autoriser la connexion USB**|Contrôle si les appareils peuvent accéder à des périphériques de stockage externe via une connexion USB.|
|**Autoriser le mode antivol**|Configurer si le mode antivol Windows est activé.|

### Fonctionnalités

|Nom du paramètre|Détails|
|----------------|----------------------|---------------------|
|**Autoriser la fonction copier-coller**|Active ou désactive l'utilisation du copier-coller sur l’appareil.<br>(Windows 10 Mobile uniquement)|
|**Autoriser l'enregistrement vocal**|Active ou désactive les fonctionnalités d’enregistrement de la voix sur l’appareil.<br>(Windows 10 Mobile uniquement)|
|**Autoriser Cortana**|Active ou désactive l'assistant vocal Cortana.|
|**Autoriser les notifications du centre de notifications**|Active ou désactive les notifications du centre de notifications sur l'écran de verrouillage de l'appareil.<br>(Windows 10 Mobile uniquement)|

### Defender

Tous les paramètres sont pour Windows 10 Desktop uniquement.

|Nom du paramètre|Détails|
|-|-|
|**Autoriser la surveillance en temps réel**|Active la recherche en temps réel des logiciels malveillants, logiciels espions et autres logiciels indésirables.|
|**Autoriser l'analyse du comportement**|Permet à Defender de rechercher certains modèles connus d'activité suspecte sur les appareils.|
|**Activer le système NIS (Network Inspection System)**|Le système NIS (Network Inspection System) vous aide à protéger les appareils contre les attaques transmises via le réseau à l'aide de signatures de vulnérabilités connues fournies par le Microsoft Endpoint Protection Center afin de détecter et de bloquer tout trafic malveillant.|
|**Analyser tous les téléchargements**|Contrôle si Defender analyse tous les fichiers téléchargés depuis Internet.|
|**Autoriser l'analyse de scripts**|Configure Defender pour analyser les scripts utilisés dans Internet Explorer Defender.|
|**Surveiller l'activité des fichiers et des programmes**|Activez ce paramètre pour autoriser Defender à surveiller l'activité des fichiers et des programmes sur les appareils.|
|**Durée du suivi des logiciels malveillants dont le cas a été résolu (en jours)**|Permet à Defender de continuer à suivre les logiciels malveillants résolus pendant un certain nombre de jours que vous spécifiez, pour vous permettre de vérifier manuellement les appareils affectés. Si vous définissez le nombre de jours du suivi sur **0**, les logiciels malveillants restent dans le dossier de quarantaine et ne sont pas automatiquement supprimés. |
|**Autoriser l'accès à l'interface utilisateur cliente**|Détermine si l'interface utilisateur de Windows Defender est masquée aux utilisateurs finaux.<br>Lorsque ce paramètre est modifié, le changement est appliqué au prochain redémarrage de l'ordinateur de l'utilisateur final.|
|**Planifier une analyse quotidienne rapide**|Permet de planifier une analyse rapide exécutée tous les jours à l’heure de votre choix.|
|**Planifier une analyse système**|Vous permet de planifier une analyse système complète ou rapide exécutée régulièrement le jour et à l’heure de votre choix.|
|**Limiter l'utilisation du processeur lors d'une analyse à**|Vous permet de limiter la quantité de ressources du processeur que les analyses sont autorisées à utiliser (de **1** à **100**)|
|**Analyser les fichiers d'archives**|Permet à Defender d'analyser les fichiers archivés tels que les archives Zip ou Cab.|
|**Analyser les messages électroniques**|Permet à Defender d’analyser les messages électroniques lorsqu'ils arrivent sur l’appareil.|
|**Analyser les lecteurs amovibles**|Permet à Defender d'analyser les lecteurs amovibles tels que les clés USB.|
|**Analyser les lecteurs réseau mappés**|Permet à Defender d'analyser les fichiers sur un lecteur réseau mappé.<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|
|**Analyser les fichiers ouverts à partir de dossiers partagés sur le réseau**|Permet à Defender d'analyser les fichiers sur des lecteurs réseau partagés (par exemple, les lecteurs accessibles à partir d'un chemin d'accès UNC).<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|
|**Intervalle de mise à jour des signatures**|Spécifiez l'intervalle auquel Defender vérifie les nouveaux fichiers de signatures.|
|**Autoriser la protection de cloud**|Autorisez ou empêchez Microsoft Active Protection Service de recevoir des informations sur l'activité des logiciels malveillants à partir des appareils que vous gérez. Ces informations serviront à améliorer le service.|
|**Demander aux utilisateurs d'envoyer des exemples**|Contrôle si les fichiers susceptibles de nécessiter une analyse plus approfondie de la part de Microsoft pour déterminer s’il s’agit de logiciels malveillants sont automatiquement envoyés à Microsoft.|
|**Fichiers et dossiers à exclure lors de l'exécution d'une analyse ou de l'utilisation de la protection en temps réel**|Ajoutez un ou plusieurs fichiers et dossiers comme **C:\Path** ou **%ProgramFiles%\Path\filename.exe** à la liste des exclusions. Ces fichiers et dossiers ne seront pas inclus dans les analyses en temps réel ou planifiées.|
|**Extensions de fichier à exclure lors d'une analyse ou de la protection en temps réel**|Ajoutez une ou plusieurs extensions de fichier comme **jpg** ou **txt** à la liste des exclusions. Tous les fichiers avec ces extensions ne seront pas inclus dans les analyses en temps réel ou planifiées.|
|**Processus à exclure lors d'une analyse ou de la protection en temps réel**|Ajoutez un ou plusieurs processus du type **.exe**, **.com**, ou **.scr** à la liste des exclusions. Ces processus ne seront pas inclus dans les analyses en temps réel ou planifiées.| 


### Paramètres des mises à jour

|Nom du paramètre|Détails|
|----------------|---------------|
|**Autoriser les mises à jour automatiques**|Activez ce paramètre pour autoriser les mises à jour automatiques. Ensuite, configurez l'un des paramètres suivants pour contrôler le comportement de mise à jour :<br /><br />**Notification de téléchargement**<br /><br />**Installer automatiquement au moment de la maintenance**<br /><br />**Installer et redémarrer automatiquement au moment de la maintenance**<br /><br />**Installer et redémarrer automatiquement au moment planifié** **Remarque :** Quand cette option est sélectionnée, vous pouvez aussi configurer les paramètres suivants : **Supprimer la notification à l’utilisateur final** et **Définir un jour d’installation pour les mises à jour planifiées**<br>(Windows 10 Desktop uniquement)|

## Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée** Microsoft Intune pour Windows 10 et Windows 10 Mobile afin de déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui permettent de contrôler les fonctionnalités des appareils Windows 10 et Windows 10 Mobile. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Windows 10 qui ne sont pas configurables avec une stratégie de configuration générale Intune.



### Paramètres généraux de la stratégie personnalisée

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Entrez un nom unique pour la stratégie afin de vous aider à l’identifier dans la console Intune.|
    |**Description**|Entrez une description générale de la stratégie et d'autres informations pertinentes pour faciliter sa localisation.|

### Paramètres OMA-URI de la stratégie personnalisée

|Nom du paramètre|Détails|
    |--------|--------------------|
    |**Nom du paramètre**|Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.|
    |**Description du paramètre**|Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.|
    |**Type de données**|Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez parmi :<br /><br />-   **Chaîne**<br />-   **Chaîne (XML)**<br />-   **Date et heure**<br />-   **Entier**<br />-   **Virgule flottante**<br />-   **Booléen**|
    |**OMA-URI (sensible à la casse)**|Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.|
    |**Valeur**|Spécifiez la valeur à associer à l'identificateur OMA-URI spécifié précédemment.|


## Paramètres URI personnalisés pour les appareils Windows 10
Cette rubrique répertorie les paramètres que vous pouvez configurer sur les appareils Windows 10 et Windows 10 Mobile dans le cadre d’une **stratégie personnalisée Windows 10** Microsoft Intune.

Si vous souhaitez utiliser la stratégie URI personnalisée Windows, tous les appareils doivent être inscrits auprès d’Intune.

### Paramètres URI de la stratégie

|Nom de la stratégie|Détails|
|---------------|------------|-----------|
|**​AllowAutoUpdate**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** - **5** (par défaut : **1**)|
|**ScheduledInstallDay**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** - Tous les jours (par défaut)<br>**1** - Dimanche<br>**2** - Lundi<br>**3** - Mardi<br>**4** - Mercredi<br>**5** - Jeudi<br>**6** - Vendredi<br>**7** - Samedi|
|**ScheduledInstallTime**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – **23** heures (**0** correspond à minuit) (par défaut : **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** - L’utilisateur ne peut pas définir le minuteur de la période de grâce du mot de passe, et la valeur « chaque fois » est définie.<br>**1** - L’utilisateur peut définir le minuteur de la période de grâce du mot de passe (par défaut).|
|**WiFi/AllowWiFi**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser **Utiliser la connexion Wi-Fi**.<br>**1** –**Autoriser l’utilisation de la connexion Wi-Fi** (par défaut).|
|**WiFi/AllowInternetSharing**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser le partage Internet.<br>**1** – Autoriser le partage Internet (par défaut).|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**WiFi/AllowManualWiFiConfiguration**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Aucune connexion non-Wi-Fi en dehors de celles approvisionnées par la Gestion des appareils mobiles n’est autorisée.<br>**1** – L’ajout de nouveaux SSID réseau au-delà de ceux approvisionnés par MDM est autorisé (par défaut).|
|**System/AllowLocation**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**System/AllowTelemetry**<br>(Poste de travail et Mobile)|**Chemin complet à l’URI : **./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé (paramètre Entreprise uniquement)<br>**1** – Limité<br>**2** – Complet (par défaut)<br>**3** – Complet et informations de diagnostic|
|**System/AllowExperimentation**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI : **./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Paramètres uniquement (par défaut)<br>**2** – Paramètres et expérimentation|
|**Security/AntiTheftMode**<br>(Mobile uniquement)|**Chemin complet à l’URI :** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser le mode antivol<br>**1** – Préférence utilisateur (par défaut)|
|**Connectivity/AllowUSBConnection**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**System/AllowUserToResetPhone**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Connectivity/AllowCellularDataRoaming**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Connectivity/AllowVPNOverCellular**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Un VPN n’est pas autorisé sur une connexion cellulaire.<br>**1** – Un VPN peut utiliser n’importe quelle connexion, y compris une connexion cellulaire (par défaut).|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Connectivity/AllowBluetooth**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser l'utilisateur à activer le Bluetooth.<br>**1** – Réservé. L'utilisateur peut activer et configurer le Bluetooth (non pris en charge dans Windows Phone 8.1 pour MDM, EAS, Windows 10 Desktop ou Windows 10 Mobile)<br>**2** - Autorisé. L’utilisateur peut activer et configurer le Bluetooth (par défaut).|
|**Experience/AllowScreenCapture**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Experience/AllowTaskSwitcher**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Experience/AllowVoiceRecording**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Experience/AllowSyncMySettings**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser l'itinérance<br>**1** – Autoriser l’itinérance (par défaut)|
|**Experience/AllowManualMDMUnenrollment**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Security/AllowManualRootCertificateInstallation**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Security/AllowAddProvisioningPackages**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Search/DisableBackoff**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** (par défaut)<br>**1**|
|**Search/PreventRemoteQueries**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0**<br>**1** (par défaut)|
|**Search/AllowUsingDiacritics**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br> **0** (par défaut)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** (par défaut)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** (par défaut)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0**<br>**1** (par défaut)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** (par défaut)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Security/RequireProvisioningPackageSignature**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** (par défaut)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**TextInput/AllowIMENetworkAccess**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser<br>L'ouverture du dictionnaire étendu est désactivée.<br>Un utilisateur ne peut pas :<br>ajouter un nouveau dictionnaire d'étendu ouvert ;<br /><br />ajouter un nouveau fichier de configuration d'intégration de la recherche ;<br>utiliser la fonctionnalité de candidat de cloud ;<br>envoyer un mot inscrit par l'utilisateur.<br>En outre :<br>Un dictionnaire étendu ouvert qui a été ajouté avant l'activation de ce paramètre de stratégie n'est pas utilisé pour la conversion.<br>Un fichier de configuration d'intégration de la recherche qui a été installé avant d'activer ce paramètre de stratégie n'est pas utilisé.<br>**1** - Autoriser<br>Un dictionnaire étendu ouvert peut être ajouté et utilisé par défaut. Par ailleurs, la fonction d'intégration de la recherche peut être utilisée par défaut.<br>Un utilisateur peut :<br>Utiliser la fonctionnalité cloud qui convient<br>Envoyer un mot inscrit par l’utilisateur|
|**TextInput/AllowIMELogging**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** - La journalisation des erreurs de conversion est désactivée. Les données réglées automatiquement et les données d'historique d'entrée ne sont pas enregistrées dans un fichier.<br>**1** - La journalisation des erreurs de conversion est activée. Les données réglées automatiquement et les données d’historique d’entrée sont enregistrées dans un fichier (par défaut).|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**TextInput/AllowJapaneseUserDictionary**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères Shift-JIS.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères JIS0208.|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Aucun caractère n’est filtré (par défaut).<br>**1** – Tous les caractères sont filtrés, sauf les caractères JIS0208 ou EUDC.|
|**TextInput/AllowInputPanel**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Bluetooth/AllowDiscoverableMode**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Bluetooth/AllowAdvertising**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowDataSense**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowVPN**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowWorkplace**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowDateTime**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowLanguage**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowRegion**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowSignInOptions**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowYourAccount**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowPowerSleep**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Settings/AllowAutoPlay**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Experience/AllowCortana**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**Search/SafeSearchPermissions**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Strict, niveau de filtrage le plus élevé en matière de contenu pour adultes.<br>**1** – Modéré, niveau de filtrage modéré en matière de contenu pour adultes (les résultats de recherche valides ne sont pas filtrés – par défaut).|
|**Experience/AllowCopyPaste**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**ForceStartSize**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Autoriser l’utilisateur à modifier la taille (par défaut).<br>**1** - Forcer un affichage n’utilisant pas le plein écran.<br>**1** - Forcer le plein écran.|
|**Update/RequireDeferUpgrade**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** : ne pas reporter la mise à niveau (rester dans la branche active, CB – par défaut)<br>**1** : activer le report des mises à jour et des mises à niveau (l’appareil suit les règles de la branche actuelle d’entreprise, CBB)<br /><br />Pour plus d'informations, voir :<br>[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(Poste de travail et Mobile)|**Description :** stratégie de report des mises à jour logicielles pendant quatre semaines<br /><br />**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br> **0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**-**4** : nombre de semaines de report des mises à jour logicielles.<br /><br />Pour plus d'informations, voir :<br>[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(Poste de travail et Mobile)|**Description :** stratégie de report des mises à niveau des fonctionnalités jusqu’à huit mois<br /><br />**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**-**8** : nombre de mois de report des mises à niveau des fonctionnalités.<br /><br />Pour plus d'informations, voir :<br>[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(Poste de travail et Mobile)|**Description :** autorise un ordinateur CBB à arrêter de recevoir des mises à jour et des mises à niveau pendant cinq semaines. Cela doit être utilisé en cas de problème avec une mise à jour.<br /><br />**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** : appliquer immédiatement les mises à jour (par défaut)<br>**1**: suspendre les mises à jour et les mises à niveau (expire au bout de cinq semaines)|

### Paramètres URI de Windows Defender

|Nom de la stratégie|Détails|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowBehaviorMonitoring**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowIntrusionPreventionSystem**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowIOAVProtection**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowScriptScanning**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowOnAccessProtection**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**RealTimeScanDirection**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Analyser tous les fichiers (analyse bidirectionnelle – par défaut)<br>**1** – Analyser les fichiers entrants<br>**2** – Analyser les fichiers sortants|
|**DaysToRetainCleanedMalware**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** - **90** – Représente la durée pendant laquelle les logiciels malveillants sont conservés.<br>**Valeur par défaut :** **0** – Les logiciels malveillants sont conservés indéfiniment dans le dossier de quarantaine et ne sont pas supprimés automatiquement.|
|**AllowUserUIAccess**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**ScanParameter**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**1** – Analyse rapide (par défaut)<br>**2** – Analyse complète|
|**ScheduleScanDay**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Tous les jours (par défaut)<br>**1** - Lundi<br>**2** - Mardi<br>**3** - Mercredi<br>**4** - Jeudi<br>**5** - Vendredi<br>**6** - Samedi<br>**7** - Dimanche<br>**8** - Aucune analyse planifiée|
|**ScheduleScanTime**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (par défaut)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1381** – Fenêtre de maintenance|
|**ScheduleQuickScanTime**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – 00:00<br>**60** – 1:00<br>**120** – 2:00 (par défaut)<br>**180** – 3:00<br>**240** – 4:00<br>**300** – 5:00<br>**360** – 6:00<br>**420** – 7:00<br>**480** – 8:00<br>**540** – 9:00<br>**600** – 10:00<br>**660** – 11:00<br>**720** – 12:00<br>**780** – 13:00<br>**840** – 14:00<br>**900** – 15:00<br>**960** – 16:00<br>**1020** – 17:00<br>**1080** – 18:00<br>**1140** – 19:00<br>**1200** – 20:00<br>**1260** – 21:00<br>**1320** – 22:00<br>**1380** – 23:00|
|**AVGCPULoadFactor**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :0** - **100** (par défaut : **50**)|
|**AllowArchiveScanning**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowEmailScanning**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Type de données :** Entier<br>**Valeurs autorisées :**<br>**0** – Non autorisé (par défaut)<br>**1** – Autorisé|
|**AllowFullScanRemovableDriveScanning**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé (par défaut)<br>**1** – Autorisé|
|**AllowFullScanOnMappedNetworkDrives**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**AllowScanningNetworkFiles**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut) – S’exécute également quand RTP est activé quand la valeur Autorisé est définie.|
|**SignatureUpdateInterval**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas vérifier les signatures par intervalle<br>**1** – Vérifier les signatures toutes les heures<br>**2** – Vérifier les signatures toutes les 2 heures, etc.<br>**24** – Vérifier les signatures tous les jours<br>**Valeur par défaut :** 8 – Vérifier les signatures toutes les 8 heures|
|**AllowCloudProtection**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Non autorisé<br>**1** – Autorisé (par défaut)|
|**SubmitSamplesConsent**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Toujours demander (par défaut)<br>**1** – Envoyer automatiquement des échantillons sécurisés<br>**2** – Ne jamais envoyer<br>**3** – Envoyer automatiquement tous les échantillons|
|**ExcludedExtensions**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :**<br>*&lt;liste d’extensions séparées par des points-virgules&gt;* Par exemple : **obj;lib**<br>**Par défaut :** Aucune extension n’est exclue.|
|**ExcludedPaths**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :**<br /><br />*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br /><br />Exemple : **c:\test;c:\test1.exe**<br /><br />**Valeur par défaut :** Aucun chemin n’est exclu.|
|**ExcludedProcesses**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :**<br>*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br>Exemple : **c:\test.exe;c:\test1.exe**<br>**Valeur par défaut :** Aucun processus n’est exclu.|

### Paramètres URI du navigateur Edge

|Nom de la stratégie|Détails|
|---------------|------------|-----------|
|**Autoriser ce navigateur**<br>(Mobile uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** : navigation désactivée<br>**1** : navigation activée (par défaut)|
|**AllowSearchSuggestionsinAddressBar**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas afficher les suggestions de recherche<br>**1** – Afficher les suggestions de recherche (par défaut)|
|**SendIntranetTraffictoInternetExplorer**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Désactivé (ouvre les sites intranet dans le navigateur Edge – par défaut)<br>**1** – Activé (ouvre les sites intranet dans Internet Explorer)|
|**Autoriser Do Not Track**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Désactivé (DNT non envoyé – par défaut)<br>**1** – Activé (envoyer DNT)|
|**Configurer SmartScreen**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas autoriser<br>**1** – Autoriser (par défaut)|
|**Autoriser les fenêtres contextuelles**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Bloquer les fenêtres contextuelles (par défaut)<br>**1** – Autoriser les fenêtres contextuelles|
|**Autoriser les cookies**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Ne pas bloquer. Autoriser les cookies de tous les sites web (par défaut)<br>**1** – Bloquer uniquement les cookies tiers<br>**2** – Bloquer tous les cookies|
|**Autoriser l'enregistrement du mot de passe**<br>(Poste de travail et Mobile)|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Le gestionnaire de mots de passe est désactivé <br>**1** – Le gestionnaire de mots de passe est activé (par défaut)|
|**Autoriser le remplissage automatique**<br>(Poste de travail uniquement)|**Chemin complet de l’URI :** .//Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br>**0** – Désactivé (par défaut)<br>**1** – Activé|
|**Configurer la liste des sites d’entreprise**<br>(Poste de travail uniquement)|**Chemin d’accès complet des URI :** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :<br>0** – Non configuré<br>**1** – Utiliser la liste des sites d’entreprise d’Internet Explorer si configuré (par défaut)<br>**2** – Spécifier l’emplacement de la liste des sites d’entreprise|

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO1-->


