---
title: "Guide du Kit SDK de l’application Microsoft Intune pour les développeurs Android | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 952cfa4f23f8ba080ce53f6785baceb8a0a367c6
ms.openlocfilehash: 829ba47807b3b773c810be290b636d9f18e9c2bd


---

# Guide du Kit de développement logiciel (SDK) de l’application Microsoft Intune pour les développeurs Android

> [!NOTE]
> Vous pouvez d’abord consulter la [Présentation du Kit SDK de l’application Intune](intune-app-sdk.md), qui aborde les fonctionnalités actuelles du SDK et la manière de préparer l’intégration sur chaque plateforme prise en charge. 

## Contenu du SDK 

Le SDK de l’application Intune pour Android est une bibliothèque Android standard sans dépendances externes. Le SDK se compose des éléments suivants :  

* **`Microsoft.Intune MAM.SDK.jar`** : interfaces nécessaires pour prendre en charge la gestion des applications mobiles dans une application, ainsi que l’interopérabilité avec l’application Portail d’entreprise Microsoft Intune. Les applications doivent spécifier ce fichier en tant que référence de bibliothèque Android.

* **`Microsoft.Intune.MAM.SDK.Support.v4.jar`**: interfaces nécessaires pour prendre en charge la gestion des applications mobiles dans les applications qui tirent parti de la bibliothèque de prise en charge v4 Android.  Les applications nécessitant cette prise en charge doivent référencer directement le fichier jar. 

* **`Microsoft.Intune.MAM.SDK.Support.v7.jar`**: interfaces nécessaires pour prendre en charge la gestion des applications mobiles dans les applications qui tirent parti de la bibliothèque de prise en charge v7 Android.   Les applications nécessitant cette prise en charge doivent référencer directement le fichier jar.

* **Répertoire de ressources**: ressources (telles que des chaînes) sur lesquelles repose le SDK. 

* **`Microsoft.Intune.MAM.SDK.aar`** : composants du SDK, à l’exception des fichiers jar Support.V4 et Support.V7. Si votre système de génération prend en charge les fichiers AAR, ce fichier peut être utilisé à la place des composants individuels.

* **`AndroidManifest.xml`** : points d’entrée supplémentaires et exigences de la bibliothèque. 

* **`THIRDPARTYNOTICES.TXT`** : avis d’attribution qui reconnaît le code tiers et/ou OSS qui sera compilé dans votre application. 

## Configuration requise 

Le SDK de l’application Intune est un projet Android compilé. Il est donc en grande partie indépendant de la version d’Android utilisée par l’application pour ses versions d’API (minimale ou cible). Le SDK prend en charge l’API Android de la version 14 (Android 4.0+) à la version 24. 

## Fonctionnement du SDK de l’application Intune 

Le SDK de l’application Intune nécessite la modification du code source d’une application pour permettre l’activation des stratégies de gestion des applications. Pour cela, vous devez remplacer les classes de base Android par des classes managées équivalentes qui sont signalées dans le document par le préfixe `MAM`. Les classes du SDK résident entre la classe de base Android et la propre version dérivée de cette classe de l’application.  Si vous prenez l’exemple d’une activité, vous vous retrouvez avec une hiérarchie d’héritage qui ressemble à ceci : `Activity ->MAMActivity->AppSpecificActivity`.

Quand `AppSpecificActivity` souhaite interagir avec son parent, par exemple `super.onCreate())`, `MAMActivity` est la superclasse, et ce malgré sa présence dans la hiérarchie d’héritage et le remplacement de quelques méthodes. Les applications Android, qui ont un seul mode, peuvent accéder à l’ensemble du système par l’intermédiaire de leur objet Context.  En revanche, les applications qui intègrent le SDK de l’application Intune ont deux modes puisqu’elles continuent à accéder au système par l’intermédiaire de l’objet Context. Toutefois, en fonction de l’activité de base utilisée, l’objet Context est fourni par Android ou fait l’objet d’un multiplexage intelligent entre une vue restreinte du système et l’objet Context fourni par Android.

