---
title: "Guide du Kit SDK de l’application Microsoft Intune pour les développeurs Android | Documentation Microsoft"
description: "Le SDK d’application Microsoft Intune pour Android vous permet d’incorporer la gestion des applications mobiles Intune à votre application Android."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 905be6a926dc5bab8e9b1016ba82751ee47313e5
ms.openlocfilehash: 178fbaeb1d3235a81cb4da49b7a955f6999c49a2
ms.lasthandoff: 02/18/2017


---


# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a>Guide du Kit SDK de l’application Microsoft Intune pour les développeurs Android

> [!NOTE]
> Vous pouvez d’abord consulter la [Présentation du SDK de l’application Intune](intune-app-sdk.md), qui aborde les fonctionnalités actuelles du SDK et la manière de préparer l’intégration sur chaque plateforme prise en charge.

Le SDK d’application Microsoft Intune pour Android vous permet d’incorporer la gestion des applications mobiles Intune à votre application Android. Une application compatible GAM est une application intégrée au SDK d’application Intune. Elle permet aux administrateurs informatiques de déployer des stratégies sur votre application mobile quand celle-ci est activement gérée par Intune.

## <a name="whats-in-the-sdk"></a>Contenu du SDK

Le SDK de l’application Intune pour Android est une bibliothèque Android standard sans dépendances externes. Le SDK se compose des éléments suivants :  

* **Microsoft.Intune.MAM.SDK.jar** : interfaces nécessaires pour prendre en charge la gestion des applications mobiles, ainsi que l’interopérabilité avec l’application Portail d’entreprise Intune. Les applications doivent spécifier ce fichier en tant que référence de bibliothèque Android.

* **Microsoft.Intune.MAM.SDK.Support.v4.jar** : interfaces nécessaires pour prendre en charge la gestion des applications mobiles dans les applications qui utilisent la bibliothèque de prise en charge v4 Android. Les applications nécessitant cette prise en charge doivent référencer directement le fichier JAR.

* **Microsoft.Intune.MAM.SDK.Support.v7.jar** : interfaces nécessaires pour prendre en charge la gestion des applications mobiles dans les applications qui utilisent la bibliothèque de prise en charge v7 Android. Les applications nécessitant cette prise en charge doivent référencer directement le fichier JAR.

* **Répertoire de ressources** : ressources (telles que des chaînes) sur lesquelles repose le SDK.

* **Microsoft.Intune.MAM.SDK.aar** : composants du SDK, à l’exception des fichiers JAR Support.V4 et Support.V7. Si votre système de génération prend en charge les fichiers AAR, ce fichier peut être utilisé à la place des composants individuels.

* **AndroidManifest.xml** : points d’entrée supplémentaires et exigences de la bibliothèque.

* **THIRDPARTYNOTICES.TXT** : avis d’attribution qui reconnaît que le code tiers et/ou OSS sera compilé dans votre application.

## <a name="requirements"></a>Configuration requise

Le SDK de l’application Intune est un projet Android compilé. Ainsi, il est en grande partie non affecté par la version d’Android utilisée par l’application pour ses versions d’API (minimale ou cible). Le SDK prend en charge l’API Android de la version 14 (Android 4.0+) à la version 24.

Le SDK de l’application Intune pour Android repose sur la présence de l’application [Portail d’entreprise](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) sur l’appareil pour activer les stratégies de gestion des applications mobiles. Pour la gestion des applications mobiles sans inscription des appareils, l’utilisateur n’est *pas* obligé d’inscrire l’appareil à l’aide de l’application Portail d’entreprise.


## <a name="how-the-intune-app-sdk-works"></a>Fonctionnement du SDK d’application Intune

###<a name="entry-points"></a>Points d’entrée

Le SDK de l’application Intune nécessite la modification du code source d’une application pour permettre l’activation des stratégies de gestion des applications Intune. Pour cela, vous devez remplacer les classes de base Android par des classes de base Intune équivalentes, dont les noms portent le préfixe `MAM`. Les classes du SDK résident entre la classe de base Android et la propre version dérivée de cette classe de l’application. Si vous prenez l’exemple d’une activité, vous vous retrouvez avec une hiérarchie d’héritage qui ressemble à ceci : `Activity` > `MAMActivity` > `AppSpecificActivity`.

Par exemple, quand `AppSpecificActivity` interagit avec son parent (par exemple, un appel à `super.onCreate()`), `MAMActivity` est la super classe.

