---
title: "Paramètres de la stratégie iOS | Microsoft Intune"
description: "Créez des stratégies qui contrôlent les paramètres et fonctionnalités sur les appareils iOS que vous gérez avec Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bc5ff023b5d29ded999c7e49c5e7c2aee8a23bba
ms.openlocfilehash: e71cc1e8e2cb0f46507ff63d962f3d477acfb72e


---

# Paramètres de la stratégie d’iOS dans Microsoft Intune

Intune fournit un éventail de paramètres généraux intégrés, que vous pouvez configurer sur les appareils iOS. En outre, vous pouvez recourir à l’outil Apple Configurator pour créer des paramètres personnalisés qui ne sont pas disponibles à partir d’Intune.

## Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale iOS** de Microsoft Intune pour configurer les paramètres suivants :

-   **Paramètres de sécurité de l’appareil et paramètres généraux**. Choisissez des paramètres dans une liste de paramètres prédéfinis, qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l’appareil.

-   **Mode plein écran**. Verrouillez un appareil pour autoriser le fonctionnement de certaines fonctionnalités uniquement. Par exemple, vous pouvez autoriser un appareil à exécuter une seule application gérée que vous spécifiez ou désactiver les boutons du volume sur un appareil. Ces paramètres peuvent être utilisés pour un modèle de démonstration d’un appareil ou pour un appareil dédié à l’exécution d’une seule fonction, par exemple dans un point de vente.

-   **Applications conformes et non conformes**. Spécifiez une liste d’applications conformes ou non conformes au sein de votre entreprise. Sur les appareils Android et iOS, le **Rapport sur les applications non conformes** peut être utilisé pour vérifier la conformité des applications spécifiées dans la liste par rapport à celle des applications installées par les utilisateurs (sans qu’il soit possible de bloquer leur installation).

> [!TIP]
> Vous pouvez configurer les conditions générales pour vous assurer que les utilisateurs reconnaissent le fait que les applications se trouvant sur leurs appareils, y compris des applications personnelles, seront évaluées et que les applications non conformes seront bloquées ou signalées comme non conformes. Les utilisateurs doivent accepter ces conditions générales avant de pouvoir inscrire leur appareil et utiliser le portail d'entreprise pour obtenir des applications. Pour plus d’informations sur l’utilisation des conditions générales, consultez [Paramètres de la stratégie des conditions générales dans Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Si le paramètre que vous recherchez n’apparaît pas dans cette rubrique, vous pouvez peut-être le créer à l’aide d’une stratégie personnalisée iOS qui vous permet d’importer les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Pour en savoir plus, consultez la section « Paramètres de la stratégie personnalisée » de la présente rubrique.