Le SDK de l’application Intune pour Android repose sur la présence de l’application Portail d’entreprise sur l’appareil pour activer les stratégies de gestion des applications mobiles. Quand l’application Portail d’entreprise n’est pas présente, le comportement de l’application prenant en charge la gestion des applications mobiles n’est pas modifié, et celle-ci agit comme toute autre application mobile. Quand le Portail d’entreprise est installé et qu’une stratégie est appliquée à l’utilisateur, les points d’entrée du SDK sont initialisés en mode asynchrone. L’initialisation est uniquement requise au moment de la création initiale du processus par Android. Pendant l’initialisation, une connexion est établie avec l’application Portail d’entreprise, et la stratégie de restriction d’application est téléchargée.  

## Comment effectuer l’intégration au SDK de l’application Intune
 
Comme indiqué précédemment, le SDK de l’application Intune nécessite la modification du code source de l’application pour permettre l’activation des stratégies de gestion des applications. Voici les étapes que vous devez effectuer pour activer la gestion des applications mobiles dans votre application : 

### Remplacer les classes, méthodes et activités par leurs équivalents MAM (obligatoire) 

* Les classes de base Android doivent être remplacées par leur équivalent MAM. Pour ce faire, recherchez toutes les instances des classes répertoriées dans le tableau ci-dessous et remplacez-les par leur équivalent dans le SDK de l’application Intune.  

    | Classe Android | Classe de remplacement (SDK de l’application Intune) |
    |--|--|
    | android.app.Activity | MAMActivity |
    | android.app.ActivityGroup | MAMActivityGroup |
    | android.app.AliasActivity | MAMAliasActivity |
    | android.app.Application | MAMApplication |
    | android.app.DialogFragment | MAMDialogFragment |
    | android.app.ExpandableListActivity | MAMExpandableListActivity |
    | android.app.Fragment | MAMFragment |
    | android.app.IntentService | MAMIntentService |
    | android.app.LauncherActivity | MAMLauncherActivity |
    | android.app.ListActivity | MAMListActivity |
    | android.app.NativeActivity | MAMNativeActivity |
    | android.app.PendingIntent | MAMPendingIntent |
    | android.app.Service | MAMService |
    | android.app.TabActivity | MAMTabActivity |
    | android.app.TaskStackBuilder | MAMTaskStackBuilder |
    | android.app.backup.BackupAgent | MAMBackupAgent |
    | android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
    | android.app.backup.FileBackupHelper | MAMFileBackupHelper |
    | android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
    | android.content.BroadcastReceiver | MAMBroadcastReceiver |
    | android.content.ContentProvider | MAMContentProvider |
    | android.os.Binder | MAMBinder* |
    | android.provider.DocumentsProvider | MAMDocumentsProvider |
    | android.preference.PreferenceActivity | MAMPreferenceActivity |

    *Vous devez uniquement remplacer Binder par MAMBinder si Binder n’est pas généré à partir d’une interface AIDL.

    **Microsoft.Intune.MAM.SDK.Suppou det.v4.jar**:

    | Classe Android (MAM Intune) | Classe de remplacement (SDK) |
    |--|--|
    | android.support.v4.app.DialogFragment | MAMDialogFragment
    | android.support.v4.app.FragmentActivity | MAMFragmentActivity
    | android.support.v4.app.Fragment | MAMFragment
    | android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
    | android.support.v4.content.FileProvider | MAMFileProvider
    
    **Microsoft.Intune.MAM.SDK.Suppou det.v7.jar**:

    |Classe Android | Classe de remplacement (SDK MAM Intune) |
    |--|--|
    |android.support.v7.app.ActionBarActivity | MAMActionBarActivity |


