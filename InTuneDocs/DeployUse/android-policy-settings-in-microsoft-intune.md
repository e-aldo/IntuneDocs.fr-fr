---

title: "Paramètres de la stratégie de configuration Android et Samsung KNOX | Microsoft Intune"
description: "Créez des stratégies qui contrôlent les paramètres et fonctionnalités sur les appareils Android que vous gérez avec Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65d2c9c1f5d81dae33422bd4bf7c0e2e21bb96e4
ms.openlocfilehash: 31c91609b913034ad3aaae0950145d4db5f59a0a


---

# Paramètres de la stratégie de configuration Android et Samsung KNOX dans Microsoft Intune

Intune fournit un éventail de paramètres généraux intégrés que vous pouvez configurer sur les appareils Android. Vous pouvez aussi spécifier des valeurs OMA-URI (Open Mobile Alliance Uniform Resource Identifier) pour créer des paramètres personnalisés qui ne sont pas disponibles à partir d’Intune.

## Stratégie de configuration générale

Utilisez la **stratégie de configuration générale Android** d’Intune pour configurer les paramètres suivants :

-   **Paramètres de sécurité des appareils mobiles** - Choisissez des paramètres dans une liste de paramètres prédéfinis qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l’appareil.

-   **Mode plein écran** (appareils Samsung KNOX uniquement) - Verrouillez un appareil pour n’autoriser que certaines fonctionnalités. Par exemple, vous pouvez autoriser un appareil à exécuter une seule application gérée que vous spécifiez ou désactiver les boutons du volume sur un appareil. Ces paramètres peuvent être utilisés pour le modèle de démonstration d’un appareil ou pour un appareil dédié à une seule fonction, par exemple dans un point de vente.

-   **Applications conformes et non conformes** - Spécifiez une liste d’applications conformes ou non conformes dans votre entreprise. Sur les appareils Android et iOS, le **Rapport sur les applications non conformes** peut être utilisé pour comparer la conformité des applications que vous avez spécifiées dans la liste aux applications que les utilisateurs ont installées. En fait, le rapport ne peut pas bloquer l’installation de l’application.

> [!TIP]
> Vous pouvez configurer les conditions générales pour vous assurer que les utilisateurs acceptent que toutes les applications sur leurs appareils, y compris les applications personnelles, soient évaluées et que les applications non conformes soient bloquées ou signalées non conformes. Les utilisateurs doivent accepter ces conditions générales avant de pouvoir inscrire leur appareil et utiliser le portail d'entreprise pour obtenir des applications. Pour plus d’informations sur l’utilisation des conditions générales, consultez [Paramètres de la stratégie de conditions générales dans Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md).