### Paramètres de sécurité
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Indique si l’utilisateur doit saisir un mot de passe pour accéder à son appareil.|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple une valeur numérique uniquement, ou alphanumérique.|
|**Nombre de caractères complexes requis dans le mot de passe**|Spécifie le nombre de caractères de symbole (comme **#** ou **@**) devant être inclus dans le mot de passe.|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères à inclure dans le mot de passe.|
|**Autoriser les mots de passe simples**|Autorise des mots de passe simples, comme **0000** et **1234**.|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Spécifie le nombre de tentatives de connexion ayant échoué que le paramètre système autorise avant d’effacer le contenu de l’appareil.|
|**Minutes d’inactivité avant demande du mot de passe**<sup>1</sup>|Spécifie la durée pendant laquelle l’appareil peut rester inactif avant de demander à l’utilisateur de saisir à nouveau le mot de passe.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant que l’utilisateur ne doive modifier le mot de passe de l’appareil.|
|**Mémoriser l'historique des mots de passe**|Spécifie si l’utilisateur peut utiliser des mots de passe précédemment utilisés.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.|
|**Minutes d’inactivité avant arrêt de l’écran**<sup>1</sup>|Spécifiez le nombre de minutes avant l’arrêt de l’appareil.|
|**Autoriser le déverrouillage par empreinte digitale**|Autoriser le déverrouillage de l’appareil par empreinte digitale.|
<sup>1</sup> Pour les appareils iOS, quand vous configurez les paramètres **Minutes d’inactivité avant arrêt de l’écran** et **Minutes d’inactivité avant demande du mot de passe**, ceux-ci sont appliqués de manière séquentielle. Par exemple, si vous affectez aux deux paramètres la valeur **5** minutes, l'écran s'éteint automatiquement après 5 minutes, et l'appareil se verrouille après 5 minutes de plus. Toutefois, si l'utilisateur désactive manuellement l'écran, le second paramètre est immédiatement appliqué. Dans le même exemple, une fois que l'utilisateur a désactivé l'écran, l'appareil se verrouille 5 minutes plus tard.

### Paramètres système
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser les captures d'écran**|Permet à l’utilisateur de capturer le contenu de l’écran en tant qu’image.|
|**Autoriser le centre de contrôle sur l'écran verrouillé**|Autorise l’utilisateur à accéder à l’application du centre de contrôle lorsque l’appareil est verrouillé.|
|**Autoriser l'affichage des notifications sur l'écran verrouillé**|Autoriser l’utilisateur à accéder à l’affichage des notifications sans déverrouiller l’appareil.|
|**Autoriser l'affichage du mode Aujourd'hui sur l'écran verrouillé**|Autorise l’utilisateur à afficher les notifications lorsque l’appareil est verrouillé.|
|**Autoriser les certificats TLS non autorisés**|Autoriser les certificats Transport Layer Security non autorisés sur l’appareil.|
|**Autoriser la soumission des données de diagnostic**|Autoriser ou bloquer l’envoi de données de diagnostic à Apple depuis l’appareil.|
|**Autoriser le livret lors du verrouillage**|Autoriser l’utilisateur à accéder à l’application de livret lorsque l’appareil est verrouillé.|

### Paramètres du cloud pour les documents et les données
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser la sauvegarde dans iCloud**|Autorise l’utilisateur à sauvegarder les données de l’appareil dans iCloud.|
|**Autoriser la synchronisation des documents dans iCloud**|Autoriser la synchronisation des documents et des clés-valeurs sur votre espace de stockage iCloud.|
|**Autoriser la synchronisation du flux de photos dans iCloud**|Autoriser la synchronisation des photos de votre appareil sur iCloud.|
|**Exiger la sauvegarde chiffrée**|Exiger le chiffrement des sauvegardes d’appareil.|
|**Autoriser les applications gérées à synchroniser des données sur iCloud**|Autorise les applications que vous gérez avec Intune à synchroniser les données sur le compte iCloud de l’utilisateur.|
|**Autoriser la procédure de transfert à poursuivre sur un autre appareil**|Autorise l’utilisateur à reprendre le travail qu’il a commencé sur un appareil iOS, sur un autre appareil iOS ou Mac OS X.|

### Paramètres d’application du navigateur
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser Safari**|Spécifier si le navigateur Safari peut être utilisé sur l’appareil.|
|**Autoriser le remplissage automatique**|Autorise l’utilisateur à modifier les paramètres de saisie semi-automatique dans le navigateur.|
|**Autoriser le bloqueur de fenêtres publicitaires**|Activer ou désactiver le bloqueur de fenêtres publicitaires du navigateur.|
|**Autoriser les cookies**|Autorise le navigateur à utiliser des cookies.|
|**Autoriser les scripts Java**|Autoriser l’exécution des scripts Java dans le navigateur.|
|**Autoriser l'avertissement de fraudes**|Autoriser l’affichage d’avertissements antifraude dans le navigateur.|

### Paramètres d’application relatifs aux applications
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser la boutique d'applications**|Autorise l’accès à l’App Store depuis l’appareil.|
|**Demander un mot de passe pour accéder à la boutique d'applications**|Oblige l’utilisateur à saisir un mot de passe pour pouvoir visiter l’App Store.|
|**Autoriser les achats dans l'application**|Autoriser les achats depuis une application en cours d’exécution.|
|**Autoriser les documents gérés dans d'autres applications non gérées**|Autoriser les documents d'entreprise à être affichés dans toute application.<br>**Exemple** : Vous voulez empêcher les utilisateurs d’enregistrer des fichiers de OneDrive dans Dropbox. Attribuez la valeur Non à ce paramètre. Une fois que l’appareil a reçu la stratégie (par exemple, après un redémarrage), il cesse d’autoriser l’enregistrement.|
|**Autoriser les documents non gérés dans d'autres applications gérées**|Autoriser tout document à être affiché dans les applications d’entreprise gérées.|
|**Autoriser la vidéoconférence**|Autorise les applications de vidéoconférence comme FaceTime sur l’appareil.|
|**Autoriser le contenu pour adultes dans la boutique multimédia**|Autoriser l’appareil à accéder au contenu réservé aux adultes depuis le magasin.|
|**Autoriser l’utilisateur à télécharger du contenu indiqué comme étant « Littérature érotique » à partir de l’iBooks Store**|Autorise l’utilisateur à télécharger des livres de la catégorie « Littérature érotique ».|

### Paramètres d’application relatifs aux jeux
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser l'ajout d'amis Game Center**|Autoriser l’utilisateur à ajouter des amis dans le Game Center.|
|**Autoriser les jeux multijoueur**|Autoriser l’utilisateur à jouer à des jeux multijoueur sur l’appareil.|

### Paramètres des fonctionnalités de l’appareil pour le matériel
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser l'appareil photo**|Spécifie si l’appareil photo de l’appareil peut être utilisé.|
|**Exiger un mot de passe associé pour les demandes AirPlay sortantes**|Nécessite un mot de passe de jumelage lorsque l’utilisateur a recours à AirPlay pour diffuser le contenu vers d’autres appareils Apple.|

### Paramètres des fonctionnalités de l’appareil pour les appareils cellulaires
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser l'itinérance vocale**|Autoriser l’itinérance vocale quand l’appareil se trouve sur un réseau cellulaire.|
|**Autoriser l'itinérance des données**|Autoriser l’itinérance des données quand l’appareil se trouve sur un réseau cellulaire.|
|**Autoriser l'extraction en arrière-plan globale pendant l'itinérance**|Autoriser l’appareil à récupérer des données comme les courriers électroniques lorsqu’il est en mode itinérance sur un réseau cellulaire.|

### Paramètres des fonctionnalités de l’appareil pour les fonctions
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|-------|
|**Autoriser Siri**|Autoriser l’utilisation de l’assistant vocal Siri sur l’appareil.|
|**Autoriser Siri quand l'appareil est verrouillé**|Autoriser l’utilisation de l’assistant vocal Siri sur l’appareil lorsqu’il est verrouillé.|
|**Autoriser la composition vocale**|Autoriser l’utilisation de la fonctionnalité de numérotation vocale sur l’appareil.|


### Paramètres des applications conformes et non conformes
Dans la liste **Applications conformes &amp; non conformes**, spécifiez une liste d’applications conformes ou non conformes à l’aide des informations ci-après.

> [!NOTE]
> Une stratégie ne peut contenir qu’une liste d’applications conformes ou une liste d’applications non conformes. Vous ne pouvez pas spécifier les deux dans la même stratégie.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.|
|**Signaler une non-conformité quand les utilisateurs installent les applications non listées**|Répertorie les applications que les utilisateurs sont autorisés à installer. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications. Pour obtenir une aide supplémentaire, consultez la section « Comment spécifier des URL de magasins d’applications » de la présente rubrique.|
|**Importer des applications**|Importe la liste d’applications que vous avez spécifiées dans un fichier de valeurs séparées par des virgules. Dans ce fichier, utilisez le format suivant : nom de l’application, éditeur, URL de l’application.|
|**Éditer**|Permet de modifier le nom, l’éditeur et l’URL de l’application sélectionnée.|
|**Supprimer**|Supprime l’application sélectionnée dans la liste.|

### Paramètres du mode plein écran

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Sélectionner une application gérée qui sera autorisée à s'exécuter quand l'appareil est en mode plein écran**|Sélectionnez **Parcourir**, puis spécifiez l’application gérée ou une application d’un Windows Store qui est autorisée à s’exécuter lorsque l’appareil est en mode plein écran. Aucune autre application ne pourra s'exécuter sur l'appareil. Pour obtenir de l’aide, consultez la section « Comment spécifier des URL de magasins d’applications » de la présente rubrique.|
|**Autoriser l'interaction tactile**|Active ou désactive l’écran tactile sur l’appareil.|
|**Autoriser la rotation d'écran**|Active ou désactive la modification de l’orientation de l’écran lorsque l’utilisateur fait pivoter l’appareil.|
|**Autoriser les boutons de volume**|Active ou désactive l’utilisation des boutons de volume sur l’appareil.|
|**Autoriser la modification de sonnerie**|Active ou désactive le commutateur de sonnerie (désactivation du son) sur l’appareil.|
|**Activer le bouton Veille/sortie de veille de l'écran**|Active ou désactive le bouton Veille/sortie de veille de l’écran sur l’appareil.|
|**Autoriser le verrouillage automatique**|Active ou désactive le verrouillage automatique de l’appareil.|
|**Activer Audio mono**|Active ou désactive le paramètre d’accessibilité **Audio mono**.|
|**Activer VoiceOver**|Active ou désactive le paramètre d’accessibilité **VoiceOver**, qui lit à haute voix le texte affiché à l’appareil.|
|**Activer les réglages VoiceOver**|Active ou désactive les réglages VoiceOver qui vous permettent de régler la fonction VoiceOver (par exemple, la vitesse de lecture à haute voix du texte affiché à l’écran).|
|**Activer le zoom**|Active ou désactive le paramètre d’accessibilité **Zoom**, qui vous permet d’utiliser la fonctionnalité tactile pour agrandir l’affichage de l’appareil.|
|**Activer les réglages du zoom**|Active ou désactive les réglages du zoom qui vous permettent de régler la fonction de zoom.|
|**Activer les couleurs inversées**|Active ou désactive le paramètre d’accessibilité **Inverser les couleurs**, qui ajuste l’affichage pour aider les utilisateurs ayant des troubles visuels.|
|**Activer les réglages de couleurs inversées**|Active ou désactive les réglages de couleurs inversées, qui permettent à l’utilisateur d’ajuster la fonction de couleurs inversées.|
|**Activer l'assistance tactile**|Active ou désactive le paramètre d’accessibilité **Assistance tactile**, qui permet à l’utilisateur d’effectuer des mouvements à l’écran pouvant être difficiles à effectuer.|
|**Activer les réglages d'assistance tactile**|Active ou désactive les réglages d’assistance tactile, qui permettent à l’utilisateur de régler la fonction d’assistance tactile.|
|**Activer la sélection vocale**|Active ou désactive les paramètres d’accessibilité **Sélection Speak**, qui peuvent lire à haute voix le texte que l’utilisateur sélectionne.|
> [!NOTE]
> Les remarques suivantes s'appliquent aux paramètres du mode plein écran pour les appareils iOS :
>
> -   Avant de pouvoir configurer un appareil iOS pour le mode plein écran, vous devez utiliser l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) ou le Gestionnaire d’inscription d’appareil pour mettre l’appareil en mode supervisé. Pour en savoir plus sur l’outil Apple Configurator, consultez votre documentation Apple.
> -   Si l’application iOS que vous spécifiez est installée après le déploiement de la stratégie de configuration, l’appareil ne bascule en mode plein écran qu’après son redémarrage.

