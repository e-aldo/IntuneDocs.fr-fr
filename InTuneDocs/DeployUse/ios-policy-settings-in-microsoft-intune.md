---
# required metadata

title: Paramètres de la stratégie iOS | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie d’iOS dans Microsoft Intune

## Paramètres de la stratégie de configuration générale

Utilisez la **stratégie de configuration générale iOS** de Microsoft Intune pour configurer les paramètres suivants :

-   **Paramètres de sécurité des appareils mobiles** : choisissez des paramètres dans une liste de paramètres prédéfinis qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l'appareil.

-   **Mode plein écran** : verrouille un appareil pour autoriser uniquement le fonctionnement de certaines fonctionnalités. Par exemple, vous pouvez autoriser un appareil à exécuter seulement une application gérée que vous spécifiez ou vous pouvez désactiver les boutons de volume sur un appareil. Ces paramètres peuvent être utilisés pour un modèle de démonstration d'un appareil ou pour un appareil dédié à l'exécution d'une seule fonction, par exemple dans un point de vente.

-   **Applications conformes et non conformes** : spécifiez une liste d’applications conformes ou non conformes dans votre entreprise. Sur les appareils Android et iOS, le **Rapport sur les applications non conformes** peut être utilisé pour comparer la conformité des applications que vous avez spécifiées dans la liste aux applications que les utilisateurs ont installées (sans qu'il soit possible de bloquer l'installation de l'application).

> [!TIP]
> Vous pouvez configurer les conditions générales pour vous assurer que les utilisateurs reconnaissent le fait que des applications sur leurs appareils, y compris des applications personnelles, seront évaluées et que les applications non conformes seront bloquées signalées comme étant non conformes. Les utilisateurs doivent accepter ces conditions générales avant de pouvoir inscrire leur appareil et utiliser le portail d'entreprise pour obtenir des applications. Pour plus d’informations sur l’utilisation des conditions générales, consultez [Paramètres de la stratégie des conditions générales dans Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Si le paramètre que vous recherchez n’apparaît pas dans cette rubrique, vous pouvez peut-être le créer à l’aide d’une stratégie personnalisée iOS qui vous permet d’importer les paramètres vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Pour plus d’informations, consultez **Paramètres de stratégie personnalisée** plus loin dans cette rubrique.

### Paramètres de sécurité

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Spécifiez si les utilisateurs doivent saisir un mot de passe pour accéder à leur appareil.|Oui|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple, numérique uniquement ou alphanumérique|Oui|
|**Type de mot de passe requis - Nombre minimum de jeux de caractères**|Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe). Toutefois, pour les appareils iOS, il spécifie le nombre de caractères de symbole devant être inclus dans le mot de passe)|Oui|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères figurant dans le mot de passe.|Oui|
|**Autoriser les mots de passe simples**|Autoriser les mots de passe simples comme « 0000 » et « 1234 ».|Oui|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Réinitialise l'appareil si le nombre d'échecs de tentative de est atteint.|Oui|
|**Minutes d’inactivité avant arrêt de l’écran**<sup>1</sup>|Spécifiez le nombre de minutes avant l’arrêt de l’appareil.|Oui|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant de devoir modifier le mot de passe de l’appareil.|Oui|
|**Mémoriser l'historique des mots de passe**|Spécifie si l’utilisateur peut utiliser des mots de passe précédemment utilisés.|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.|Oui|
|**Minutes d’inactivité avant demande du mot de passe**<sup>1</sup>|Spécifie la durée pendant laquelle l’appareil peut rester inactif avant de demander à l’utilisateur de saisir à nouveau le mot de passe.|Oui|
|**Autoriser le déverrouillage par empreinte digitale**|Autoriser le déverrouillage de l’appareil par empreinte digitale.|iOS 7.1 et versions ultérieures|
<sup>1</sup> Pour les appareils iOS, quand vous configurez les paramètres **Minutes d’inactivité avant arrêt de l’écran** et **Minutes d’inactivité avant demande du mot de passe**, ceux-ci sont appliqués de manière séquentielle. Par exemple, si vous affectez aux deux paramètres la valeur **5** minutes, l'écran s'éteint automatiquement après 5 minutes, et l'appareil se verrouille après 5 minutes de plus. Toutefois, si l'utilisateur désactive manuellement l'écran, le second paramètre est immédiatement appliqué. Dans le même exemple, une fois que l'utilisateur a désactivé l'écran, l'appareil se verrouille 5 minutes plus tard.

