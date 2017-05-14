---
title: "Guide du SDK des applications Microsoft Intune pour les développeurs iOS │ Microsoft Docs"
description: "Le SDK des applications Microsoft Intune pour iOS vous permet d’incorporer les stratégies de protection des applications Intune (sous forme de gestion des applications mobiles) à votre application iOS."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df54ac3a62b5ef21e8a32f3a282dd5299974a1b0
ms.openlocfilehash: 1d2cb0d4b9442262c562e559a675f5a4a28ee572
ms.contentlocale: fr-fr
ms.lasthandoff: 05/03/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Guide du SDK des applications Microsoft Intune pour les développeurs iOS

> [!NOTE]
> Vous pouvez d’abord consulter l’article [Bien démarrer avec le SDK des applications Microsoft Intune](intune-app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.

Le SDK des applications Microsoft Intune pour iOS vous permet d’incorporer les stratégies de protection des applications Intune (appelées aussi stratégies **APP** ou **MAM**) à votre application iOS native. Une application MAM est une application intégrée au SDK des applications Intune. Les administrateurs informatiques peuvent déployer des stratégies de protection des applications sur votre application mobile quand Intune gère activement l’application.

## <a name="prerequisites"></a>Prérequis

* Vous avez besoin d’un ordinateur Mac OS qui exécute OS X 10.8.5 ou ultérieur et sur lequel Xcode 8 ou ultérieur est installé.

* Votre application doit être ciblée pour iOS 9 ou ultérieur.

* Passez en revue les [Termes du contrat de licence du SDK des applications Intune pour iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant le SDK des applications Intune pour iOS, vous acceptez les termes du contrat de licence.  Si vous ne les acceptez pas, n’utilisez pas le logiciel.

* Téléchargez les fichiers du SDK des applications Intune pour iOS sur [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Contenu du SDK

Le SDK des applications Intune pour iOS inclut une bibliothèque statique, des fichiers de ressources, des en-têtes d’API, un fichier .plist de paramètres de débogage et un outil de configuration. Les applications mobiles peuvent simplement inclure les fichiers de ressources et être liées aux bibliothèques de manière statique pour l’application de la plupart des stratégies. Les fonctionnalités de gestion des applications mobiles Intune avancées sont appliquées par le biais d’API.

Ce guide traite de l’utilisation des composants suivants du SDK des applications Intune pour iOS :

* **libIntuneMAM.a** : Bibliothèque statique du SDK des applications Intune. Si votre application n’utilise pas d’extension, liez cette bibliothèque à votre projet pour inclure votre application dans la gestion des applications mobiles Intune.

* **IntuneMAM.framework** : Framework du SDK des applications Intune. Liez ce framework à votre projet pour inclure votre application dans la gestion des applications mobiles Intune. Utilisez le framework à la place de la bibliothèque statique si votre application utilise des extensions et pour empêcher votre projet de créer plusieurs copies de la bibliothèque statique.

* **IntuneMAMResources.Bundle** : Bundle de ressources qui contient les ressources sur lesquelles repose le SDK.

* **En-têtes** : Expose les API du SDK des applications Intune. Si vous utilisez une API, vous devez inclure le fichier d’en-tête contenant l’API. Les fichiers d’en-tête suivants incluent les appels de fonction API nécessaires pour activer la fonctionnalité du SDK des applications Intune :

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Fonctionnement du SDK de l’application Intune

L’objectif du SDK des applications Intune pour iOS consiste à ajouter des fonctionnalités de gestion aux applications iOS par le biais de modifications minimales du code. Moins il y a de modifications de code, plus le délai de commercialisation est rapide, sans impact sur la cohérence et la stabilité de votre application mobile.


## <a name="build-the-sdk-into-your-mobile-app"></a>Intégrer le SDK à votre application mobile

Pour activer le SDK des applications Intune, effectuez les étapes suivantes :

1. **Option 1 (recommandée)** : Liez `IntuneMAM.framework` à votre projet. Faites glisser `IntuneMAM.framework` vers la liste **Frameworks et bibliothèques liés** de la cible du projet.

    > [!NOTE]
    > Si vous utilisez le framework, vous devez manuellement supprimer les architectures de simulateur du framework universel avant d’envoyer votre application à l’App Store. Pour plus de détails, consultez [Envoyer votre application à l’App Store](#Submit-your-app-to-the-App-Store).

2. **Option 2** : Liez la bibliothèque `libIntuneMAM.a`. Faites glisser `libIntuneMAM.a` dans la liste **Frameworks et bibliothèques liés** de la cible du projet.

    ![SDK des applications Intune pour iOS : Frameworks et bibliothèques liés](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Si vous envisagez de publier votre application dans l’App Store, utilisez la version de `libIntuneMAM.a` générée pour la publication et non la version de débogage. La version Release se trouve dans le dossier **release**. La version de débogage a une sortie détaillée qui vous permet de résoudre les problèmes avec le SDK des applications Intune.

    Ajoutez `-force_load {PATH_TO_LIB}/libIntuneMAM.a` à l’un des éléments suivants, en remplaçant `{PATH_TO_LIB}` par l’emplacement du SDK des applications Intune :
      * Le paramètre de configuration de build `OTHER_LDFLAGS` du projet
      * Les **autres indicateurs de l’éditeur de liens** de l’interface utilisateur

        > [!NOTE]
        > Pour rechercher `PATH_TO_LIB`, sélectionnez le fichier `libIntuneMAM.a` et choisissez **Obtenir des informations** dans le menu **Fichier**. Copiez et collez les informations correspondant au champ **Where** (le chemin) à partir de la section **General** de la fenêtre **Info**.

3. Ajoutez ces frameworks iOS au projet :
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework


4. Ajoutez le bundle de ressources `IntuneMAMResources.bundle` au projet en le faisant glisser sous **Copy Bundle Resources** (Copier les ressources du bundle) dans **Build Phases** (Phases de génération).

    ![SDK des applications Intune pour iOS : Copier les ressources du bundle](../media/intune-app-sdk-ios-copy-bundle-resources.png)

5. Si votre application mobile définit un fichier nib ou storyboard principal dans son fichier Info.plist, coupez les champs **Main Storyboard** ou **Main Nib**. Dans Info.plist, collez ces champs et leur valeur correspondante sous un nouveau dictionnaire nommé **IntuneMAMSettings** avec les noms de clé suivants, selon le cas :
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Si votre application mobile ne définit pas de fichier nib ou storyboard principal dans son fichier Info.plist, ces paramètres ne sont pas nécessaires.

    Vous pouvez consulter Info.plist en format brut (pour voir les noms de clé) en cliquant avec le bouton droit n’importe où dans le corps du document et en choisissant le type de vue **Show Raw Keys/Values** (Afficher les clés/valeurs brutes).

6. Activez le partage de trousseau (s’il ne l’est pas déjà) en choisissant **Capabilities** (Fonctionnalités) dans chaque cible du projet et en activant le commutateur **Keychain Sharing** (Partage de trousseau). Le partage de trousseau est nécessaire pour passer à l’étape suivante.

  > [!NOTE]
    > Votre profil de configuration doit prendre en charge les nouvelles valeurs de partage de trousseau. Les groupes de trousseau d’accès doivent prendre en charge un caractère générique. Vous pouvez le vérifier en effectuant les étapes suivantes : ouvrez le fichier .mobileprovision dans un éditeur de texte, recherchez **keychain-access-groups** et vérifiez que vous avez un caractère générique. Exemple :
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Une fois que vous avez activé le partage de trousseau, effectuez les étapes suivantes pour créer un groupe d’accès distinct dans lequel le SDK des applications Intune stocke ses données. Vous pouvez créer un groupe d’accès au trousseau à l’aide de l’interface utilisateur ou du fichier des droits. Si vous utilisez l’interface utilisateur pour créer le groupe d’accès au trousseau, suivez les étapes ci-dessous :

    1. Si vous n’avez pas défini de groupe d’accès au trousseau pour votre application mobile, ajoutez l’ID de bundle de l’application comme premier groupe.

    2. Ajoutez le groupe du trousseau partagé `com.microsoft.intune.mam` à vos groupes d’accès existants. Le SDK des applications Intune utilise ce groupe d’accès pour stocker des données.

    3. Ajoutez `com.microsoft.adalcache` à vos groupes d’accès existants.

        4. Ajoutez `com.microsoft.workplacejoin` à vos groupes d’accès existants.
            ![SDK des applications Intune pour iOS : Partage de trousseau](../media/intune-app-sdk-ios-keychain-sharing.png)

      5. Si vous utilisez le fichier des droits pour créer le groupe d’accès au trousseau, ajoutez le suffixe `$(AppIdentifierPrefix)` au groupe d’accès au trousseau dans le fichier des droits. Exemple :

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Un fichier de droits est un fichier XML unique pour votre application mobile. Il est utilisé pour spécifier des autorisations et des fonctionnalités spéciales dans votre application iOS.

7. Si l’application définit des schémas d’URL dans son fichier Info.plist, ajoutez un autre schéma avec le suffixe `-intunemam` pour chaque schéma d’URL.

8. Pour les applications mobiles développées sur iOS 9+, incluez chaque protocole que votre application passe à `UIApplication canOpenURL` dans le tableau `LSApplicationQueriesSchemes` du fichier Info.plist de votre application. Par ailleurs, pour chaque protocole répertorié, ajoutez un nouveau protocole avec `-intunemam`. Vous devez également inclure `http-intunemam`, `https-intunemam` et `ms-outlook-intunemam` dans le tableau.

9. Si l’application a des groupes d’applications définis dans ses droits, ajoutez-les au dictionnaire **IntuneMAMSettings** sous la clé `AppGroupIdentifiers` sous la forme d’un tableau de chaînes.



## <a name="configure-azure-active-directory-authentication-library-adal"></a>Configurer Azure Active Directory Authentication Library (ADAL)

Le SDK des applications Intune utilise [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) pour son authentification et les scénarios de lancement conditionnel. Il s’appuie également sur la bibliothèque ADAL pour inscrire l’identité de l’utilisateur au service MAM pour une gestion sans inscription d’appareil.

En règle générale, la bibliothèque ADAL nécessite que les applications s’inscrivent dans Azure Active Directory (AAD) et obtiennent un ID unique (ClientID) et d’autres identificateurs, pour garantir la sécurité des jetons accordés à l’application. Sauf indication contraire, le SDK des applications Intune utilise les valeurs d’inscription par défaut quand il contacte Azure AD.  

Si votre application utilise déjà la bibliothèque ADAL pour authentifier les utilisateurs, l’application doit utiliser ses valeurs d’inscription existantes et remplacer les valeurs par défaut du SDK des applications Intune. Cela empêche les utilisateurs d’avoir à s’authentifier deux fois (une fois pour le SDK des applications Intune et une fois pour l’application).

### <a name="recommendations"></a>Recommandations

Votre application doit être, de préférence, liée à la [dernière version de la bibliothèque ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) sur sa branche maître. Le SDK des applications Intune utilise actuellement la branche broker de la bibliothèque ADAL pour prendre en charge les applications qui nécessitent un accès conditionnel. (Ces applications dépendent par conséquent de l’application Microsoft Authenticator.) Toutefois, le SDK est toujours compatible avec la branche maître de la bibliothèque ADAL. Utilisez la branche qui convient à votre application.

### <a name="link-to-adal-binaries"></a>Créer une liaison aux fichiers binaires ADAL

Suivez les étapes ci-dessous pour lier votre application aux fichiers binaires ADAL :

1. Téléchargez [Azure Active Directory Authentication Library (ADAL) pour Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) à partir de GitHub, puis suivez les [instructions](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) de téléchargement de la bibliothèque ADAL à l’aide de sous-modules Git ou de CocoaPods.

2. Ajoutez le bundle de ressources `ADALiOSBundle.bundle` au projet en le faisant glisser sous **Copy Bundle Resources** (Copier les ressources du bundle) dans **Build Phases** (Phases de génération).

3. Ajoutez `-force_load {PATH_TO_LIB}/libADALiOS.a` au paramètre de configuration de build `OTHER_LDFLAGS` du projet ou sous **Autres indicateurs de l’éditeur de liens** dans l’interface utilisateur. `PATH_TO_LIB` doit être remplacé par l’emplacement des fichiers binaires ADAL.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Partager le cache de jetons ADAL avec d’autres applications signées avec le même profil de configuration ?**

Suivez les instructions ci-dessous si vous voulez partager des jetons ADAL entre applications signées avec le même profil de configuration :

1. Si vous n’avez pas défini de groupe d’accès au trousseau pour votre application, ajoutez l’ID de bundle de l’application comme premier groupe.

2. Activez l’authentification unique ADAL en ajoutant les groupes d’accès `com.microsoft.adalcache` et `com.microsoft.workplacejoin` dans les droits du trousseau.

3. Si vous définissez explicitement le groupe d’accès au trousseau du cache partagé ADAL, vérifiez qu’il est défini sur `<app_id_prefix>.com.microsoft.adalcache`. La bibliothèque ADAL définit ce paramètre pour vous, sauf si vous le remplacez. Si vous voulez spécifier un groupe d’accès au trousseau personnalisé pour remplacer `com.microsoft.adalcache`, spécifiez-le dans le fichier Info.plist sous IntuneMAMSettings, à l’aide de la clé `ADALCacheKeychainGroupOverride`.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Configurer les paramètres ADAL pour le SDK des applications Intune

Si votre application utilise déjà la bibliothèque ADAL pour l’authentification et qu’elle a ses propres paramètres ADAL, vous pouvez forcer le SDK des applications Intune à utiliser les mêmes paramètres pendant l’authentification auprès d’Azure Active Directory. De cette façon, l’application ne demande pas deux fois à l’utilisateur de s’authentifier. Consultez [Configurer les paramètres du SDK des applications Intune](#configure-settings-for-the-intune-app-sdk) pour plus d’informations sur le remplissage des paramètres suivants :  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Si votre application utilise déjà la bibliothèque ADAL, les configurations suivantes sont nécessaires :

1. Dans le fichier Info.plist du projet, sous le dictionnaire **IntuneMAMSettings** avec le nom de clé `ADALClientId`, spécifiez l’ID de client à utiliser pour les appels ADAL.

2. Également sous le dictionnaire **IntuneMAMSettings** avec le nom de clé `ADALAuthority`, indiquez l’autorité Azure AD.

3. Toujours sous le dictionnaire **IntuneMAMSettings** avec le nom de clé `ADALRedirectUri`, indiquez l’URI de redirection à utiliser pour les appels ADAL. Vous pouvez également spécifier `ADALRedirectScheme` selon le format de l’URI de redirection de votre application.


Par ailleurs, vous pouvez remplacer l’URL de l’autorité Azure AD par une URL spécifique du locataire au moment de l’exécution. Pour ce faire, définissez simplement la propriété `aadAuthorityUriOverride` sur l’instance `IntuneMAMPolicyManager`.

> [!NOTE]
> La définition de l’URL de l’autorité AAD est nécessaire pour que le service [APP sans inscription d’appareil](#App-protection-policy-without-device-enrollment) permette au SDK de réutiliser le jeton d’actualisation ADAL récupéré par l’application.

Le SDK continue d’utiliser l’URL de cette autorité pour l’actualisation des stratégies et toutes les demandes d’inscription ultérieures, sauf si la valeur est effacée ou changée.  Par conséquent, la valeur doit être effacée quand un utilisateur géré se déconnecte de l’application et réinitialisée quand un nouvel utilisateur géré se connecte.

### <a name="if-your-app-does-not-use-adal"></a>Si votre application n’utilise pas la bibliothèque ADAL

Si votre application n’utilise pas la bibliothèque ADAL, le SDK des applications Intune fournit des valeurs par défaut pour les paramètres ADAL et gère l’authentification auprès d’Azure AD. Vous n’avez pas besoin de spécifier de valeurs pour les paramètres ADAL répertoriés ci-dessus.

## <a name="app-protection-policy-without-device-enrollment"></a>Stratégie de protection des applications sans inscription d’appareil

### <a name="overview"></a>Vue d'ensemble
La stratégie de protection des applications Intune sans inscription d’appareil, également appelée **APP-WE** ou MAM-WE, permet aux applications d’être gérées par Intune sans que l’appareil soit inscrit à la gestion des appareils mobiles Intune (MDM). Pour prendre en charge cette nouvelle fonctionnalité, l’application doit inscrire les comptes d’utilisateur pour la gestion. Pour utiliser les nouvelles API, effectuez les étapes suivantes :

1. Utilisez la dernière version du SDK des applications Intune, qui prend en charge la gestion des applications avec ou sans inscription d’appareil.

2. Ajoutez IntuneMAMEnrollment.h à tout fichier qui appelle les API.

### <a name="register-user-accounts"></a>Inscrire des comptes d’utilisateurs

Une application peut recevoir une stratégie de protection des applications du service Intune si elle est inscrite au service APP-WE avec un compte d’utilisateur spécifié. L’application est chargée d’inscrire tous les nouveaux utilisateurs qui se connectent avec le SDK. Une fois que le nouveau compte d’utilisateur est authentifié, l’application doit appeler la méthode `registerAndEnrollAccount` dans Headers/IntuneMAMEnrollment.h :

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
En appelant la méthode `registerAndEnrollAccount`, le SDK inscrit le compte d’utilisateur et tente d’inscrire l’application pour ce compte. En cas d’échec de l’inscription pour une raison quelconque, le SDK retente automatiquement l’inscription 24 heures plus tard. Pour le débogage, l’application peut recevoir des notifications, via un délégué, concernant les résultats de toutes les demandes d’inscription.

Une fois que cette API a été appelée, l’application peut continuer à fonctionner normalement. Si l’inscription est effectuée, le SDK informe l’utilisateur qu’un redémarrage de l’application est nécessaire. À ce stade, l’utilisateur peut redémarrer immédiatement l’application.

### <a name="deregister-user-accounts"></a>Désinscrire des comptes d’utilisateurs

Avant qu’un utilisateur se déconnecte d’une application, celle-ci doit désinscrire l’utilisateur dans le SDK. De cette façon :

1. Le compte de l’utilisateur ne peut plus s’inscrire.

2. La stratégie de protection des applications est supprimée.

3. Si l’application lance une réinitialisation sélective (facultative), toutes les données d’entreprise sont supprimées.

Avant que l’utilisateur soit déconnecté, l’application doit appeler l’API suivante dans `Headers/IntuneMAMEnrollment.h` :

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Cette méthode doit être appelée avant la suppression des jetons Azure AD du compte d’utilisateur. Le SDK utilise les jetons AAD du compte d’utilisateur pour effectuer des demandes spécifiques au service APP-WE pour l’utilisateur.

Si l’application supprime elle-même les données d’entreprise de l’utilisateur, l’indicateur `doWipe` peut être défini sur false. Sinon, l’application peut demander au SDK de lancer une réinitialisation sélective. Cela se traduit par un appel au délégué de réinitialisation sélective de l’application.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a>Applications qui n’utilisent pas la bibliothèque ADAL

Les applications qui ne connectent pas l’utilisateur à l’aide de la bibliothèque ADAL peuvent toujours recevoir une stratégie de protection des applications du service Intune en appelant l’API qui permet au SDK de gérer l’authentification. Les applications doivent utiliser cette technique quand elles n’ont pas authentifié un utilisateur avec Azure AD, mais doivent quand même récupérer une stratégie de protection des applications pour renforcer la protection des données. C’est le cas, par exemple, quand un autre service d’authentification est utilisé pour se connecter à l’application ou quand l’application ne prend pas en charge la connexion. Pour ce faire, l’application doit appeler la méthode `loginAndEnrollAccount` Headers/IntuneMAMEnrollment.h :

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Avec cette méthode, le SDK demande à l’utilisateur des informations d’identification quand il n’existe aucun jeton. Le SDK tente ensuite d’inscrire l’application au service APP-WE pour le compte d’utilisateur fourni. La méthode peut être appelée avec l’identité « nil ». Dans ce cas, le SDK effectue l’inscription avec l’utilisateur géré existant sur l’appareil ou demande à l’utilisateur un nom d’utilisateur s’il n’existe aucun utilisateur.

En cas d’échec de l’inscription, l’application doit rappeler cette API plus tard, en fonction des détails de l’échec de l’appel. L’application peut recevoir des [notifications](#Status-result-and-debug-notifications), via un délégué, concernant les résultats de toutes les demandes d’inscription.

Une fois que cette API a été appelée, l’application peut continuer à fonctionner normalement. Si l’inscription est effectuée, le SDK informe l’utilisateur qu’un redémarrage de l’application est nécessaire.

## <a name="status-result-and-debug-notifications"></a>Notifications d’état, de résultat et de débogage

L’application peut recevoir des notifications d’état, de résultat et de débogage concernant les demandes au service MAM Intune suivantes :

 - Demandes d’inscription
 - Demandes de mise à jour de stratégie
 - Demandes de désinscription

Les notifications sont présentées via des méthodes déléguées dans `Headers/IntuneMAMEnrollmentDelegate.h` :

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

Ces méthodes déléguées retournent un objet `IntuneMAMEnrollmentStatus` avec les informations suivantes :

- L’identité du compte associé à la demande
- Un code d’état qui indique le résultat de la demande
- Une chaîne d’erreur avec une description du code d’état
- Un objet `NSError`

Cet objet est défini dans `IntuneMAMEnrollmentStatus.h`, ainsi que les codes d’état spécifiques qui peuvent être retournés.


### <a name="sample-code"></a>Exemple de code

Voici des exemples d’implémentation de méthodes déléguées :

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>Redémarrage de l’application

Quand une application reçoit des stratégies de protection des applications pour la première fois, elle doit redémarrer pour appliquer les crochets nécessaires. Pour notifier l’application qu’un redémarrage doit se produire, le SDK fournit une méthode déléguée dans Headers/IntuneMAMPolicyDelegate.h.

```objc
 - (BOOL) restartApplication
```
La valeur de retour de cette méthode indique au SDK si l’application doit gérer le redémarrage nécessaire :   

 - Si la valeur true est retournée, l’application doit gérer le redémarrage.   

 - Si la valeur false est retournée, le SDK redémarre l’application après le retour de la méthode. Le SDK affiche immédiatement une boîte de dialogue qui demande à l’utilisateur de redémarrer l’application.

## <a name="customize-your-apps-behavior"></a>Personnaliser le comportement de votre application

Le SDK des applications Intune contient plusieurs API que vous pouvez appeler pour obtenir des informations sur la stratégie de protection des applications Intune déployée sur l’application. Vous pouvez utiliser ces données pour personnaliser le comportement de votre application. La plupart des paramètres de stratégie de protection des applications sont appliqués automatiquement par le SDK et non par l’application. Le seul paramètre que l’application doit implémenter est le contrôle Save-as.

### <a name="get-app-protection-policy"></a>Obtenir la stratégie de protection des applications

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
La classe IntuneMAMPolicyManager expose la stratégie de protection des applications Intune déployée sur l’application. En particulier, elle expose les API qui sont utiles pour l’[activation de plusieurs identités](#-enable-multi-identity-optional).

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
La classe IntuneMAMPolicy expose la stratégie de protection des applications Intune déployée sur l’application. La plupart des paramètres de stratégie exposés dans cette classe sont appliqués par le SDK, mais vous pouvez toujours personnaliser le comportement de votre application selon le mode d’application des paramètres de stratégie.

Cette classe expose certaines API nécessaires à l’implémentation des contrôles Save-as, détaillée dans la section suivante.

### <a name="implement-save-as-controls"></a>Implémenter des contrôles Save-as

Intune permet aux administrateurs informatiques de sélectionner les emplacements de stockage dans lesquels une application gérée peut enregistrer des données. Les applications peuvent interroger le SDK des applications Intune pour connaître les emplacements de stockage autorisés à l’aide de l’API **isSaveToAllowedForLocation**, définie dans **IntuneMAMPolicy.h**.

Pour que les applications puissent enregistrer des données gérées dans un emplacement local ou un stockage cloud, elles doivent vérifier avec l’API **isSaveToAllowedForLocation** si l’administrateur informatique a permis l’enregistrement des données à cet endroit.

Quand les applications utilisent l’API **isSaveToAllowedForLocation**, elles doivent passer l’UPN de l’emplacement de stockage, s’il est disponible.

#### <a name="supported-save-locations"></a>Emplacements d’enregistrement pris en charge

L’API **isSaveToAllowedForLocation** fournit des constantes pour vérifier si l’administrateur informatique autorise l’enregistrement des données dans les emplacements suivants, définis dans IntuneMAMPolicy.h :

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Les applications doivent utiliser les constantes dans l’API **isSaveToAllowedForLocation** pour vérifier si les données peuvent être enregistrées dans les emplacements considérés comme étant « gérés » (par exemple, OneDrive Entreprise) ou « personnels ». Par ailleurs, l’API doit être utilisée quand l’application ne peut pas vérifier si un emplacement est « géré » ou « personnel ».

Les emplacements considérés comme étant « personnels » sont représentés par la constante `IntuneMAMSaveLocationOther`.

La constante `IntuneMAMSaveLocationLocalDrive` doit être utilisée quand l’application enregistre les données à un emplacement quelconque sur l’appareil local.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Configurer les paramètres du SDK des applications Intune

Vous pouvez utiliser le dictionnaire **IntuneMAMSettings** du fichier Info.plist de l’application pour configurer le SDK des applications Intune. Si le dictionnaire IntuneMAMSettings n’apparaît pas dans votre fichier Info.plist, vous devez créer un dictionnaire dans le fichier Info.plist de votre application avec le nom de champ « IntuneMAMSettings ».

Sous le dictionnaire IntuneMAMSettings, vous pouvez ajouter des lignes de clé/valeur pour les paramètres de configuration afin de configurer le SDK. Le tableau ci-dessous répertorie tous les paramètres pris en charge.

Certains de ces paramètres ont pu être traités dans les sections précédentes et d’autres ne s’appliquent pas à toutes les applications.

Paramètre  | Type  | Définition | Nécessaire ?
--       |  --   |   --       |  --
ADALClientId  | Chaîne  | Identificateur de client Azure AD de l’application. | Obligatoire si l’application utilise la bibliothèque ADAL. |
ADALAuthority | Chaîne | Autorité Azure AD de l’application en cours d’utilisation. Vous devez utiliser votre propre environnement dans lequel les comptes AAD ont été configurés. | Obligatoire si l’application utilise la bibliothèque ADAL. Si cette valeur est absente, une valeur par défaut Intune est utilisée.|
ADALRedirectUri  | Chaîne  | URI de redirection Azure AD de l’application. | ADALRedirectUri ou ADALRedirectScheme est nécessaire si l’application utilise la bibliothèque ADAL.  |
ADALRedirectScheme  | Chaîne  | Schéma de redirection Azure AD de l’application. Ce paramètre peut être utilisé à la place d’ADALRedirectUri si l’URI de redirection de l’application est au format `scheme://bundle_id`. | ADALRedirectUri ou ADALRedirectScheme est nécessaire si l’application utilise la bibliothèque ADAL. |
ADALLogOverrideDisabled | Booléen  | Indique si le SDK achemine tous les journaux de la bibliothèque ADAL (y compris les appels ADAL à partir de l’application, le cas échéant) dans son propre fichier journal. La valeur par défaut est NON. Définissez la valeur sur OUI si l’application doit définir le rappel de son propre journal ADAL. | Facultatif. |
ADALCacheKeychainGroupOverride | Chaîne  | Spécifie le groupe d’accès au trousseau à utiliser pour le cache ADAL, à la place de « com.microsoft.adalcache ». Notez que ce paramètre n’a pas le préfixe app-id. Ce préfixe est ajouté à la chaîne fournie au moment de l’exécution. | Facultatif. |
AppGroupIdentifiers | Tableau de chaînes  | Tableau de groupes d’applications issu de la section com.apple.security.application-groups des droits de l’application. | Obligatoire si l’application utilise des groupes d’applications. |
ContainingAppBundleId | Chaîne | Spécifie l’ID de bundle de l’application conteneur de l’extension. | Obligatoire pour les extensions iOS. |
DebugSettingsEnabled| Booléen | Si la valeur est OUI, les stratégies de test dans le bundle de paramètres peuvent être appliquées. Les applications ne doivent *pas* être publiées avec ce paramètre activé. | Facultatif. |
MainNibFile<br>MainNibFile~ipad  | Chaîne  | Ce paramètre doit contenir le nom du fichier nib principal de l’application.  | Obligatoire si l’application définit MainNibFile dans Info.plist. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Chaîne  | Ce paramètre doit contenir le nom du fichier storyboard principal de l’application. | Obligatoire si l’application définit UIMainStoryboardFile dans Info.plist. |
MAMPolicyRequired| Booléen| Spécifie si le démarrage de l’application est bloqué en cas d’absence de stratégie de protection des applications Intune. La valeur par défaut est NON. <br><br> Remarque : Les applications ne peuvent pas être envoyées à l’App Store si MAMPolicyRequired est défini sur OUI. | Facultatif. |
MAMPolicyWarnAbsent | Booléen| Spécifie si l’application avertit l’utilisateur au lancement de l’application en cas d’absence de stratégie de protection des applications Intune. Notez que les applications ne peuvent pas être envoyées à l’App Store si ce paramètre est défini sur OUI. | Facultatif. |
MultiIdentity | Booléen| Spécifie si l’application prend en charge plusieurs identités. | Facultatif. |
SplashIconFile <br>SplashIconFile~ipad | Chaîne  | Spécifie le fichier de l’icône de démarrage Intune. | Facultatif. |
SplashDuration | Nombre | Durée minimale, en secondes, de l’affichage de l’écran de démarrage Intune au lancement de l’application. La valeur par défaut est 1,5. | Facultatif. |
BackgroundColor| Chaîne| Spécifie la couleur d’arrière-plan des écrans de démarrage et de code PIN. Accepte une chaîne hexadécimale RVB au format #XXXXXX, où X peut être compris entre 0 et 9 ou A et F. Le signe dièse peut être omis.   | Facultatif. La valeur par défaut est gris clair. |
ForegroundColor| Chaîne| Spécifie la couleur de premier plan des écrans de démarrage et de code PIN, comme la couleur du texte. Accepte une chaîne hexadécimale RVB au format #XXXXXX, où X peut être compris entre 0 et 9 ou A et F. Le signe dièse peut être omis.  | Facultatif. La valeur par défaut est noir. |
AccentColor | Chaîne| Spécifie la couleur d’accentuation de l’écran de code PIN, comme la couleur de surbrillance de zone et la couleur de texte du bouton. Accepte une chaîne hexadécimale RVB au format #XXXXXX, où X peut être compris entre 0 et 9 ou A et F. Le signe dièse peut être omis.| Facultatif. La valeur par défaut est bleu système. |
MAMTelemetryDisabled| Booléen| Spécifie que le SDK n’envoie pas les données de télémétrie au serveur principal.| Facultatif. |

> [!NOTE]
> Si votre application est publiée dans l’App Store, `MAMPolicyRequired` doit être défini sur « NON », conformément aux normes de l’App Store.

## <a name="telemetry"></a>Télémétrie

Par défaut, le SDK des applications Intune pour iOS consigne les données de télémétrie pour les événements d’utilisation suivants. Ces données sont envoyées à Microsoft Intune.

* **Lancement d’applications** : Permet à Microsoft Intune d’en savoir plus sur l’utilisation des applications MAM par type de gestion (MAM avec gestion des appareils mobiles, MAM sans inscription à la gestion des appareils mobiles, etc.).

* **Appels d’inscription** : Permet à Microsoft Intune d’en savoir plus sur les taux de réussite et d’autres mesures de performances des appels d’inscription côté client.

> [!NOTE]
> Si vous choisissez de ne pas envoyer les données de télémétrie du SDK des applications Intune à Microsoft Intune à partir de votre application mobile, vous devez désactiver la capture de télémétrie du SDK des applications Intune. Définissez la propriété `MAMTelemetryDisabled` sur OUI dans le dictionnaire IntuneMAMSettings.

## <a name="enable-multi-identity-optional"></a>Activer plusieurs identités (facultatif)

Par défaut, le SDK applique une stratégie à l’ensemble de l’application. La possibilité d’activer plusieurs identités est une fonctionnalité MAM que vous pouvez utiliser pour appliquer une stratégie selon l’identité. Cette fonctionnalité implique davantage de participation de l’application que les autres fonctionnalités MAM.

L’application doit informer le SDK quand elle a l’intention de changer l’identité active. Le SDK indique également à l’application quand un changement d’identité est nécessaire. Actuellement, seule une identité gérée est prise en charge. Une fois que l’utilisateur a inscrit l’appareil ou l’application, le SDK utilise cette identité et la considère comme l’identité gérée principale. Les autres utilisateurs de l’application sont considérés comme étant non gérés avec des paramètres de stratégie non restreints.

Notez qu’une identité est définie simplement sous forme de chaîne. Les identités respectent la casse. Les demandes d’identité au SDK peuvent ne pas retourner la même casse que celle utilisée à l’origine quand l’identité à été définie.

### <a name="identity-overview"></a>Vue d’ensemble de l’identité

Une identité est simplement le nom d’utilisateur d’un compte (par exemple, user@contoso.com). Les développeurs peuvent définir l’identité de l’application sur les niveaux suivants :

* **Identité du processus** : Définit l’identité au niveau du processus. Principalement utilisée pour les applications avec identité unique. Cette identité affecte tous les fichiers, tâches et interface utilisateur.

* **Identité de l’interface utilisateur** : Détermine les stratégies qui sont appliquées aux tâches de l’interface utilisateur sur le thread principal, comme les opérations de couper/copier/coller, l’entrée du code PIN, l’authentification et le partage de données. L’identité de l’interface utilisateur n’affecte pas les tâches de fichier comme la sauvegarde et le chiffrement.

* **Identité du thread** : Concerne les stratégies qui sont appliquées sur le thread actuel. Cette identité affecte tous les fichiers, tâches et interface utilisateur.

L’application est chargée de définir les identités de manière appropriée, que l’utilisateur soit géré ou non.

À tout moment, chaque thread a une identité effective pour les tâches d’interface utilisateur et des tâches de fichier. Il s’agit de l’identité utilisée pour vérifier les stratégies, le cas échéant, qui doivent être appliquées. Si l’identité est définie sur « Aucune identité » ou que l’utilisateur n’est pas géré, aucune stratégie n’est appliquée. Les graphiques ci-dessous montrent comment les identités effectives sont déterminées.

  ![SDK des applications Intune pour iOS : Frameworks et bibliothèques liés](../media/intune-app-sdk/ios-thread-identities.png)

### <a name="thread-queues"></a>Files d’attente du thread

Les applications distribuent souvent des tâches synchrones et asynchrones aux files d’attente du thread. Le SDK intercepte les appels GCD (Grand Central Dispatch) et associe l’identité du thread actuel aux tâches distribuées. Quand les tâches sont terminées, le SDK remplace temporairement l’identité du thread par l’identité associée aux tâches, termine les tâches, puis restaure l’identité du thread d’origine.


Comme `NSOperationQueue` repose sur GCD, `NSOperations` s’exécute sur l’identité du thread au moment où les tâches sont ajoutées à `NSOperationQueue`. `NSOperations` ou les fonctions distribuées directement par le biais de GCD peuvent également changer l’identité du thread actuel lors de leur exécution. Cette identité remplace l’identité héritée du thread de distribution.

### <a name="file-owner"></a>Propriétaire du fichier

Le SDK effectue le suivi de l’identité des propriétaires de fichier local et applique des stratégies en conséquence. Un propriétaire de fichier est établi quand un fichier est créé ou qu’il est ouvert en mode tronqué. Le propriétaire est défini sur l’identité de la tâche de fichier effective du thread qui effectue la tâche.

Sinon, les applications peuvent définir l’identité du propriétaire du fichier explicitement à l’aide de `IntuneMAMFilePolicyManager`. Les applications peuvent utiliser `IntuneMAMFilePolicyManager` pour récupérer le propriétaire du fichier et définir l’identité de l’interface utilisateur avant d’afficher le contenu du fichier.

### <a name="shared-data"></a>Données partagées

Si l’application crée des fichiers avec des données d’utilisateurs gérés et non gérés, elle doit chiffrer les données de l’utilisateur géré. Vous pouvez chiffrer des données à l’aide des API `protect` et `unprotect` dans `IntuneMAMDataProtectionManager`.

La méthode `protect` accepte une identité qui peut être un utilisateur géré ou non géré. Si l’utilisateur est géré, les données sont chiffrées. Si l’utilisateur n’est pas géré, un en-tête est ajouté aux données qui encodent l’identité, mais les données ne sont pas chiffrées. Vous pouvez utiliser la méthode `protectionInfo` pour récupérer le propriétaire des données.

### <a name="share-extensions"></a>Extensions de partage

Si l’application a une extension de partage, le propriétaire de l’élément partagé peut être récupéré par le biais de la méthode `protectionInfoForItemProvider` dans `IntuneMAMDataProtectionManager`. Si l’élément partagé est un fichier, le SDK gère la définition du propriétaire du fichier. Si l’élément partagé est représenté par des données, l’application doit définir le propriétaire du fichier si ces données sont conservées dans un fichier et doit appeler l’API `setUIPolicyIdentity` avant d’afficher ces données dans l’interface utilisateur.

### <a name="turning-on-multi-identity"></a>Activation de plusieurs identités

Par défaut, les applications sont considérées comme ayant une identité unique. Le SDK définit l’identité du processus pour l’utilisateur inscrit. Pour activer la prise en charge de plusieurs identités, ajoutez un paramètre booléen avec le nom `MultiIdentity` et la valeur OUI au dictionnaire IntuneMAMSettings dans le fichier Info.plist de l’application.

> [!NOTE]
> Quand plusieurs identités sont activées, l’identité du processus, l’identité de l’interface utilisateur et les identités de thread sont définies sur zéro. L’application est chargée de les définir correctement.

### <a name="switching-identities"></a>Changement d’identité

* **Changement d’identité lancé par l’application** :

    Au lancement, les applications gérant plusieurs identités sont considérées comme s’exécutant sous un compte inconnu non géré. L’interface utilisateur de lancement conditionnel ne s’exécute pas et aucune stratégie n’est appliquée à l’application. L’application notifie le SDK chaque fois que l’identité doit être changée. En général, cela se produit chaque fois que l’application est sur le point d’afficher les données d’un compte d’utilisateur spécifique.

    C’est le cas, par exemple, quand l’utilisateur tente d’ouvrir un document, une boîte aux lettres ou un onglet sur un ordinateur portable. L’application doit notifier le SDK avant que le fichier, la boîte aux lettres ou l’onglet ne soit réellement ouvert. Cette opération est effectuée avec l’API `setUIPolicyIdentity` dans `IntuneMAMPolicyManager`. Cette API doit être appelée, que l’utilisateur soit géré ou non. Si l’utilisateur est géré, le SDK effectue les vérifications du lancement conditionnel, comme la détection de jailbreak, l’entrée du code PIN et l’authentification.

    Le résultat du changement d’identité est retourné à l’application de façon asynchrone par le biais d’un gestionnaire d’achèvement. L’application reporte l’ouverture du document, de la boîte aux lettres ou de l’onglet tant qu’un code de résultat n’est pas retourné. En cas d’échec du changement d’identité, l’application doit annuler la tâche.

* **Changement d’identité lancé par le SDK** :

    Parfois, le SDK doit demander à l’application de basculer sur une identité spécifique. Les applications gérant plusieurs identités doivent implémenter la méthode `identitySwitchRequired` dans `IntuneMAMPolicyDelegate` pour traiter cette demande.

    Quand cette méthode est appelée, si l’application peut gérer la demande de basculement sur l’identité spécifiée, elle doit passer `IntuneMAMAddIdentityResultSuccess` au gestionnaire d’achèvement. Si elle ne peut pas gérer le basculement de l’identité, l’application doit passer `IntuneMAMAddIdentityResultFailed` au gestionnaire d’achèvement.

    L’application n’a pas besoin d’appeler `setUIPolicyIdentity` en réponse à cet appel. Si le SDK a besoin que l’application bascule sur un compte d’utilisateur non géré, une chaîne vide est passée dans l’appel `identitySwitchRequired`.

* **Réinitialisation sélective** :

    Quand une réinitialisation sélective est effectuée dans l’application, le SDK appelle la méthode `wipeDataForAccount` dans `IntuneMAMPolicyDelegate`. L’application est chargée de supprimer le compte de l’utilisateur spécifié et toutes les données associées. Le SDK est capable de supprimer tous les fichiers appartenant à l’utilisateur et le fait si l’application retourne la valeur FALSE pour l’appel `wipeDataForAccount`.

    Notez que cette méthode est appelée à partir d’un thread d’arrière-plan. L’application ne doit pas retourner de valeur tant que toutes les données de l’utilisateur n’ont pas été supprimées (à l’exception des fichiers, si l’application retourne FALSE).

## <a name="test-app-protection-policy-settings-in-xcode"></a>Tester les paramètres de stratégie de protection des applications dans Xcode

Avant de tester manuellement votre application gérée par Intune en production, vous pouvez utiliser un fichier Settings.bundle dans Xcode. Cela vous permet de définir des stratégies de protection des applications pour le test sans connexion à Intune.

### <a name="enable-policy-testing"></a>Activer le test de stratégie

Suivez les étapes ci-dessous pour activer le test de stratégie dans Xcode :

1. Vérifiez que vous utilisez une version de débogage. Ajoutez un fichier Settings.bundle en cliquant avec le bouton droit sur le dossier de niveau supérieur dans votre projet. Choisissez **Ajouter** > **Nouveau fichier** dans le menu. Sous **Ressources**, choisissez le modèle **Settings Bundle**.

2.  Copiez le bloc suivant dans le fichier Settings.bundle/**Root.plist** pour la version de débogage :
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. Dans le dictionnaire **IntuneMAMSettings** du fichier Info.plist de l’application, ajoutez une valeur booléenne appelée « DebugSettingsEnabled ». Définissez la valeur de DebugSettingsEnabled sur « OUI ».



### <a name="app-protection-policy-settings"></a>Paramètres de stratégie de protection des applications

Le tableau ci-dessous décrit les paramètres de stratégie de protection des applications que vous pouvez tester à l’aide de MAMDebugSettings.plist. Pour activer un paramètre, ajoutez-le dans MAMDebugSettings.plist.

| Nom du paramètre de stratégie | Description | Valeurs possibles |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | Durée en minutes pendant laquelle l’application peut être hors connexion avant qu’Intune bloque son lancement ou sa reprise si l’authentification est activée. | Tout entier supérieur à 0 |
|    AccessRecheckOnlineTimeout | Durée en minutes pendant laquelle l’application peut s’exécuter avant que l’utilisateur ne soit invité à entrer le code PIN ou à s’authentifier au lancement ou à la reprise de l’application (si l’authentification ou un code PIN pour l’accès est activé). | Tout entier supérieur à 0 |
| AppSharingFromLevel | Spécifie les applications à partir desquelles cette application peut accepter des données. | 0 = |
## <a name="ios-best-practices"></a>Bonnes pratiques pour iOS

Voici les pratiques recommandées dans le cadre du développement pour iOS :

* Le système de fichiers iOS respecte la casse. Vérifiez que la casse est correcte pour les noms de fichier comme `libIntuneMAM.a` et `IntuneMAMResources.bundle`.

* Si Xcode a des difficultés à localiser `libIntuneMAM.a`, vous pouvez résoudre ce problème en ajoutant le chemin à cette bibliothèque dans les chemins de recherche de l’éditeur de liens.

## <a name="faqs"></a>FAQ


**Toutes les API sont-elles adressables par le biais de Swift natif ou de l’interopérabilité entre Objective-C et Swift ?**

Les API du SDK des applications Intune sont écrites en Objective-C uniquement et ne prennent pas en charge le code Swift **natif**. L’interopérabilité entre Swift et Objective-C est nécessaire.


**Tous les utilisateurs de mon application doivent-ils être inscrits au service APP-WE ?**

Non. En réalité, seuls les comptes professionnels ou scolaires doivent être inscrits dans le SDK des applications Intune. Les applications sont chargées de déterminer si un compte est utilisé dans un contexte professionnel ou scolaire.   

**Qu’en est-il des utilisateurs qui sont déjà connectés à l’application ? Ont-ils besoin d’être inscrits ?**

L’application est chargée de l’inscription des utilisateurs une fois qu’ils ont été authentifiés. L’application est également chargée de l’inscription de tous les comptes potentiellement préexistants quand l’application a reçu les fonctionnalités MAM sans gestion des appareils mobiles.   

Pour ce faire, l’application doit utiliser la méthode `registeredAccounts:`. Cette méthode retourne un NSDictionary contenant tous les comptes inscrits au service MAM Intune. Si un compte existant dans l’application ne figure pas dans la liste, l’application doit l’inscrire via `registerAndEnrollAccount:`.

**Quelle est la fréquence à laquelle le SDK retente les inscriptions ?**

Le SDK réessaie automatiquement toutes les inscriptions ayant échouées dans un intervalle de 24 heures. De cette façon, le SDK vérifie que l’utilisateur est inscrit et reçoit les stratégies si son organisation a activé la gestion MAM une fois que l’utilisateur s’est connecté à l’application.

Le SDK n’effectue plus de nouvelle tentative quand il détecte qu’un utilisateur a inscrit l’application. C’est parce que seul un utilisateur peut inscrire une application à un moment donné. Si l’utilisateur est désinscrit, les nouvelles tentatives recommencent dans le même intervalle de 24 heures.

**Pourquoi l’utilisateur doit-il être désinscrit ?**

Le SDK prend ces actions en arrière-plan régulièrement :

 - Si l’application n’est pas encore inscrite, il tente d’inscrire les comptes inscrits toutes les 24 heures.
 - Si l’application est inscrite, le SDK recherche les mises à jour des stratégies de protection des applications toutes les 8 heures.

La désinscription d’un utilisateur indique au SDK que l’utilisateur n’utilisera plus l’application. Il peut donc arrêter tous les événements périodiques pour ce compte d’utilisateur. Il déclenche également une désinscription de l’application ainsi qu’une réinitialisation sélective si nécessaire.

**Dois-je définir l’indicateur doWipe sur true dans la méthode de désinscription ?**

Cette méthode doit être appelée avant que l’utilisateur ne soit déconnecté de l’application.  Si les données de l’utilisateur sont supprimées de l’application dans le cadre de la déconnexion, `doWipe` peut être défini sur false. En revanche, si l’application ne supprime pas les données de l’utilisateur, `doWipe` doit être défini sur true pour que le SDK puisse supprimer les données.

**Existe-t-il d’autres moyens pour désinscrire une application ?**

Oui, l’administrateur informatique peut envoyer une commande de réinitialisation sélective à l’application. Cette opération désinscrit l’utilisateur et efface ses données. Le SDK gère automatiquement ce scénario et envoie une notification via la méthode déléguée de désinscription.



## <a name="submit-your-app-to-the-app-store"></a>Envoyer votre application à l’App Store

Les versions de bibliothèque statique et de framework du SDK des applications Intune sont des fichiers binaires universels. Cela signifie qu’elles contiennent le code de toutes les architectures d’appareil et de simulateur. Apple rejette les applications envoyées à l’App Store si elles contiennent du code de simulateur. Lors de la compilation de versions de bibliothèque statique ou d’appareil uniquement, l’éditeur de liens supprime automatiquement le code du simulateur. Suivez les étapes ci-dessous pour vérifier que tout le code de simulateur est supprimé avant de charger votre application dans l’App Store.

1. Vérifiez que `IntuneMAM.framework` se trouve sur votre bureau.

2. Exécutez ces commandes :

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    La première commande supprime les architectures de simulateur du fichier DYLIB du framework. La deuxième commande copie le fichier DYLIB d’appareil uniquement dans le répertoire du framework.