### Informations de référence pour les applications conformes et non conformes

Utilisez le **Rapport sur les applications non conformes** pour afficher la conformité des applications autorisées et bloquées.

##### Pour exécuter le rapport sur les applications non conformes

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Rapports** &gt; **Rapport sur les applications non conformes**.

2.  Sélectionnez les groupes d’appareils que vous voulez vérifier, en indiquant si vous voulez vérifier les applications conformes, non conformes ou les deux, puis choisissez **Afficher le rapport**.

#### Comment spécifier des URL de magasins d'applications
Pour spécifier une URL d'application dans la liste des applications conformes et non conformes, ou dans l'option **Sélectionnez une application gérée qui sera autorisée à s'exécuter quand l'appareil est en mode plein écran** (iOS uniquement), utilisez le format suivant :

1. À l’aide d’un moteur de recherche, recherchez l’application à utiliser dans l’App Store iTunes, puis ouvrez la page de l’application.

2. Copiez l’URL de la page et utilisez-la en tant qu’adresse permettant de configurer la liste des applications conformes ou non conformes, ou l’application à exécuter en mode plein écran.

**Exemple :** rechercher **Microsoft Word pour iPad**. L’URL que vous utilisez est la suivante : **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> Vous pouvez également utiliser le logiciel iTunes pour rechercher l'application, puis la commande **Copier le lien** pour obtenir l'URL de l'application.