### Paramètres système

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser les captures d'écran**|Permet à l’utilisateur de capturer le contenu de l’écran en tant qu’image.|Oui|
|**Autoriser le centre de contrôle sur l'écran verrouillé**|Détermine si l'application de centre de contrôle est accessible lorsque l'appareil est verrouillé.|iOS 7.1 et versions ultérieures|
|**Autoriser l'affichage des notifications sur l'écran verrouillé**|Autoriser l’utilisateur à accéder à l’affichage des notifications sans déverrouiller l’appareil.|iOS 7.1 et versions ultérieures|
|**Autoriser l'affichage du mode Aujourd'hui sur l'écran verrouillé**|Détermine si les notifications peuvent s'afficher lorsque l'appareil est verrouillé.|iOS 7.1 et versions ultérieures|
|**Autoriser la soumission des données de diagnostic**|Autoriser ou bloquer l’envoi de données de diagnostic à Apple depuis l’appareil.|Oui|
|**Autoriser les certificats TLS non autorisés**|Autoriser les certificats Transport Layer Security non autorisés sur l’appareil.|Oui|
|**Autoriser le livret lors du verrouillage**|Autoriser l’utilisateur à accéder à l’application de livret lorsque l’appareil est verrouillé.|Oui|

### Paramètres du cloud - documents et données

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser la sauvegarde dans iCloud**|Autorise l’utilisateur à sauvegarder l’appareil sur iCloud.|Oui|
|**Autoriser la synchronisation des documents dans iCloud**|Autoriser la synchronisation des documents et des clés-valeurs sur votre espace de stockage iCloud. Oui|
|**Autoriser la synchronisation du flux de photos dans iCloud**|Autoriser la synchronisation des photos de votre appareil sur iCloud.|Oui|
|**Exiger la sauvegarde chiffrée**|Exiger le chiffrement des sauvegardes d’appareil.|Oui|

### Paramètres de l'application - navigateur

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser Safari**|Spécifier si le navigateur Safari peut être utilisé sur l’appareil.|Oui|
|**Autoriser le remplissage automatique**|L'utilisateur peut modifier les paramètres de saisie semi-automatique dans le navigateur.|Oui|
|**Autoriser le bloqueur de fenêtres publicitaires**|Activer ou désactiver le bloqueur de fenêtres publicitaires du navigateur.|Oui|
|**Autoriser les cookies**|Autoriser le navigateur web de l’appareil à utiliser des cookies.|Oui|
|**Autoriser les scripts Java**|Autoriser l’exécution des scripts Java dans le navigateur.|Oui|
|**Autoriser l'avertissement de fraudes**|Autoriser les avertissements antifraude dans le navigateur de l’appareil.|Oui|

### Paramètres de l'application - applications

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser la boutique d'applications**|Autorise l’accès à l’App Store depuis l’appareil.|Oui|
|**Demander un mot de passe pour accéder à la boutique d'applications**|Oui|
|**Autoriser les achats dans l'application**|Autoriser les achats depuis une application en cours d’exécution.|Oui|
|**Autoriser les documents gérés dans d'autres applications non gérées**|Autoriser la visualisation des documents d’entreprise depuis toute application.|OS 7.1 et versions ultérieures|
|**Autoriser les documents non gérés dans d'autres applications gérées**|Autoriser tout document à être affiché dans les applications d’entreprise gérées.|iOS 7.1 et versions ultérieures|
|**Autoriser la vidéoconférence**|Autoriser les applications de vidéoconférence comme Facetime sur l’appareil.|Oui|
|**Autoriser le contenu pour adultes dans la boutique multimédia**|Autoriser l’appareil à accéder au contenu réservé aux adultes depuis le magasin.|Oui|

### Paramètres de l'application - Jeux

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser l'ajout d'amis Game Center**|Autoriser l’utilisateur à ajouter des amis dans le Game Center.|Oui|
|**Autoriser les jeux multijoueur**|Autoriser l’utilisateur à jouer à des jeux multijoueur sur l’appareil.|Oui|

### Paramètres des fonctionnalités de l'appareil - matériel

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser l'appareil photo**|Spécifie si l’appareil photo de l’appareil peut être utilisé.|Oui|

