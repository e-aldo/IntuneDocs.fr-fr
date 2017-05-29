---
title: "Guide du Kit SDK d’application Microsoft Intune pour les développeurs iOS | Microsoft Docs"
description: "Le SDK d’application Microsoft Intune pour iOS vous permet d’incorporer des stratégies de protection des applications Intune, sous la forme de stratégies de gestion des applications mobiles (GAM), à votre application iOS."
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
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 767b0564e88cd1662f7567829d26baff1218e312
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Guide du Kit SDK d’application Microsoft Intune pour les développeurs iOS

> [!NOTE]
> Vous pouvez d’abord lire le guide [Bien démarrer avec le SDK d’application Intune](intune-app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.

Le kit SDK d’application Microsoft Intune pour iOS vous permet d’incorporer des stratégies de protection des applications Intune (également appelées **stratégies APP** ou **GAM**) dans votre application iOS native. Une application prenant en charge la gestion GAM est une application intégrée au kit SDK d’application Intune. Les administrateurs informatiques peuvent déployer des stratégies de protection des applications sur votre application mobile quand celle-ci est activement gérée par Intune.

## <a name="prerequisites"></a>Conditions préalables

* Vous devez disposer d’un ordinateur Mac OS qui exécute OS X 10.8.5 ou ultérieur et qui est équipé de XCode 8 ou ultérieur.

* Votre application doit être ciblée pour iOS 9 ou une version ultérieure.

* Consultez les [termes du contrat de licence du SDK d’application Intune pour iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant le SDK d’application Intune pour iOS, vous acceptez les termes de ce contrat de licence.  Si vous ne les acceptez pas, n'utilisez pas le logiciel.

* Téléchargez les fichiers pour le SDK d’application Intune pour iOS sur [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Contenu du SDK

Le SDK d’application Intune pour iOS inclut une bibliothèque statique, des fichiers de ressources, des en-têtes d’API, un fichier .plist de paramètres de débogage et un outil de configuration. Les applications mobiles peuvent simplement inclure les fichiers de ressources et être liées aux bibliothèques de manière statique pour l’application de la plupart des stratégies. Les fonctionnalités de gestion des applications mobiles Intune avancées sont appliquées par le biais d’API.

Ce guide couvre l’utilisation des composants suivants du SDK d’application Intune pour iOS :

* **libIntuneMAM.a** : bibliothèque statique du SDK d’application Intune. Si votre application n’utilise pas d’extensions, liez cette bibliothèque à votre projet pour activer la gestion des applications mobiles Intune pour votre application.

* **IntuneMAM.framework** : infrastructure du SDK d’application Intune. Liez cette infrastructure à votre projet pour activer la gestion des applications mobiles Intune pour votre application. Utilisez l’infrastructure à la place de la bibliothèque statique si votre application utilise des extensions, pour que votre projet ne crée pas plusieurs copies de la bibliothèque statique.

* **IntuneMAMResources.Bundle** : groupe de ressources contenant les ressources sur lesquelles le SDK est basé.

* **En-têtes**: expose les API du SDK d’application Intune. Si vous utilisez une API, vous devez inclure le fichier d’en-tête contenant l’API. Les fichiers d’en-tête suivants incluent les appels de fonction d’API nécessaires pour activer la fonctionnalité du SDK d’application Intune :

    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h


## <a name="how-the-intune-app-sdk-works"></a>Fonctionnement du SDK d’application Intune

L’objectif du SDK d’application Intune pour iOS consiste à ajouter des fonctionnalités de gestion aux applications iOS par le biais de modifications minimales du code. Moins le code change, plus la commercialisation est rapide, la cohérence et la stabilité de votre application mobile n’étant pas affectées.


## <a name="build-the-sdk-into-your-mobile-app"></a>Générer le SDK dans votre application mobile

Pour activer le SDK d’application Intune, procédez comme suit :

1. **Option 1 (recommandée)** : liez `IntuneMAM.framework` à votre projet. Faites glisser `IntuneMAM.framework` vers la liste **Binaires incorporés** de la cible du projet.

    > [!NOTE]
    > Si vous utilisez l’infrastructure, vous devez éliminer manuellement les architectures de simulateur de l’infrastructure universelle avant de soumettre votre application à l’App Store. Pour plus d’informations, consultez [Soumettre votre application à l’App Store](#Submit-your-app-to-the-App-Store).

2. **Option 2** : créez un lien vers la bibliothèque `libIntuneMAM.a`. Faites glisser la bibliothèque `libIntuneMAM.a` sur la liste **Infrastructures et bibliothèques liées** de la cible du projet.

    ![SDK d’application Intune pour iOS : infrastructures et bibliothèques liées](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    > [!NOTE]
    > Si vous prévoyez de publier votre application sur l’App Store, utilisez la version de `libIntuneMAM.a` générée pour la version release et non la version Debug. La version release se trouve dans le dossier **release**. La version Debug a une sortie détaillée qui aide à résoudre les problèmes rencontrés avec le SDK d’application Intune.

    Ajoutez `-force_load {PATH_TO_LIB}/libIntuneMAM.a` à l’un des éléments suivants, en remplaçant `{PATH_TO_LIB}` par l’emplacement du SDK d’application Intune :
      * Le paramètre de configuration de la build `OTHER_LDFLAGS` du projet
      * Les **autres indicateurs de l’éditeur de liens** de l’interface utilisateur

        > [!NOTE]
        > Pour trouver `PATH_TO_LIB`, sélectionnez le fichier `libIntuneMAM.a` et choisissez **Obtenir les informations** dans le menu **Fichier**. Copiez et collez les informations **Où** (chemin) à partir de la section **Général** de la fenêtre **Informations**.

3. Ajoutez ces infrastructures iOS au projet :
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework


4. Ajoutez le groupe de ressources `IntuneMAMResources.bundle` au projet en faisant glisser le groupe de ressources sous **Copier les ressources de groupe** dans **Phases de la build**.

    ![SDK d’application Intune pour iOS : copier les ressources de groupe](../media/intune-app-sdk-ios-copy-bundle-resources.png)

5. Si votre application mobile définit un fichier nib ou storyboard principal dans son fichier Info.plist, coupez le ou les champs **Main Storyboard** ou **Main Nib**. Collez ces champs et leurs valeurs correspondantes dans le fichier Info.plist sous un nouveau dictionnaire nommé **IntuneMAMSettings** avec les noms de clé ci-après, selon le cas :
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Si votre application mobile ne définit pas un fichier nib ou storyboard principal dans son fichier info.plist, ces paramètres ne sont pas nécessaires.

    Vous pouvez consulter le fichier info.plist dans son format brut (pour voir les noms de clé) en cliquant avec le bouton droit n’importe où dans le corps du document et en remplaçant le type d’affichage par **Afficher les clés/valeurs brutes**.

6. Activez le partage de trousseau (s’il ne l’est pas déjà) en cliquant sur **Fonctionnalités** dans chaque cible du projet et en activant le commutateur **Partage de trousseau**. Le partage de trousseau est nécessaire pour passer à l’étape suivante.

  > [!NOTE]
    > Votre profil d’approvisionnement doit prendre en charge de nouvelles valeurs de partage de trousseau. Les groupes de trousseau d’accès doivent prendre en charge un caractère générique. Vous pouvez le vérifier en ouvrant le fichier .mobileprovision dans un éditeur de texte, en recherchant **keychain-access-groups** et en vérifiant que vous avez un caractère générique. Exemple :
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

7. Après avoir activé le partage de trousseau, procédez comme suit pour créer un groupe d’accès distinct dans lequel le SDK d’application Intune stockera ses données. Vous pouvez créer un groupe d’accès au trousseau à l’aide de l’interface utilisateur ou du fichier des droits. Si vous utilisez l’interface utilisateur pour créer le groupe d’accès au trousseau, suivez les étapes ci-dessous :

    1. Si votre application mobile n’a pas de groupes d’accès au trousseau définis, ajoutez l’ID d’offre groupée de l’application comme premier groupe.

    2. Ajoutez le groupe de trousseau partagé `com.microsoft.intune.mam` à vos groupes d’accès existants. Ce groupe d’accès est utilisé par le SDK d’application Intune pour stocker des données.

    3. Ajoutez `com.microsoft.adalcache` à vos groupes d’accès existants.

        4. Ajoutez `com.microsoft.workplacejoin` à vos groupes d’accès existants.
            ![SDK d’application Intune pour iOS : partage de trousseau](../media/intune-app-sdk-ios-keychain-sharing.png)

      5. Si vous utilisez le fichier des droits pour créer le groupe d’accès au trousseau, ajoutez `$(AppIdentifierPrefix)` au début du groupe d’accès au trousseau dans le fichier des droits. Exemple :

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Un fichier de droits d’accès est un fichier XML propre à votre application mobile. Il permet de spécifier des fonctionnalités et des autorisations spéciales dans votre application iOS.

7. Si l’application définit des modèles d’URL dans son fichier info.plist, ajoutez un autre modèle avec un suffixe `-intunemam` pour chaque modèle d’URL.

8. Pour les applications mobiles développées sur iOS 9+, incluez chaque protocole que votre application mobile passe à `UIApplication canOpenURL` dans le tableau `LSApplicationQueriesSchemes` du fichier Info.plist de votre application. Par ailleurs, pour chaque protocole répertorié, ajoutez un nouveau protocole et insérez `-intunemam` à la fin. Vous devez également inclure `http-intunemam`, `https-intunemam`et `ms-outlook-intunemam` dans le tableau.

9. Si l’application a des groupes d’applications définis dans ses droits, ajoutez ces groupes au dictionnaire **IntuneMAMSettings** sous la clé `AppGroupIdentifiers` sous la forme d’un tableau de chaînes.



## <a name="configure-azure-active-directory-authentication-library-adal"></a>Configurer Azure Active Directory Authentication Library (ADAL)

Le SDK d’application Intune utilise [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) pour ses scénarios d’authentification et de lancement conditionnel. Il s’appuie également sur la bibliothèque ADAL pour inscrire l’identité de l’utilisateur auprès du service GAM pour les scénarios sans inscription des appareils.

En règle générale, ADAL exige que les applications soient inscrites auprès d’Azure Active Directory (AAD) et dotées d’un ID unique (ID client) ainsi que d’autres identificateurs, pour garantir la sécurité des jetons octroyés à l’application. Sauf mention contraire, le SDK d’application Intune utilise les valeurs d’inscription par défaut pour contacter Azure AD.  

Si votre application utilise déjà ADAL pour authentifier les utilisateurs, elle doit utiliser ses valeurs d’inscription existantes et remplacer les valeurs par défaut du SDK d’application Intune. De cette façon, les utilisateurs ne sont pas invités à s’authentifier deux fois (une fois par le SDK d’application Intune et une autre fois par l’application).

### <a name="recommendations"></a>Recommandations

Il est recommandé que votre application soit liée à la [version la plus récente de la bibliothèque ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) sur la branche principale. Le SDK d’application Intune utilise actuellement la branche de broker d’ADAL pour prendre en charge les applications qui nécessitent un accès conditionnel. (Ces applications dépendent par conséquent de l’application Microsoft Authenticator.) Mais le SDK est toujours compatible avec la branche maître d’ADAL. Utilisez la branche qui convient à votre application.

### <a name="link-to-adal-binaries"></a>Lien vers les fichiers binaires ADAL

Suivez les étapes ci-dessous pour lier votre application aux fichiers binaires ADAL :

1. Téléchargez la [Bibliothèque d’authentification Azure Active Directory (ADAL) pour Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) à partir de GitHub, puis suivez les [instructions](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) sur la manière de télécharger la bibliothèque ADAL à l’aide des sous-modules Git ou de CocoaPods.

2. Incluez le groupe de ressources `ADALiOSBundle.bundle` dans le projet en faisant glisser le groupe de ressources sous **Copier les ressources de groupe** dans **Phases de la build**.

3. Ajoutez `-force_load {PATH_TO_LIB}/libADALiOS.a` au paramètre de configuration de la build `OTHER_LDFLAGS` du projet ou à **Autres indicateurs de l’éditeur de liens** dans l’interface utilisateur. `PATH_TO_LIB` doit être remplacé par l’emplacement des binaires ADAL.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Partager le cache de jeton ADAL avec d’autres applications signées avec le même profil d’approvisionnement ?**

Suivez les instructions ci-dessous si vous souhaitez partager des jetons ADAL entre des applications signées avec le même profil d’approvisionnement :

1. Si votre application n’a pas de groupes d’accès au trousseau définis, ajoutez l’ID d’offre groupée de l’application comme premier groupe.

2. Activez l’authentification unique (SSO) ADAL en ajoutant les groupes d’accès `com.microsoft.adalcache` et `com.microsoft.workplacejoin` dans les droits du trousseau.

3. Si vous définissez explicitement le groupe de trousseaux du cache partagé ADAL, vérifiez qu’il a la valeur `<app_id_prefix>.com.microsoft.adalcache`. ADAL définit ceci pour vous, sauf si vous le remplacez. Si vous voulez spécifier un groupe de trousseaux personnalisé pour remplacer `com.microsoft.adalcache`, spécifiez-le dans le fichier Info.plist sous IntuneMAMSettings en utilisant la clé `ADALCacheKeychainGroupOverride`.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Configurer les paramètres ADAL pour le SDK d’application Intune

Si votre application utilise déjà la bibliothèque ADAL pour l’authentification et dispose de ses propres paramètres ADAL, vous pouvez forcer le SDK d’application Intune à utiliser les mêmes paramètres lors de l’authentification auprès d’Azure Active Directory. Ceci permet de s’assurer que l’application ne demandera pas deux fois à l’utilisateur de s’authentifier. Consultez [Configurer les paramètres du SDK d’application Intune](#configure-settings-for-the-intune-app-sdk) pour plus d’informations sur le remplissage des paramètres suivants :  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Si votre application utilise déjà ADAL, les configurations suivantes sont requises :

1. Dans le fichier Info.plist du projet, sous le dictionnaire **IntuneMAMSettings** avec le nom de clé `ADALClientId`, spécifiez l’ID de client à utiliser pour les appels ADAL.

2. Également sous le dictionnaire **IntuneMAMSettings** avec le nom de clé `ADALAuthority`, spécifiez l’autorité Azure AD.

3. Également sous le dictionnaire **IntuneMAMSettings** avec le nom de clé `ADALRedirectUri`, spécifiez l’URI de redirection à utiliser pour les appels ADAL. Vous pouvez également spécifier `ADALRedirectScheme` selon le format de l’URI de redirection de votre application.


Vous pouvez également remplacer l’URL de l’autorité Azure AD par une URL propre au locataire au moment de l’exécution. Pour ce faire, il vous suffit de définir la propriété `aadAuthorityUriOverride` sur l’instance `IntuneMAMPolicyManager`.

> [!NOTE]
> La configuration de l’URL de l’autorité AAD est requise pour que la [stratégie APP sans inscription des appareils](#App-protection-policy-without-device-enrollment) permette au SDK de réutiliser le jeton d’actualisation ADAL extrait par l’application.

Le SDK continue d’utiliser cette URL de l’autorité pour l’actualisation de la stratégie et pour toute demande d’inscription ultérieure, sauf si la valeur est supprimée ou modifiée.  Par conséquent, il est important de supprimer la valeur quand un utilisateur managé se déconnecte de l’application, puis de la réinitialiser quand un nouvel utilisateur managé se connecte.

### <a name="if-your-app-does-not-use-adal"></a>Si votre application n’utilise pas ADAL

Si votre application n’utilise pas ADAL, le SDK d’application Intune fournit des valeurs par défaut pour les paramètres ADAL et gère l’authentification auprès d’Azure AD. Il est inutile de spécifier des valeurs pour les paramètres ADAL répertoriés ci-dessus.

## <a name="app-protection-policy-without-device-enrollment"></a>Stratégie de protection des applications sans inscription des appareils

### <a name="overview"></a>Vue d'ensemble
La stratégie de protection des applications Intune sans inscription des appareils, également appelée **APP-WE** ou MAM-WE, permet aux applications d’être gérées par Intune sans nécessiter l’inscription de l’appareil auprès de la gestion des appareils mobiles (MDM) Intune. Pour prendre en charge cette nouvelle fonctionnalité, l’application doit procéder à l’inscription des comptes d’utilisateurs en vue de leur gestion. Pour utiliser les nouvelles API, procédez comme suit :

1. Utilisez la dernière version du SDK d’application Intune qui prend en charge la gestion des applications avec ou sans inscription des appareils.

2. Ajoutez IntuneMAMEnrollment.h à tout fichier appelant les API.

### <a name="register-user-accounts"></a>Inscrire des comptes d’utilisateurs

Une application peut recevoir une stratégie de protection d’application du service Intune si l’application s’inscrit auprès du service APP-WE au nom d’un compte d’utilisateur spécifié. L’application doit inscrire tout utilisateur nouvellement connecté au SDK. Une fois le nouveau compte d’utilisateur authentifié, l’application doit appeler la méthode `registerAndEnrollAccount` dans Headers/IntuneMAMEnrollment.h :

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
En appelant la méthode `registerAndEnrollAccount`, le SDK inscrit le compte d’utilisateur et tente d’inscrire l’application au nom de ce compte. Si l’inscription échoue pour une raison quelconque, le SDK retente automatiquement l’inscription 24 heures plus tard. Pour le débogage, l’application peut recevoir des notifications, par le biais d’un délégué, sur les résultats de toute demande d’inscription.

Une fois que cette API a été appelée, l’application peut continuer à fonctionner normalement. Si l’inscription réussit, le SDK informe l’utilisateur qu’il doit redémarrer l’application. L’utilisateur peut redémarrer l’application tout de suite.

### <a name="deregister-user-accounts"></a>Désinscrire des comptes d’utilisateurs

Avant qu’un utilisateur se déconnecte d’une application, celle-ci doit désinscrire l’utilisateur du SDK. De cette façon :

1. Les tentatives d’inscription ne se produisent plus pour le compte de l’utilisateur.

2. La stratégie de protection d’application sera supprimée.

3. Si l’application lance une réinitialisation sélective (facultative), toutes les données d’entreprise sont supprimées.

Avant que l’utilisateur ne soit déconnecté, l’application doit appeler l’API suivante dans `Headers/IntuneMAMEnrollment.h` :

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

Cette méthode doit être appelée avant la suppression des jetons Azure AD du compte d’utilisateur. Le SDK a besoin des jetons AAD du compte d’utilisateur pour effectuer des demandes spécifiques au service APP-WE au nom de l’utilisateur.

Si l’application supprime elle-même les données d’entreprise de l’utilisateur, l’indicateur `doWipe` peut être défini sur false. Dans le cas contraire, l’application peut demander au SDK de lancer une réinitialisation sélective. Il en résulte un appel au délégué de réinitialisation sélective de l’application.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a>Applications n’utilisant pas ADAL

Les applications qui ne connectent pas l’utilisateur avec ADAL peuvent toujours recevoir une stratégie de protection d’application du service Intune en appelant l’API pour que le SDK gère cette authentification. Les applications doivent utiliser cette technique si elles n’ont pas authentifié un utilisateur avec Azure AD, mais qu’elles doivent néanmoins récupérer la stratégie de protection d’application pour protéger les données. Cela peut arriver si un autre service d’authentification est utilisé pour la connexion à l’application ou si l’application ne prend pas du tout en charge la connexion. Pour cela, l’application doit appeler la méthode `loginAndEnrollAccount` dans Headers/IntuneMAMEnrollment.h :

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

En appelant cette méthode, le SDK demande des informations d’identification à l’utilisateur si aucun jeton existant ne peut être trouvé. Le SDK tente alors d’inscrire l’application auprès du service APP-WE au nom du compte d’utilisateur fourni. La méthode peut être appelée avec « nil » comme identité. Dans ce cas, le SDK effectue l’inscription avec l’utilisateur géré existant sur l’appareil ou demande un nom d’utilisateur à l’utilisateur si aucun utilisateur existant n’est trouvé.

Si l’inscription échoue, il est recommandé que l’application rappelle ultérieurement cette API, en fonction des détails de l’échec. L’application peut recevoir des [notifications](#Status-result-and-debug-notifications), par le biais d’un délégué, concernant les résultats de toute demande d’inscription.

Une fois cette API appelée, l’application peut continuer à fonctionner normalement. Si l’inscription réussit, le SDK informe l’utilisateur qu’il doit redémarrer l’application.

## <a name="status-result-and-debug-notifications"></a>Notifications d’état, de résultat et de débogage

L’application peut recevoir des notifications d’état, de résultat et de débogage concernant les demandes suivantes adressées au service GAM Intune :

 - Demandes d’inscription
 - Demandes de mise à jour de stratégie
 - Demandes de désinscription

Les notifications sont présentées par le biais de méthodes déléguées dans `Headers/IntuneMAMEnrollmentDelegate.h` :

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

Ces méthodes déléguées retournent un objet `IntuneMAMEnrollmentStatus` qui contient les informations suivantes :

- L’identité du compte associé à la demande
- Un code d’état indiquant le résultat de la demande
- Une chaîne d’erreur avec une description du code d’état
- Objet `NSError`

Cet objet est défini dans `IntuneMAMEnrollmentStatus.h`, ainsi que les codes d’état spécifiques qui peuvent être renvoyés.


### <a name="sample-code"></a>Exemple de code

Voici des exemples d’implémentation des méthodes déléguées :

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

Quand une application reçoit des stratégies de protection des applications pour la première fois, elle doit redémarrer pour appliquer les hooks nécessaires. Pour notifier l’application qu’un redémarrage doit être effectué, le SDK fournit une méthode déléguée dans Headers/IntuneMAMPolicyDelegate.h.

```objc
 - (BOOL) restartApplication
```
La valeur renvoyée par cette méthode indique au SDK si l’application doit gérer le redémarrage requis :   

 - Si la méthode renvoie la valeur true, l’application doit gérer le redémarrage.   

 - Si la valeur false est retournée, le SDK doit redémarrer l’application après le retour de cette méthode. Le SDK affiche immédiatement une boîte de dialogue qui demande à l’utilisateur de redémarrer l’application.

## <a name="customize-your-apps-behavior"></a>Personnaliser le comportement de votre application

Le SDK d’application Intune comporte plusieurs API que vous pouvez appeler pour obtenir des informations sur la stratégie de protection d’application Intune déployée sur l’application. Vous pouvez utiliser ces données pour personnaliser le comportement de votre application. La plupart des paramètres de stratégie de protection d’application sont automatiquement appliqués par le SDK, et non par l’application. Le seul paramètre que l’application doit implémenter est le contrôle Enregistrer sous.

### <a name="get-app-protection-policy"></a>Obtenir la stratégie de protection d’application

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
La classe IntuneMAMPolicyManager expose la stratégie de protection d’application Intune déployée sur l’application. En particulier, elle expose les API qui sont utiles pour l’[activation de la multi-identité](#-enable-multi-identity-optional).

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
La classe IntuneMAMPolicy expose la stratégie de protection d’application Intune déployée sur l’application. La plupart des paramètres de stratégie exposés dans cette classe sont appliqués par le SDK, mais vous pouvez toujours personnaliser le comportement de votre application en fonction de la façon dont les paramètres de stratégie sont appliqués.

Cette classe expose des API nécessaires pour implémenter des contrôles Enregistrer sous, décrits en détail dans la section suivante.

### <a name="implement-save-as-controls"></a>Implémenter des contrôles Enregistrer sous

Intune permet aux administrateurs informatiques de sélectionner les emplacements de stockage dans lesquels une application gérée peut enregistrer des données. Les applications peuvent interroger le SDK d’application Intune pour connaître les emplacements de stockage autorisés à l’aide de l’API **isSaveToAllowedForLocation**, définie dans**IntuneMAMPolicy.h**.

Avant d’enregistrer des données gérées dans un emplacement de stockage local ou de type cloud, les applications doivent vérifier si l’administrateur a autorisé l’enregistrement de données à cet emplacement à l’aide de l’API **isSaveToAllowedForLocation**.

Quand les applications utilisent l’API **isSaveToAllowedForLocation**, elles doivent passer l’UPN utilisé pour l’emplacement de stockage, s’il est disponible.

#### <a name="supported-save-locations"></a>Emplacements d’enregistrement pris en charge

L’API **isSaveToAllowedForLocation** fournit des constantes pour vérifier si l’administrateur informatique autorise l’enregistrement des données dans les emplacements suivants définis dans IntuneMAMPolicy.h :

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Les applications doivent utiliser les constantes dans l’API **isSaveToAllowedForLocation** pour vérifier si les données peuvent être enregistrées dans des emplacements considérés comme « gérés », tels que OneDrive Entreprise, ou « personnels ». En outre, l’API doit être utilisée quand l’application ne peut pas déterminer si un emplacement est « géré » ou « personnel ».

Les emplacements connus comme étant « personnels » sont représentés par la constante `IntuneMAMSaveLocationOther`.

Utilisez la constante `IntuneMAMSaveLocationLocalDrive` quand l’application enregistre des données à n’importe quel emplacement sur l’appareil local.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Configurer des paramètres pour le SDK d’application Intune

Vous pouvez utiliser le dictionnaire **IntuneMAMSettings** dans le fichier Info.plist de l’application pour paramétrer et configurer le SDK d’application Intune. Si le dictionnaire IntuneMAMSettings n’apparaît pas dans votre fichier Info.plist, vous devez créer un dictionnaire dans le fichier Info.plist de votre application avec le nom de champ « IntuneMAMSettings ».

Sous le dictionnaire IntuneMAMSettings, vous pouvez ajouter des lignes de paramètres de configuration clé/valeur pour configurer le SDK. Le tableau ci-après répertorie tous les paramètres pris en charge.

Certains de ces paramètres peuvent avoir été traités dans les sections précédentes, tandis que d’autres ne s’appliquent pas à toutes les applications.

Paramètre  | Type  | Définition | Nécessaire ?
--       |  --   |   --       |  --
ADALClientId  | Chaîne  | Identificateur du client Azure AD de l’application. | Obligatoire si l’application utilise ADAL. |
ADALAuthority | Chaîne | Autorité Azure AD de l’application en cours d’utilisation. Vous devez utiliser votre propre environnement où les comptes AAD ont été configurés. | Obligatoire si l’application utilise ADAL. Si cette valeur est omise, une valeur par défaut Intune est utilisée.|
ADALRedirectUri  | Chaîne  | URI de redirection Azure AD de l’application. | ADALRedirectUri ou ADALRedirectScheme est nécessaire si l’application utilise ADAL.  |
ADALRedirectScheme  | Chaîne  | Modèle de redirection Azure AD de l’application. Ceci peut être utilisé à la place d’ADALRedirectUri si l’URI de redirection de l’application est au format `scheme://bundle_id`. | ADALRedirectUri ou ADALRedirectScheme est nécessaire si l’application utilise ADAL. |
ADALLogOverrideDisabled | Booléen  | Indique si le SDK achemine tous les journaux ADAL (notamment les appels ADAL à partir l’application le cas échéant) dans son propre fichier journal. La valeur par défaut est NON. Affectez la valeur OUI si l’application doit définir le rappel de son propre journal ADAL. | Facultatif. |
ADALCacheKeychainGroupOverride | Chaîne  | Spécifie le groupe de trousseaux à utiliser pour le cache ADAL au lieu de « com.microsoft.adalcache ». Notez qu’il n’a pas le préfixe app-id. Il est préfixé par la chaîne fournie lors de l’exécution. | Facultatif. |
AppGroupIdentifiers | Tableau de chaînes  | Tableau de groupes d’applications issu de la section com.apple.security.application-groups des droits de l’application. | Obligatoire si l’application utilise des groupes d’applications. |
ContainingAppBundleId | Chaîne | Spécifie l’ID d’offre groupée de l’application conteneur de l’extension. | Obligatoire pour les extensions iOS. |
DebugSettingsEnabled| Booléen | S’il est défini sur YES, les stratégies de test dans le groupe de paramètres peuvent être appliquées. Les applications *ne doivent pas* être livrées avec ce paramètre activé. | Facultatif. |
MainNibFile<br>MainNibFile~ipad  | Chaîne  | Ce paramètre doit avoir le nom de fichier nib principal de l’application.  | Obligatoire si l’application définit MainNibFile dans Info.plist. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Chaîne  | Ce paramètre doit avoir le nom de fichier storyboard principal de l’application. | Obligatoire si l’application définit UIMainStoryboardFile dans Info.plist. |
AutoEnrollOnLaunch| Booléen| Spécifie si l’application doit tenter de s’inscrire automatiquement au lancement si une identité gérée existante est détectée et qu’elle ne l’a pas encore fait. La valeur par défaut est NON. <br><br> Remarques : Si aucune identité managée n’est trouvée ou si aucun jeton valide pour l’identité n’est disponible dans le cache ADAL, la tentative d’inscription échoue en mode silencieux sans demander d’informations d’identification, sauf si l’application a également défini MAMPolicyRequired avec la valeur Oui. | Facultatif. |
+AutoEnrollOnLaunch| Booléen| Spécifie si l’application doit tenter de s’inscrire automatiquement au lancement si une identité gérée existante est détectée et qu’elle ne l’a pas encore fait. La valeur par défaut est NON. <br><br> Remarques : Si aucune identité managée n’est trouvée ou si aucun jeton valide pour l’identité n’est disponible dans le cache ADAL, la tentative d’inscription échoue en mode silencieux sans demander d’informations d’identification, sauf si l’application a également défini MAMPolicyRequired avec la valeur Oui. | Facultatif. |
 +MAMPolicyRequired| Booléen| Spécifie si le démarrage de l’application doit être bloqué si l’application n’a pas de stratégie de protection d’application Intune. La valeur par défaut est NON. <br><br> Remarques : Les applications ne peuvent pas être envoyées à l’App Store avec MAMPolicyRequired défini avec la valeur OUI. Lorsque vous définissez MAMPolicyRequired avec la valeur Oui, AutoEnrollOnLaunch doit également être défini avec la valeur Oui. | Facultatif. |
 +MAMPolicyWarnAbsent | Booléen| Spécifie si l’application avertit l’utilisateur pendant le lancement si l’application n’a pas de stratégie de protection d’application Intune. <br><br> Remarque : Les utilisateurs pourront continuer à utiliser l’application sans stratégie après avoir ignoré l’avertissement. | Facultatif. |
MultiIdentity | Booléen| Spécifie si l’application prend en charge plusieurs identités. | Facultatif. |
SplashIconFile <br>SplashIconFile~ipad | Chaîne  | Spécifie le fichier d’icône de démarrage Intune. | Facultatif. |
SplashDuration | Nombre | Durée minimale en secondes d’affichage de l’écran de démarrage Intune au lancement de l’application. La valeur par défaut est 1,5. | Facultatif. |
BackgroundColor| Chaîne| Spécifie la couleur d’arrière-plan pour les écrans de démarrage et d’entrée du code confidentiel. Accepte une chaîne hexadécimale RVB au format #XXXXXX, où X peut être 0-9 ou A-F. Le signe dièse peut être omis.   | Facultatif. La valeur par défaut est le gris clair. |
ForegroundColor| Chaîne| Spécifie la couleur de premier plan pour les écrans de démarrage et d’entrée du code confidentiel, comme la couleur du texte. Accepte une chaîne hexadécimale RVB au format #XXXXXX, où X peut être 0-9 ou A-F. Le signe dièse peut être omis.  | Facultatif. La valeur par défaut est le noir. |
AccentColor | Chaîne| Spécifie la couleur d’accentuation de l’écran d’entrée du code confidentiel, comme la couleur de texte des boutons et la couleur de surbrillance des zones. Accepte une chaîne hexadécimale RVB au format #XXXXXX, où X peut être 0-9 ou A-F. Le signe dièse peut être omis.| Facultatif. La valeur par défaut est le bleu. |
MAMTelemetryDisabled| Booléen| Spécifie si le SDK n’envoie pas de données de télémétrie à son serveur principal.| Facultatif. |

> [!NOTE]
> Si votre application doit être publiée dans l’App Store, `MAMPolicyRequired` doit être défini sur « NO », conformément aux normes de l’App Store.

## <a name="telemetry"></a>Télémétrie

Par défaut, le SDK d’application Intune pour iOS enregistre des données de télémétrie sur les événements d’utilisation suivants. Ces données sont envoyées à Microsoft Intune.

* **Lancement d’applications** : Pour aider Microsoft Intune à en savoir plus sur l’utilisation des applications compatibles GAM par type de gestion (GAM avec MDM, GAM sans inscription à MDM, etc.).

* **Appels d’inscription** : Pour aider Microsoft Intune à en savoir plus sur les taux de réussite et d’autres mesures de performances des appels d’inscription initiés à partir du côté client.

> [!NOTE]
> Si vous choisissez de ne pas envoyer les données télémétriques du SDK d’application Intune à Microsoft Intune à partir de votre application mobile, vous devez désactiver la capture de la télémétrie du SDK d’application Intune. Affectez OUI à la propriété `MAMTelemetryDisabled` dans le dictionnaire IntuneMAMSettings.

## <a name="enable-multi-identity-optional"></a>Activer la multi-identité (facultatif)

Par défaut, le SDK applique une stratégie à l’application dans son ensemble. La multi-identité est une fonctionnalité GAM que vous pouvez activer pour appliquer une stratégie par niveau d’identité. Ceci nécessite davantage de participation de l’application que d’autres fonctionnalités GAM.

L’application doit informer le SDK d’application quand elle va changer l’identité active. Le SDK notifie aussi l’application quand un changement d’identité est nécessaire. Actuellement, une seule identité gérée est prise en charge. Une fois que l’utilisateur inscrit l’appareil ou l’application, le SDK utilise cette identité et la considère comme l’identité gérée principale. Les autres utilisateurs de l’application sont considérés comme non gérés avec des paramètres de stratégie non limités.

Notez qu’une identité est simplement définie sous la forme d’une chaîne. Les identités ne respectent pas la casse. Les demandes d’une identité au SDK peuvent ne pas retourner la même casse que celle initialement utilisée lors de la définition de l’identité.

### <a name="identity-overview"></a>Vue d’ensemble de l’identité

Une identité est simplement le nom d’utilisateur d’un compte (par exemple, user@contoso.com). Les développeurs peuvent définir l’identité de l’application sur les niveaux suivants :

* **Identité du processus** : Définit l’identité au niveau du processus. Elle est principalement utilisée pour les applications avec une seule identité. Cette identité affecte toutes les tâches, les fichiers et l’interface utilisateur.

* **Identité de l’interface utilisateur** : Détermine les stratégies qui sont appliquées aux tâches de l’interface utilisateur sur le thread principal (par exemple : couper/copier/coller, code confidentiel, authentification, partage de données, etc.). L’identité de l’interface utilisateur n’affecte pas les tâches relatives aux fichiers comme le chiffrement et la sauvegarde.

* **Identité du thread** : Affecte les stratégies qui sont appliquées sur le thread actif. Cette identité affecte toutes les tâches, les fichiers et l’interface utilisateur.

L’application doit définir l’identité de façon appropriée, que l’utilisateur soit géré ou non.

À tout moment, chaque thread a une identité effective pour les tâches de l’interface utilisateur et celles relatives aux fichiers. Il s’agit de l’identité utilisée pour vérifier les stratégies qui doivent être appliquées, le cas échéant. Si l’identité est « aucune identité » ou si l’utilisateur n’est pas géré, aucune stratégie n’est appliquée. Les schémas ci-dessous montrent comment les identités effectives sont déterminées.

  ![SDK d’application Intune pour iOS : infrastructures et bibliothèques liées](../media/intune-app-sdk/ios-thread-identities.png)

### <a name="thread-queues"></a>Files d’attente de threads

Les applications distribuent souvent des tâches synchrones et asynchrones à des files d’attente de threads. Le SDK intercepte les appels au GCD (Grand Central Dispatch) et associe l’identité du thread actif aux tâches distribués. Quand les tâches sont terminées, le SDK remplace temporairement l’identité du thread par l’identité associée à la tâche, termine les tâches, puis restaure l’identité du thread d’origine.


Comme `NSOperationQueue` est basé sur GCD, les `NSOperations` s’exécutent sur l’identité du thread au moment où les tâches sont ajoutées à `NSOperationQueue`. Les `NSOperations` ou les fonctions distribuées directement par le biais de GCD peuvent également changer l’identité du thread actif lors de leur exécution. Cette identité remplace l’identité héritée du thread de distribution.

### <a name="file-owner"></a>Propriétaire des fichiers

Le SDK fait le suivi des identités des propriétaires des fichiers locaux et applique des stratégies en conséquence. Un propriétaire de fichier est établi quand un fichier est créé ou quand un fichier est ouvert en mode tronqué. L’identité de la tâche de fichier effective du thread exécutant la tâche est affectée au propriétaire.

Les applications peuvent également définir explicitement l’identité du propriétaire du fichier en utilisant `IntuneMAMFilePolicyManager`. Les applications peuvent utiliser `IntuneMAMFilePolicyManager` pour récupérer le propriétaire du fichier et définir l’identité de l’interface utilisateur avant d’afficher le contenu du fichier.

### <a name="shared-data"></a>Données partagées

Si l’application crée des fichiers qui contiennent des données provenant d’utilisateurs gérés et d’autres non gérés, elle est responsable du chiffrement des données de l’utilisateur géré. Vous pouvez chiffrer des données à l’aide des API `protect` et `unprotect` dans `IntuneMAMDataProtectionManager`.

La méthode `protect` accepte une identité qui peut être un utilisateur géré ou non. Si l’utilisateur est géré, les données sont chiffrées. Si l’utilisateur n’est pas géré, un en-tête est ajouté aux données de codage de l’identité, mais les données ne sont pas chiffrées. Vous pouvez utiliser la méthode `protectionInfo` pour récupérer le propriétaire des données.

### <a name="share-extensions"></a>Extensions de partage

Si l’application a une extension de partage, le propriétaire de l’élément partagé peut être récupéré à l’aide de la méthode `protectionInfoForItemProvider` dans `IntuneMAMDataProtectionManager`. Si l’élément partagé est un fichier, le SDK gère la définition du propriétaire du fichier. Si l’élément partagé est constitué de données, l’application est responsable de la définition du propriétaire du fichier si ces données sont conservées dans un fichier, et elle est aussi responsable de l’appel de l’API `setUIPolicyIdentity` avant d’afficher ces données dans l’interface utilisateur.

### <a name="turning-on-multi-identity"></a>Activation de la multi-identité

Par défaut, les applications sont considérées comme ayant une identité unique. Le SDK affecte l’identité du processus à l’utilisateur inscrit. Pour activer la prise en charge de la multi-identité, ajoutez un paramètre booléen avec le nom `MultiIdentity` et la valeur YES au dictionnaire IntuneMAMSettings dans le fichier Info.plist de l’application.

> [!NOTE]
> Quand la multi-identité est activée, l’identité du processus, celle de l’interface utilisateur et celles des threads ont la valeur nil. L’application doit les définir correctement.

### <a name="switching-identities"></a>Changement d’identités

* **Changement d’identité initié par l’application** :

    Au lancement, les applications multi-identités sont considérées comme s’exécutant sous un compte inconnu, non géré. L’interface utilisateur avec lancement conditionnel ne s’exécute pas et aucune stratégie n’est appliquée à l’application. L’application doit notifier le SDK chaque fois que l’identité doit être modifiée. En général, ceci se produit chaque fois que l’application est sur le point d’afficher des données pour un compte d’utilisateur spécifique.

    C’est le cas par exemple quand l’utilisateur tente d’ouvrir un document, une boîte aux lettres ou un onglet dans un bloc-notes. L’application doit notifier le SDK avant que le fichier, la boîte aux lettres ou l’onglet soit réellement ouvert. Cette opération est effectuée via l’API `setUIPolicyIdentity` dans `IntuneMAMPolicyManager`. Cette API doit être appelée que l’utilisateur soit géré ou non. Si l’utilisateur est géré, le SDK effectue les vérifications du lancement conditionnel (par exemple : détection de jailbreak, code confidentiel et authentification).

    Le résultat du changement d’identité est retourné à l’application de façon asynchrone via un gestionnaire d’achèvement. L’application doit reporter l’ouverture du document, de la boîte aux lettres ou de l’onglet jusqu’à ce qu’un code de résultat indiquant la réussite soit retourné. Si le changement d’identité échoue, l’application doit annuler la tâche.

* **Changement d’identité initié par le SDK** :

    Parfois, le SDK doit demander à l’application de passer à une identité spécifique. Les applications multi-identités doivent implémenter la méthode `identitySwitchRequired` dans `IntuneMAMPolicyDelegate` pour traiter cette demande.

    Quand cette méthode est appelée, si l’application peut traiter la demande de passage à l’identité spécifiée, elle doit passer `IntuneMAMAddIdentityResultSuccess` au gestionnaire d’achèvement. Si elle ne peut pas gérer le changement d’identité, l’application doit passer `IntuneMAMAddIdentityResultFailed` au gestionnaire d’achèvement.

    L’application n’a pas besoin d’appeler `setUIPolicyIdentity` en réponse à cet appel. Si le SDK a besoin de l’application pour passer à un compte d’utilisateur non managé, une chaîne vide est passée dans l’appel de `identitySwitchRequired`.

* **Réinitialisation sélective** :

    Quand l’application fait l’objet d’une réinitialisation sélective, le SDK appelle la méthode `wipeDataForAccount` dans `IntuneMAMPolicyDelegate`. L’application doit supprimer le compte d’utilisateur spécifié et les données qui y sont associées. Le SDK peut supprimer tous les fichiers appartenant à l’utilisateur et le fait si l’application retourne FALSE à la suite de l’appel à `wipeDataForAccount`.

    Notez que cette méthode est appelée à partir d’un thread d’arrière-plan. L’application ne doit pas retourner de valeur tant que toutes les données de l’utilisateur n’ont pas été supprimées (à l’exception des fichiers si l’application retourne FALSE).

## <a name="test-app-protection-policy-settings-in-xcode"></a>Tester les paramètres de stratégie de protection d’application dans Xcode

Avant de tester manuellement votre application compatible Intune en production, vous pouvez utiliser un fichier Settings.bundle dans Xcode. Ainsi, vous pouvez définir des stratégies de protection d’application pour le test sans qu’une connexion à Intune soit nécessaire.

### <a name="enable-policy-testing"></a>Activer le test de stratégie

Suivez les étapes ci-dessous pour activer le test de stratégie dans Xcode :

1. Assurez-vous d’être dans un build de débogage. Ajoutez un fichier Settings.bundle en cliquant avec le bouton droit sur le dossier de premier niveau dans votre projet. Sélectionnez **Ajouter** > **Nouveau fichier** dans le menu. Sous **Ressources**, sélectionnez le modèle **Groupe de paramètres**.

2.  Copiez le bloc suivant dans le fichier Settings.bundle/**Root.plist** pour le build de débogage :
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

3. Dans le dictionnaire **IntuneMAMSettings** dans le fichier Info.plist de l’application, ajoutez une valeur booléenne appelée « DebugSettingsEnabled ». Définissez la valeur de DebugSettingsEnabled sur « OUI ».



### <a name="app-protection-policy-settings"></a>Paramètres de stratégie de protection d’application

Le tableau ci-dessous décrit les paramètres de la stratégie de protection d’application que vous pouvez tester à l’aide de MAMDebugSettings.plist. Pour activer un paramètre, vous devez l’ajouter à MAMDebugSettings.plist.

| Nom de paramètre de stratégie | Description | Valeurs possibles |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | La durée en minutes pendant laquelle l’application peut être hors connexion avant qu’Intune ne bloque le lancement ou la reprise de l’application si l’authentification est activée. | Tout entier supérieur à 0 |
|    AccessRecheckOnlineTimeout | La durée en minutes pendant laquelle l’application peut s’exécuter avant que l’utilisateur ne soit invité à fournir son code confidentiel ou son authentification au lancement ou à la reprise (si l’authentification ou le code confidentiel pour l’accès est activé(e)). | Tout entier supérieur à 0 |
| AppSharingFromLevel | Spécifie de quelles applications cette application peut accepter des données. | 0 = |
## <a name="ios-best-practices"></a>Bonnes pratiques pour iOS

Voici les bonnes pratiques recommandées dans le cadre du développement pour iOS :

* Le système de fichiers iOS respecte la casse. Vérifiez que la casse est correcte dans les noms de fichiers comme `libIntuneMAM.a` et `IntuneMAMResources.bundle`.

* Si Xcode a des difficultés à trouver `libIntuneMAM.a`, vous pouvez résoudre ce problème en ajoutant le chemin à cette bibliothèque dans les chemins de recherche de l’éditeur de liens.

## <a name="faqs"></a>Foire aux questions


**Est-ce que toutes les API sont adressables via le code Swift natif ou l’interopérabilité Objective-C et Swift ?**

Les API du SDK d’application Intune sont en Objective-C uniquement et ne prennent pas en charge le code Swift **natif**. Une interopérabilité de Swift avec Objective-C est requise.


**Tous les utilisateurs de mon application doivent-ils être inscrits auprès du service APP-WE ?**

Non. En fait, seuls les comptes professionnels ou scolaires doivent être inscrits auprès du SDK d’application Intune. Les applications doivent déterminer si un compte est utilisé dans un contexte professionnel ou scolaire.   

**Qu’en est-il des utilisateurs qui se sont déjà connectés à l’application ? Doivent-ils être inscrits ?**

L’application est responsable de l’inscription des utilisateurs une fois qu’ils sont authentifiés. L’application est également responsable de l’inscription des comptes existants qui étaient présents avant que l’application ne dispose des fonctionnalités GAM sans MDM.   

Pour cela, l’application doit utiliser la méthode `registeredAccounts:`. Cette méthode retourne un NSDictionary contenant tous les comptes inscrits dans le service GAM Intune. Si des comptes existants dans l’application ne sont pas dans la liste, l’application doit inscrire ces comptes par le biais de `registerAndEnrollAccount:`.

**À quelle fréquence le SDK réessaie-t-il les inscriptions ?**

Le SDK réessaye automatiquement toutes les inscriptions ayant échoué selon un intervalle de 24 heures. Le SDK procède ainsi pour garantir que si l’organisation d’un utilisateur a activé GAM après que l’utilisateur s’est connecté à l’application, cet utilisateur est inscrit et reçoit les stratégies avec succès.

Le SDK arrête les nouvelles tentatives quand il détecte qu’un utilisateur a inscrit l’application avec succès. La raison en est qu’un seul utilisateur peut inscrire une application à un moment donné. Si l’utilisateur est désinscrit, les nouvelles tentatives reprennent selon le même intervalle de 24 heures.

**Pourquoi l’utilisateur doit-il être désinscrit ?**

Le SDK effectue périodiquement ces actions en arrière-plan :

 - Si l’application n’est pas encore inscrite, il tente d’inscrire tous les comptes inscrits toutes les 24 heures.
 - Si l’application est inscrite, le SDK recherche les mises à jour des stratégies de protection des applications toutes les 8 heures.

La désinscription d’un utilisateur indique au SDK que l’utilisateur n’utilise plus l’application et qu’il peut arrêter les événements périodiques ci-dessus pour ce compte d’utilisateur. Elle déclenche également une désinscription de l’application et une réinitialisation sélective si nécessaire.

**Dois-je définir l’indicateur doWipe sur true dans la méthode de désinscription ?**

Cette méthode doit être appelée avant que l’utilisateur soit déconnecté de l’application.  Si les données de l’utilisateur sont supprimées de l’application dans le cadre de la déconnexion, `doWipe` peut être défini avec la valeur false. Mais si l’application ne supprime pas les données de l’utilisateur, `doWipe` doit être défini avec la valeur true pour que le SDK puisse supprimer les données.

**Existe-t-il d’autres façons de désinscrire une application ?**

Oui, l’administrateur informatique peut envoyer une commande de réinitialisation sélective à l’application qui désinscrit l’utilisateur et réinitialise ses données. Le SDK gère automatiquement ce scénario et envoie une notification par le biais de la méthode déléguée de désinscription.



## <a name="submit-your-app-to-the-app-store"></a>Soumettre votre application à l’App Store

Les générations de la bibliothèque statique et de l’infrastructure du SDK d’application Intune sont des binaires universels. Cela signifie qu’ils contiennent le code pour toutes les architectures d’appareils et de simulateurs. Apple rejette les applications soumises à l’App Store si elles ont du code de simulateur. Lors de la compilation avec la bibliothèque statique pour les builds destinées seulement aux appareils, l’éditeur de liens supprime automatiquement le code du simulateur. Suivez les étapes ci-dessous pour vous assurer que tout le code du simulateur est supprimé avant de charger votre application dans l’App Store.

1. Vérifiez que `IntuneMAM.framework` est sur votre poste de travail.

2. Exécutez les commandes suivantes :

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    La première commande élimine les architectures de simulateur des fichiers DYLIB de l’infrastructure. La deuxième commande recopie les fichiers DYLIB pour appareils uniquement dans le répertoire de l’infrastructure.