* Quand vous utilisez un point d’entrée Android qui a été remplacé par son équivalent MAM, une autre version du cycle de vie du point d’entrée doit être utilisée (à l’exception de la classe `MAMApplication`).

    Par exemple, quand vous dérivez de `MAMActivity`au lieu de remplacer `onCreate` et d’appeler `super.onCreate`, l’activité doit remplacer `onMAMCreate` et appeler`uper.onMAMCreate`. Cela permet, dans certains cas, de restreindre le lancement de l’activité (entre autres). 

### Activer les fonctionnalités qui nécessitent la participation de l’application 

Il existe certaines stratégies que le SDK ne peut pas implémenter seul. Pour permettre à l’application de contrôler son comportement pour ces fonctionnalités, nous exposons plusieurs API que vous trouverez dans l’interface `AppPolicy` figurant ci-après.  

    /**
     * External facing app policies.
     */
    public interface AppPolicy {
        /**
         * Restrict where an app can save personal data.
         * 
         * @return True if the app is allowed to save to personal data stores;
         *         false otherwise.
         */
        boolean getIsSaveToPersonalAllowed();
    
        /**
         * Check if policy prohibits saving to a content provider location.
         * 
         * @param location
         *            a content URI to check
         * @return True if location is not a content URI or if policy does not 
         *         prohibit saving to the content location.
         */
        boolean getIsSaveToLocationAllowed(android.net.Uri location); 
    
        /**
         * Whether the SDK PIN prompt is enlightened for the app.
         * 
         * @return True if the PIN is enabled. False otherwise.
         */
        boolean getIsPinRequired();
        /**
         * Whether the Intune Managed Browser is required to open web links.
         *
         * @return True if the Managed Browser is required, false otherwise
         */
        boolean getIsManagedBrowserRequired();
    }

### Permettre à l’administrateur informatique de contrôler le comportement d’enregistrement de l’application

Bon nombre d’applications implémentent des fonctionnalités permettant aux utilisateurs finaux d’enregistrer des fichiers localement ou dans un autre service. Grâce au SDK de l’application Intune, les administrateurs informatiques peuvent se protéger contre les fuites de données en appliquant des restrictions de stratégie adaptées à leur organisation.  Parmi les stratégies dont il a le contrôle, l’administrateur peut définir si l’utilisateur final est autorisé à enregistrer dans un magasin de données personnel (emplacement local, carte SD, services de sauvegarde, etc.). La participation de l’application est nécessaire pour activer la fonctionnalité. Si votre application permet d’enregistrer des données dans des emplacements personnels ou dans le cloud directement à partir de l’application, vous devez implémenter cette fonctionnalité de manière à ce que l’administrateur informatique puisse vérifier si l’enregistrement dans un emplacement est autorisé ou non. L’API ci-dessous permet à l’application de savoir si l’enregistrement dans un magasin personnel est autorisé en fonction de la stratégie d’administration actuelle. L’application peut ensuite appliquer la stratégie puisqu’elle a connaissance du magasin de données personnel accessible à l’utilisateur final dans l’application.  

Pour déterminer si la stratégie est appliquée, l’application peut effectuer l’appel suivant : 

    MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();

**Remarque**: MAMComponents.get(AppPolicy.class) retourne toujours une stratégie d’application non null, même si l’appareil ou l’application n’est pas géré. 

### Permettre à l’application de détecter la nécessité d’une stratégie de code confidentiel
 
 Dans d’autres stratégies, l’application peut avoir besoin de désactiver certaines de ses fonctionnalités pour ne pas dupliquer celles du SDK de l’application Intune. Par exemple, si l’application propose sa propre expérience en matière de code confidentiel, elle souhaitera peut-être la désactiver si le SDK est configuré pour demander à l’utilisateur final d’entrer un code confidentiel. 

Pour déterminer si la stratégie de code confidentiel est configurée pour exiger périodiquement la saisie d’un code confidentiel, l’application peut effectuer l’appel suivant : 

    MAMComponents.get(AppPolicy.class).getIsPinRequired();

### Inscription aux notifications à partir du SDK  

