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

Utilisez la **stratégie de configuration générale** Microsoft pour Windows 10 pour configurer les paramètres généraux des appareils Windows 10 Mobile et Windows 10 Desktop inscrits :


### Mot de passe

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Exiger un mot de passe pour déverrouiller des appareils**|Exigez un mot de passe sur les appareils pris en charge.|Oui|Oui|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple, numérique uniquement ou alphanumérique|Oui|Oui|
|**Type de mot de passe requis** - **Nombre minimum de jeux de caractères**|Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe.|Oui|Oui|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères que le mot de passe de l’appareil doit contenir.|Non|Oui|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Réinitialise l'appareil si le nombre d'échecs de tentative de est atteint.|Oui|Oui|
|**Minutes d'inactivité avant arrêt de l'écran**|Spécifie la durée pendant laquelle l’appareil doit être inactif avant que l’écran de veille se verrouille.|Oui|Oui|
|**Expiration du mot de passe (jours)**|Spécifie la durée après laquelle le mot de passe d'un appareil doit être modifié.|Oui|Oui|
|**Mémoriser l'historique des mots de passe**|Spécifie si vous souhaitez empêcher l'utilisateur final de créer des mots de passe utilisés précédemment.|Oui|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.|Oui|Oui|
|**Autoriser un mot de passe image et un code confidentiel**|Vous permet d'utiliser des gestes simples sur une image ou un code confidentiel simple pour vous connecter.|Oui|Non|
|**Exiger un mot de passe quand l'appareil quitte un état inactif**|Si cette option est activée, l'utilisateur doit entrer un mot de passe pour déverrouiller l’appareil pour qu’il quitte l’état inactif.|Non|Oui|

### Chiffrement

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Exiger le chiffrement sur l'appareil mobile**|Active le chiffrement sur les appareils ciblés.|Non|Oui|

### d'exploitation

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser la capture d'écran**|Autorise l’utilisateur à capturer le contenu de l’écran d’appareil en tant qu’image.|Non|Oui|
|**Autoriser la désinscription manuelle**|Permet à l'utilisateur de supprimer manuellement le compte d'espace de travail de l'appareil|Oui|Oui|
|**Autoriser l'installation manuelle de certificats racines**|Spécifie si l'utilisateur peut installer des certificats racines manuellement|Non|Oui|
|**Autoriser l'envoi des données de diagnostic et d'utilisation à Microsoft**|Détermine la quantité de données de diagnostic et d'utilisation envoyées à Microsoft à partir des appareils.<br>**Non** - Aucune donnée n’est envoyée à Microsoft<br>**De Base** - L'appareil envoie uniquement des informations limitées à Microsoft<br>**Amélioré** - Envoie des données de diagnostic améliorées à Microsoft<br>**Complète (recommandée)** - envoie les mêmes données que **Amélioré**, ainsi que des données supplémentaires sur l'état de l’appareil|Oui|Oui|


### Compte et synchronisation

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser le compte Microsoft**|Permet à l'utilisateur d'associer un compte Microsoft à l’appareil.|Oui|Oui|
|**Autoriser l'ajout manuel de comptes non-Microsoft**|Permet à l'utilisateur d'ajouter des comptes de messagerie à l'appareil qui ne sont pas associés à un compte Microsoft.|Oui|Oui|
|**Autoriser la synchronisation des paramètres pour les comptes Microsoft**|Permet aux paramètres d’appareil et d'application associés à un compte Microsoft de se synchroniser entre les appareils.|Oui|Oui|

### Paramètres de messagerie

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Rendre le compte Microsoft facultatif dans l'application Windows Mail**|Configurez cette option pour supprimer l'obligation d’utiliser un compte Microsoft dans Windows Mail.|Oui|Non|



