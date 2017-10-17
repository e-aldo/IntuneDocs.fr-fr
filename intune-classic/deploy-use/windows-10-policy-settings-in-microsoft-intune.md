---
title: "Paramètres de la stratégie dans Windows 10"
description: "Utilisez les paramètres de stratégie indiqués dans cette rubrique pour configurer les paramètres intégrés et personnalisés des appareils Windows 10 Mobile et Windows 10 Desktop inscrits."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fa802c1e84a4f40a8b67a6faa84edb8e5843025e
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Paramètres de stratégie Intune pour les appareils Windows 10 dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique contient des informations qui vous aideront à comprendre les paramètres de stratégie Intune que vous pouvez utiliser pour gérer des appareils Windows 10. Lisez cette rubrique et les procédures dans [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

Vous pouvez choisir parmi deux types de stratégie :

- **Stratégie personnalisée** : Utilisez la **stratégie personnalisée** Microsoft Intune pour Windows 10 et Windows 10 Mobile pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils. Dans Windows 10, de nombreux paramètres CSP sont disponibles, par exemple le [fournisseur de services de configuration de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Stratégie de configuration générale** : Utilisez ce type de stratégie quand vous voulez sélectionner des paramètres à partir d’une liste prédéfinie fournie dans Microsoft Intune.

## <a name="custom-policy-settings"></a>Paramètres de la stratégie personnalisée

Fournissez les paramètres suivants dans une stratégie personnalisée.

### <a name="general-settings"></a>Paramètres généraux :

Entrez un nom et une éventuelle description pour cette stratégie pour l’identifier facilement dans la console Intune.

### <a name="oma-uri-settings"></a>Paramètres OMA-URI

Pour chaque paramètre OMA-URI à ajouter, entrez les informations suivantes :

- **Nom du paramètre** : Affectez un nom unique au paramètre OMA-URI pour mieux l’identifier dans la liste des paramètres. Vous trouverez plus d’informations sur les paramètres de l’URI à l’aide du [fournisseur de services de configuration de stratégie](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Description du paramètre** : Si vous le souhaitez, entrez une description du paramètre.
- **Type de données** : Choisissez parmi les types de données suivants :
    - **Chaîne**
    - **Chaîne (XML)**
    - **Date et heure**
    - **Entier**
    - **Virgule flottante**
    - **Booléen**
- **OMA-URI (sensible à la casse)** : Spécifiez l’identificateur OMA-URI pour lequel vous voulez fournir un paramètre.
- **Valeur** : Spécifiez la valeur à associer à l’identificateur OMA-URI que vous avez entré.

### <a name="example"></a>Exemple
Dans la capture d’écran ci-après, le paramètre **Connectivity/AllowVPNOverCellular** a été activé. Il permet à un appareil Windows 10 d’ouvrir une connexion VPN sur un réseau de téléphonie mobile.

> ![Exemple de stratégie personnalisée contenant des paramètres VPN](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>Comment trouver les stratégies que vous pouvez configurer

Vous trouverez une liste complète de tous les fournisseurs de services de configuration pris en charge par Windows 10 dans la [référence de fournisseur de services de configuration](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) dans la bibliothèque de documentation de Windows.

Les paramètres ne sont pas tous compatibles avec toutes les versions de Windows 10. Le tableau de la rubrique Windows indique quelles versions sont prises en charge pour chaque fournisseur de services de configuration.

De plus, Intune ne prend pas en charge tous les paramètres mentionnés dans la rubrique. Pour savoir si Intune prend en charge le paramètre de votre choix, ouvrez la rubrique relative à ce paramètre. Chaque page de paramètre indique ses opérations prises en charge. Pour fonctionner avec Intune, le paramètre doit prendre en charge les opérations **Ajouter** ou **Remplacer**.

## <a name="general-configuration-policy-settings"></a>Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale** Microsoft Intune pour Windows 10 pour configurer les paramètres intégrés des appareils Windows 10 Desktop et Windows 10 Mobile inscrits.

### <a name="password"></a>Mot de passe

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Exiger un mot de passe pour déverrouiller des appareils**|-|
|**Type de mot de passe requis**|Spécifie si le mot de passe doit être alphanumérique ou numérique uniquement|
|**Type de mot de passe requis** - **Nombre minimum de jeux de caractères**| Spécifie le nombre de jeux de caractères (lettres minuscules, lettres majuscules, chiffres et symboles) à inclure dans le mot de passe|
|**Longueur minimale du mot de passe**|S’applique à Windows 10 Mobile uniquement|
|**Nombre d’échecs de connexion répétée autorisé avant réinitialisation de l’appareil**.|Pour les appareils exécutant Windows 10 : si BitLocker est activé sur l’appareil, ce dernier passe en mode de récupération BitLocker après le nombre d’échecs de connexion que vous avez spécifié. Si BitLocker n’est pas activé sur l’appareil, alors ce paramètre ne s’applique pas.<br>Pour les appareils exécutant Windows 10 Mobile : après le nombre d’échecs de connexion que vous spécifiez, l’appareil est réinitialisé.|
|**Minutes d’inactivité avant arrêt de l’écran**|Spécifie la durée pendant laquelle l’appareil doit être inactif avant le verrouillage de l’écran|
|**Expiration du mot de passe (jours)**|Spécifie la durée après laquelle le mot de passe d’un appareil doit être modifié|
|**Mémoriser l’historique des mots de passe**|Spécifie si l’utilisateur peut ou non créer des mots de passe utilisés précédemment|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil|
|**Exiger un mot de passe quand l’appareil quitte un état inactif**|Spécifie que l’utilisateur doit entrer un mot de passe pour déverrouiller l’appareil (Windows 10 Mobile uniquement)|

### <a name="encryption"></a>Chiffrement

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Exiger le chiffrement sur l'appareil mobile**|Active le chiffrement sur les appareils ciblés<br>(Windows 10 Mobile uniquement)|

### <a name="system"></a>Système

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Autoriser la capture d’écran**|Permet à l’utilisateur de capturer l’écran de l’appareil sous forme d’image (Windows 10 Mobile uniquement)|
|**Autoriser la désinscription manuelle**|Permet à l’utilisateur de supprimer manuellement le compte d’espace de travail de l’appareil|
|**Autoriser l'installation manuelle de certificats racines**|S’applique à Windows 10 Mobile|
|**Autoriser l’envoi des données de diagnostic et d’utilisation à Microsoft**|Les valeurs possibles sont les suivantes :<br><br>**Non** - Aucune donnée n’est envoyée à Microsoft<br>**Basique** - Une quantité limitée d’informations est envoyée à Microsoft<br>**Amélioré** - Des données de diagnostic avancées sont envoyées à Microsoft<br>**Complète (recommandée)** - envoie les mêmes données que **Amélioré**, ainsi que des données supplémentaires sur l'état de l’appareil|


### <a name="account-and-synchronization"></a>Compte et synchronisation

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser le compte Microsoft**|Permet à l’utilisateur d’associer un compte Microsoft à l’appareil|
|**Autoriser l’ajout manuel de comptes non-Microsoft**|Permet à l’utilisateur d’ajouter des comptes de messagerie à l’appareil qui ne sont pas associés à un compte Microsoft|
|**Autoriser la synchronisation des paramètres pour les comptes Microsoft**|Permet aux paramètres d’appareil et d’application associés à un compte Microsoft de se synchroniser entre les appareils|

### <a name="microsoft-edge"></a>Microsoft Edge

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Autoriser le navigateur web**|Permet d’utiliser le navigateur web Microsoft Edge sur l’appareil<br>(Windows 10 Mobile uniquement)|
|**Autoriser les suggestions de recherche dans la barre d’adresse**|Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche|
|**Autoriser l’envoi du trafic intranet vers Internet Explorer**|Permet aux utilisateurs d’ouvrir des sites web intranet dans Internet Explorer<br>(Windows 10 Desktop uniquement)|
|**Autoriser Do Not Track**|Configure le navigateur Microsoft Edge pour envoyer des en-êtes Do Not Track aux sites web que les utilisateurs visitent|
|**Activer SmartScreen**||
|**Autoriser les scripts actifs**|Autorise l’exécution de scripts, tels que JavaScript, dans le navigateur Microsoft Edge|
|**Autoriser les fenêtres indépendantes**|S’applique à Windows 10 Desktop uniquement|
|**Autoriser les cookies**||
|**Autoriser le remplissage automatique**|Permet aux utilisateurs de modifier les paramètres de saisie semi-automatique dans le navigateur<br>(Windows 10 Desktop uniquement)|
|**Autoriser le gestionnaire de mots de passe**|Active ou désactive la fonctionnalité Gestionnaire de mots de passe Microsoft Edge|
|**Emplacement de la liste des sites en mode entreprise**|Indique où trouver la liste des sites web qui s’ouvrent en Mode entreprise. Les utilisateurs ne peuvent pas modifier cette liste.<br>(Windows 10 Desktop uniquement)|

### <a name="apps"></a>Applications

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser la boutique d’applications**|S’applique à Windows 10 Mobile uniquement|



### <a name="cellular"></a>Cellulaire

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser l’itinérance des données**|Autorisez l’itinérance entre réseaux lors de l’accès aux données.|
|**Autoriser une connexion VPN sur un réseau cellulaire**|Détermine si l’appareil peut accéder aux connexions VPN quand il est connecté à un réseau cellulaire.|
|**Autoriser l’itinérance VPN sur un réseau cellulaire**|Détermine si l’appareil peut accéder aux connexions VPN quand il est en itinérance sur un réseau cellulaire.|

### <a name="hardware"></a>Matériel

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|
|**Autoriser l’appareil photo**|-|
|**Autoriser le stockage amovible**|Spécifie si des appareils de stockage externe comme une carte SD peuvent être utilisés avec l’appareil.|
|**Autoriser le Wi-Fi**|S’applique à Windows 10 Mobile uniquement|
|**Autoriser le partage Internet**|Autorise l’utilisation du partage de connexion Internet sur l’appareil|
|**Autoriser la configuration manuelle du Wi-Fi**|Détermine si les utilisateurs peuvent configurer leurs propres connexions Wi-Fi ou s’ils peuvent uniquement utiliser les connexions configurées par un profil Wi-Fi.<br>(Windows 10 Mobile uniquement)|
|**Autoriser la connexion automatique aux points d’accès Wi-Fi gratuits**|Permet à l’appareil de se connecter automatiquement aux points d’accès Wi-Fi gratuits et d’accepter automatiquement les termes et conditions de la connexion.|
|**Autoriser la géolocalisation**|Spécifie si l’appareil peut utiliser les informations des services d’emplacement.|
|**Autoriser NFC**|Permet à l’appareil d’utiliser ses fonctionnalités NFC (Near Field Communications).|
|**Autoriser Bluetooth**|-|
|**Autoriser le mode découvrable Bluetooth**|Permet à cet appareil d’être découvert par d’autres appareils Bluetooth.|
|**Autoriser la publicité Bluetooth**|Permet aux appareils de recevoir des publicités par Bluetooth.|
|**Autoriser la réinitialisation du téléphone**|Détermine si l’utilisateur peut rétablir les paramètres d’usine de son appareil|
|**Autoriser la connexion USB**|Détermine si les appareils peuvent accéder à des appareils de stockage externe par le biais d’une connexion USB.|
|**Autoriser le mode antivol**|Détermine si le mode antivol Windows est activé|

### <a name="features"></a>Fonctionnalités

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser la fonction copier-coller**|S’applique à Windows 10 Mobile uniquement|
|**Autoriser l’enregistrement vocal**|S’applique à Windows 10 Mobile uniquement|
|**Autoriser Cortana**|Active ou désactive l’assistant vocal Cortana.|
|**Autoriser les notifications du centre de notifications**|Active ou désactive les notifications du centre de notifications sur l’écran de verrouillage de l’appareil.<br>(Windows 10 Mobile uniquement)|

### <a name="windows-defender"></a>Windows Defender

Tous les paramètres sont pour Windows 10 Desktop uniquement.

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|----------------------|---------------------|
|**Autoriser la surveillance en temps réel**|Active la recherche en temps réel des logiciels malveillants, logiciels espions et autres logiciels indésirables|
|**Autoriser l’analyse du comportement**|Permet à Defender de rechercher certains modèles connus d’activité suspecte sur les appareils|
|**Activer le système NIS (Network Inspection System)**|Le système NIS (Network Inspection System) vous aide à protéger les appareils contre les attaques réseau à l’aide de signatures de vulnérabilités connues fournies par le Microsoft Endpoint Protection Center afin de détecter et de bloquer tout trafic malveillant|
|**Analyser tous les téléchargements**|Détermine si Defender analyse tous les fichiers téléchargés à partir d’Internet|
|**Autoriser l’analyse de scripts**|Configure Defender pour analyser les scripts utilisés dans Internet Explorer Defender|
|**Surveiller l’activité des fichiers et des programmes**|Autorise Defender à surveiller l’activité des fichiers et des programmes sur des appareils|
|**Durée du suivi des logiciels malveillants dont le cas a été résolu (en jours)**|Permet à Defender de continuer à suivre les logiciels malveillants résolus pendant un certain nombre de jours que vous spécifiez, pour vous permettre de vérifier manuellement les appareils affectés. Si vous définissez le nombre de jours du suivi sur **0**, les logiciels malveillants restent dans le dossier de quarantaine et ne sont pas automatiquement supprimés. |
|**Autoriser l’accès à l’interface utilisateur cliente**|Détermine si l’interface utilisateur de Windows Defender est masquée pour les utilisateurs.<br>Lorsque ce paramètre est modifié, le changement est appliqué au prochain redémarrage de l’ordinateur de l’utilisateur.|
|**Planifier une analyse quotidienne rapide**|Permet de planifier une analyse rapide exécutée tous les jours à l’heure de votre choix|
|**Planifier une analyse système**|Permet de planifier une analyse système complète ou rapide exécutée régulièrement le jour et à l’heure de votre choix|
|**Limiter l’utilisation du processeur pendant une analyse**|Vous permet de limiter la quantité de ressources du processeur que les analyses sont autorisées à utiliser (de **1** à **100**)|
|**Analyser les fichiers d’archive**|Permet à Defender d’analyser les fichiers archivés tels que les archives .zip ou .cab.|
|**Analyser les messages électroniques**|Permet à Defender d’analyser les e-mails quand ils arrivent sur l’appareil|
|**Analyser les lecteurs amovibles**|Permet à Defender d’analyser les lecteurs amovibles tels que les clés USB|
|**Analyser les lecteurs réseau mappés**|Permet à Defender d’analyser les fichiers sur un lecteur réseau mappé.<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|
|**Analyser les fichiers ouverts à partir de dossiers partagés sur le réseau**|Permet à Defender d’analyser les fichiers sur des lecteurs réseau partagés (par exemple, les lecteurs accessibles à partir d’un chemin UNC).<br>Si les fichiers sur le lecteur sont en lecture seule, Defender ne pourra pas supprimer les logiciels malveillants détectés dans ces fichiers.|
|**Intervalle de mise à jour des signatures**|Spécifie l’intervalle auquel Defender vérifie les nouveaux fichiers de signature.|
|**Autoriser la protection de cloud**|Autorise ou empêche Microsoft Active Protection Service de recevoir des informations sur l’activité des logiciels malveillants en provenance des appareils que vous gérez. Ces informations serviront à améliorer le service.|
|**Demander aux utilisateurs d’envoyer des exemples**|Contrôle si les fichiers susceptibles de nécessiter une analyse plus approfondie de la part de Microsoft pour déterminer s’il s’agit de logiciels malveillants sont automatiquement envoyés à Microsoft|
|**Détection des applications potentiellement indésirables**|Protège les appareils Windows Desktop inscrits contre l’exécution de logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée.|
|**Fichiers et dossiers à exclure lors de l’exécution d’une analyse ou de l’utilisation de la protection en temps réel**|Ajoute un ou plusieurs fichiers et dossiers comme **C:\Chemin** ou **%ProgramFiles%\Chemin\NomFichier.exe** à la liste des exclusions. Ces fichiers et dossiers ne sont pas inclus dans les analyses en temps réel ou planifiées.|
|**Extensions de fichier à exclure lors d’une analyse ou de la protection en temps réel**|Ajoutez une ou plusieurs extensions de fichier comme **jpg** ou **txt** à la liste des exclusions. Tous les fichiers avec ces extensions ne sont pas inclus dans les analyses en temps réel ou planifiées.|
|**Processus à exclure lors d’une analyse ou de la protection en temps réel**|Ajoute un ou plusieurs processus du type **.exe**, **.com** ou **.scr** à la liste des exclusions. Ces processus ne sont pas inclus dans les analyses en temps réel ou planifiées.|


### <a name="updates"></a>Updates

|Nom du paramètre|Informations supplémentaires (si requises)|
|----------------|---------------|
|**Autoriser les mises à jour automatiques**|Autorise les mises à jour automatiques. Configurez l’un des paramètres suivants pour contrôler le comportement de mise à jour :<br />**Notification de téléchargement**<br />**Installer automatiquement au moment de la maintenance**<br />**Installer et redémarrer automatiquement au moment de la maintenance**<br />**Installer et redémarrer automatiquement au moment planifié** : notez que quand cette option est sélectionnée, vous pouvez aussi configurer les paramètres suivants : **Supprimer la notification à l’utilisateur final** et **Définir un jour d’installation pour les mises à jour planifiées**.<br>(Windows 10 Desktop uniquement)|
|**Autoriser les fonctionnalités préliminaires**|Permet à Microsoft de déployer des versions préliminaires de paramètres et de fonctionnalités sur des appareils dotés de Windows 10. Vous pouvez décider d’autoriser l’installation des paramètres uniquement, ou de toutes les versions préliminaires de paramètres et de fonctionnalités.|

### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