Le SDK de l’application Intune permet à votre application de contrôler son comportement quand certaines stratégies, notamment une stratégie de réinitialisation à distance, sont utilisées par l’administrateur informatique. Pour cela, vous devez vous inscrire aux notifications à partir du SDK en créant une classe `MAMNotificationReceiver` et en l’inscrivant auprès de `MAMNotificationReceiverRegistry`. Vous devez fournir le récepteur et le type de notification que le récepteur souhaite recevoir dans  `App.onCreate`, comme l’illustre l’exemple ci-dessous :
 
    @Override
      public void onCreate() {
            super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class).registerReceiver(
    new ToastNotificationReceiver(), MAMNotificationType.WIPE_USER_DATA);
    }

`MAMNotificationReceiver` reçoit simplement des notifications. Certaines notifications sont gérées directement par le SDK, tandis que d’autres nécessitent la participation de l’application. Une application doit retourner true ou false à la suite d’une notification. Elle doit toujours retourner true, sauf en cas d’échec d’une action entreprise après la notification. Cet échec peut être signalé au service Intune, notamment si l’application indique qu’elle n’a pas pu réinitialiser les données utilisateur. Le blocage de `MAMNotificationReceiver.onReceive`peut se faire en toute sécurité ; son rappel n’est pas exécuté sur le thread de l’interface utilisateur. 

L’interface MAMNotificationReceiver, telle que définie dans le SDK, est incluse ci-dessous : 

    /**
     * The SDK is signaling that a MAM event has occurred. 
     * 
     */
    public interface MAMNotificationReceiver {
      /**
      * A notification was received.
      * 
      * @param notification
      *            The notification that was received.
    * @return The receiver should return true if it handled the
    *   notification without error (or if it decided to ignore the
    *   notification). If the receiver tried to take some action in 
    *   response to the notification but failed to complete that
      *   action it should return false.
      */
      boolean onReceive(MAMNotification notification);
    }

Les notifications suivantes sont envoyées à l’application et certaines d’entre elles peuvent nécessiter la participation de l’application : 

* **Notification `WIPE_USER_DATA`** : cette notification est envoyée dans une classe `MAMUserNotification`. Quand cette notification est reçue, l’application doit supprimer toutes les données associées à l’identité passée avec la classe `MAMUserNotification`. Cette notification est actuellement envoyée lors de l’annulation de l’inscription au service Intune. Le nom principal de l’utilisateur est généralement spécifié au cours du processus d’inscription. Si vous vous inscrivez à cette notification, votre application doit s’assurer que toutes les données utilisateur ont été supprimées. Si vous ne vous inscrivez pas à cette notification, le comportement de réinitialisation sélective par défaut est adopté. 

* **Notification `WIPE_USER_AUXILIARY_DATA`** : les applications peuvent s’inscrire à cette notification si elles souhaitent que le SDK de l’application Intune effectue la réinitialisation par défaut, tout en ayant la possibilité de supprimer des données auxiliaires au moment de la réinitialisation.  

* **Notification `REFRESH_POLICY`** : cette notification est envoyée dans une classe MAMNotification sans informations supplémentaires. Quand cette notification est reçue, toute stratégie mise en cache doit être considérée comme n’étant plus invalidée. La stratégie doit donc être examinée. C’est généralement le SDK qui s’en charge ; toutefois, cette tâche peut revenir à l’application si la stratégie est utilisée de façon permanente. 

### Méthodes et intentions en attente 

Après avoir dérivé d’un des points d’entrée MAM, vous pouvez utiliser normalement l’objet Context pour démarrer les activités, notamment à l’aide de `PackageManager`.  Les classes  `PendingIntents` font exception à cette règle. Quand vous appelez ces classes, vous devez modifier le nom de la classe. Par exemple, au lieu d’utiliser `PendingIntent.get*`, `MAMPendingIntents.get*` . 