### Microsoft Edge

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser le navigateur web**|Permet d’utiliser le navigateur web Edge sur l’appareil.|Non|Oui|
|**Autoriser les suggestions de recherche dans la barre d'adresse**|Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche.|Oui|Oui|
|**Autoriser l'envoi du trafic intranet vers Internet Explorer**|Permet aux utilisateurs d’ouvrir des sites web intranet dans Internet Explorer.|Oui|Non|
|**Autoriser Do Not Track**|Configure le navigateur Edge pour envoyer des en-êtes Do Not Track aux sites Web que les utilisateurs visitent.|Oui|Oui|
|**Activer SmartScreen**|Active le paramètre de navigateur SmartScreen sur les appareils.|Oui|Oui|
|**Autoriser les scripts actifs**|Autoriser l'exécution de scripts, tels que JavaScript, dans le navigateur Edge.|Oui|Oui|
|**Autoriser les fenêtres contextuelles**|Active ou désactive le bloqueur de fenêtres publicitaires du navigateur.|Oui|Non|
|**Autoriser les cookies**|Autoriser ou désactiver les cookies.|Oui|Oui|
|**Autoriser le remplissage automatique**|Autoriser les utilisateurs à modifier les paramètres de saisie semi-automatique dans le navigateur.|Oui|Non|
|**Autoriser le gestionnaire de mots de passe**|Activer ou désactiver la fonctionnalité Gestionnaire de mots de passe Edge.|Oui|Oui|
|**Emplacement de la liste des sites en mode entreprise**|Indique où trouver la liste des sites web qui s'ouvrent en Mode entreprise. Les utilisateurs ne peuvent pas modifier cette liste.|Oui|Non|

### Applications

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser la boutique d'applications**|Autoriser l’utilisateur à accéder à l’App Store sur l’appareil.|Non|Oui|



### Cellulaire

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser l'itinérance des données**|Autorisez l'itinérance entre réseaux lors de l'accès aux données.|Oui|Oui|
|**Autoriser une connexion VPN sur un réseau cellulaire**|Contrôle si l’appareil peut accéder aux connexions VPN lorsqu'il est connecté à un réseau cellulaire.|Oui|Oui|
|**Autoriser l'itinérance VPN sur un réseau cellulaire**|Contrôle si l’appareil peut accéder aux connexions VPN lorsqu'il est en itinérance sur un réseau cellulaire.|Oui|Oui|

### Matériel

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser l'appareil photo**|Spécifie si l’appareil photo de l’appareil peut être utilisé.|Oui|Oui|
|**Autoriser le stockage amovible**|Spécifie si des périphériques de stockage externe telle une carte SD peuvent être utilisés avec l'appareil.|Oui|Oui|
|**Autoriser le Wi-Fi**|Autorise l’utilisation des fonctionnalités Wi-Fi de l’appareil.|Non|Oui|
|**Autoriser le partage Internet**|Autorise l'utilisation du partage de connexion Internet sur l'appareil.|Oui|Oui|
|**Autoriser la configuration manuelle du Wi-Fi**|Détermine si les utilisateurs peuvent configurer leurs propres connexions Wi-Fi ou s'ils peuvent uniquement utiliser les connexions configurées par un profil Wi-Fi.|Non|Oui|
|**Autoriser la connexion automatique aux points d'accès Wi-Fi gratuits**|Permet à l’appareil de se connecter automatiquement aux points d'accès Wi-Fi gratuits et d’accepter automatiquement les termes et conditions de la connexion.|Oui|Oui|
|**Autoriser la géolocalisation**|Spécifie si l'appareil peut utiliser les informations des services d'emplacement.|Oui|Oui|
|**Autoriser NFC**|Permet à l’appareil d’utiliser ses fonctionnalités NFC (Near Field Communications).|Oui|Oui|
|**Autoriser Bluetooth**|Permet d'utiliser les fonctionnalités Bluetooth de l'appareil.|Oui|Oui|
|**Autoriser le mode découvrable Bluetooth**|Permet à cet appareil d’être découvert par d'autres appareils Bluetooth.|Oui|Oui|
|**Autoriser la publicité Bluetooth**|Permet aux appareils de recevoir des publicités par Bluetooth.|Oui|Oui|
|**Autoriser le mode connectable Bluetooth** **Important :** |Ce paramètre n’est plus pris en charge par Windows 10 et sera supprimé à l’avenir.|Oui|Oui|
|**Autoriser la réinitialisation du téléphone**|Détermine si l'utilisateur peut rétablir les paramètres d'usine de son appareil.|Oui|Oui|
|**Autoriser la connexion USB**|Contrôle si les appareils peuvent accéder à des périphériques de stockage externe via une connexion USB.|Oui|Oui|
|**Autoriser le mode antivol**|Configurer si le mode antivol Windows est activé.|Oui|Oui|