### Paramètres d’inscription
Tous les paramètres s’appliquent à iOS 7.1 et aux versions ultérieures.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Autoriser le verrou d'activation quand l'appareil est en mode supervisé**|Active le verrou d’activation sur des appareils iOS supervisés.|

### Surveillance
Vous pouvez configurer les paramètres suivants sur les appareils exécutant iOS 7.1 et versions ultérieures en mode supervisé.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Autoriser la modification du compte**|Autoriser l’utilisateur à modifier les paramètres de compte tels que les configurations des e-mails.|
|**Autoriser AirDrop**|Autoriser l’utilisation de la fonctionnalité AirDrop pour échanger du contenu avec des appareils proches.|
|**Autoriser les modifications sur les paramètres d’utilisation des données cellulaires des applications**|Autoriser l’utilisateur à contrôler les applications qui sont autorisées à utiliser des données cellulaires.|
|**Autoriser Siri à interroger le contenu généré par l’utilisateur à partir d’Internet**|Autoriser Siri à accéder à des sites web pour répondre à des questions.|
|**Autoriser l’accès à l’IBooks Store**|Autoriser l’utilisateur à parcourir et à acheter des livres depuis l’IBooks Store.|
|**Autoriser les modifications sur les paramètres de l’application Localiser mes amis**|Autoriser l’utilisateur à modifier les paramètres de l’application Localiser mes amis.|
|**Autoriser l’utilisation de l’option d’effacement de tout le contenu et de tous les paramètres sur l’appareil**|Autoriser l’utilisateur à utiliser l’option d’effacement de l’ensemble du contenu et des paramètres sur l’appareil.|
|**Autoriser l’utilisateur à activer des restrictions dans les paramètres de l’appareil**|Autoriser l’utilisateur à configurer des restrictions sur l’appareil (contrôle parental).|
|**Autoriser la recherche Spotlight à retourner des résultats d’Internet**|Autoriser la recherche Spotlight à se connecter à Internet pour fournir des résultats supplémentaires.|
|**Autoriser l’utilisation de l’application Game Center**|Autoriser l’utilisation de l’application Game Center.|
|**Autoriser le jumelage d’hôtes pour contrôler les appareils avec lesquels un appareil iOS peut être jumelé**|Autoriser le jumelage d’hôtes pour aider l’administrateur à contrôler les appareils avec lesquels un appareil doté d’iOS 7 peut être jumelé.|
|**Autoriser l’utilisateur à installer des profils de configuration et des certificats**|Autoriser l’utilisateur à installer des profils de configuration et des certificats.|
|**Autoriser l’utilisation de l’application Messages sur l’appareil**|Autoriser l’utilisation de l’application Messages pour envoyer des SMS.|