Dans certains cas, une méthode disponible dans la classe Android a été marquée comme finale dans la classe de remplacement MAM. Dans ce cas, la classe de remplacement MAM fournit une méthode portant un nom similaire (généralement avec le suffixe « MAM ») qui doit être remplacée. Par exemple, au lieu de remplacer `ContentProvider.query`, vous devez remplacer `MAMContentProvider.queryMAM`. Le compilateur Java doit appliquer les restrictions finales pour éviter que la méthode d’origine ne soit remplacée accidentellement à la place de l’équivalent MAM. 

## Protection des données de sauvegarde 

À compter d’Android Marshmallow (API 23), les applications Android peuvent désormais sauvegarder leurs données de deux façons. Ces options, disponibles pour une utilisation dans votre application, font appel à des étapes différentes pour vérifier que la protection des données MAM est appliquée correctement. Vous pouvez consulter le tableau ci-dessous pour obtenir une vue d’ensemble des actions correspondantes requises à l’adoption d’un comportement de protection des données approprié.  Vous trouverez également d’autres informations sur la sauvegarde Android dans le [guide de sauvegarde des données pour les développeurs Android](http://developer.android.com/guide/topics/data/backup.html). 

### Sauvegarde complète automatique

À compter d’Android M, Android propose des sauvegardes complètes automatiques aux applications, quelle que soit l’API cible en cas d’exécution sur un appareil Android M. Tant que l’attribut `android:allowBackup` n’a pas la valeur false, une application reçoit des sauvegardes complètes et non filtrées. En raison du risque de perte de données, le SDK exige les modifications répertoriées dans le tableau ci-dessous pour vérifier que la protection des données est appliquée.  Il est important de suivre les instructions indiquées ci-dessous pour protéger correctement les données du client.  Si vous définissez `android:allowBackup=false` , votre application ne sera jamais mise en file d’attente par le système d’exploitation en vue de sa sauvegarde. Par ailleurs, dans la mesure où aucune sauvegarde ne sera effectuée, aucune action supplémentaire n’est requise pour la gestion des applications mobiles.
 
 ## Sauvegardes « clé/valeur »

Cette option, accessible à toutes les API, utilise `BackupAgent` et `BackupAgentHelper`. 

#### Utilisation de BackupAgentHelper

`BackupAgentHelper` est beaucoup plus simple à implémenter que `BackupAgent` tant sur le plan des fonctionnalités Android natives que de l’intégration de la gestion des applications mobiles. `BackupAgentHelper` permet au développeur d’inscrire des fichiers entiers et des préférences partagées auprès de `FileBackupHelper` ou de `SharedPreferencesBackupHelper`, respectivement. Ceux-ci sont ensuite ajoutés à `BackupAgentHelper` au moment de la création. 

#### Utilisation de BackupAgent

`BackupAgent` vous permet d’être beaucoup plus explicite quant aux données à sauvegarder. Toutefois, cette option signifie que vous ne pouvez pas tirer parti de l’infrastructure de sauvegarde Android.  Dans la mesure où vous avez la responsabilité de l’implémentation, d’autres étapes sont requises pour assurer la protection appropriée des données de la gestion des applications mobiles. Étant donné que l’essentiel du travail incombe au développeur, c’est-à-dire vous, l’intégration de la gestion des applications mobiles est un peu plus complexe. 

##### L’application ne doit pas être nécessairement un agent de sauvegarde
  
Voici les options à disposition du développeur quand `Android:allowbBackup =true`:

###### Sauvegarde complète en fonction d’un fichier de configuration : 

Fournissez une ressource sous la balise de métadonnées `com.microsoft.intune.mam.FullBackupContent` dans votre manifeste. Par exemple :
    `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Ajoutez l’attribut suivant à la balise `<application>` : `android:fullBackupContent="@xml/my_scheme"`, où `my_scheme` est une ressource XML dans votre application. 

###### Sauvegarde complète sans exclusions 

Fournissez une balise dans le manifeste telle que `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />` 
 
Ajoutez l’attribut suivant à la balise `<application>` : `android:fullBackupContent="true"`.

##### L’application dispose d’un agent de sauvegarde

Suivez les recommandations contenues dans les sections `BackupAgent` et `BackupAgentHelper` ci-dessus. 

Songez à passer à `MAMDefaultFullBackupAgent`, qui permet de sauvegarder facilement sur Android M. 

#### Avant la sauvegarde

Avant de lancer la sauvegarde, vous devez vérifier que les mémoires tampons de fichiers ou de données que vous envisagez de sauvegarder sont autorisées à être sauvegardées. Pour cela, utilisez la fonction `isBackupAllowed` disponible dans `MAMFileProtectionManager` et `MAMDataProtectionManager` . Si la mémoire tampon de fichiers ou de données ne peut pas être sauvegardée, vous ne devez pas essayer de vous en servir dans votre sauvegarde.

À un moment donné de la sauvegarde, si vous souhaitez sauvegarder les identités des fichiers vérifiés lors de l’étape 1, vous devez appeler `backupMAMFileIdentity(BackupDataOutput data, File … files)` avec les fichiers dont vous souhaitez extraire les données. Des entités de sauvegarde sont alors automatiquement créées et écrites dans `BackupDataOutput` pour vous. Ces entités sont automatiquement consommées lors de la restauration. 

### Configurer Azure Directory Authentication Library (ADAL)  

Le SDK s’appuie sur la bibliothèque ADAL pour ses scénarios d’authentification et de lancement conditionnel, ce qui nécessite que les applications soient en partie configurées pour Azure Active Directory. Les valeurs de configuration sont communiquées au SDK par le biais de métadonnées `AndroidManifest` . Pour configurer votre application et mettre en œuvre une authentification approprié, ajoutez le code suivant au nœud de l’application dans `AndroidManifest`. Certaines de ces configurations sont uniquement nécessaires si votre application utilise la bibliothèque ADAL pour l’authentification en général. Dans ce cas, vous avez besoin des valeurs spécifiques que votre application utilise pour s’inscrire auprès d’AAD. De cette façon, l’utilisateur final n’est pas invité à s’authentifier à deux reprises quand AAD détecte deux valeurs d’inscription distinctes : l’une provenant de l’application et l’autre du SDK. 

        <meta-data
            android:name="com.microsoft.intune.mam.aad.Authority"
            android:value="https://AAD authority/" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.ClientID"
            android:value="your-client-ID-GUID" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
            android:value="your-redirect-URI" />
        <meta-data
            android:name="com.microsoft.intune.mam.aad.SkipBroker"
            android:value="[true | false]" />

Les GUID ne sont pas censés avoir une accolade de début ou de fin.

#### Configurations ADAL courantes 

Voici les configurations courantes des valeurs expliquées ci-dessus. 

##### L’application n’intègre pas la bibliothèque ADAL

* L’autorité doit être définie avec l’environnement désiré dans lequel les comptes AAD ont été configurés.

* SkipBroker doit avoir la valeur true.

##### L’application intègre la bibliothèque ADAL

* L’autorité doit être définie avec l’environnement désiré dans lequel les comptes AAD ont été configurés.

* L’ID de client doit être défini avec l’ID client de l’application.

* `NonBrokerRedirectURI` doit être défini avec un URI de redirection valide pour l’application.
    * Or `urn:ietf:wg:oauth:2.0:oob` doit être configuré en tant qu’URI de redirection AAD valide.

* SkipBroker doit avoir la valeur false (ou être absent)

* AAD doit être configuré pour accepter l’URI de redirection du service Broker.

##### L’application intègre la bibliothèque ADAL, mais ne prend pas en charge l’application AAD Authenticator.

* L’autorité doit être définie avec l’environnement désiré dans lequel les comptes AAD ont été configurés.

* L’ID de client doit être défini avec l’ID client de l’application.

* `NonBrokerRedirectURI` doit être défini avec un URI de redirection valide pour l’application.

    * Or `urn:ietf:wg:oauth:2.0:oob` doit être configuré en tant qu’URI de redirection AAD valide.

### Comment activer la journalisation dans le SDK 

La journalisation est effectuée par le biais de infrastructure `java.util.logging` . Pour recevoir les journaux, configurez la journalisation globale comme décrit dans le [guide technique Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). En fonction de l’application, `App.onCreate` est généralement le meilleur endroit pour lancer la journalisation. Notez que les messages du journal sont indexés par le nom de la classe, lequel peut être masqué.

## Limitations de plateforme connues 

### Limitations concernant la taille des fichiers 

Sur Android, les limitations du format de fichier exécutable Dalvik peuvent devenir un problème pour les grandes bases de code qui s’exécutent sans ProGuard. Plus précisément, les limitations suivantes peuvent se produire : 

* Limite de 65 Ko sur les champs

* Limite de 65 Ko sur les méthodes

Quand vous incluez plusieurs projets, chaque android:package reçoit une copie de R, ce qui augmente considérablement le nombre de champs au fur et à mesure que des bibliothèques sont ajoutées. Les recommandations suivantes peuvent vous aider à atténuer cette limitation :
 
* Tous les projets de bibliothèque doivent partager le même android:package dans la mesure du possible. Cela ne se traduit pas par un échec sporadique dans le champ dans la mesure où il s’agit simplement d’un problème au moment de la génération.   En outre, les versions plus récentes du SDK Android effectuent un prétraitement des fichiers DEX pour ôter une partie de la redondance. Cela permet de réduire davantage la distance entre les champs.

* Utilisez les outils de génération du SDK Android les plus récents.

* Supprimez toutes les bibliothèques inutiles et inutilisées (par exemple, `android.support.v4`)

### Limitations concernant l’application de la stratégie

**Capture d’écran**: le SDK ne peut pas appliquer une nouvelle valeur de capture d’écran dans les activités qui sont déjà passées par Activity.onCreate. Il peut en résulter une période au cours de laquelle l’application est configurée pour désactiver les captures d’écran ; toutefois, il est toujours possible d’en prendre.

**Utilisation de programmes de résolution de contenu* : la stratégie de transfert ou de réception peut bloquer entièrement ou en partie l’utilisation d’un programme de résolution de contenu pour accéder au fournisseur de contenu dans une autre application. Par conséquent, les méthodes ContentResolver retournent null ou lèvent une valeur d’échec (par exemple, `openOutputStream` lève `FileNotFoundException` en cas de blocage). L’application peut déterminer si l’échec de l’écriture des données par le biais d’un programme de résolution de contenu est causé par une stratégie (ou pourrait être causé par une stratégie) en appelant :

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Services exportés**: le fichier `AndroidManifest.xml` inclus dans le SDK de l’application Intune contient `MAMNotificationReceiverService`. Il doit s’agir d’un service exporté pour autoriser le Portail d’entreprise à envoyer des notifications à une application compatible. Le service vérifie l’appelant pour s’assurer que seul le Portail d’entreprise est autorisé à envoyer des notifications. 

## Meilleures pratiques recommandées pour Android 

Le SDK Intune respecte le contrat fourni par l’API Android, bien que des conditions d’échec puissent être déclenchées plus fréquemment à la suite de l’application de stratégies. Ces meilleures pratiques pour Android réduisent la probabilité d’un échec : 

* Il est fort probable que les fonctions du SDK Android susceptibles de retourner null sont déjà null.  Pour réduire les problèmes, assurez-vous que les vérifications null sont placées au bon endroit.

* Les fonctionnalités qui peuvent faire l’objet d’une vérification doivent être vérifiées par l’intermédiaire des API de leur Kit SDK.

* Les appels des fonctions dérivées doivent être acheminés aux versions de leurs superclasses.

* Évitez d’utiliser les API de façon ambiguë. Par exemple, l’utilisation d’ `Activity.startActivityForResult/onActivityResult` sans vérifier requestCode entraîne un comportement étrange.



<!--HONumber=Sep16_HO2-->


