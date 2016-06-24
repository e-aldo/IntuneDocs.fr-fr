---
# required metadata

title: Paramètres de la stratégie de configuration Android et Samsung KNOX | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: heenamac
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie de configuration Android et Samsung KNOX dans Microsoft Intune

## Stratégie de configuration générale

Utilisez la **stratégie de configuration générale Android** de Microsoft Intune pour configurer les paramètres suivants :

-   **Paramètres de sécurité des appareils mobiles** : choisissez des paramètres dans une liste de paramètres prédéfinis qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l'appareil.

-   **Mode plein écran** (appareils Samsung KNOX uniquement) : verrouillez un appareil pour autoriser uniquement le fonctionnement de certaines fonctionnalités. Par exemple, vous pouvez autoriser un appareil à exécuter seulement une application gérée que vous spécifiez ou vous pouvez désactiver les boutons de volume sur un appareil. Ces paramètres peuvent être utilisés pour un modèle de démonstration d'un appareil ou pour un appareil dédié à l'exécution d'une seule fonction, par exemple dans un point de vente.

-   **Applications conformes et non conformes** : spécifiez une liste d’applications conformes ou non conformes dans votre entreprise. Sur les appareils Android et iOS, le **Rapport sur les applications non conformes** peut être utilisé pour comparer la conformité des applications que vous avez spécifiées dans la liste aux applications que les utilisateurs ont installées (sans qu'il soit possible de bloquer l'installation de l'application).

> [!TIP]
> Vous pouvez configurer les conditions générales pour vous assurer que les utilisateurs reconnaissent le fait que des applications sur leurs appareils, y compris des applications personnelles, seront évaluées et que les applications non conformes seront bloquées signalées comme étant non conformes. Les utilisateurs doivent accepter ces conditions générales avant de pouvoir inscrire leur appareil et utiliser le portail d'entreprise pour obtenir des applications. Pour plus d’informations sur l’utilisation des conditions générales, consultez [Paramètres de la stratégie de conditions générales dans Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Si le paramètre que vous recherchez n’est pas mentionné dans cette rubrique, vous pourrez peut-être le créer à l’aide d’une stratégie personnalisée Android qui vous permet d’utiliser des paramètres OMA-URI pour contrôler l’appareil. Pour plus d’informations, consultez **Paramètres de stratégie personnalisée** plus loin dans cette rubrique.

### Paramètres de mot de passe

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Exigez un mot de passe sur les appareils pris en charge.|Oui|Oui|
|**Longueur minimale du mot de passe**|Longueur minimale du mot de passe.|Oui|Oui|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Réinitialise l'appareil si le nombre d'échecs de tentative de est atteint.|Oui|Oui|
|**Minutes d'inactivité avant arrêt de l'écran**|Spécifiez le nombre de minutes avant le verrouillage automatique de l’appareil.|Oui|Oui|
|**Expiration du mot de passe (jours)**|Nombre de jours avant qu'un mot de passe ne doive être modifié.|Oui|Oui|
|**Mémoriser l'historique des mots de passe**|Mémoriser cette quantité de mots de passe précédemment utilisés.|Oui|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Empêche la réutilisation des mots de passe déjà utilisés.|Oui|Oui|
|**Qualité du mot de passe**|Sélectionnez le niveau de complexité du mot de passe requis et spécifiez si les appareils biométriques peuvent être utilisés.|Oui|Oui|
|**Autoriser le déverrouillage par empreinte digitale**|Autoriser l’utilisation d’une empreinte digitale pour déverrouiller l’appareil.|Non|Oui|

### Paramètres de chiffrement

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Exiger le chiffrement sur l'appareil mobile**|Requiert que les fichiers de l'appareil mobile soient chiffrés.|Oui|Oui|
|**Exiger le chiffrement sur les cartes de stockage**|Spécifie si la carte de stockage de l’appareil doit être chiffrée.|Non|Oui|

### Paramètres système

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser la capture d'écran**|Autorise l’utilisateur à capturer le contenu de l’écran en tant qu’image.|Non|Oui|
|**Autoriser la soumission des données de diagnostic**|Autorise l’appareil à soumettre des informations de diagnostic à Google.|Non|Oui|
|**Autoriser la réinitialisation aux paramètres d'usine**|Autorisez l'utilisateur à rétablir les paramètres d'usine sur l'appareil.|Non|Oui|

### Paramètres du cloud - documents et données

|Nom du paramètre|Détails|Android et Samsung KNOX|Android 4.0+|
|----------------|----------------------------|----------------|
|**Autoriser la sauvegarde Google**|Autorise l’utilisation de la sauvegarde de Google.|Non|Oui|

### Paramètres du cloud - comptes et synchronisation

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser la synchronisation automatique de compte Google**|Autorise la synchronisation automatique des paramètres du compte Google.|Non|Oui|

### Paramètres de l'application - navigateur

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser le navigateur web**|Spécifie si le navigateur web de l’appareil peut être utilisé.|Non|Oui|
|**Autoriser le remplissage automatique**|Autoriser l’utilisation de la fonction de remplissage automatique du navigateur web.|Non|Oui|
|**Autoriser le bloqueur de fenêtres publicitaires**|Autoriser l’utilisation du bloqueur de fenêtres publicitaires dans le navigateur.|Non|Oui|
|**Autoriser les cookies**|Autoriser le navigateur web de l’appareil à utiliser des cookies.|Non|Oui|
|**Autoriser les scripts actifs**|Autoriser le navigateur web de l’appareil à utiliser Active Scripting.|Non|Oui|

### Paramètres de l'application - applications

|Nom du paramètre|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser la boutique Google Play**|Autoriser l’utilisateur à accéder à la Boutique Google Play sur l’appareil.|Non|Oui|

### Paramètres des fonctionnalités de l'appareil - matériel

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser l'appareil photo**|Autorise l’utilisation de l’appareil photo de l’appareil.|Oui|Oui|
|**Autoriser le stockage amovible**|Autorise l’appareil à utiliser du stockage amovible, comme une carte SD.|Non|Oui|
|**Autoriser le Wi-Fi**|Autorise l’utilisation des fonctionnalités Wi-Fi de l’appareil.|Non|Oui|
|**Autoriser la connexion Wi-Fi**|Autorise l’utilisation de la connexion Wi-Fi sur l’appareil.|Non|Oui|
|**Autoriser la géolocalisation**|Permet à l'appareil d'utiliser les informations d'emplacement.|Non|Oui|
|**Autoriser NFC**|Autorise les opérations qui utilisent la communication en champ proche si l’appareil la prend en charge.|Non|Oui|
|**Autoriser Bluetooth**|Autorise l’utilisation de la fonction Bluetooth sur l’appareil.|Non|Oui|
|**Autoriser l'extinction**|Autorise l’utilisateur à mettre l’appareil hors tension.<br /><br />Si ce paramètre est désactivé, le paramètre **Nombre d’échecs de connexion successifs autorisé avant réinitialisation de l’appareil** pour les appareils Samsung KNOX ne fonctionne pas.|Non|Oui|

### Paramètres des fonctionnalités de l'appareil - cellulaire

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser l'itinérance vocale**|Autoriser l’itinérance vocale quand l’appareil se trouve sur un réseau cellulaire.|Non|Oui|
|**Autoriser l'itinérance des données**|Autoriser l’itinérance des données quand l’appareil se trouve sur un réseau cellulaire.|Non|Oui|
|**Autoriser les messages SMS/MMS**|Autoriser l’utilisation de la messagerie SMS et MMS sur l’appareil.|Non|Oui|

### Paramètres des fonctionnalités de l'appareil - fonctionnalités

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser l'assistant vocal**|Autorise l’utilisation du logiciel Assistant vocal sur l’appareil.|Non|Oui|
|**Autoriser la composition vocale**|Active ou désactive la fonctionnalité de numérotation vocale sur l’appareil.|Non|Oui|
|**Autoriser la fonction copier-coller**|Autoriser les fonctions Copier et Coller sur l’appareil.|Non|Oui|
|**Autoriser le partage du Presse-papiers entre applications**|Utilisez le Presse-papiers pour copier-coller entre les applications.|Non|Oui|
|**Autoriser YouTube**|Autoriser l’utilisation de YouTube sur l’appareil.|Non|Oui|

### Paramètres des applications conformes et non conformes
Dans la liste **Applications conformes &amp; non conformes**, spécifiez une liste d’applications conformes ou non conformes à l’aide des informations suivantes :

> [!NOTE]
> Une stratégie ne peut contenir qu'une liste d'applications conformes ou une liste d'applications non conformes. Vous ne pouvez pas spécifier les deux dans la même stratégie.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter. Si les utilisateurs installent l’une de ces applications, elle apparaîtra dans le rapport sur les applications non conformes.|
|**Ne pas signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications que vous voulez autoriser au sein de l’entreprise. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez un nom de votre choix, éventuellement l'éditeur de l'application, et l'URL de l'application dans le magasin d'applications.<br /><br />Pour obtenir de l’aide, consultez Comment spécifier des URL de magasins d’applications plus loin dans cette rubrique.|
|**Importer des applications**|Importe une liste d'applications que vous avez spécifiée dans un fichier de valeurs séparées par des virgules. Utilisez le format Nom de l'application, Éditeur, URL de l'application dans le fichier.|
|**Éditer**|Vous permet de modifier le nom, l'éditeur et l'URL de l'application sélectionnée.|
|**Supprimer**|Supprime l'application sélectionnée dans la liste.|

### Paramètres du mode plein écran
Spécifiez les paramètres suivants pour les **appareils Samsung KNOX** :

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Sélectionner une application gérée qui sera autorisée à s'exécuter quand l'appareil est en mode plein écran**|Sélectionnez **Parcourir**, puis choisissez l’application gérée qui peut s’exécuter quand l’appareil est en mode plein écran (les applications spécifiées sous la forme d’un lien vers le Store ne sont pas prises en charge). Aucune autre application ne pourra s'exécuter sur l'appareil.|
|**Autoriser les boutons de volume**|Active ou désactive l'utilisation des boutons de volume sur l'appareil.|
|**Activer le bouton Veille/sortie de veille de l'écran**|Active ou désactive le bouton Veille/sortie de veille de l'écran sur l'appareil.|

### Informations de référence pour les applications conformes et non conformes

#### Contrôler les applications conformes et non conformes
Utilisez le **Rapport sur les applications non conformes** pour afficher la conformité des applications autorisées et bloquées.

###### Pour exécuter le rapport sur les applications non conformes

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Rapports** &gt; **Rapport sur les applications non conformes**.

2.  Sélectionnez les groupes d’appareils que vous voulez vérifier, qu’il s’agisse des applications conformes, non conformes ou des deux, puis sélectionnez **Afficher le rapport**.

#### Comment spécifier des URL de magasins d'applications
Pour spécifier une URL d'application dans la liste des applications conformes et non conformes, utilisez le format suivant :

Dans la [section Applications de Google Play](https://play.google.com/store/apps), recherchez l’application à utiliser.

Ouvrez la page d'installation de l'application, puis copiez l'URL dans le Presse-papiers. Vous pouvez maintenant utiliser cette URL dans la liste des applications conformes ou non conformes.

**Exemple :** recherchez Google Play pour Microsoft Office Mobile. L’URL que vous utilisez est **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée Android** de Microsoft Intune pour déployer des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Android qui ne sont pas configurables avec des stratégies Intune.

> [!NOTE] Les stratégies personnalisées Android prennent uniquement en charge la configuration des paramètres Wi-Fi pour les appareils Android qui ont une clé prépartagée.

### Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Entrez un nom unique pour la stratégie personnalisée Android pour pouvoir l’identifier dans la console Intune.|
    |**Description**|Fournissez une description générale de la stratégie personnalisée Android et d'autres informations pertinentes pour mieux la localiser.|

### Paramètres OMA-URI

   |Nom du paramètre|Détails|
    |--------|--------------------|
    |**Nom du paramètre**|Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.|
    |**Description du paramètre**|Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.|
    |**Type de données**|Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne, Chaîne (XML), Date et heure, Entier, Virgule flottante** ou **Booléen**.|
    |**OMA-URI (sensible à la casse)**|Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.|
    |**Valeur**|Spécifiez la valeur à associer à l'identificateur OMA-URI spécifié précédemment.|

### Exemple : configurer un profil Wi-Fi personnalisé avec une clé prépartagée
Bien qu’Intune prenne en charge les profils Wi-Fi pour les appareils Android, cette fonctionnalité ne prend pas actuellement en charge l’inclusion d’une clé prépartagée dans la configuration. Dans cet exemple, vous allez apprendre à créer une stratégie personnalisée Android qui crée un profil Wi-Fi avec une clé prépartagée sur l'appareil Android.

#### Pour créer un profil Wi-Fi avec une clé prépartagée

1.  Vérifiez que vos utilisateurs utilisent la version la plus récente de l’application [Portail d’entreprise Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) pour Android.

2.  Créez une stratégie personnalisée Android et ajoutez le paramètre suivant :

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Nom du paramètre**|Affectez un nom de votre choix au paramètre.|
|**Description du paramètre**|Entrez la description du paramètre.|
|**Type de données**|Sélectionnez **Chaîne (XML)**.|
|**OMA-URI**|Entrez ceci : ./Vendor/MSFT/WiFi/Profile/*&lt;votre profil Wi-Fi&gt;*/Settings|

3.  Pour **Valeur**, copiez et collez le code XML suivant :

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile 
                    <SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile 
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  Une fois terminé, enregistrez la stratégie et déployez-la sur les appareils Android requis. Le nouveau profil Wi-Fi apparaît dans la liste des connexions sur l'appareil.

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO2-->