## Paramètres de la stratégie personnalisée

Utilisez la **stratégie de configuration personnalisée iOS** de Microsoft Intune pour déployer les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) sur des appareils iOS. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans une stratégie personnalisée iOS d’Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité vous permet de déployer les paramètres iOS qui ne sont pas configurables avec des stratégies de configuration générales Intune.

### Conditions préalables
Avant de commencer, vous devez installer l’outil Apple Configurator et créer un fichier de configuration contenant les paramètres que vous souhaitez déployer sur les utilisateurs ou les appareils. Visitez le [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) pour télécharger l’outil Apple Configurator et en savoir plus à ce sujet.

> [!NOTE]
> Intune ne signale pas la conformité de chaque paramètre dans une stratégie personnalisée iOS. Toutefois, la conformité d'ensemble de la stratégie est signalée.

### Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Affectez un nom unique à la stratégie personnalisée iOS pour vous aider à l’identifier dans la console Intune.|
    |**Description**|Fournissez une description générale de la stratégie personnalisée iOS et d'autres informations pertinentes pour mieux la localiser.|

### Configuration personnalisée

|Nom du paramètre|Détails|
    |----------------|--------------------|
|**Nom du profil de configuration personnalisé (montré aux utilisateurs)**|Entrez le nom de la stratégie tel qu’il sera affiché sur l’appareil et dans les rapports de stratégie Intune.|
|**Fichier de configuration de profil**|Sélectionnez l’option **Importer**, puis accédez au profil de configuration que vous avez créé à l’aide de l’outil Apple Configurator. **Remarque :** Vérifiez que les paramètres que vous exportez à partir de l’outil Apple Configurator sont compatibles avec la version d’iOS sur les appareils sur lesquels vous déployez la stratégie personnalisée iOS. Pour en savoir plus sur la résolution des paramètres incompatibles, recherchez l’élément **Configuration Profile Reference** et **Mobile Device Management Protocol Reference** sur le site web [Apple Developer](https://developer.apple.com/).|
    |**Détails du profil de configuration**|Affichez le code XML du profil de configuration que vous avez importé.|

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO1-->