### Fonctionnalités

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Autoriser la fonction copier-coller**|Active ou désactive l'utilisation du copier-coller sur l’appareil.|Non|Oui|
|**Autoriser l'enregistrement vocal**|Active ou désactive les fonctionnalités d’enregistrement de la voix sur l’appareil.|Non|Oui|
|**Autoriser Cortana**|Active ou désactive l'assistant vocal Cortana.|Oui|Oui|
|**Autoriser les notifications du centre de notifications**|Active ou désactive les notifications du centre de notifications sur l'écran de verrouillage de l'appareil.|Non|Oui|

### Defender

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|-|-|
|**Autoriser la surveillance en temps réel**|Active la recherche en temps réel des logiciels malveillants, logiciels espions et autres logiciels indésirables.|Oui|Non|
|**Autoriser l'analyse du comportement**|Permet à Defender de rechercher certains modèles connus d'activité suspecte sur les appareils.|Oui|Non
|**Activer le système NIS (Network Inspection System)**|Le système NIS (Network Inspection System) vous aide à protéger les appareils contre les attaques transmises via le réseau à l'aide de signatures de vulnérabilités connues fournies par le Microsoft Endpoint Protection Center afin de détecter et de bloquer tout trafic malveillant.|Oui|Non
|**Analyser tous les téléchargements**|Contrôle si Defender analyse tous les fichiers téléchargés depuis Internet.|Oui|Non
|**Autoriser l'analyse de scripts**|Configure Defender pour analyser les scripts utilisés dans Internet Explorer Defender.|Oui|Non
|**Surveiller l'activité des fichiers et des programmes**|Activez ce paramètre pour autoriser Defender à surveiller l'activité des fichiers et des programmes sur les appareils.|Oui|Non
|**Durée du suivi des logiciels malveillants dont le cas a été résolu (en jours)**|Permet à Defender de continuer à suivre les logiciels malveillants résolus pendant un certain nombre de jours que vous spécifiez, pour vous permettre de vérifier manuellement les appareils affectés. Si vous définissez le nombre de jours du suivi sur **0**, les logiciels malveillants restent dans le dossier de quarantaine et ne sont pas automatiquement supprimés. |Oui|Non
|**Autoriser l'accès à l'interface utilisateur cliente**|Détermine si l'interface utilisateur de Windows Defender est masquée aux utilisateurs finaux.<br>Lorsque ce paramètre est modifié, le changement est appliqué au prochain redémarrage de l'ordinateur de l'utilisateur final.|Oui|Non
|**Planifier une analyse quotidienne rapide**|Permet de planifier une analyse rapide exécutée tous les jours à l’heure de votre choix.|Oui|Non
|**Planifier une analyse système**|Vous permet de planifier une analyse système complète ou rapide exécutée régulièrement le jour et à l’heure de votre choix.|Oui|Non
|**Limiter l'utilisation du processeur lors d'une analyse à**|Vous permet de limiter la quantité de ressources du processeur que les analyses sont autorisées à utiliser (de **1** à **100**))|Oui|Non
|**Analyser les fichiers d'archives**|Permet à Defender d'analyser les fichiers archivés tels que les archives Zip ou Cab.|Oui|Non
|**Analyser les messages électroniques**|Permet à Defender d’analyser les messages électroniques lorsqu'ils arrivent sur l’appareil.|Oui|Non
|**Analyser les lecteurs amovibles**|Permet à Defender d'analyser les lecteurs amovibles tels que les clés USB.|Oui|Non
|**Analyser les lecteurs réseau mappés**|Permet à Defender d'analyser les fichiers sur un lecteur réseau mappé.<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|Oui|Non
|**Analyser les fichiers ouverts à partir de dossiers partagés sur le réseau**|Permet à Defender d'analyser les fichiers sur des lecteurs réseau partagés (par exemple, les lecteurs accessibles à partir d'un chemin d'accès UNC).<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|Oui|Non
|**Intervalle de mise à jour des signatures**|Spécifiez l'intervalle auquel Defender vérifie les nouveaux fichiers de signatures.|Oui|Non
|**Autoriser la protection de cloud**|Autorisez ou empêchez Microsoft Active Protection Service de recevoir des informations sur l'activité des logiciels malveillants à partir des appareils que vous gérez. Ces informations serviront à améliorer le service.|Oui|Non
|**Demander aux utilisateurs d'envoyer des exemples**|Contrôle si les fichiers susceptibles de nécessiter une analyse plus approfondie de la part de Microsoft pour déterminer s’il s’agit de logiciels malveillants sont automatiquement envoyés à Microsoft.|Oui|Non
|**Fichiers et dossiers à exclure lors de l'exécution d'une analyse ou de l'utilisation de la protection en temps réel**|Ajoutez un ou plusieurs fichiers et dossiers comme **C:\Path** ou **%ProgramFiles%\Path\filename.exe** à la liste des exclusions. Ces fichiers et dossiers ne seront pas inclus dans les analyses en temps réel ou planifiées.|Oui|Non
|**Extensions de fichier à exclure lors d'une analyse ou de la protection en temps réel**|Ajoutez une ou plusieurs extensions de fichier comme **jpg** ou **txt** à la liste des exclusions. Tous les fichiers avec ces extensions ne seront pas inclus dans les analyses en temps réel ou planifiées.|Oui|Non
|**Processus à exclure lors d'une analyse ou de la protection en temps réel**|Ajoutez un ou plusieurs processus du type **.exe**, **.com**, ou **.scr** à la liste des exclusions. Ces processus ne seront pas inclus dans les analyses en temps réel ou planifiées.|Oui|Non| 