### Paramètres des fonctionnalités de l'appareil - cellulaire

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser l'itinérance vocale**|Autoriser l’itinérance vocale quand l’appareil se trouve sur un réseau cellulaire.|Oui|
|**Autoriser l'itinérance des données**|Autoriser l’itinérance des données quand l’appareil se trouve sur un réseau cellulaire.|Oui|
|**Autoriser l'extraction en arrière-plan globale pendant l'itinérance**|Autoriser l’appareil à récupérer des données comme les courriers électroniques lorsqu’il est en mode itinérance sur un réseau cellulaire.|Oui|

### Paramètres des fonctionnalités de l'appareil - fonctionnalités

|Nom du paramètre|Détails|iOS|
|----------------|-------|
|**Autoriser Siri**|Autoriser l’utilisation de l’assistant vocal Siri sur l’appareil.|Oui|
|**Autoriser Siri quand l'appareil est verrouillé**|Autoriser l’utilisation de l’assistant vocal Siri sur l’appareil lorsqu’il est verrouillé.|Oui|
|**Autoriser la composition vocale**|Autoriser l’utilisation de la fonctionnalité de numérotation vocale sur l’appareil.|Oui|


### Paramètres des applications conformes et non conformes
Dans la liste **Applications conformes &amp; non conformes**, spécifiez une liste d’applications conformes ou non conformes à l’aide des informations suivantes :

> [!NOTE]
> Une stratégie ne peut contenir qu'une liste d'applications conformes ou une liste d'applications non conformes. Vous ne pouvez pas spécifier les deux dans la même stratégie.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.|
|**Ne pas signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications que les utilisateurs sont autorisés à installer. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications. Pour plus d’aide, consultez **Comment spécifier des URL de magasins d’applications** plus loin dans cette rubrique.|
|**Importer des applications**|Importe une liste d'applications que vous avez spécifiée dans un fichier de valeurs séparées par des virgules. Utilisez le format Nom de l'application, Éditeur, URL de l'application dans le fichier.|
|**Éditer**|Vous permet de modifier le nom, l'éditeur et l'URL de l'application sélectionnée.|
|**Supprimer**|Supprime l'application sélectionnée dans la liste.|