Si le paramètre que vous recherchez n’est pas mentionné dans cette rubrique, vous pourrez peut-être le créer à l’aide d’une stratégie personnalisée Android qui vous permet d’utiliser des paramètres OMA-URI pour contrôler l’appareil. Pour plus d’informations, accédez à la section [Paramètres de stratégie personnalisée](#custom-policy-settings) plus loin dans cette rubrique.

### Paramètres de mot de passe

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Spécifie si un mot de passe est exigé sur les appareils pris en charge.|Oui|Oui|
|**Longueur minimale du mot de passe**|Spécifie la longueur minimale du mot de passe.|Oui|Oui|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Spécifie le nombre d’échecs de connexion à autoriser avant réinitialisation de l’appareil.|Oui|Oui|
|**Minutes d'inactivité avant arrêt de l'écran**|Spécifie le nombre de minutes d’inactivité avant verrouillage automatique de l’appareil.|Oui|Oui|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant qu’un mot de passe ne doive être changé.|Oui|Oui|
|**Mémoriser l'historique des mots de passe**|Spécifie le nombre de mots de passe déjà utilisés à mémoriser.|Oui|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Empêche la réutilisation des mots de passe précédents.|Oui|Oui|
|**Qualité du mot de passe**|Spécifie le niveau de complexité du mot de passe exigé et si les appareils biométriques peuvent être utilisés.|Oui|Oui|
|**Autoriser le déverrouillage par empreinte digitale**|Autorise l’utilisation d’une empreinte digitale pour déverrouiller l’appareil.|Non|Oui|
|**Autoriser Smart Lock et d’autres agents de confiance**<br>(Android 5 et versions ultérieures)|Permet de contrôler la fonctionnalité Smart Lock sur les appareils Android compatibles. Cette fonctionnalité du téléphone, parfois appelée agent de confiance, vous permet de désactiver ou de contourner le mot de passe de l’écran de verrouillage de l’appareil si celui-ci se trouve dans un emplacement fiable (par exemple, quand il est connecté à un appareil Bluetooth spécifique ou qu’il se trouve à proximité d’une balise NFC). Vous pouvez utiliser ce paramètre pour empêcher les utilisateurs de configurer Smart Lock.|Oui|Non|

### Paramètres de chiffrement

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Exiger le chiffrement sur l'appareil mobile**|Requiert que les fichiers de l'appareil mobile soient chiffrés.|Oui|Oui|
|**Exiger le chiffrement sur les cartes de stockage**|Spécifie si la carte de stockage de l’appareil doit être chiffrée.|Non|Oui|

### Paramètres système

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser la capture d'écran**|Autorise l’utilisateur à capturer le contenu de l’écran comme image.|Non|Oui|
|**Autoriser la soumission des données de diagnostic**|Autorise l’appareil à soumettre des informations de diagnostic à Google.|Non|Oui|
|**Autoriser la réinitialisation aux paramètres d'usine**|Autorise l’utilisateur à rétablir les paramètres d’usine sur l’appareil.|Non|Oui|

### Paramètres du cloud - documents et données

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------------------|----------------|
|**Autoriser la sauvegarde Google**|Autorise l’utilisation de la sauvegarde de Google.|Non|Oui|

### Paramètres du cloud - comptes et synchronisation

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser la synchronisation automatique de compte Google**|Autorise la synchronisation automatique des paramètres du compte Google.|Non|Oui|

### Paramètres de l'application - navigateur

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser le navigateur web**|Spécifie si le navigateur web par défaut de l’appareil peut être utilisé.|Non|Oui|
|**Autoriser le remplissage automatique**|Autorise l’utilisation de la fonction de remplissage automatique du navigateur web.|Non|Oui|
|**Autoriser le bloqueur de fenêtres publicitaires**|Autoriser l’utilisation du bloqueur de fenêtres publicitaires dans le navigateur.|Non|Oui|
|**Autoriser les cookies**|Autorise le navigateur web de l’appareil à utiliser des cookies.|Non|Oui|
|**Autoriser les scripts actifs**|Autorise le navigateur web de l’appareil à utiliser Active Scripting.|Non|Oui|

### Paramètres de l'application - applications

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser la boutique Google Play**|Autorise l’utilisateur à accéder à la Boutique Google Play sur l’appareil.|Non|Oui|

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
|**Autoriser l'itinérance vocale**|Autorise l’itinérance vocale quand l’appareil se trouve sur un réseau de téléphonie mobile.|Non|Oui|
|**Autoriser l'itinérance des données**|Autorise l’itinérance des données quand l’appareil se trouve sur un réseau de téléphonie mobile.|Non|Oui|
|**Autoriser les messages SMS/MMS**|Autorise l’utilisation de la messagerie SMS et MMS sur l’appareil.|Non|Oui|

### Paramètres des fonctionnalités de l'appareil - fonctionnalités

|Nom du paramètre|Détails|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Autoriser l'assistant vocal**|Autorise l’utilisation du logiciel Assistant vocal sur l’appareil.|Non|Oui|
|**Autoriser la composition vocale**|Active ou désactive la fonctionnalité de numérotation vocale sur l’appareil.|Non|Oui|
|**Autoriser la fonction copier-coller**|Autorise les fonctions Copier et Coller sur l’appareil.|Non|Oui|
|**Autoriser le partage du Presse-papiers entre applications**|Autorise l’utilisation du Presse-papiers pour copier-coller entre les applications.|Non|Oui|
|**Autoriser YouTube**|Autorise l’utilisation de YouTube sur l’appareil.|Non|Oui|

### Paramètres des applications conformes et non conformes
Dans la liste **Applications conformes &amp; non conformes**, spécifiez une liste d’applications conformes ou non conformes qui utilisent les informations suivantes :

> [!NOTE]
> Une stratégie ne peut contenir qu’une liste d’applications conformes ou une liste d’applications non conformes. Vous ne pouvez pas spécifier les deux dans la même stratégie.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter. Si les utilisateurs installent l’une de ces applications, elle apparaîtra dans le rapport sur les applications non conformes.|
|**Ne pas signaler une non-conformité quand les utilisateurs installent les applications listées**|Répertorie les applications que vous voulez autoriser. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez le nom de l’application, l’éditeur de l’application (facultatif) et l’URL de l’application dans l’App Store.<br /><br />Pour plus d’informations, consultez [Spécifier les URL vers les App Stores](#specify-urls-to-app-stores) plus loin dans cette rubrique.|
|**Importer des applications**|Importe une liste d’applications que vous avez spécifiée dans un fichier de valeurs séparées par des virgules. Utilisez le format, le nom de l’application, l’éditeur et l’URL de l’application dans le fichier.|
|**Modifier**|Vous permet de modifier le nom, l’éditeur et l’URL de l’application sélectionnée.|
|**Supprimer**|Supprime l'application sélectionnée dans la liste.|

### Paramètres du mode plein écran
Spécifiez les paramètres suivants pour les **appareils Samsung KNOX** :

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Sélectionner une application gérée qui peut s’exécuter quand l’appareil est en mode plein écran**|Sélectionnez **Parcourir** et choisissez l’application gérée qui peut s’exécuter quand l’appareil est en mode plein écran (les applications spécifiées sous la forme d’un lien vers le magasin ne sont pas prises en charge). Aucune autre application ne pourra s'exécuter sur l'appareil.|
|**Autoriser les boutons de volume**|Active ou désactive l'utilisation des boutons de volume sur l'appareil.|
|**Activer le bouton Veille/sortie de veille de l'écran**|Active ou désactive le bouton Veille/sortie de veille de l'écran sur l'appareil.|

### Informations de référence pour les applications conformes et non conformes

#### Contrôler les applications conformes et non conformes
Utilisez le **Rapport sur les applications non conformes** pour afficher la conformité des applications autorisées et bloquées.

###### Pour exécuter le rapport sur les applications non conformes

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Rapports** &gt; **Rapport sur les applications non conformes**.

2.  Sélectionnez les groupes d’appareils que vous souhaitez vérifier. Décidez ensuite si vous souhaitez vérifier les applications conformes, les applications non conformes ou les deux. Enfin, choisissez **Afficher le rapport**.

#### Spécifier les URL vers les App Stores
Pour spécifier une URL d’application dans la liste des applications conformes et non conformes, procédez comme suit :

Dans la [section Applications de Google Play](https://play.google.com/store/apps), recherchez l’application à utiliser.

Ouvrez la page d’installation de l’application, puis copiez l’URL dans le Presse-papiers. Vous pouvez maintenant utiliser cette URL dans la liste des applications conformes ou non conformes.

Exemple : Recherchez Microsoft Office Mobile dans Google Play. L’URL que vous utilisez est **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée Android** de Microsoft Intune pour déployer les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Android qui ne sont pas configurables avec des stratégies Intune.

> [!NOTE]
> Actuellement, les stratégies personnalisées Android prennent uniquement en charge la configuration des paramètres Wi-Fi pour les appareils Android qui contiennent une clé prépartagée.

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
    |**Valeur**|Spécifiez la valeur à associer à l’identificateur OMA-URI spécifié précédemment.|

### Exemples

- [Création d’un profil Wi-Fi avec une clé prépartagée](pre-shared-key-wi-fi-profile.md)
- [Utiliser une stratégie personnalisée pour créer un profil VPN par application pour les appareils Android](per-app-vpn-for-android-pulse-secure.md)
- [Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX](custom-policy-to-allow-and-block-samsung-knox-apps.md)

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