### Paramètres des mises à jour

|Nom du paramètre|Détails|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Autoriser les mises à jour automatiques**|Activez ce paramètre pour autoriser les mises à jour automatiques. Ensuite, configurez l'un des paramètres suivants pour contrôler le comportement de mise à jour :<br /><br />**Notification de téléchargement**<br /><br />**Installer automatiquement au moment de la maintenance**<br /><br />**Installer et redémarrer automatiquement au moment de la maintenance**<br /><br />**Installer et redémarrer automatiquement au moment planifié** **Remarque :** quand cette option est sélectionnée, vous pouvez aussi configurer les paramètres suivants : **Supprimer la notification à l'utilisateur final** et **Définir un jour d'installation pour les mises à jour planifiées**.|Oui|Non|

## Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée** Microsoft Intune pour Windows 10 et Windows 10 Mobile afin de déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui permettent de contrôler les fonctionnalités des appareils Windows 10 et Windows 10 Mobile. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Windows 10 qui ne sont pas configurables avec une stratégie de configuration générale Intune. Pour plus d’informations sur les paramètres que vous pouvez configurer avec ces stratégies, consultez [Gérer les paramètres et les fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Pour obtenir la liste des paramètres OMA-URI que vous pouvez configurer sur des appareils Windows 10 inscrits, consultez Paramètres URI personnalisés pour les appareils Windows 10 plus loin dans cette rubrique.

### Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Entrez un nom unique pour la stratégie afin de vous aider à l’identifier dans la console Intune.|
    |**Description**|Entrez une description générale de la stratégie et d'autres informations pertinentes pour faciliter sa localisation.|

### Paramètres OMA-URI

|Nom du paramètre|Détails|
    |--------|--------------------|
    |**Nom du paramètre**|Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.|
    |**Description du paramètre**|Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.|
    |**Type de données**|Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez parmi :<br /><br />-   **Chaîne**<br />-   **Chaîne (XML)**<br />-   **Date et heure**<br />-   **Entier**<br />-   **Virgule flottante**<br />-   **Booléen**|
    |**OMA-URI (sensible à la casse)**|Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.|
    |**Valeur**|Spécifiez la valeur à associer à l'identificateur OMA-URI spécifié précédemment.|


## Paramètres URI personnalisés pour les appareils Windows 10
Cette rubrique répertorie les paramètres que vous pouvez configurer sur les appareils Windows 10 et Windows 10 Mobile dans le cadre d'une **stratégie personnalisée Windows 10** Microsoft Intune.


> [!NOTE]
> Dans la colonne **Prend en charge** du tableau suivant, les valeurs suivantes sont utilisées :
> 
> -   **Bureau** : le paramètre prend uniquement en charge les ordinateurs Windows 10 Professionnel et Entreprise qui sont inscrits auprès d’Intune.
> -   **Mobile** : le paramètre prend uniquement en charge les appareils Windows 10 Mobile.
> -   **Les deux** : le paramètre prend en charge les ordinateurs de bureau et les appareils mobiles.
> 
> Si vous souhaitez utiliser la stratégie URI personnalisée Windows, tous les appareils doivent être inscrits auprès d’Intune.

