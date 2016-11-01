---
title: "Guide du Kit SDK d’application Microsoft Intune pour les développeurs iOS | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6b998728b3db60d10cadbcd34b5412fa76cb586f
ms.openlocfilehash: ddc47ef5846bf448cf0de1e57b527e8ec4c562cc


---

# Guide du Kit SDK d’application Microsoft Intune pour les développeurs iOS

> [!NOTE]
> Vous pouvez d’abord consulter le [Guide de prise en main du Kit SDK d’application Intune](intune-app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.* 

Le SDK d’application Microsoft Intune pour iOS vous permet d’incorporer la gestion des applications mobiles Intune à votre application iOS. Une application compatible GAM est une application intégrée au SDK d’application Intune. Elle permet aux administrateurs informatiques de déployer des stratégies sur votre application mobile quand l’application est gérée activement par Intune.


# Contenu du SDK 

Le SDK d’application Intune pour iOS inclut une bibliothèque statique, des fichiers de ressources, des en-têtes d’API, un fichier plist de paramètres de débogage et un outil de configuration. Les applications mobiles peuvent simplement inclure les fichiers de ressources et être liées aux bibliothèques de manière statique pour l’application de la plupart des stratégies. Les fonctionnalités de gestion des applications mobiles Intune avancées sont appliquées par le biais d’API.

Ce guide couvre l’utilisation des composants suivants du SDK d’application Intune pour iOS :

* **libIntuneMAM.a** : bibliothèque statique du SDK d’application Intune. Si votre application n’utilise pas d’extensions, liez cette bibliothèque à votre projet pour activer la gestion des applications mobiles Intune pour votre application. Vous pouvez trouver des instructions dans la section « Génération de votre application avec le SDK d’application Intune ».

* **IntuneMAM.framework** : infrastructure du SDK d’application Intune. Liez cette infrastructure à votre projet pour activer la gestion des applications mobiles Intune pour votre application. Utilisez l’infrastructure à la place de la bibliothèque statique si votre application utilise des extensions, pour que votre projet ne crée pas plusieurs copies de la bibliothèque statique.

* **IntuneMAMResources.Bundle** : groupe de ressources qui contient les ressources sur lesquelles le SDK est basé. 

* **En-têtes**: expose les API du SDK d’application Intune. Si vous utilisez une API, vous devez inclure le fichier d’en-tête contenant l’API. Les fichiers d’en-tête suivants incluent les appels de fonction d’API nécessaires pour activer la fonctionnalité du SDK d’application Intune. 
    
    * IntuneMAMAsyncResult.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMLogger.h 


# Fonctionnement du SDK d’application Intune

L’objectif du SDK d’application Intune pour iOS consiste à ajouter des fonctionnalités de gestion aux applications iOS par le biais de modifications minimales du code. Moins le code change, plus la commercialisation est rapide, la cohérence et la stabilité de votre application mobile étant en plus toujours garanties. 

L’application doit être liée à la bibliothèque statique et doit inclure le groupe de ressources. Le fichier MAMDebugSettings.plist est facultatif et peut être inclus dans le package pour simuler des stratégies de gestion des applications mobiles appliquées à l’application sans avoir à déployer l’application par le biais de Microsoft Intune. De plus, dans les versions Debug, les stratégies du fichier MAMDebugSettings.plist sont appliquées en transférant le fichier dans le répertoire Documents de l’application via le partage de fichiers iTunes.

# Génération du SDK dans votre application mobile 

Suivez les étapes ci-dessous pour activer le SDK d’application Intune :

1. **Option 1** : établissez un lien vers la bibliothèque `libIntuneMAM.a` en procédant comme suit :

    Faites glisser et déposez la bibliothèque `libIntuneMAM.a` vers la liste « Infrastructures et bibliothèques liées » de la cible du projet.
    ![SDK d’application Intune pour iOS : infrastructures et bibliothèques liées](../media/intune-app-sdk-ios-linked-frameworks-and-libraries.png) 

    **Remarque** : Si vous prévoyez de publier votre application sur l’App Store, utilisez la version de `libIntuneMAM.a` générée pour la version finale et non pas pour la version Debug. La version finale se trouve dans le dossier « release ». La version Debug a une sortie détaillée qui aide à résoudre les problèmes rencontrés avec le SDK d’application Intune.
    
    **Option 2** : lier le `IntuneMAM.framework` à votre projet. Faites glisser et déposez `IntuneMAM.framework` vers la liste « Infrastructures et bibliothèques liées » de la cible du projet.
    
    **Remarque** : Si vous utilisez l’infrastructure, vous devez éliminer manuellement les architectures de simulateur de l’infrastructure universelle avant de soumettre votre application à l’App Store. Consultez la section intitulée « Soumission de votre application à l’App Store ».

2. Ajoutez les infrastructures iOS suivantes au projet :
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.dylib
    * libc++.dylib
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

    **Remarque** : Si l’application est ciblée pour iOS 7, définissez l’attribut « Status » de `LocalAuthentication.framework` sur « Optional ». Si « Status » n’est pas défini, l’application échoue à démarrer sur iOS 7.

    **Remarque**: Xcode 7 a remplacé les extensions `.dylib` par `.tbd`.

3. Ajoutez le groupe de ressources `IntuneMAMResources.bundle` au projet en faisant glisser le groupe de ressources sous « Copier les ressources de groupe » dans « Phases de la build ».
![SDK d’application Intune pour iOS : copier les ressources de groupe](../media/intune-app-sdk-ios-copy-bundle-resources.png)
 
4. Ajoutez `-force_load {PATH_TO_LIB}/libIntuneMAM.a` à l’un des éléments suivants, en remplaçant `{PATH_TO_LIB}` par l’emplacement du SDK d’application Intune :
    * Le paramètre de configuration de la build `OTHER_LDFLAGS` du projet 
    * Les « autres indicateurs de l’éditeur de liens » de l’interface utilisateur<br>

    **Remarque** : Pour trouver le `PATH_TO_LIB`, sélectionnez le fichier `libIntuneMAM.a` et choisissez « Obtenir les informations » dans le menu « Fichier ». Copiez et collez les informations « Où » (le chemin) à partir de la section « Général » de la fenêtre « Informations ».

5. Si votre application mobile définit un Nib ou un Storyboard principal dans son fichier Info.plist, supprimez les champs du fichier Main Storyboard ou Main Nib. Ajoutez les valeurs Storyboard ou Nib que vous avez supprimées précédemment à un nouveau dictionnaire nommé IntuneMAMSettings avec les noms de clé suivants, selon le cas :
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    
   **Remarque** : Si votre application mobile ne définit pas un Nib ou un Storyboard principal dans son fichier info.plist, ces paramètres **ne sont pas nécessaires**. 

    **Remarque** : Vous pouvez consulter le fichier info.plist dans son format brut (pour voir les noms de clé) en cliquant avec le bouton droit n’importe où dans le corps du document et en choisissant le type de vue en « Show Raw Keys/Values (Afficher les clés/valeurs brutes) ».

6. Activez le partage Keychain (s’il ne l’est pas déjà) en cliquant sur « Fonctionnalités » dans chaque cible du projet et en activant le commutateur « Partage Keychain ». Le partage de trousseau est requis pour passer à l’étape suivante.

    **Remarque**: Votre profil de configuration doit prendre en charge de nouvelles valeurs de partage de trousseau. Les groupes de trousseau d’accès doivent prendre en charge un caractère générique. Vous pouvez le vérifier en ouvrant le fichier .mobileprovision dans un éditeur de texte, en recherchant « keychain-access-groups » et en vérifiant que vous avez un caractère générique, par exemple : 
    ```
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```
7. Après avoir activé le partage de trousseau, procédez comme suit pour créer un groupe d’accès distinct dans lequel les données du SDK d’application Intune seront stockées. Vous pouvez créer un groupe d’accès au trousseau à l’aide de l’interface utilisateur ou du fichier des droits :

    Utilisation de l’interface utilisateur pour créer un groupe d’accès au trousseau : 
    
    * Si votre application mobile n’a pas de groupes d’accès au trousseau définis, ajoutez l’ID d’offre groupée de l’application en tant que premier groupe.
    * Ajoutez le groupe Keychain partagé `com.microsoft.intune.mam`. Ce groupe d’accès est utilisé par le SDK d’application Intune pour stocker des données.  
    * Ajoutez `com.microsoft.adalcache` à vos groupes d’accès existants. 

    ![SDK d’application Intune pour iOS : partage de trousseau](../media/intune-app-sdk-ios-keychain-sharing.png) 

    Si vous utilisez le fichier des droits pour créer le groupe d’accès au trousseau, plutôt que l’interface utilisateur standard, vous devez ajouter le groupe d’accès au trousseau avec `$(AppIdentifierPrefix)` dans le fichier des droits. Exemple :  
    * `$(AppIdentifierPrefix)com.microsoft.intune.mam` 
    * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    **Remarque**: Un fichier des droits est un fichier XML unique propre à votre application mobile qui est utilisée pour spécifier des autorisations et fonctionnalités spéciales au sein de votre application iOS.

8. Si l’application définit des modèles d’URL dans son fichier info.plist, ajoutez un autre modèle avec un suffixe `-intunemam` pour chaque modèle d’URL.

9. Pour les applications mobiles développées pour iOS 9+, vous devez inclure chaque protocole que votre application mobile passe à `UIApplication canOpenURL` dans le tableau `LSApplicationQueriesSchemes` du fichier Info.plist de votre application mobile. De plus, pour chaque protocole répertorié, un nouveau protocole doit être ajouté avec `-intunemam`. Vous devez également inclure `http-intunemam`, `https-intunemam`et `ms-outlook-intunemam` dans le tableau. 

10. Si l’application a des groupes d’applications définis dans ses droits, ajoutez ces groupes au dictionnaire IntuneMAMSettings sous la clé `AppGroupIdentitifiers`sous la forme d’un tableau de chaînes.

11. Liez votre application mobile à Azure Active Authentication Library (ADAL). La bibliothèque ADAL pour Objective C est [disponible sur Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).

    **Remarque**: Le SDK d’application Intune a été testé par rapport au code ADAL Broker Branch du 19/06/2015. Assurez-vous d’établir un lien avec la version la plus récente/fonctionnelle de la bibliothèque ADAL.

12. Incluez le groupe de ressources `ADALiOSBundle.bundle` dans le projet en faisant glisser le groupe de ressources sous « Copier les ressources de groupe » dans « Phases de la build ».

13. Utilisez l’option de l’éditeur de liens `-force_load PATH_TO_ADAL_LIBRARY` pour établir le lien avec la bibliothèque.

    Ajoutez `-force_load {PATH_TO_LIB}/libADALiOS.a` au paramètre de configuration de la build `OTHER_LDFLAGS`du projet ou à « Autres indicateurs de l’éditeur de liens » dans l’interface utilisateur. `PATH_TO_LIB` doit être remplacé par l’emplacement des binaires ADAL. 

# Configuration des paramètres de la bibliothèque ADAL dans votre application 

Le SDK d’application Intune utilise la bibliothèque ADAL pour son authentification et le scénario de lancement conditionnel. Il s’appuie également sur la bibliothèque ADAL pour inscrire l’identité de l’utilisateur auprès du service GAM pour les scénarios sans inscription des appareils. 

En règle générale, la bibliothèque ADAL exige que les applications s’inscrivent et obtiennent un ID unique, appelé ClientID, et d’autres identificateurs, pour garantir la sécurité des jetons octroyés à l’application. Le SDK d’application Intune utilise les valeurs d’inscription par défaut pour contacter Azure Active Directory.  

Si l’application elle-même utilise la bibliothèque ADAL pour son scénario d’authentification, l’application doit utiliser ses valeurs d’inscription existantes et remplacer les valeurs par défaut du SDK d’application Intune pour veiller à ce que les utilisateurs finaux ne soient pas invités à s’authentifier deux fois (une fois par le SDK d’application Intune et une fois par l’application). 

##Forum aux questions sur la bibliothèque ADAL

**Quels fichiers binaires ADAL dois-je utiliser ?** 

Le SDK d’application Intune utilise actuellement la branche de broker de [ADAL sur GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-objc) pour prendre en charge les applications qui nécessitent un accès conditionnel (applications qui dépendent par conséquent de l’application Microsoft Authenticator). Cependant, le SDK est toujours compatible avec la branche maître de la bibliothèque ADAL. Utilisez la branche qui convient à votre application.

**Comment lier les fichiers binaires ADAL ?**

Ajoutez `-force_load {PATH_TO_LIB}/libADALiOS.a` au paramètre de configuration de la build `OTHER_LDFLAGS` du projet ou à « Autres indicateurs de l’éditeur de liens » dans l’interface utilisateur. `PATH_TO_LIB` doit être remplacé par l’emplacement des binaires ADAL. En outre, copiez le groupe de la bibliothèque ADAL dans votre application.  

Pour plus d’informations, consultez les instructions de [ADAL sur Github](https://github.com/AzureAD/azure-activedirectory-library-for-objc).


**Comment partager le cache ADAL avec d’autres applications signées avec le même profil de configuration ?**

Si votre application mobile n’a pas de groupes d’accès Keychain définis, ajoutez l’ID d’offre groupée de l’application comme premier groupe.
Activez l’authentification unique ADAL en ajoutant les groupes d’accès `com.microsoft.adalcache` et `com.microsoft.workplacejoin` dans les droits Keychain. 

Si vous définissez explicitement le groupe Keychain du cache partagé ADAL, vérifiez qu’il est défini sur `<app_id_prefix>.com.microsoft.adalcache`. ADAL définit ceci pour vous, sauf si vous le remplacez. Si vous voulez spécifier un groupe Keychain personnalisé pour remplacer `com.microsoft.adalcache`, spécifiez-le dans le fichier Info.plist sous « IntuneMAMSettings », en utilisant la clé `ADALCacheKeychainGroupOverride`.

**Comment forcer le SDK d’application Intune à utiliser les paramètres ADAL que mon application utilise déjà ?** 

Si votre application utilise déjà ADAL, consultez la section sur IntuneMAMSettings ci-dessous pour plus d’informations sur le remplissage des paramètres ci-dessous :  

* ADALClientId
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

**Comment basculer entre les environnements de test internes et les environnements de production AAD ?**

Le paramètre `AadAuthorityURI` dans `MAMPolicies.plist` peut être utilisé pour spécifier l’environnement AAD utilisé pour les appels ADAL. Il est actuellement configuré pour utiliser par défaut l’environnement de préproduction (PPE) AAD, sauf s’il est remplacé.
    
Pour tester sur l’environnement PPE, vous pouvez utiliser un commutateur de compilation ou d’exécution. 

Pour un commutateur d’environnement de compilation des URL du service GAM et AAD, définissez l’indicateur booléen `UsePPE` sur true dans MAMEnvironment.plist. (**Remarque** : Il n’existe aucune prise en charge pour cette opération via Info.plist.) 

Pour un commutateur d’environnement d’exécution, définissez `com.microsoft.intune.mam.useppe` dans les valeurs par défaut de l’utilisateur standard sur « 1 » pour utiliser PPE. Ceci remplace le paramètre `com.microsoft.intune.mam.AADAuthorityEnvironment` existant. 

**Comment remplacer l’URL de l’autorité AAD avec une URL spécifique au locataire fournie à l’exécution ?** 

Définissez la propriété `aadAuthorityUriOverride` sur l’instance IntuneMAMPolicyManager.

**Remarque** : Vous avez besoin de ceci dans le scénario GAM sans inscription des appareils pour permettre au SDK de réutiliser le jeton d’actualisation ADAL extrait par l’application.

**Remarque :** Le SDK continue d’utiliser cette URL de l’autorité pour l’actualisation de la stratégie et pour toute demande d’inscription ultérieure, sauf si la valeur est supprimée ou modifiée.  Par conséquent, il est important de supprimer la valeur quand un utilisateur d’entreprise se déconnecte de l’application, puis de la réinitialiser quand un nouvel utilisateur d’entreprise se reconnecte.


**Que dois-je faire si mon application elle-même utilise ADAL pour l’authentification ?**

Les étapes ci-dessous sont nécessaires si l’application elle-même utilise déjà ADAL pour l’authentification. Si votre application n’est pas basée sur ADAL, consultez la section expliquant comment s’inscrire auprès du service Intune si votre application n’utilise pas ADAL.

* Dans le fichier Info.plist du projet, sous le dictionnaire IntuneMAMSettings avec le nom de clé `ADALClientId`, spécifiez la valeur de ClientID à utiliser pour les appels ADAL. 

* Dans le fichier Info.plist du projet, sous le dictionnaire IntuneMAMSettings avec le nom de clé `ADALRedirectUri`, spécifiez la valeur de l’URI de redirection à utiliser pour les appels ADAL. Vous pouvez également spécifier `ADALRedirectScheme` selon le format de l’URI de redirection de votre application.



#Inscription de votre application auprès du service GAM 

## Utilisation des API
Le SDK d’application Intune offre maintenant la possibilité pour les applications iOS de recevoir des stratégies GAM d’Intune sans devoir être inscrits auprès de la gestion des appareils mobiles avec Intune. Pour prendre en charge cette nouvelle fonctionnalité, le SDK fournit de nouvelles API qui permettent à l’application de recevoir des stratégies GAM. Pour utiliser les nouvelles API, procédez comme suit :

1. Utilisez la dernière version du SDK d’application Intune qui prend en charge la gestion des applications avec ou sans inscription des appareils. Si votre application a utilisé une version antérieure du SDK sans cette fonctionnalité, vous devez mettre à jour la bibliothèque GAM Intune, ainsi que le dossier Headers avec les fichiers d’en-tête de la dernière version du SDK.

2. Ajoutez IntuneMAMEnrollment.h à tout fichier appelant les API 

3. Pour tester sur l’environnement PPE, vous pouvez inclure un commutateur de compilation ou d’exécution. 

    Pour un commutateur d’environnement de compilation des URL du service GAM et AAD, définissez l’indicateur booléen `UsePPE` sur true dans MAMEnvironment.plist. (**Remarque** : Il n’existe aucune prise en charge pour cette opération via Info.plist.) 

    Pour un commutateur d’environnement d’exécution, définissez `com.microsoft.intune.mam.useppe` dans les valeurs par défaut de l’utilisateur standard sur « 1 » pour utiliser PPE. Ceci remplace le paramètre `com.microsoft.intune.mam.AADAuthorityEnvironment` existant. 


##Inscription de comptes 

Une application peut recevoir des stratégies GAM du service Intune si l’application est inscrite au nom d’un compte d’utilisateur spécifié.  Il est de la responsabilité de l’application d’inscrire tout utilisateur nouvellement connecté auprès du SDK d’application Intune.  Une fois que le nouveau compte d’utilisateur a été authentifié, l’application doit appeler la méthode `registerAndEnrollAccount` qui se trouve dans Headers/IntuneMAMEnrollment.h : 

```
/** 


 *  This method will add the account to the list of registered accounts. 
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK 
 */ 

(void)registerAndEnrollAccount:(NSString *)identity; 

```
En appelant la méthode ci-dessus, le SDK inscrit le compte d’utilisateur et tente d’inscrire l’application au nom de ce compte.  Si l’inscription échoue pour une raison quelconque, le SDK retente automatiquement l’inscription 24 heures plus tard.  Pour le débogage, l’application peut recevoir des notifications, via un délégué, sur les résultats de toute demande d’inscription (consultez les informations détaillées ci-dessous).

Une fois que cette API a été appelée, l’application peut continuer à fonctionner normalement.  Si l’inscription réussit, le SDK informe l’utilisateur qu’il doit redémarrer l’application.  L’utilisateur peut redémarrer l’application tout de suite.


##Désinscription de comptes 


Avant qu’un utilisateur se déconnecte d’une application, celle-ci doit désinscrire l’utilisateur du SDK.  De cette façon : 

1. Les tentatives d’inscription ne se produisent plus pour le compte de l’utilisateur. 
2. Si l’utilisateur a inscrit l’application avec succès, l’utilisateur et l’application sont désinscrits du service GAM Intune, et les stratégies GAM seront supprimées.
3. Une réinitialisation sélective peut aussi être lancée pour garantir que les données professionnelles ou scolaires associées sont supprimées. 

Avant que l’utilisateur soit déconnecté, l’application doit appeler l’API suivante dans Headers/IntuneMAMEnrollment.h : 

```
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

Cette méthode doit être appelée avant la suppression des jetons AAD du compte d’utilisateur.  Le SDK a besoin du jeton d’application de l’utilisateur pour effectuer des demandes spécifiques au service GAM Intune au nom de l’utilisateur. 

Si l’application supprime elle-même les données professionnelles ou scolaires associées, l’indicateur `doWipe` peut être défini sur false.  Dans le cas contraire, l’application peut demander au SDK de lancer une réinitialisation sélective, ce qui entraîne un appel du délégué de réinitialisation sélective de l’application. 

```
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES]; 
```


##Inscription sans connexion préalable 

Une application qui ne connecte pas l’utilisateur avec Azure Active Directory peut toujours recevoir les stratégies GAM du service Intune en appelant l’API ci-dessous pour que le SDK gère cette authentification. Les applications doivent utiliser ceci quand elles n’ont pas authentifié un utilisateur avec AAD, mais que vous devez néanmoins récupérer les stratégies GAM pour protéger les données des applications, par exemple si un autre service d’authentification est utilisé pour la connexion à l’application ou si l’application ne prend pas du tout en charge la connexion. Pour cela, l’application doit appeler la méthode `loginAndEnrollAccount` qui se trouve dans Headers/IntuneMAMEnrollment.h :

```
/** 
 *  Creates an enrollment request which is started immediately. 
 *  If no token can be retrieved for the identity, the user will be prompted 
 *  to enter their credentials, after which enrollment will be retried. 
 *  @param identity The UPN of the account to be logged in and enrolled. 
 */ 
 (void)loginAndEnrollAccount: (NSString *)identity; 

```
En appelant cette méthode, le SDK demande des informations d’identification à l’utilisateur si aucun jeton existant ne peut être trouvé, puis tente d’inscrire l’application au nom de ce compte. La méthode peut être appelée avec « nil » comme identité, auquel cas le SDK inscrit avec l’utilisateur GAM existant sur l’appareil ou demande un nom d’utilisateur à l’utilisateur si aucun n’est trouvé. 

Si l’inscription échoue, il est recommandé que l’application rappelle ultérieurement cette API, en fonction des détails de l’échec. L’application peut recevoir des notifications, via un délégué, sur les résultats de toute demande d’inscription (consultez les informations détaillées). 

Une fois que cette API a été appelée, l’application peut continuer à fonctionner normalement.  Si l’inscription réussit, le SDK informe l’utilisateur qu’un redémarrage de l’application est nécessaire, comme indiqué dans la section ci-dessus sur l’inscription des comptes. 

##Informations de débogage 

L’application peut recevoir des notifications de débogage sur les demandes suivantes adressées au service GAM Intune : 

 - Demandes d’inscription 
 - Demandes de mise à jour de stratégie 
 - Demandes de désinscription 

Les notifications sont présentées via des méthodes déléguées qui se trouvent dans Headers/IntuneMAMEnrollmentDelegate.h : 

```
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

Ces méthodes déléguées retournent un objet ```IntuneMAMEnrollmentStatus``` qui contient les informations suivantes : 

- L’identité du compte associé à la demande 
- Un code d’état indiquant le résultat de la demande 
- Une chaîne d’erreur avec une description du code d’état 
- Un objet NSError 

Cet objet est défini dans Headers/IntuneMAMEnrollmentStatus.h, ainsi que les codes d’état spécifiques qui peuvent être retournés. 

Il est important de noter que ces informations sont destinées à des fins de débogage, et aucune logique métier de l’application métier ne doit s’appuyer sur ces notifications.  L’idée est que l’application peut envoyer ces informations à un service de télémétrie à des fins de débogage ou de surveillance. 


##Exemple de code 

Voici des exemples d’implémentation des méthodes déléguées : 

```
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


##Redémarrage de l’application 

Quand une application reçoit des stratégies GAM pour la première fois, elle doit redémarrer pour appliquer les hooks nécessaires.  Pour notifier l’application qu’un redémarrage doit être effectué, le SDK fournit une méthode déléguée dans Headers/IntuneMAMPolicyDelegate.h. 
```
 - (BOOL) restartApplication 
```
La valeur de retour de cette méthode indique au SDK si l’application gère le redémarrage nécessaire.   

 - Si la valeur true est retournée, l’application est responsable de la gestion du redémarrage.   
 - Si la valeur false est retournée, le SDK doit redémarrer l’application après le retour de cette méthode.  Le SDK affiche immédiatement une boîte de dialogue qui informe l’utilisateur que l’application doit être redémarrée. 

#Implémentation de contrôles Enregistrer sous

Intune permet aux administrateurs informatiques de sélectionner les emplacements de stockage dans lesquels une application gérée peut enregistrer des données. Les applications peuvent interroger le SDK d’application Intune pour connaître les emplacements de stockage autorisés à l’aide de l’API **isSaveToAllowedForLocation**.

Avant d’enregistrer des données gérées dans un emplacement de stockage local ou de type cloud, les applications doivent vérifier avec l’API **isSaveToAllowedForLocation** si l’administrateur a autorisé l’enregistrement de données à cet emplacement.

Quand les applications utilisent l’API **isSaveToAllowedForLocation**, elles doivent transmettre l’UPN utilisé pour l’emplacement de stockage, s’il est disponible.

##Emplacements pris en charge

L’API **isSaveToAllowedForLocation** fournit des constantes pour vérifier les emplacements suivants :

* IntuneMAMSaveLocationOther 
* IntuneMAMSaveLocationOneDriveForBusiness 
* IntuneMAMSaveLocationSharePoint 
* IntuneMAMSaveLocationBox 
* IntuneMAMSaveLocationDropbox 
* IntuneMAMSaveLocationGoogleDrive 
* IntuneMAMSaveLocationLocalDrive 

Les applications doivent utiliser les constantes dans l’API **isSaveToAllowedForLocation** afin de vérifier si les données peuvent être enregistrées aux emplacements considérés comme « gérés », tels que OneDrive Entreprise, ou « personnels ». En outre, l’API doit être utilisée quand l’application est incapable de déterminer si un emplacement est « géré » ou « personnel ». 

Quand un emplacement est connu pour être « personnel », les applications doivent utiliser la valeur **IntuneMAMSaveLocationOther**. 

Utilisez la constante **IntuneMAMSaveLocationLocalDrive** quand l’application enregistre les données à n’importe quel emplacement sur l’appareil local.



# Configurer les paramètres du SDK d’application Intune

Le dictionnaire IntuneMAMSettings contenu dans le fichier info.plist de l’application est utilisé pour configurer le SDK d’application Intune. Voici la liste de tous les paramètres pris en charge. 

Certains de ces paramètres peuvent avoir été traités dans les sections précédentes et d’autres ne s’appliquent pas à toutes les applications. 

Paramètre  | Type  | Définition | Nécessaire ?
--       |  --   |   --       |  --
ADALClientId  | Chaîne  | Identificateur du client AAD de l’application. | Obligatoire si l’application utilise ADAL.
ADALRedirectUri  | Chaîne  | URI de redirection AAD de l’application. | ADALRedirectUri ou ADALRedirectScheme est nécessaire si l’application utilise ADAL. 
ADALRedirectScheme  | Chaîne  | Modèle de redirection AAD de l’application. Ceci peut être utilisé à la place d’ADALRedirectUri si l’URI de redirection de l’application est au format `scheme://bundle_id`. | ADALRedirectUri ou ADALRedirectScheme est nécessaire si l’application utilise ADAL. 
ADALLogOverrideDisabled | Booléen  | Indique si le SDK achemine tous les journaux de la bibliothèque ADAL (y compris les appels de la bibliothèque ADAL depuis l’application le cas échéant) dans son propre fichier journal. La valeur par défaut est NON. Affectez la valeur OUI si l’application doit définir le rappel de son propre journal ADAL. | Facultatif.
ADALCacheKeychainGroupOverride | Chaîne  | Spécifie le groupe Keychain à utiliser pour le cache ADAL au lieu de « com.microsoft.adalcache ». Notez qu’il ne contient pas le préfixe app-id. Il est préfixé par la chaîne fournie lors de l’exécution. | Facultatif.
AppGroupIdentifiers | Tableau de chaînes  | Tableau de groupes d’applications issu de la section com.apple.security.application-groups des droits de l’application. | Obligatoire si l’application utilise des groupes d’applications.
ContainingAppBundleId | Chaîne | Spécifie que l’ID d’offre groupée de l’application conteneur de l’extension. | Obligatoire pour les extensions iOS.
DebugSettingsEnabled| Booléen | S’il est défini sur YES, les stratégies de test dans le groupe de paramètres peuvent être appliquées. Les applications **ne doivent pas** être livrées avec ce paramètre activé. | Facultatif.
MainNibFile<br>MainNibFile~ipad  | Chaîne  | Ce paramètre doit contenir le nom de fichier nib principal de l’application.  | Obligatoire si l’application définit MainNibFile dans son fichier Info.plist.
MainStoryboardFile<br>MainStoryboardFile~ipad  | Chaîne  | Ce paramètre doit contenir le nom de fichier storyboard principal de l’application. | Obligatoire si l’application définit UIMainStoryboardFile dans son fichier Info.plist
MAMPolicyRequired| Booléen| Spécifie si le lancement de l’application doit être bloqué si l’application n’a pas de stratégie GAM Intune. La valeur par défaut est « Non ». 
MAMPolicyWarnAbsent | Booléen| Spécifie si l’application avertit l’utilisateur lors du lancement si l’application n’a pas de stratégie GAM Intune. Remarque : Les applications ne peuvent pas être envoyées au Store avec ce paramètre défini sur YES | Facultatif.
MultiIdentity | Booléen| Spécifie si l’application prend ou non en charge plusieurs identités | Facultatif.
SplashIconFile <br>SplashIconFile~ipad | Chaîne  | Spécifie le fichier d’icône de démarrage Intune. Consultez la section « Fichiers image au démarrage » ici pour plus d’informations. | Facultatif.
SplashDuration | Nombre | Durée minimale en secondes d’affichage de l’écran de démarrage Intune au lancement de l’application. La valeur par défaut est 1,5. | Facultatif.
BackgroundColor| Chaîne| Spécifie la couleur d’arrière-plan pour l’écran de démarrage et pour l’écran où entrer le code confidentiel. Accepte une chaîne hexadécimale RVB au format « #XXXXXX », où « X » peut être 0-9 ou A-F. Le signe dièse peut être omis.   | Facultatif, sa valeur par défaut est le gris clair.
ForegroundColor| Chaîne| Spécifie la couleur de premier plan pour l’écran de démarrage et pour l’écran où entrer le code confidentiel, comme la couleur du texte. Accepte une chaîne hexadécimale RVB au format « #XXXXXX », où « X » peut être 0-9 ou A-F. Le signe dièse peut être omis.  | Facultatif, sa valeur par défaut est le noir.
AccentColor | Chaîne| Spécifie la couleur d’accentuation de l’écran où entrer le code confidentiel, comme la couleur de texte des boutons et la couleur de surbrillance des zones.  Accepte une chaîne hexadécimale RVB au format « #XXXXXX », où « X » peut être 0-9 ou A-F. Le signe dièse peut être omis.| Facultatif, sa valeur par défaut est le bleu.
MAMTelemetryDisabled| Booléen| Spécifie si le SDK ne renvoie pas de données de télémétrie à son serveur principal| Facultatif.
MAMTelemetryUsePPE | Booléen | Spécifie si le SDK envoie des données au serveur principal de l’environnement de préproduction (PPE). Utilisez ceci quand vous testez vos applications avec une stratégie Intune pour que les données de télémétrie de test ne se mélangent pas avec les données du client. | Facultatif.

## Télémétrie 

Par défaut, le SDK d’application Intune pour iOS enregistre des données de télémétrie sur les événements d’utilisation, qui sont envoyées à Microsoft Intune. Des données sont journalisées pour les événements d’utilisation suivants : 

1. **Lancement d’applications** : pour aider Microsoft Intune à en savoir plus sur l’utilisation des applications compatibles GAL par type de gestion (GAM avec la gestion des applications mobiles, GAM sans inscription auprès de la gestion des applications mobiles, etc.)

2. **Appel d’API EnrollApplication** : pour aider Microsoft Intune à en savoir plus sur les taux de réussite et différentes autres mesures de performances des appels à `enrollApplication` du côté client.

**Remarque** : Si vous choisissez de ne pas envoyer les données de télémétrie du SDK d’application Intune à Microsoft Intune depuis votre application mobile, vous devez désactiver la capture de la télémétrie du SDK en définissant la propriété `MAMTelemetryDisabled`sur « YES » dans le dictionnaire IntuneMAMSettings.


## Génération du SDK dans votre extension (facultatif) 

Lors de la génération d’extensions, suivez les mêmes instructions pour générer votre application mobile que celles indiquées dans la section « Génération du SDK dans votre application mobile ». Mettez aussi à jour le fichier info.plist de chaque extension en ajoutant une clé `ContainingAppBundleId`dans le dictionnaire IntuneMAMSettings avec la valeur de l’id d’offre groupée de l’application conteneur.

## Génération du SDK dans votre infrastructure (facultatif)

Avec les dernières mises à jour apportées au SDK d’application Intune, vous n’avez pas à compiler votre application mobile avec des indicateurs de l’éditeur de liens spécifiques si votre application mobile contient des infrastructures d’applications incorporées. 

## Fichiers image au démarrage (facultatif)

Quand une application compatible avec la gestion des applications mobiles est activement gérée par Microsoft Intune, le SDK d’application Intune affiche un écran de démarrage au lancement des applications pour indiquer à l’utilisateur que l’application est gérée. Vous pouvez éventuellement ajouter des fichiers image à afficher sur la page de démarrage « Géré par votre entreprise ». Pour les images, respectez les instructions suivantes :

* Ajoutez les noms de fichiers sous le dictionnaire IntuneMAMSettings dans le fichier Info.plist de l’application avec les noms de clé `SplashIconFile` et `SplashIconFile~ipad`. 

* Configuration requise et taille de l’image :

    * 180 x 180 pour iPhone 6s Plus et iPhone 6 Plus, 120 x 120 pour les autres modèles iPhone et 152 x 152 pour iPad. 
    
    * Supprimez l’extension .png des noms de fichiers. 
    
    * Utilisez l’option de l’éditeur de liens `@2x` pour les versions de mise à l’échelle 2x et le suffixe `@3x` pour les versions de mise à l’échelle 3x des fichiers image. Si les images ne sont pas à la bonne taille, elles sont ajustées. Si les valeurs SplashIconFile ne sont pas spécifiées, le SDK d’application Intune sélectionne l’une des icônes de l’application (60 x 60 pour tous les iPhone, 76 x 76 pour iPad).

**Remarque**: cet écran est déclenché au lancement, mais il peut être désactivé définitivement par l’utilisateur.



#Activation de la multi-identité (facultatif)

Par défaut, le SDK applique une stratégie à l’application comme un tout. La multi-identité est une fonctionnalité GAM qui peut être activée pour permettre la stratégie d’être appliquée à un niveau par identité.  Ceci nécessite davantage de participation de l’application que d’autres fonctionnalités GAM. 

L’application doit informer le SDK d’application quand elle va changer l’identité active. Le SDK notifie aussi l’application quand un changement d’identité est nécessaire. Actuellement, une seule identité gérée est prise en charge. Une fois que l’utilisateur inscrit l’appareil ou l’application, le SDK utilise cette identité et la considère comme l’identité gérée principale. Les autres utilisateurs de l’application sont considérés comme non gérés avec des paramètres de stratégie non limités. 

Notez qu’une identité est simplement définie sous la forme d’une chaîne. Les identités ne respectent pas la casse et les demandes d’une identité au SDK peuvent ne pas retourner la même casse que celle qui a été initialement utilisée lors de la définition de l’identité.


##Présentation des identités 
  
Une identité est simplement le nom d’utilisateur d’un compte (par exemple, utilisateur@contoso.com). Les développeurs peuvent définir l’identité de l’application sur les différents niveaux suivants : 

* **Identité du processus**: l’identité du processus définit l’identité au niveau du processus et est principalement utilisée pour les applications avec une seule identité. Cette identité affecte toutes les opérations, les fichiers et l’interface utilisateur.
* **Identité de l’interface utilisateur** : détermine les stratégies qui sont appliquées aux opérations de l’interface utilisateur sur le thread principal, comme couper/copier/coller, un code confidentiel, l’authentification, le partage de données, etc. L’identité de l’interface utilisateur n’affecte pas les opérations de fichier (chiffrement, sauvegarde, etc.).
* **Identité du thread** : l’identité du thread a une incidence sur les stratégies qui sont appliquées sur le thread actif. Ceci affecte toutes les opérations, les fichiers et l’interface utilisateur.

L’application a la responsabilité de définir l’identité de façon appropriée selon que l’utilisateur ou non est géré.

À tout moment, chaque thread a une identité effective pour les opérations de l’interface utilisateur et les opérations de fichiers. Il s’agit de l’identité utilisée pour déterminer quelles stratégies doivent être appliquées, le cas échéant. Si l’identité est « aucune identité » ou si l’utilisateur n’est pas géré, aucune stratégie n’est appliquée. 
 
 

##Files d’attente de threads
 
Les applications distribuent souvent des tâches synchrones et asynchrones à des files d’attente de threads. Le SDK intercepte les appels au GCD (Grand Central Dispatch) et associe l’identité du thread actif aux tâches distribués. Quand les tâches sont exécutées, le SDK change temporairement l’identité du thread avec l’identité associée à la tâche, exécute les tâches, puis restaure l’identité du thread d’origine. Comme `NSOperationQueue` est basé sur GCD, les `NSOperations` s’exécute sur l’identité du thread au moment où elles sont ajoutées à `NSOperationQueue`. Les `NSOperations` ou les fonctions distribuées en utilisant GCD directement ont également la capacité de changer l’identité du thread actif lors de leur exécution. Cette identité remplace l’identité héritée du thread de distribution. 

##Propriétaire des fichiers
 
Le SDK fait le suivi des identité du propriétaire des fichiers locaux et applique des stratégies en conséquence. Le propriétaire du fichier est établi quand le fichier est créé ou quand le fichier est ouvert en mode tronqué. Le propriétaire est défini sur l’identité de l’opération de fichier effective du thread exécutant l’opération. Les applications peuvent également définir explicitement l’identité du propriétaire du fichier en utilisant `IntuneMAMFilePolicyManager`. Les applications peuvent utiliser `IntuneMAMFilePolicyManager` pour récupérer le propriétaire du fichier et définir l’identité de l’interface utilisateur avant d’afficher le contenu du fichier.


##Fichiers de données partagés
 
Si l’application crée des fichiers qui contiennent des données provenant d’utilisateurs gérés et d’autres non gérés, elle est responsable du chiffrement des données de l’utilisateur géré. Les données peuvent être chiffrées à l’aide des API `protect` et `unprotect``IntuneMAMDataProtectionManager`. La méthode `protect` accepte une identité qui peut être un utilisateur géré ou non géré. Si l’utilisateur est géré, les données sont chiffrées. Si l’utilisateur est non géré, un en-tête est ajouté aux données de codage de l’identité, mais les données ne sont pas chiffrées.  La méthode `protectionInfo` peut être utilisée pour récupérer le propriétaire des données.

##Extensions de partage
 
Si l’application contient une extension de partage, le propriétaire de l’élément partagé peut être récupéré à l’aide de la méthode `protectionInfoForItemProvider` dans `IntuneMAMDataProtectionManager`. Si l’élément partagé est un fichier, le SDK gère la définition du propriétaire du fichier. Si l’élément partagé est constitué de données, l’application est responsable de la définition du propriétaire du fichier si ces données sont conservées dans un fichier, et elle est aussi responsable de l’appel de l’API `setUIPolicyIdentity` (décrite ci-dessous) avant d’afficher ces données dans l’interface utilisateur.
 
##Activation de la multi-identité
 
Par défaut, les applications sont considérées comme une seule identité et le kit de développement logiciel (SDK) attribue l’identité du processus à l’utilisateur inscrit. Pour activer la prise en charge de la multi-identité, le paramètre booléen `MultiIdentity` avec la valeur « YES » doit être ajouté au dictionnaire **IntuneMAMSettings** dans le fichier Info.plist de l’application. 

> [!NOTE]
> Quand la multi-identité est activée, l’identité du processus, celle de l’interface utilisateur et celles des threads ne sont pas définies. C’est à l’application de le faire.

 
##Changement d’identités
 
###Changement d’identité initié par l’application
Au lancement, les applications multi-identités sont considérées comme s’exécutant sous un compte inconnu, non géré. L’interface utilisateur avec lancement conditionnel ne s’exécute pas et aucune stratégie n’est appliquée à l’application. L’application est responsable de notifier le SDK chaque fois que l’identité doit être changée. En général, ceci se produit chaque fois que l’application est sur le point d’afficher des données pour un compte d’utilisateur spécifique.

C’est le cas par exemple quand l’utilisateur tente d’ouvrir un document, une boîte aux lettres ou un onglet dans un bloc-notes. L’application doit notifier le SDK avant que le fichier, la boîte aux lettres ou l’onglet soit réellement ouvert. Cette opération est effectuée via l’API `setUIPolicyIdentity` dans `IntuneMAMPolicyManager`. Cette API doit être appelée que l’utilisateur soit géré ou non. Si l’utilisateur est géré, le SDK effectue les vérifications du lancement conditionnel (détection de jailbreak, code confidentiel, authentification, etc.). Le résultat du changement d’identité est retourné à l’application de façon asynchrone via un gestionnaire d’achèvement. L’application doit postposer l’ouverture du document, de la boîte aux lettres, de l’onglet, etc. jusqu’à ce qu’un code de résultat indiquant la réussite soit retourné. Si le changement d’identité a échoué, l’application doit annuler l’opération. 

###Changement d’identité initié par le SDK
Il existe des cas où le SDK doit demander à l’application de passer à une identité spécifique. Les applications multi-identités doivent implémenter la méthode `identitySwitchRequired` dans `IntuneMAMPolicyDelegate` pour traiter cette demande. Quand elle est appelée, si l’application est en mesure de traiter la demande de passage à l’identité spécifiée, elle doit passer `IntuneMAMAddIdentityResultSuccess` au gestionnaire d’achèvement. Si elle n’est pas en mesure de gérer le changement d’identité, l’application doit passer `IntuneMAMAddIdentityResultFailed` au gestionnaire d’achèvement. L’application n’a pas besoin d’appeler `setUIPolicyIdentity` en réponse à cet appel. Si le SDK a besoin de l’application pour passer à un compte d’utilisateur non managé, une chaîne vide est passée dans l’appel de `identitySwitchRequired`. 
 
###réinitialisation sélective
Quand l’application fait l’objet d’une réinitialisation sélective, le SDK appelle la méthode `wipeDataForAccount` dans `IntuneMAMPolicyDelegate`. L’application a la responsabilité de supprimer le compte d’utilisateur spécifié et les données qui y sont associées. Le SDK est capable de supprimer tous les fichiers appartenant à l’utilisateur et le fait si l’application retourne « FALSE » pour l’appel de `wipeDataForAccount`. Notez que cette méthode est appelée depuis un thread d’arrière-plan et que l’application ne doit pas retourner tant que toutes les données de l’utilisateur n’ont pas été supprimées (à l’exception des fichiers si l’application retourne « FALSE »).

# Débogage du SDK des applications Intune dans Xcode

Avant de tester votre application compatible GAM avec Microsoft Intune, vous pouvez utiliser un fichier **Settings.bundle** dans Xcode. Ainsi, vous pouvez définir des stratégies de test sans requérir de connexion à Intune. Pour l’activer :

* Ajoutez un fichier Settings.bundle en cliquant avec le bouton droit sur le dossier de plus haut niveau dans votre projet. Sélectionnez « Ajouter -> Nouveau fichier » dans le menu. Sélectionnez le modèle « Groupe de paramètres » à ajouter sous « Ressources ».

* Sur les versions Debug uniquement, copiez le fichier MAMDebugSettings.plist dans Settings.bundle.

* Dans Root.plist (dans Settings.bundle), ajoutez une préférence avec "Type" = Child Pane et "FileName" = MAMDebugSettings.

* Dans **Paramètres -> Nom_de_votre_application**, activez « Activer les stratégies de test ».

* Lancez l’application (soit dans, soit en dehors de Xcode). 

* Dans **Paramètres -> Nom_de_votre_application -> Activer les stratégies de test**, activez une stratégie, par exemple « Code confidentiel ».

* Lancez l’application (soit dans, soit en dehors de Xcode). Vérifiez que PIN fonctionne comme prévu.

> [!NOTE]
> Vous pouvez maintenant utiliser **Paramètres -> nom_de_votre_application -> Activer les stratégies de test** pour activer et désactiver des paramètres.

# Pratiques recommandées pour iOS

Voici quelques pratiques recommandées dans le cadre du développement pour iOS :

Le système de fichiers iOS respecte la casse. Vérifiez que la casse est correcte dans les noms de fichiers comme `libIntuneMAM.a` et `IntuneMAMResources.bundle`.

Si Xcode a des difficultés à trouver `libIntuneMAM.a`, vous pouvez résoudre ce problème en ajoutant le chemin à cette bibliothèque dans les chemins de recherche de l’éditeur de liens.



##FAQ 

 **Tous les utilisateurs de mon application doivent-ils être inscrits auprès du service GAM ?**

Non.  En fait, seuls les comptes professionnels ou scolaires doivent être inscrits auprès du SDK d’application Intune.  Les applications doivent déterminer si un compte est utilisé dans un contexte professionnel ou scolaire.   
 
**Qu’en est-il des utilisateurs qui se sont déjà connectés à l’application ?  Doivent-ils être inscrits ?** 

Si l’application est responsable de l’inscription des utilisateurs une fois qu’ils sont authentifiés avec succès, elle est également responsable de l’inscription des comptes existants étaient présents avant que l’application ait des fonctionnalités GAM sans la gestion des applications mobiles.   


Pour cela, l’application doit utiliser la méthode `registeredAccounts:`.  Cette méthode retourne un NSDictionary contenant tous les comptes inscrits dans le service GAM Intune.  Si des comptes existants dans l’application ne sont pas présents dans la liste, l’application doit inscrire ces comptes via `registerAndEnrollAccount:`. 


 

**À quelle fréquence le SDK réessaye-t-il les inscriptions ?** 

Le SDK réessaye automatiquement toutes les inscriptions ayant échoué selon un intervalle de 24 heures.  Le SDK procède ainsi pour garantir que si l’organisation d’un utilisateur a activé GAM après que l’utilisateur s’est connecté à l’application, cet utilisateur est inscrit et reçoit les stratégies avec succès. 

Le SDK arrête les nouvelles tentatives quand il détecte qu’un utilisateur a inscrit l’application avec succès.  La raison en est qu’un seul utilisateur peut inscrire une application à un moment donné. Si l’utilisateur est désinscrit, les nouvelles tentatives reprennent selon le même intervalle de 24 heures. 


 
**Pourquoi l’utilisateur doit-il être désinscrit ?** 

Le SDK effectue périodiquement les actions suivantes en arrière-plan :

 - Si l’application n’est pas encore inscrite, il tente d’inscrire tous les comptes inscrits toutes les 24 heures. 
 - Si l’application est inscrite, le SDK recherche les mises à jour des stratégies GAM toutes les 8 heures. 

En désinscrivant un utilisateur, il notifie au SDK que l’utilisateur n’utilise plus l’application et peut arrêter les événements périodiques ci-dessus pour ce compte d’utilisateur.  Elle déclenche également une désinscription de l’application et une réinitialisation sélective si nécessaire. 

**Dois-je définir l’indicateur doWipe sur true dans la méthode de désinscription ?** Cette méthode doit être appelée avant que l’utilisateur soit déconnecté de l’application.  Si, dans le cadre de la déconnexion, les données de l’utilisateur sont supprimées de l’application, `doWipe` peut être défini sur false.  Cependant, si l’application ne supprime pas effectivement les données de l’utilisateur, cet indicateur doit être défini sur true pour que le SDK puisse supprimer manuellement les données elles-mêmes. 

**Existe-t-il d’autres façons de désinscrire une application ?** Oui, l’administrateur informatique peut envoyer une commande de réinitialisation sélective à l’application, qui fait que l’utilisateur est désinscrit et que ses données sont effacées.  Le SDK gère automatiquement ce scénario et envoie une notification via la méthode déléguée de désinscription. 

#Soumission de votre application à l’App Store
Les générations de la bibliothèque statique et de l’infrastructure du SDK d’application Intune sont des binaires universels, ce qui signifie qu’ils contiennent le code pour toutes les architectures d’appareils et de simulateurs. Apple rejette les applications soumises à l’App Store si elles contiennent du code de simulateur. Lors de la compilation avec la bibliothèque statique pour les builds destinées seulement aux appareils, l’éditeur de liens supprime automatiquement le code du simulateur.

Si vous utilisez la **build d’infrastructure**, vous devez éliminer manuellement les architectures de simulateur de l’infrastructure universelle avant de soumettre votre application à l’App Store. Les instructions ci-dessous vous aident à le faire :

1. Assurez-vous que `IntuneMAM.framework` est sur votre poste de travail.
2. Exécutez les commandes suivantes :
    
    ```
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```
    La première commande élimine les architectures de simulateur des fichiers dylib de l’infrastructure.
    ```
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM 
    ```
    La deuxième commande recopie les fichiers dylib pour appareils uniquement dans le répertoire de l’infrastructure.



<!--HONumber=Oct16_HO3-->