### Paramètres du mode plein écran

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Sélectionner une application gérée qui sera autorisée à s'exécuter quand l'appareil est en mode plein écran**|Cliquez sur **Parcourir**, puis spécifiez l'application gérée ou une application d'un magasin qui sera autorisée à s'exécuter quand l'appareil est en mode plein écran. Aucune autre application ne peut s’exécuter sur l’appareil. Pour plus d’aide, consultez **Comment spécifier des URL de magasins d’applications** plus loin dans cette rubrique.|
|**Autoriser l'interaction tactile**|Active ou désactive l'écran tactile sur l'appareil.|
|**Autoriser la rotation d'écran**|Active ou désactive la modification de l'orientation de l'écran quand vous faites pivoter l'appareil.|
|**Autoriser les boutons de volume**|Active ou désactive l'utilisation des boutons de volume sur l'appareil.|
|**Autoriser la modification de sonnerie**|Active ou désactive le commutateur de sonnerie (désactivation du son) sur l'appareil.|
|**Activer le bouton Veille/sortie de veille de l'écran**|Active ou désactive le bouton Veille/sortie de veille de l'écran sur l'appareil.|
|**Autoriser le verrouillage automatique**|Active ou désactive le verrouillage automatique de l'appareil.|
|**Activer Audio mono**|Active ou désactive le paramètre d'accessibilité **Audio mono**.|
|**Activer VoiceOver**|Active ou désactive le paramètre d'accessibilité **VoiceOver** qui lit à haute voix le texte sur l'affichage de l'appareil.|
|**Activer les réglages VoiceOver**|Active ou désactive les réglages VoiceOver qui vous permettent de régler la fonction VoiceOver (par exemple la vitesse de lecture à haute voix du texte à l'écran).|
|**Activer le zoom**|Active ou désactive le paramètre d'accessibilité **Zoom** qui vous permet d'utiliser la fonctionnalité tactile pour agrandir l'affichage de l'appareil.|
|**Activer les réglages du zoom**|Active ou désactive les réglages du zoom qui vous permettent de régler la fonction de zoom.|
|**Activer les couleurs inversées**|Active ou désactive le paramètre d'accessibilité **Inverser les couleurs** qui ajuste l'affichage pour aider les utilisateurs ayant des troubles visuels.|
|**Activer les réglages de couleurs inversées**|Active ou désactive les réglages de couleurs inversées qui vous permettent d'ajuster la fonction de couleurs inversées.|
|**Activer l'assistance tactile**|Active ou désactive le paramètre d'accessibilité **Assistance tactile** qui aide les utilisateurs à effectuer des mouvements à l'écran qui peuvent être difficiles à effectuer.|
|**Activer les réglages d'assistance tactile**|Active ou désactive les réglages d'assistance tactile qui vous permettent de régler la fonction tactile d'assistance.|
|**Activer la sélection vocale**|Active ou désactive les paramètres d'accessibilité **Sélection Speak** qui peuvent lire à haute voix le texte que vous sélectionnez.|
> [!NOTE] Les remarques suivantes s’appliquent aux paramètres du mode plein écran pour les appareils iOS :
> 
> -   Avant de pouvoir configurer un appareil iOS pour le mode plein écran, vous devez utiliser l' [outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) ou le gestionnaire d'inscription d'appareil pour mettre l'appareil en mode supervisé. Pour plus d'informations sur l'outil Apple Configurator, consultez votre documentation pour développeurs Apple.
> -   Si l'application iOS que vous spécifiez est installée après le déploiement de la stratégie de configuration, l'appareil ne bascule en mode plein écran qu'après son redémarrage.

### Informations de référence pour les applications conformes et non conformes

#### Contrôler les applications conformes et non conformes
Utilisez le **Rapport sur les applications non conformes** pour afficher la conformité des applications autorisées et bloquées.

##### Pour exécuter le rapport sur les applications non conformes

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Rapports** &gt; **Rapport sur les applications non conformes**.

2.  Sélectionnez les groupes d'appareils que vous souhaitez vérifier, si vous souhaitez vérifier les applications conformes, les applications non conformes ou les deux, puis cliquez sur **Afficher le rapport**.

#### Comment spécifier des URL de magasins d'applications
Pour spécifier une URL d'application dans la liste des applications conformes et non conformes, ou dans l'option **Sélectionnez une application gérée qui sera autorisée à s'exécuter quand l'appareil est en mode plein écran** (iOS uniquement), utilisez le format suivant :

À l'aide d'un moteur de recherche, recherchez l'application à utiliser dans l'App Store iTunes, puis ouvrez la page de l'application.

Copiez l'URL de la page et utilisez-la en tant qu'URL permettant de configurer la liste des applications conformes ou non conformes, ou l'application à exécuter en mode plein écran.

**Exemple :** rechercher **Microsoft Word pour iPad**. L'URL que vous utilisez sera **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE] Vous pouvez également utiliser le logiciel iTunes pour rechercher l’application, puis la commande **Copier le lien** pour obtenir l’URL de l’application.


## Paramètres de la stratégie personnalisée

Utilisez la **stratégie de configuration personnalisée iOS** de Microsoft Intune pour déployer les paramètres que vous avez créés à l’aide de l’[outil Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) sur des appareils iOS. Cet outil vous permet de créer plusieurs paramètres qui contrôlent le fonctionnement de ces appareils et de les exporter vers un profil de configuration. Vous pouvez ensuite importer ce profil de configuration dans une stratégie personnalisée iOS d’Intune et déployer les paramètres sur les utilisateurs et les appareils de votre organisation.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres iOS qui ne sont pas configurables avec une stratégie de configuration générale Intune.

### Conditions préalables
Avant de commencer, vous devez installer l'outil Apple Configurator et créer un fichier de configuration contenant les paramètres que vous souhaitez déployer sur les utilisateurs ou les appareils. Visitez le [Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12)pour télécharger l'outil Apple Configurator et en savoir plus.

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
|**Fichier de configuration de profil**|Cliquez sur **Importer**, puis recherchez le profil de configuration que vous avez créé à l'aide de l'outil Apple Configurator. **Remarque :** Vérifiez que les paramètres que vous exportez à partir de l’outil Apple Configurator sont compatibles avec la version d’iOS sur les appareils sur lesquels vous déployez la stratégie personnalisée iOS. Pour plus d’informations sur la résolution des paramètres incompatibles, recherchez **Configuration Profile Reference** et **Mobile Device Management Protocol Reference** sur le site web [Apple Developer](https://developer.apple.com/).|
    |**Détails du profil de configuration**|Affiche le code XML du profil de configuration que vous avez importé.|

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO1-->