### Stratégie

|Nom de la stratégie|Prend en charge|Détails|
|---------------|------------|-----------|
|**​AllowAutoUpdate**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :0** - **5**<br /><br />**Valeur par défaut :** 1|
|**ScheduledInstallDay**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - Tous les jours<br /><br />**1** - Dimanche<br /><br />**2** - Lundi<br /><br />**3** - Mardi<br /><br />**4** - Mercredi<br /><br />**5** - Jeudi<br /><br />**6** - Vendredi<br /><br />**7** - Samedi<br /><br />**Valeur par défaut :** 0|
|**ScheduledInstallTime**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :0** à **23** heures (0 correspond à minuit)<br /><br />**Valeur par défaut :** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - L’utilisateur ne peut pas définir le minuteur de la période de grâce du mot de passe, et la valeur « chaque fois » est définie.<br /><br />**1** - L’utilisateur peut définir le minuteur de la période de grâce du mot de passe.<br /><br />**Valeur par défaut :** 1|
|**WiFi/AllowWiFi**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas autoriser **Utiliser la connexion Wi-Fi**.<br /><br />**1** – Autoriser **Utiliser la connexion Wi-Fi**.<br /><br />**Valeur par défaut :** 1|
|**WiFi/AllowInternetSharing**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas autoriser le partage Internet.<br /><br />**1** – Autoriser le partage Internet.<br /><br />**Valeur par défaut :** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**WiFi/AllowManualWiFiConfiguration**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Aucune connexion non-Wi-Fi en dehors de celles approvisionnées par la Gestion des appareils mobiles n’est autorisée.<br /><br />**1** – L'ajout de nouveaux SSID réseau au-delà de ceux approvisionnés par MDM est autorisé.<br /><br />**Valeur par défaut :** 1|
|**System/AllowLocation**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**System/AllowTelemetry**|Les deux|**Chemin complet à l’URI : **./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé (paramètre Entreprise uniquement)<br /><br />**1** – Limité<br /><br />**2** – Complet<br /><br />**3** – Complet et informations de diagnostic<br /><br />**Valeur par défaut :** 2|
|**System/AllowExperimentation**|Les deux|**Chemin complet de l’URI : **./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Paramètres uniquement<br /><br />**2** – Paramètres et expérimentation<br /><br />**Valeur par défaut :** 1|
|**Security/AntiTheftMode**|Mobile|**Chemin complet à l’URI :** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas autoriser le mode antivol<br /><br />**1** – Préférence utilisateur<br /><br />**Valeur par défaut :** 1|
|**Connectivity/AllowUSBConnection**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**System/AllowUserToResetPhone**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Connectivity/AllowCellularDataRoaming**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Connectivity/AllowVPNOverCellular**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Un VPN n’est pas autorisé sur une connexion cellulaire.<br /><br />**1** – Un VPN peut utiliser n'importe quelle connexion, y compris une connexion cellulaire.<br /><br />**Valeur par défaut :** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Connectivity/AllowBluetooth**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas autoriser l'utilisateur à activer le Bluetooth.<br /><br />**1** – Réservé. L'utilisateur peut activer et configurer le Bluetooth (non pris en charge dans Windows Phone 8.1 pour MDM, EAS, Windows 10 Desktop ou Windows 10 Mobile)<br /><br />**2** - Autorisé. L'utilisateur peut activer et configurer le Bluetooth.<br /><br />**Valeur par défaut :** 2|
|**Experience/AllowScreenCapture**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Experience/AllowTaskSwitcher**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Experience/AllowVoiceRecording**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Experience/AllowSyncMySettings**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas autoriser l'itinérance<br /><br />**1** – Autoriser l'itinérance<br /><br />**Valeur par défaut :** 1|
|**Experience/AllowManualMDMUnenrollment**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Security/AllowManualRootCertificateInstallation**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Security/AllowAddProvisioningPackages**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Search/DisableBackoff**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 0|
|**Search/PreventRemoteQueries**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 1|
|**Search/AllowUsingDiacritics**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 0|
|**Search/AlwaysUseAutoLangDetection**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 0|
|**Search/DisableRemovableDriveIndexing**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 0|
|**Security/AllowRemoveProvisioningPackage**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Security/RequireProvisioningPackageSignature**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0**<br /><br />**1**<br /><br />**Valeur par défaut :** 0|
|**AboveLock/AllowActionCenterNotifications**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowIMENetworkAccess**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas autoriser<br /><br />L'ouverture du dictionnaire étendu est désactivée.<br /><br />Un utilisateur ne peut pas :<br /><br />ajouter un nouveau dictionnaire d'étendu ouvert ;<br /><br />ajouter un nouveau fichier de configuration d'intégration de la recherche ;<br /><br />utiliser la fonctionnalité de candidat de cloud ;<br /><br />envoyer un mot inscrit par l'utilisateur.<br /><br />En outre :<br /><br />Un dictionnaire étendu ouvert qui a été ajouté avant l'activation de ce paramètre de stratégie n'est pas utilisé pour la conversion.<br /><br />Un fichier de configuration d'intégration de la recherche qui a été installé avant d'activer ce paramètre de stratégie n'est pas utilisé.<br /><br />**1** - Autoriser<br /><br />Un dictionnaire étendu ouvert peut être ajouté et utilisé par défaut. Par ailleurs, la fonction d'intégration de la recherche peut être utilisée par défaut.<br /><br />Un utilisateur peut :<br /><br />utiliser la fonctionnalité de candidat de cloud ;<br /><br />envoyer un mot inscrit par l'utilisateur.<br /><br />**Valeur par défaut :**|
|**TextInput/AllowKoreanExtendedHanja**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowIMELogging**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - La journalisation des erreurs de conversion est désactivée. Les données réglées automatiquement et les données d'historique d'entrée ne sont pas enregistrées dans un fichier.<br /><br />**1** - La journalisation des erreurs de conversion est activée. Les données réglées automatiquement et les données d'historique d'entrée sont enregistrées dans un fichier.<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowJapaneseUserDictionary**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - Tous les caractères sont filtrés, sauf les caractères JIS.<br /><br />**1** - Aucun caractère n’est filtré.<br /><br />**Valeur par défaut :** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - Tous les caractères sont filtrés, sauf les caractères JIS0208.<br /><br />**1** - Aucun caractère n’est filtré.<br /><br />**Valeur par défaut :** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - Tous les caractères sont filtrés, sauf les caractères JIS0208 ou EUDC.<br /><br />**1** - Aucun caractère n’est filtré.<br /><br />**Valeur par défaut :** 1|
|**TextInput/AllowInputPanel**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Bluetooth/AllowDiscoverableMode**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Bluetooth/AllowAdvertising**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowDataSense**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowVPN**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowWorkplace**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowDateTime**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowLanguage**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowRegion**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowSignInOptions**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowYourAccount**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowPowerSleep**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Settings/AllowAutoPlay**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Experience/AllowCortana**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**Search/SafeSearchPermissions**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Strict, niveau de filtrage le plus élevé en matière de contenu pour adultes.<br /><br />**1** – Modéré, niveau de filtrage modéré en matière de contenu pour adultes (les résultats de recherche valides ne sont pas filtrés).<br /><br />**Valeur par défaut :** 1|
|**Experience/AllowCopyPaste**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**ForceStartSize**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - Autoriser l’utilisateur à modifier la taille.<br /><br />**1** - Forcer un affichage n’utilisant pas le plein écran.<br /><br />**1** - Forcer le plein écran.<br /><br />**Valeur par défaut :** 0|
|**Update/RequireDeferUpgrade**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** : ne pas reporter la mise à niveau (rester dans la branche active, CB)<br /><br />**1** : activer le report des mises à jour et des mises à niveau (l’appareil suit les règles de la branche actuelle d’entreprise, CBB)<br /><br />**Valeur par défaut : 0**<br /><br />Pour plus d'informations, voir :<br /><br />[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Les deux|**Description :** stratégie de report des mises à jour logicielles pendant quatre semaines<br /><br />**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :** 0 : appliquer les mises à jour immédiatement ; 1-4 : nombre de semaines desquelles différer les mises à jour logicielles.<br /><br />**Valeur par défaut : 0**<br /><br /><br />Pour plus d'informations, voir :<br /><br />[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Les deux|**Description :** stratégie de report des mises à niveau des fonctionnalités jusqu’à huit mois<br /><br />**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :** 0 : appliquer les mises à jour immédiatement ; 1-8 : nombre de mois desquels différer les mises à niveau des fonctionnalités.<br /><br />**Valeur par défaut : 0**<br /><br />Pour plus d'informations, voir :<br /><br />[Introduction à la maintenance de Windows 10](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan de déploiement de Windows 10](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Les deux|**Description :** autorise un ordinateur CBB à arrêter de recevoir des mises à jour et des mises à niveau pendant cinq semaines. Cela doit être utilisé en cas de problème avec une mise à jour.<br /><br />**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** : appliquer immédiatement les mises à jour (par défaut)<br /><br />**1**: suspendre les mises à jour et les mises à niveau (expire au bout de cinq semaines)<br /><br />**Valeur par défaut : 0**|

### Windows Defender

|Nom de la stratégie|Prend en charge|Détails|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowBehaviorMonitoring**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowIntrusionPreventionSystem**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowIOAVProtection**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowScriptScanning**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowOnAccessProtection**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**RealTimeScanDirection**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Analyser tous les fichiers (analyse bidirectionnelle)<br /><br />**1** – Analyser les fichiers entrants<br /><br />**2** – Analyser les fichiers sortants<br /><br />**Valeur par défaut :** 0|
|**DaysToRetainCleanedMalware**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** - **90** – Représente la durée pendant laquelle les logiciels malveillants sont conservés<br /><br />**Valeur par défaut :** 0 – Les logiciels malveillants sont conservés indéfiniment dans le dossier de quarantaine et ne sont pas supprimés automatiquement|
|**AllowUserUIAccess**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**ScanParameter**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**1** – Analyse rapide<br /><br />**2** – Analyse complète<br /><br />**Valeur par défaut :** 1|
|**ScheduleScanDay**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** - Tous les jours<br /><br />**1** - Lundi<br /><br />**2** - Mardi<br /><br />**3** - Mercredi<br /><br />**4** - Jeudi<br /><br />**5** - Vendredi<br /><br />**6** - Samedi<br /><br />**7** - Dimanche<br /><br />**8** - Aucune analyse planifiée<br /><br />**Valeur par défaut :** 0|
|**ScheduleScanTime**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – 00:00<br /><br />**60** – 1:00<br /><br />**120** – 2:00<br /><br />**180** – 3:00<br /><br />**240** – 4:00<br /><br />**300** – 5:00<br /><br />**360** – 6:00<br /><br />**420** – 7:00<br /><br />**480** – 8:00<br /><br />**540** – 9:00<br /><br />**600** – 10:00<br /><br />**660** – 11:00<br /><br />**720** – 12:00<br /><br />**780** – 13:00<br /><br />**840** – 14:00<br /><br />**900** – 15:00<br /><br />**960** – 16:00<br /><br />**1020** – 17:00<br /><br />**1080** – 18:00<br /><br />**1140** – 19:00<br /><br />**1200** – 20:00<br /><br />**1260** – 21:00<br /><br />**1320** – 22:00<br /><br />**1381** – Fenêtre de maintenance<br /><br />**Valeur par défaut :** 120|
|**ScheduleQuickScanTime**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – 00:00<br /><br />**60** – 1:00<br /><br />**120** – 2:00<br /><br />**180** – 3:00<br /><br />**240** – 4:00<br /><br />**300** – 5:00<br /><br />**360** – 6:00<br /><br />**420** – 7:00<br /><br />**480** – 8:00<br /><br />**540** – 9:00<br /><br />**600** – 10:00<br /><br />**660** – 11:00<br /><br />**720** – 12:00<br /><br />**780** – 13:00<br /><br />**840** – 14:00<br /><br />**900** – 15:00<br /><br />**960** – 16:00<br /><br />**1020** – 17:00<br /><br />**1080** – 18:00<br /><br />**1140** – 19:00<br /><br />**1200** – 20:00<br /><br />**1260** – 21:00<br /><br />**1320** – 22:00<br /><br />**1380** – 23:00<br /><br />**Valeur par défaut :** 120|
|**AVGCPULoadFactor**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :0** - **100**<br /><br />**Valeur par défaut :** 50|
|**AllowArchiveScanning**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowEmailScanning**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 0|
|**AllowFullScanRemovableDriveScanning**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 0|
|**AllowFullScanOnMappedNetworkDrives**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**AllowScanningNetworkFiles**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1 – S'exécute également quand RTP est activé quand la valeur Autorisé est définie|
|**SignatureUpdateInterval**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Ne pas vérifier les signatures par intervalle<br /><br />**1** – Vérifier les signatures toutes les heures<br /><br />**2** – Vérifier les signatures toutes les 2 heures, etc.<br /><br />**24** – Vérifier les signatures tous les jours<br /><br />**Valeur par défaut :** 8 – Vérifier les signatures toutes les 8 heures|
|**AllowCloudProtection**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Non autorisé<br /><br />**1** – Autorisé<br /><br />**Valeur par défaut :** 1|
|**SubmitSamplesConsent**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées :**<br /><br />**0** – Toujours demander<br /><br />**1** – Envoyer automatiquement des échantillons sécurisés<br /><br />**2** – Ne jamais envoyer<br /><br />**3** – Envoyer automatiquement tous les échantillons<br /><br />**Valeur par défaut :** 0|
|**ExcludedExtensions**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :**<br /><br />*&lt;liste d’extensions séparées par des points-virgules&gt;* Par exemple : **obj;lib**<br /><br />**Valeur par défaut :** Aucune extension n’est exclue.|
|**ExcludedPaths**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :**<br /><br />*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br /><br />Exemple : **c:\test;c:\test1.exe**<br /><br />**Valeur par défaut :** Aucun chemin n’est exclu.|
|**ExcludedProcesses**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées :**<br /><br />*&lt;liste de chemins d'accès séparés par des points-virgules&gt;*<br /><br />Exemple : **c:\test.exe;c:\test1.exe**<br /><br />**Valeur par défaut :** Aucun processus n’est exclu.|

### Navigateur Edge

|Nom de la stratégie|Prend en charge|Détails|
|---------------|------------|-----------|
|**Autoriser ce navigateur**|Mobile|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** : navigation désactivée ; **1** : navigation activée.<br /><br />**Valeur par défaut :** 1|
|**AllowSearchSuggestionsinAddressBar**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** : ne pas afficher les suggestions de recherche ; **1** : afficher les suggestions.<br /><br />**Valeur par défaut :** 1|
|**SendIntranetTraffictoInternetExplorer**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** : Désactivé (ouvrir les sites intranet dans le navigateur Edge) ; **1** : Activé (ouvrir les sites intranet dans Internet Explorer).<br /><br />**Valeur par défaut :** 0|
|**Autoriser Do Not Track**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** – Désactivé (DNT non envoyé) ;  **1** : Activé (envoyer DNT)<br /><br />**Valeur par défaut :** 0|
|**Configurer SmartScreen**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** – Ne pas autoriser ; **1** – Autoriser<br /><br />**Valeur par défaut :** 1|
|**Autoriser les fenêtres contextuelles**|Bureau|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** – Bloquer les fenêtres contextuelles ; **1** : Autoriser les fenêtres contextuelles<br /><br />**Valeur par défaut :** 0|
|**Autoriser les cookies**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** – Ne pas bloquer. Autoriser les cookies de tous les sites web ; **1** – Bloquer uniquement les cookies tiers ; **2** – Bloquer tous les cookies<br /><br />**Valeur par défaut :** 0|
|**Autoriser l'enregistrement du mot de passe**|Les deux|**Chemin complet de l’URI :** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** – Le gestionnaire de mots de passe est désactivé ; <br />                        **1** – Le gestionnaire de mots de passe est activé<br /><br />**Valeur par défaut :** 1|
|**Autoriser le remplissage automatique**|Bureau|**Chemin complet de l’URI :** .//Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Type de données :** Entier<br /><br />**Valeurs autorisées : 0** – Désactivé ; **1** : Activé<br /><br />**Valeur par défaut :** 0|
|**Configurer la liste des sites d’entreprise**|Bureau|**Chemin d’accès complet des URI :** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Type de données : ** Chaîne<br /><br />**Valeurs autorisées : 0** - Non configuré ; **1** - Utiliser la liste des sites en Mode entreprise d’Internet Explorer si elle est configurée ; **2** – Spécifier l’emplacement dans la liste des sites<br /><br />**Valeur par défaut :** 1|

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