Les applications Android classiques ont un seul mode et peuvent accéder au système par l’intermédiaire de leur objet [Context](https://developer.android.com/reference/android/content/Context.html). En revanche, les applications qui intègrent le SDK de l’application Intune ont deux modes. Ces applications continuent à accéder au système par le biais de l’objet `Context`. En fonction de l’`Activity` de base utilisée, l’objet `Context` sera fourni par Android ou sera multiplexé intelligemment entre une vue restreinte du système et le `Context` fourni par Android.

Quand un [point d’entrée](https://developer.android.com/guide/components/fundamentals.html) Android a été remplacé par son équivalent MAM, la version MAM du cycle de vie du point d’entrée doit être utilisée (à l’exception de la classe `MAMApplication`).

Par exemple, quand vous dérivez de `MAMActivity` au lieu de remplacer `onCreate` et d’appeler `super.onCreate`, `Activity` doit remplacer `onMAMCreate` et appeler `super.onMAMCreate`. Cela permet à Intune de restreindre le lancement d’`Activity` (entre autres) dans certains cas.


###<a name="sdk-permissions"></a>Autorisations du SDK

Le SDK d’application Intune nécessite trois [autorisations système Android](https://developer.android.com/guide/topics/security/permissions.html) sur les applications qui l’intègrent :

* `android.permission.GET_ACCOUNTS` (demandée au moment de l’exécution, si nécessaire)

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

La bibliothèque d’authentification Azure Active Directory ([ADAL](https://azure.microsoft.com/en-us/documentation/articles/active-directory-authentication-libraries/)) exige ces autorisations pour effectuer l’authentification répartie. Si ces autorisations ne sont pas accordées à l’application ou qu’elles sont révoquées par l’utilisateur, les flux d’authentification qui requièrent le service broker (l’application Portail d’entreprise) sont désactivés.


###<a name="company-portal-app"></a>Application Portail d’entreprise

Pourquoi l’application Portail d’entreprise est-elle requise ? Quand l’application Portail d’entreprise est installée sur l’appareil et qu’il a récupéré du service Intune la stratégie de restriction d’application pour l’utilisateur, les points d’entrée du SDK sont initialisés en mode asynchrone. L’initialisation est nécessaire uniquement quand Android crée initialement le processus. Pendant l’initialisation, une connexion est établie avec l’application Portail d’entreprise et la stratégie est récupérée à partir de l’application.  

> [!NOTE]
> Quand l’application Portail d’entreprise n’est pas sur l’appareil, le comportement de l’application prenant en charge Intune n’est pas modifié, et celle-ci se comporte comme une application normale.


## <a name="how-to-integrate-with-the-intune-app-sdk"></a>Comment effectuer l’intégration au SDK de l’application Intune

Comme indiqué précédemment, le SDK de l’application Intune nécessite la modification du code source de l’application pour permettre l’activation des stratégies de gestion des applications. Voici les étapes nécessaires pour activer la gestion des applications mobiles dans votre application.

### <a name="replace-classes-methods-and-activities-with-their-mam-equivalent-required"></a>Remplacer les classes, méthodes et activités par leurs équivalents MAM (obligatoire)

Les classes de base Android doivent être remplacées par leurs équivalents MAM respectifs. Pour ce faire, recherchez toutes les instances des classes répertoriées dans le tableau suivant et remplacez-les par leur équivalent dans le SDK de l’application Intune.

| Classe de base Android | Classe de remplacement (SDK de l’application Intune) |
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
| android.app.PendingIntent | MAMPendingIntent* |
| android.app.Service | MAMService |
| android.app.TabActivity | MAMTabActivity |
| android.app.TaskStackBuilder | MAMTaskStackBuilder |
| android.app.backup.BackupAgent | MAMBackupAgent |
| android.app.backup.BackupAgentHelper | MAMBackupAgentHelper |
| android.app.backup.FileBackupHelper | MAMFileBackupHelper |
| android.app.backup.SharePreferencesBackupHelper | MAMSharedPreferencesBackupHelper |
| android.content.BroadcastReceiver | MAMBroadcastReceiver |
| android.content.ContentProvider | MAMContentProvider |
| android.os.Binder | MAMBinder (nécessaire uniquement si le Binder n’est pas généré à partir d’une interface AIDL (Android Interface Definition Language)) |
| android.provider.DocumentsProvider | MAMDocumentsProvider |
| android.preference.PreferenceActivity | MAMPreferenceActivity |


**Microsoft.Intune.MAM.SDK.Suppou det.v4.jar**:

| Classe Android (GAM Intune) | Classe de remplacement (SDK de l’application Intune) |
|--|--|
| android.support.v4.app.DialogFragment | MAMDialogFragment
| android.support.v4.app.FragmentActivity | MAMFragmentActivity
| android.support.v4.app.Fragment | MAMFragment
| android.support.v4.app.TaskStackBuilder | MAMTaskStackBuilder
| android.support.v4.content.FileProvider | MAMFileProvider

**Microsoft.Intune.MAM.SDK.Suppou det.v7.jar**:

|Classe Android | Classe de remplacement (SDK de l’application Intune) |
|--|--|
|android.support.v7.app.ActionBarActivity | MAMActionBarActivity |

>[!NOTE]
>Gardez à l’esprit que quand un [point d’entrée](https://developer.android.com/guide/components/fundamentals.html) Android a été remplacé par son équivalent MAM, la version MAM du cycle de vie du point d’entrée doit être utilisée (à l’exception de la classe `MAMApplication`).
>
>Par exemple, quand vous dérivez de `MAMActivity` au lieu de remplacer `onCreate` et d’appeler `super.onCreate`, `Activity` doit remplacer `onMAMCreate` et appeler `super.onMAMCreate`. Cela permet à Intune de restreindre le lancement d’`Activity` (entre autres) dans certains cas.

#### <a name="pendingintent-classes-and-renamed-methods"></a>Classes PendingIntent et méthodes renommées

Une fois que vous avez dérivé de l’un des points d’entrée MAM, vous pouvez sans risque utiliser `Context` comme vous le feriez normalement (par exemple, démarrer des classes `Activity` et utiliser `PackageManager`).  

Les classes `PendingIntent` font exception à cette règle. Quand vous appelez ces classes, vous devez modifier le nom de la classe. Par exemple, au lieu de `PendingIntent.get*`, vous devez utiliser la méthode `MAMPendingIntent.get*`. Après cela, vous pouvez utiliser la classe `PendingIntent` résultante comme d’habitude.

Dans certains cas, une méthode disponible dans la classe Android a été marquée comme finale dans la classe de remplacement MAM. Dans ce cas, la classe de remplacement MAM fournit une méthode portant un nom similaire (généralement avec le suffixe `MAM`) que vous devez remplacer. Par exemple, au lieu de remplacer `ContentProvider.query`, vous devez remplacer `MAMContentProvider.queryMAM`. Le compilateur Java doit appliquer les restrictions finales pour éviter que la méthode d’origine ne soit remplacée accidentellement à la place de l’équivalent MAM.

###<a name="enable-features-that-require-app-participation"></a>Activer les fonctionnalités qui nécessitent la participation de l’application

Le SDK ne peut pas implémenter certaines stratégies seul. L’application peut contrôler son comportement pour avoir ces fonctionnalités à l’aide de plusieurs API que vous trouverez dans l’interface `AppPolicy` suivante.

```
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * <strong>This function is now deprecated. Please use {@link #getIsSaveToLocationAllowed(SaveLocation, String)} instead</strong>
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();


}

```

### <a name="enable-it-control-over-app-saving-behavior"></a>Permettre à l’administrateur informatique de contrôler le comportement d’enregistrement de l’application

Bon nombre d’applications implémentent des fonctionnalités permettant aux utilisateurs d’enregistrer des fichiers localement ou dans un service de stockage cloud. Grâce au SDK d’application Intune, les administrateurs informatiques peuvent se protéger contre les fuites de données en appliquant des restrictions de stratégie adaptées à leur organisation.  Parmi les stratégies dont il a le contrôle, l’administrateur informatique peut définir si l’utilisateur est autorisé à enregistrer dans un magasin de données non géré « personnel » (emplacement local, carte SD, services de sauvegarde tiers, etc.).

La participation de l’application est nécessaire pour activer la fonctionnalité. Si votre application autorise l’enregistrement des données dans des emplacements personnels ou dans le cloud directement à partir de l’application, vous devez implémenter cette fonctionnalité pour que l’administrateur informatique puisse vérifier si l’enregistrement dans un emplacement est autorisé.   

Pour déterminer si la stratégie est appliquée, l’application peut effectuer l’appel suivant. Cet appel permet à l’application de savoir si la stratégie de l’administrateur Intune actuel autorise l’enregistrement dans un magasin personnel. L’application peut ensuite appliquer la stratégie, car elle a connaissance du magasin de données personnel accessible à l’utilisateur dans l’application.

```
MAMComponents.get(AppPolicy.class).getIsSaveToPersonalAllowed();
```

> [!NOTE]
> `MAMComponents.get(AppPolicy.class)` retourne toujours une stratégie d’application non null, même si l’appareil ou l’application n’est pas placé sous une stratégie de gestion Intune.

### <a name="let-the-app-detect-if-a-pin-policy-is-required"></a>Laisser l’application détecter si une stratégie de code confidentiel est nécessaire

Pour certaines restrictions d’application Intune, vous pouvez juger utile que l’application désactive certaines de ses fonctionnalités pour ne pas dupliquer celles du SDK d’application Intune. Par exemple, si l’application propose sa propre expérience en matière de code confidentiel, vous souhaiterez peut-être la désactiver si le SDK est configuré pour demander à l’utilisateur d’entrer un code confidentiel.

Pour déterminer si une stratégie de code confidentiel Intune est configurée pour exiger un code confidentiel d’application au lancement, l’application peut effectuer cet appel :

```
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <a name="register-for-notifications-from-the-sdk"></a>S’inscrire aux notifications à partir du SDK  

Le SDK de l’application Intune permet à votre application de contrôler le comportement de certaines stratégies, notamment la réinitialisation sélective, quand l’administrateur informatique les déploie. Quand un administrateur informatique déploie une stratégie de ce type, le service Intune envoie une notification au SDK.

Votre application doit s’inscrire aux notifications en provenance du SDK en créant une classe `MAMNotificationReceiver` et en l’inscrivant auprès de `MAMNotificationReceiverRegistry`. Vous devez pour cela fournir le récepteur et le type de notification souhaité dans `App.onCreate`, comme l’illustre cet exemple :

```
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
.registerReceiver(
                new ToastNotificationReceiver(),
MAMNotificationType.WIPE_USER_DATA);
    }
```

`MAMNotificationReceiver` reçoit simplement des notifications à partir du service Intune. Le SDK gère certaines notifications directement. D’autres notifications exigent la participation de l’application.

Une application *doit* retourner true ou false à la suite d’une notification. Elle doit toujours retourner true, sauf en cas d’échec d’une action entreprise après la notification. Cet échec peut être signalé au service Intune. C’est par exemple le cas si l’application ne peut pas réinitialiser les données de l’utilisateur après le lancement d’une réinitialisation par l’administrateur informatique.

Le blocage de `MAMNotificationReceiver.onReceive` peut se faire en toute sécurité, car son rappel n’est pas exécuté sur le thread de l’interface utilisateur.

L’interface `MAMNotificationReceiver` suivante est définie dans le SDK :

```
/**
 * The SDK is signaling that a WG event has occurred.
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

```

###<a name="types-of-notifications"></a>Types de notifications

Les notifications suivantes sont envoyées à l’application. Certaines d’entre elles peuvent nécessiter la participation de l’application.

* **`WIPE_USER_DATA`** : cette notification est envoyée dans une classe `MAMUserNotification`. Quand cette notification est reçue, l’application est censée supprimer toutes les données associées à l’identité « d’entreprise » passée avec la classe `MAMUserNotification`. Cette notification est actuellement envoyée lors de l’annulation de l’inscription au service Intune. Le nom principal de l’utilisateur est généralement spécifié au cours du processus d’inscription. Si vous vous inscrivez à cette notification, votre application doit s’assurer que toutes les données de l’utilisateur ont été supprimées. Si vous ne vous inscrivez pas à cette notification, l’application adopte le comportement de réinitialisation sélective par défaut.

* **`WIPE_USER_AUXILIARY_DATA`** : les applications peuvent s’inscrire à cette notification si elles souhaitent que le SDK de l’application Intune adopte le comportement de réinitialisation sélective par défaut, tout en ayant la possibilité de supprimer des données auxiliaires au moment de la réinitialisation.  

* **`REFRESH_POLICY`** : cette notification est envoyée dans `MAMUserNotification`. Quand cette notification est reçue, toute stratégie Intune mise en cache doit être invalidée et mise à jour. Le SDK gère généralement cette tâche, mais l’application doit la gérer si la stratégie est utilisée de manière permanente.



### <a name="protection-of-backup-data"></a>Protection des données de sauvegarde

À compter d’Android Marshmallow (API 23), les applications Android peuvent sauvegarder leurs données de deux façons. Chaque option est disponible pour votre application et requiert différentes étapes pour assurer l’implémentation correcte de la protection des données Intune. Pour en savoir plus sur les méthodes de sauvegarde, vous pouvez consulter le [guide des API Android](http://developer.android.com/guide/topics/data/backup.html).

#### <a name="automatic-backup-for-apps"></a>Sauvegarde automatique pour les applications

Android a commencé à proposer des [sauvegardes complètes automatiques](https://developer.android.com/guide/topics/data/autobackup.html) aux applications sur les appareils Android Marshmallow, quelle que soit l’API cible de l’application. Si vous affectez explicitement la valeur false à `android:allowBackup` dans votre fichier AndroidManifest.xml, Android ne place jamais votre application en file d’attente pour les sauvegardes, et les données « d’entreprise » demeurent dans l’application. Dans ce cas, aucune action supplémentaire n’est nécessaire.

Par défaut, l’attribut `android:allowBackup` a la valeur true, même si `android:allowBackup` n’est pas spécifié dans le fichier manifeste. Cela signifie que toutes les données d’application sont automatiquement sauvegardées dans le compte Google Drive de l’utilisateur, comportement par défaut qui représente un *risque de fuite de données*. Le SDK nécessite les modifications suivantes pour vérifier que la protection des données est appliquée. Il est important de suivre ces instructions pour protéger correctement les données des clients si vous souhaitez que votre application s’exécute sur les appareils Android Marshmallow.  

Si vous n’avez pas écrit d’agent de sauvegarde pour sauvegarder votre application à l’aide de `MAMBackupAgent` ou `MAMBackupAgentHelper`, vous devez prendre en compte et contrôler comment la Sauvegarde automatique chargera vos données d’application. Intune vous permet d’utiliser toutes les [fonctionnalités de Sauvegarde automatique](https://developer.android.com/guide/topics/data/autobackup.html) disponibles à partir d’Android, notamment la possibilité de définir des règles personnalisées en code XML. Vous devez cependant suivre ces étapes pour aider à sécuriser vos données :

1. Utilisez le `MAMBackupAgent` par défaut pour autoriser les sauvegardes complètes automatiques conformes aux stratégies Intune. Placez `android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"` dans le manifeste de votre application.

2. Quand vous choisissez le type de sauvegarde complète que votre application doit recevoir (non filtré, filtré ou aucun), affectez à l’attribut `android:fullBackupContent` la valeur true, false, ou une ressource XML dans votre application. Copiez ce que vous mettez dans `android:fullBackupContent` dans une balise de métadonnées nommée `com.microsoft.intune.mam.FullBackupContent`.

    Par exemple, si vous souhaitez que votre application ait des sauvegardes complètes en fonction de vos règles personnalisées dans un fichier XML, indiquez une ressource sous la balise de métadonnées `com.microsoft.intune.mam.FullBackupContent` dans le manifeste comme suit :
    ```
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```



#### <a name="keyvalue-backup"></a>Sauvegarde clé/valeur

L’option de sauvegarde de clé/valeur est accessible à toutes les API et elle utilise `BackupAgentHelper` et `BackupAgent`.

##### <a name="backupagenthelper"></a>BackupAgentHelper

`BackupAgentHelper` est beaucoup plus simple à implémenter que `BackupAgent`, tant sur le plan des fonctionnalités Android natives que de l’intégration de la gestion des applications mobiles. `BackupAgentHelper` vous permet d’inscrire des fichiers entiers et des préférences partagées dans `FileBackupHelper` ou `SharedPreferencesBackupHelper`, respectivement. Ils sont ensuite ajoutés à `BackupAgentHelper` lors de la création.

##### <a name="backupagent"></a>BackupAgent

`BackupAgent` vous permet d’être beaucoup plus explicite quant aux données à sauvegarder. Mais cette option signifie que vous ne pouvez pas tirer parti du framework de sauvegarde Android. Dans la mesure où vous avez la responsabilité de l’implémentation, d’autres étapes sont nécessaires pour assurer la protection appropriée des données de la gestion des applications mobiles. L’essentiel du travail incombant au développeur, c’est-à-dire vous, l’intégration de la gestion des applications mobiles est un peu plus complexe.

###### <a name="app-does-not-have-a-backup-agent"></a>L’application ne doit pas être nécessairement un agent de sauvegarde

Voici les options à disposition du développeur quand `android:allowBackup =true`.

####### <a name="full-backup-according-to-a-configuration-file"></a>Sauvegarde complète en fonction d’un fichier de configuration

Fournissez une ressource sous la balise de métadonnées `com.microsoft.intune.mam.FullBackupContent` dans votre manifeste. Par exemple :     `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />`

Ajoutez l’attribut suivant à la balise `<application>` : `android:fullBackupContent="@xml/my_scheme"`, où `my_scheme` est une ressource XML dans votre application.

####### <a name="full-backup-without-exclusions"></a>Sauvegarde complète sans exclusions

Fournissez une balise dans le manifeste, comme `<meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />`.

Ajoutez l’attribut suivant à la balise `<application>` : `android:fullBackupContent="true"`.

###### <a name="app-has-a-backup-agent"></a>L’application dispose d’un agent de sauvegarde

Suivez les recommandations fournies précédemment dans ce guide pour `BackupAgent` et `BackupAgentHelper`.

Songez à passer à `MAMDefaultFullBackupAgent`, qui permet de sauvegarder facilement sur Android Marshmallow.

##### <a name="before-your-backup"></a>Avant la sauvegarde

Avant de lancer la sauvegarde, vous devez vérifier que les mémoires tampons de fichiers ou de données que vous prévoyez de sauvegarder sont autorisées à être sauvegardées. Pour cela, nous avons mis à votre disposition une fonction `isBackupAllowed` dans `MAMFileProtectionManager` et `MAMDataProtectionManager`. Si la mémoire tampon de fichiers ou de données ne peut pas être sauvegardée, vous ne devez pas essayer de vous en servir dans votre sauvegarde.

À un moment donné de la sauvegarde, si vous souhaitez sauvegarder les identités des fichiers vérifiés lors de l’étape 1, vous devez appeler `backupMAMFileIdentity(BackupDataOutput data, File … files)` avec les fichiers dont vous souhaitez extraire les données. Des entités de sauvegarde sont alors automatiquement créées et écrites dans `BackupDataOutput` pour vous. Ces entités sont automatiquement consommées lors de la restauration.

#### <a name="azure-directory-authentication-library-setup"></a>Configuration de la bibliothèque d’authentification Azure Active Directory  

Le SDK utilise la bibliothèque ADAL pour ses scénarios d’authentification et de lancement conditionnel. Ces scénarios exigent que les applications aient une certaine part de configuration Azure Active Directory (Azure AD). Les valeurs de configuration sont communiquées au SDK par le biais de métadonnées `AndroidManifest` .

Pour configurer votre application et mettre en œuvre une authentification appropriée, ajoutez le code suivant au nœud de l’application dans `AndroidManifest`. Certaines de ces configurations sont nécessaires uniquement si votre application utilise la bibliothèque ADAL pour l’authentification en général. Dans ce cas, vous aurez besoin des valeurs spécifiques utilisées par votre application pour s’inscrire auprès d’Azure AD. Ainsi, l’utilisateur n’est pas invité à s’authentifier à deux reprises car Azure AD détecte deux valeurs d’inscription distinctes : l’une provenant de l’application et l’autre du SDK.

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

##### <a name="common-adal-configurations"></a>Configurations ADAL courantes

Voici les configurations courantes pour les valeurs expliquées ci-dessus.

###### <a name="app-does-not-integrate-adal"></a>L’application n’intègre pas la bibliothèque ADAL

* L’autorité doit être définie avec l’environnement désiré dans lequel les comptes Azure AD ont été configurés.

* SkipBroker doit avoir la valeur true.

###### <a name="app-integrates-adal"></a>L’application intègre la bibliothèque ADAL

* L’autorité doit être définie avec l’environnement désiré dans lequel les comptes Azure AD ont été configurés.

* L’ID de client doit être défini avec l’ID client de l’application.

* `NonBrokerRedirectURI` doit être défini avec un URI de redirection valide pour l’application. Ou `urn:ietf:wg:oauth:2.0:oob` doit être défini en tant qu’URI de redirection Azure AD valide.

* SkipBroker doit avoir la valeur false (ou être absent).

* Azure AD doit être configuré pour accepter l’URI de redirection du service Broker.

###### <a name="app-integrates-adal-but-does-not-support-the-azure-ad-authenticator-app"></a>L’application intègre la bibliothèque ADAL, mais ne prend pas en charge l’application Azure AD Authenticator

* L’autorité doit être définie avec l’environnement désiré dans lequel les comptes Azure AD ont été configurés.

* L’ID de client doit être défini avec l’ID client de l’application.

* `NonBrokerRedirectURI` doit être défini avec un URI de redirection valide pour l’application. Ou `urn:ietf:wg:oauth:2.0:oob` doit être défini en tant qu’URI de redirection Azure AD valide.

#### <a name="logging-in-the-sdk"></a>Journalisation dans le SDK

La journalisation est effectuée par le biais de l’infrastructure `java.util.logging` . Pour recevoir les journaux, configurez la journalisation globale comme décrit dans le [guide technique Java](http://docs.oracle.com/javase/6/docs/technotes/guides/logging/overview.html). En fonction de l’application, `App.onCreate` est généralement le meilleur endroit pour lancer la journalisation. Notez que les messages du journal sont indexés par le nom de la classe, qui peut être masqué.

###<a name="multi-identity"></a>Prise en charge de plusieurs identités

Par défaut, le SDK d’application Intune applique une stratégie à l’application dans son ensemble. La multi-identité est une fonctionnalité GAM que vous pouvez activer pour appliquer une stratégie par niveau d’identité. Ceci nécessite une participation nettement accrue de l’application par rapport à d’autres fonctionnalités GAM. L’application doit informer le SDK d’application quand elle va changer l’identité active. Le SDK doit aussi notifier l’application quand un changement d’identité est nécessaire.

Actuellement, une seule identité gérée est prise en charge. Une fois que l’utilisateur inscrit l’appareil ou l’application, le SDK utilise cette identité et la considère comme l’identité gérée principale. Les autres utilisateurs de l’application sont considérés comme non gérés avec des paramètres de stratégie non limités.

Notez qu’une identité est simplement définie sous la forme d’une chaîne. Les identités ne respectent pas la casse. Les demandes d’une identité au SDK peuvent ne pas retourner la même casse que celle initialement utilisée lors de la définition de l’identité.

####<a name="enabling-multi-identity"></a>Activation de la multi-identité

Par défaut, toutes les applications sont considérées comme des applications d’identité unique. Une application déclare qu’elle prend en charge plusieurs identités en plaçant les métadonnées suivantes dans le manifeste Android.

```
<meta-data
            android:name="com.microsoft.intune.mam.MAMMultiIdentity"
            android:value="true" />
```
####<a name="setting-the-identity"></a>Définition de l’identité

Vous pouvez définir l’identité de l’application sur les niveaux suivants :

1. Processus

2. Contexte (généralement `Activity`)

3. Thread

Une identité définie au niveau du thread remplace une identité définie au niveau `Context`, qui remplace elle-même une identité définie au niveau du processus. Une identité définie sur `Context` est utilisée uniquement en cas de nécessité. Par exemple, aucun `Context` n’est associé aux tâches d’E/S de fichier. Vous pouvez utiliser les méthodes suivantes sur `MAMPolicyManager` pour définir l’identité et extraire les valeurs d’identité définies précédemment.

```
public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

public static String getUIPolicyIdentity(final Context context);

public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

public static String getProcessIdentity();

public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

public static String getCurrentThreadIdentity();

/**
 * Get the currently applicable app policy. Same as MAMComponents.get(AppPolicy.class). This method does
    not take the context identity into account.
 */
public static AppPolicy getPolicy();

/**
 * Get the currently applicable app policy, taking the context
 * identity into account.
 */
public static AppPolicy getPolicy(final Context context);


public static AppPolicy getPolicyForIdentity(final String identity);

public static boolean getIsIdentityManaged(final String identity);

```
Vous pouvez également effacer l’identité de l’application en lui affectant la valeur null. La chaîne vide peut être utilisée comme une identité qui n’aura jamais de restrictions. Toutes les méthodes permettant de définir l’identité transmettent les valeurs obtenues par le biais de ``` MAMIdentitySwitchResult```. Quatre valeurs peuvent être retournées :

* **SUCCEEDED** : le changement d’identité a réussi.

* **NOT_ALLOWED** : le changement d’identité n’est pas autorisé. Cela se produit en cas de tentative de changement en faveur d’un autre utilisateur d’entreprise qui appartient à la même société que l’utilisateur inscrit. Cela se produit également si l’identité de l’interface utilisateur (`Context`) fait l’objet d’une tentative de définition alors qu’une identité différente est définie sur le thread actuel.

* **CANCELLED** : l’utilisateur a annulé le changement d’identité, généralement en choisissant le bouton Précédent dans une invite de code confidentiel ou d’authentification.

* **FAILED** : le changement d’identité a échoué pour une raison non précisée.

Dans le cas de la définition d’une identité `Context`, le résultat est signalé de manière asynchrone. Si `Context` est une classe `Activity`, le résultat (réussite ou échec) du changement d’identité n’ait connu qu’après le lancement conditionnel. Un lancement conditionnel peut exiger que l’utilisateur entre un code confidentiel ou ses informations d’identification d’entreprise complètes. L’application est censée implémenter ```MAMSetUIIdentityCallback``` pour recevoir ce résultat, même s’il est autorisé de passer null pour ce paramètre.

```
public interface MAMSetUIIdentityCallback {
    void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
}
```

Vous pouvez également définir l’identité d’une activité directement par le biais d’une méthode sur `MAMActivity`, au lieu d’appeler ```MAMPolicyManager.setUIPolicyIdentity```. Pour cela, vous pouvez utiliser la méthode suivante :

 ```public final void switchMAMIdentity(final String newIdentity);```

Les applications peuvent également substituer une méthode sur `MAMActivity` pour être informées du résultat des tentatives de changement de l’identité de l’activité.

```public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);```

> [!NOTE]
> Le changement d’identité peut nécessiter la recréation de l’activité. Dans ce cas, le rappel ```onSwitchMAMIdentityComplete``` est remis à la nouvelle instance de l’activité.


####<a name="implicit-identity-changes"></a>Changements d’identité implicites

Outre la possibilité pour l’application de définir l’identité, l’identité d’un contexte ou d’un thread peut changer en fonction de l’entrée de données à partir d’une autre application prenant en charge la gestion des applications mobiles. Par exemple, si une activité est lancée à partir d’une classe `Intent` envoyée par une autre application GAM, l’identité de l’activité est définie en fonction de l’identité effective dans l’autre application au point où la classe `Intent` a été envoyée.

Pour les services, l’identité du thread est définie de la même façon pendant la durée d’un appel `onStart` ou `onBind`. Les appels dans `Binder` retournés par `onBind` définissent également l’identité du thread temporairement. Les appels dans un ```ContentProvider``` définissent de la même façon l’identité du thread pendant leur durée.

En outre, l’interaction utilisateur avec une activité peut entraîner un changement d’identité implicite. Par exemple, si l’utilisateur annule une invite d’autorisation pendant ```Resume```, un changement implicite en faveur d’une identité vide a lieu.
L’application peut être informée de ces modifications et, dans certains cas, les interdire si nécessaire. ```MAMService``` et ```MAMContentProvider``` exposent la méthode suivante, que les sous-classes peuvent substituer :

```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
```
Dans le cas de ```MAMActivity```, un paramètre supplémentaire est présent dans la méthode :
```
public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
```
La partie ```AppIdentitySwitchReason``` capture la source du changement implicite. Elle peut accepter les valeurs ```CREATE```, ```RESUME_CANCELLED``` et ```NEW_INTENT```.  La raison ```RESUME_CANCELLED``` est utilisée quand la reprise d’une activité entraîne l’affichage de l’interface utilisateur de saisie de code confidentiel, d’authentification ou d’autres données de conformité et que l’utilisateur tente d’annuler cette interface utilisateur, généralement en utilisant le bouton précédent.
```AppIdentitySwitchResultCallback``` se présente comme suit :
```
public interface AppIdentitySwitchResultCallback {
    /**
     * @param result
     *            whether the identity switch can proceed.
     */
    void reportIdentitySwitchResult(AppIdentitySwitchResult result);
}
```
```AppIdentitySwitchResult``` est ```SUCCESS``` ou ```FAILURE```.

La méthode ```onMAMIdentitySwitchRequired``` est appelée pour toutes les modifications d’identité implicites, à l’exception de celles effectuées par le biais d’une classe `Binder` retournée à partir de ```MAMService.onMAMBind```. L’implémentation par défaut d’```onMAMIdentitySwitchRequired``` appelle immédiatement ```reportIdentitySwitchResult(FAILURE)``` quand la raison est ```RESUME_CANCELLED```, et ```reportIdentitySwitchResult(SUCCESS)``` dans tous les autres cas.

La plupart des applications n’auront probablement pas besoin de bloquer ou de différer un changement d’identité d’une manière différente. Mais si une application a besoin de le faire, considérez les points suivants :

* Si un changement d’identité est bloqué, le résultat est le même que si les paramètres de partage ```Receive``` avaient interdit la saisie de données.

* Si un service est en cours d’exécution sur le thread principal, ```reportIdentitySwitchResult``` *doit* être appelé de façon synchrone, sinon le thread d’interface utilisateur se bloque.

* Pour la création de l’```Activity```, ```onMAMIdentitySwitchRequired``` est appelé avant ```onMAMCreate```. Si l’application doit afficher l’interface utilisateur pour vérifier s’il faut autoriser le changement d’identité, cette interface utilisateur doit être affichée à l’aide d’une autre activité.

* Dans ```Activity```, quand un changement en faveur de l’identité vide est demandé et que la raison est égale à ```RESUME_CANCELLED```, l’application doit modifier l’activité reprise pour afficher des données cohérentes avec ce changement d’identité. Si ce n’est pas possible, l’application doit refuser le changement et l’utilisateur est invité à se reconformer à la stratégie associée à l’identité en cours de reprise (stratégie qui, par exemple, peut prévoir la présentation de l’écran de saisie du code confidentiel).

> [!NOTE]
> Une application qui prend en charge plusieurs identités reçoit toujours les données entrantes à partir d’applications gérées et non gérées. L’application est responsable du traitement des données issues des identités gérées de manière gérée. Si une identité demandée est gérée ```(MAMPolicyManager.getIsIdentityManaged)```, mais que l’application ne peut pas utiliser ce compte (par exemple, du fait que les comptes, tels que les comptes e-mail, doivent d’abord être configurés dans l’application), le changement d’identité doit être refusé.

###<a name="file-protection"></a>Protection des fichiers

Chaque fichier se voit associer une identité au moment de la création, en fonction de l’identité de thread et de processus. Cette identité est utilisée pour le chiffrement de fichier et la réinitialisation sélective. Seuls les fichiers dont l’identité a une stratégie qui nécessite le chiffrement sont chiffrés. La réinitialisation sélective par défaut du SDK réinitialise uniquement les fichiers associés à l’identité pour laquelle une réinitialisation a été demandée. L’application peut interroger ou modifier l’identité d’un fichier à l’aide de ```MAMFileProtectionManager```.
```
public final class MAMFileProtectionManager {

    /**
     * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
     * future protection changes.
     *
     * @param identity
     *            Identity to set.
     * @param file
     *            File to protect.
     * @throws IOException
     *             If the file cannot be changed.
     */
    public static void protect(final File file, final String identity) throws IOException;

    /**
     * Get the protection info on a file.
     *
     * @param file
     *            File or directory to get information on.
     * @return File protection info, or null if there is no protection info.
     * @throws IOException
     *             If the file cannot be read or opened.
     */
    public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;
}

public interface MAMFileProtectionInfo {
String getIdentity();
}
```

> [!NOTE]
> Le balisage de l’identité d’un fichier est sensible au mode hors connexion. Prenez les points suivants en considération :
> * Si l’application Portail d’entreprise n’est pas installée, les fichiers ne peuvent pas faire l’objet d’un balisage d’identité.
>
> * Si l’application Portail d’entreprise est installée, mais que l’application n’a pas de stratégie, les fichiers ne peuvent pas faire l’objet d’un balisage d’identité de façon fiable.
>
> * Quand le balisage d’identité des fichiers devient disponible, tous les fichiers déjà créés sont traités comme personnels (appartenant à l’identité à chaîne vide), sauf si l’application a été installée en tant qu’application gérée à identité unique. Dans ce cas, ils sont considérés comme appartenant à l’utilisateur inscrit.

####<a name="data-protection"></a>Protection des données

Il est impossible de baliser un fichier comme appartenant à plusieurs identités. Les applications qui doivent stocker des données appartenant à différents utilisateurs dans le même fichier peuvent le faire manuellement à l’aide des fonctionnalités fournies par ```MAMDataProtectionManager```. Ainsi, l’application peut chiffrer les données et les lier à un utilisateur particulier. Les données chiffrées peuvent ensuite être stockées sur disque dans un fichier. Vous pouvez interroger les données associées à l’identité, et les données peuvent être déchiffrées ultérieurement.

```
public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
 * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
 *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
 *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
 *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
 *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
 * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
 *            stream must have been returned by a previous call to
      *            protect OR input.markSupported() must return true.
 *            Otherwise it will be impossible to get protection info
 *            without advancing the stream position. The stream must be
 *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
 *            returned by a previous call to protect() or a copy of
 *            such bytes.
     * @return Data protection info, or null if there is no protection
 *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}
```
###<a name="content-providers"></a>Fournisseurs de contenu

Si l’application fournit des données éventuellement liées à l’entreprise autres que ```ParcelFileDescriptor``` par le biais de ```ContentProvider```, elle doit appeler la méthode ```MAMContentProvider``` ```isProvideContentAllowed(String)``` en passant l’```UPN``` propriétaire pour le contenu. Si cette fonction retourne la valeur false, le contenu ne peut pas être retourné à l’appelant. Les descripteurs de fichier retournés par le biais d’un fournisseur de contenu sont gérés automatiquement, en fonction de l’identité des fichiers.

###<a name="selective-wipe"></a>Réinitialisation sélective

Si une application s’inscrit à la notification ```WIPE_USER_DATA```, elle ne bénéficie plus du comportement de réinitialisation sélective par défaut du SDK. Pour les applications prenant en charge plusieurs identités, cela peut être d’autant plus important, car la réinitialisation sélective GAM par défaut réinitialise uniquement les fichiers correspondant à l’identité à réinitialiser.

Si vous générez une application prenant en charge plusieurs identités, vous pouvez vous inscrire à ```WIPE_USER_AUXILIARY_DATA```. Cette notification vous permet de tirer parti du comportement de réinitialisation par défaut du SDK. Cette notification est envoyée juste avant que vous n’effectuiez la réinitialisation sélective par défaut du SDK. Notez qu’une application ne doit jamais s’inscrire à la fois à ```WIPE_USER_DATA``` et à ```WIPE_USER_AUXILIARY_DATA```.

### <a name="known-platform-limitations"></a>Limitations de plateforme connues

#### <a name="file-size-limitations"></a>Limitations concernant la taille des fichiers

Sur Android, les limitations du format de fichier exécutable Dalvik peuvent devenir un problème pour les grandes bases de code qui s’exécutent sans ProGuard. Plus précisément, les limitations suivantes peuvent se produire :

* Limite de 65 000 sur les champs

* Limite de 65 000 sur les méthodes

Quand vous incluez plusieurs projets, chaque `android:package` reçoit une copie de R. Cela augmente considérablement le nombre de champs au fur et à mesure que des bibliothèques sont ajoutées. Les recommandations suivantes peuvent vous aider à atténuer cette limitation :

* Tous les projets de bibliothèque doivent partager le même `android:package` dans la mesure du possible. Cela ne se traduit pas par un échec sporadique dans le champ, car il s’agit simplement d’un problème au moment de la génération. De plus, les versions plus récentes du SDK Android effectuent un prétraitement des fichiers DEX pour ôter une partie de la redondance. Cela permet de réduire davantage la distance entre les champs.

* Utilisez les outils de génération du SDK Android les plus récents.

* Supprimez toutes les bibliothèques inutiles et inutilisées (par exemple, `android.support.v4`).

#### <a name="policy-enforcement-limitations"></a>Limitations concernant l’application de la stratégie

**Capture d’écran** : le SDK ne peut pas appliquer une nouvelle valeur de capture d’écran dans les classes `Activity` qui sont déjà passées par `Activity.onCreate`. Il peut en résulter une période au cours de laquelle l’application est configurée pour désactiver les captures d’écran ; toutefois, il est toujours possible d’en prendre.

**Programmes de résolution de contenu** : la stratégie de transfert ou de réception peut bloquer entièrement ou en partie l’utilisation d’un programme de résolution de contenu pour accéder au fournisseur de contenu dans une autre application. En conséquence, les méthodes `ContentResolver` retourneront null ou lèveront une valeur d’échec. (Par exemple, `openOutputStream` lèvera `FileNotFoundException` en cas de blocage.) L’application peut effectuer cet appel pour vérifier si une stratégie a provoqué (ou est susceptible de provoquer) un échec d’écriture des données par le biais d’un programme de résolution de contenu :

    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI)

**Services exportés** : le fichier `AndroidManifest.xml` inclus dans le SDK d’application Intune a `MAMNotificationReceiverService`. Il doit s’agir d’un service exporté pour permettre à l’application Portail d’entreprise d’envoyer des notifications à une application compatible. Le service vérifie l’appelant pour s’assurer que seule l’application Portail d’entreprise est autorisée à envoyer des notifications.

### <a name="android-best-practices"></a>Bonnes pratiques pour Android

Le SDK Intune respecte le contrat fourni par l’API Android, bien que des conditions d’échec puissent être déclenchées plus fréquemment à la suite de l’application de stratégies. Ces meilleures pratiques pour Android réduisent la probabilité d’un échec :

* Il est fort probable que les fonctions du SDK Android susceptibles de retourner null soient déjà null. Pour réduire les problèmes, assurez-vous que les vérifications null sont placées au bon endroit.

* Pour les fonctionnalités que vous pouvez vérifier, utilisez leurs API du SDK pour la vérification.

* Les appels des fonctions dérivées doivent être acheminés aux versions de leurs superclasses.

* Évitez d’utiliser les API de façon ambiguë. Par exemple, l’utilisation d’`Activity.startActivityForResult/onActivityResult` sans vérifier `requestCode` entraîne un comportement étrange.

