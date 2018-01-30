---
title: "Plug-in Cordova du SDK d’application Microsoft Intune"
description: 
keywords: sdk, Cordova, intune
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 00c1c805dbbf661bdcd4ad6b153fee8b2bbba9ee
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Plug-in Cordova du SDK d’application Microsoft Intune

> [!NOTE]
> Vous pouvez d’abord lire l’article [Bien démarrer avec le SDK d’application Intune](app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.

## <a name="overview"></a>Vue d’ensemble

[Plug-in Cordova du SDK d’application Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) dans les applications iOS et Android reposant sur Cordova. Le plug-in permet aux développeurs d’intégrer des fonctionnalités de protection des données et des applications Intune à leur application Cordova.

Comme vous pourrez le constater, il est possible d’activer des fonctionnalités du SDK sans modifier le comportement de votre application. Une fois que vous avez intégré le plug-in dans votre application iOS ou Android, l’administrateur Microsoft Intune sera en mesure de déployer la stratégie de protection des applications Intune, qui se compose d’un ensemble de fonctionnalités de protection des données. Le plug-in est conçu afin que la plupart des étapes s’effectuent automatiquement au cours du processus de génération Cordova. Ainsi, vous devriez être en mesure d’activer rapidement votre application pour la protection des applications Intune. Pour démarrer, suivez les étapes ci-dessous, selon votre plateforme cible.

## <a name="supported-platforms"></a>Plateformes prises en charge

* Le plug-in fonctionne sous les systèmes d’exploitation Windows, Mac et Linux
* Le plug-in fonctionne pour les applications Android avec `minSdkVersion` >= 14 et `targetSdkVersion` <= 24
* Le plug-in fonctionne pour les applications iOS ciblées pour iOS 9.0 et les versions ultérieures.

## <a name="intune-mobile-application-management-scenarios"></a>Scénarios de gestion des applications mobiles Intune

* Appareils inscrits auprès de MDM Intune
* Appareils inscrits auprès d’une gestion de la mobilité d’entreprise tierce
* Appareils non gérés (non inscrits auprès de MDM)

Les applications Cordova développées avec le plug-in Cordova du SDK d’application Intune peuvent maintenant recevoir des stratégies de protection des applications Intune sur des appareils inscrits et non inscrits à la gestion des appareils mobiles (MDM) Intune.

## <a name="prerequisites"></a>Conditions préalables

### <a name="android"></a>Android

* La dernière application Portail d’entreprise Microsoft Intune doit toujours être installée sur l’appareil.
* Java 7 (minimum) doit se trouver dans le chemin d’accès où vous exécuterez la génération Cordova lors de l’utilisation du plug-in.

### <a name="ios"></a>iOS

* La dernière application Portail d’entreprise Microsoft Intune doit être installée sur l’appareil pour les fonctionnalités de gestion des appareils mobiles (MDM). Elle n’est *pas* requise pour la stratégie de protection des applications Intune sans les fonctionnalités d’inscription des appareils.

### <a name="both-platforms"></a>Les deux plateformes

* La version 0.8.0+ du [plug-in Azure Active Directory Authentication Libraries (ADAL) pour Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) est obligatoire.

> [!NOTE]
> En raison d’un bogue Apache Cordova décrit [ici](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), les applications qui disposent déjà de la dépendance du plug-in ne mettent pas automatiquement à niveau le plug-in avec la version demandée.



## <a name="quick-start"></a>Démarrage rapide

1. Mettez à jour votre version ADAL :

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. Ajoutez le plug-in Cordova du SDK d’application Intune :

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>Générer le plug-in dans votre application iOS

Vous devez suivre quelques étapes pour activer la stratégie de protection des applications Intune dans votre application. Par souci pratique, ces étapes s’effectuent automatiquement pendant le processus de génération Cordova comme hook de prébuild. Ainsi, les étapes automatisées modifient vos fichiers `*.pbxproj`, `*-Info.plist` et `*.entitlements` associés à une configuration de projet. Si votre projet ne contient pas de fichier de droits, le plug-in en crée automatiquement un.

Ce programme d’installation prend en charge une seule cible et effectue la configuration sur la première cible trouvée s’il en existe plusieurs. Si le processus échoue, vérifiez les points suivants :

1. Le projet Xcode de votre application est `[name].xcodeproj` où `[name]` correspond à la valeur définie dans `config.xml`.
2. Votre projet utilise la [structure de répertoires d’application Cordova standard](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="build-the-plugin-into-your-android-app"></a>Générer le plug-in dans votre application Android

1. Importez ce plug-in avec les derniers outils Cordova. Le plug-in est automatiquement appelé dans le cadre d’une étape `after_compile`.

2. Le plug-in crée une version Intune d’un APK généré (API Android 14+) à la fin du processus de génération. La sortie de génération contient un `[Project]-intunewrapped-[Build_Configuration].apk` (par exemple, `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> Le plug-in prend uniquement en charge les builds Gradle.

En raison d’un bogue Cordova répertorié [ici](https://issues.apache.org/jira/browse/CB-9434) qui fait que certains hooks Cordova sont ignorés sur `cordova run`, vous devez procéder comme suit pour exécuter l’application encapsulée à partir de la ligne de commande :

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Signer votre application Android

Le plug-in reconnaît automatiquement les informations sur la signature que vous avez fournies à Cordova aux emplacements suivants :

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Consultez les [informations sur la signature Cordova Gradle](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) pour plus d’informations sur le format attendu.

Actuellement, nous ne prenons pas en charge la possibilité de fournir des informations sur la signature dans `build.json` ou les emplacements arbitraires fournis via les paramètres pour la génération de Cordova.

## <a name="debugging-from-visual-studio"></a>Débogage à partir de Visual Studio

Après avoir lancé l’application pour la première fois, une boîte de dialogue vous informant que l’application est gérée par Intune doit apparaître. Appuyez sur « Ne plus afficher » et cliquez sur le bouton de débogage/exécution une nouvelle fois à partir de Visual Studio pour atteindre les points d’arrêt.

## <a name="known-limitations"></a>Limitations connues

### <a name="android"></a>Android

* La prise en charge MultiDex est incomplète.
* L’application doit disposer de `minSdkVersion` égal à 14 et de `targetSdkVersion` égal à 24, ou valeurs inférieures. Nous ne prenons actuellement pas en charge les applications ciblant l’API 25
* Nous ne pouvons pas signer à nouveau des applications qui ont été signées avec le schéma de signature V2. Lorsque des applications avec le schéma de signature V2 sont encapsulées par le plug-in, la sortie encapsulée .apk ne sera pas signée.
*
  * Vous pouvez désactiver la signature V2 de Cordova par défaut en ajoutant le code suivant à votre fichier `build-extras.gradle` :

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Chaque fois que vous modifiez la liste des UTI sous le nœud **CFBundleDocumentTypes** du fichier **Info.plist**, vous devez effacer les UTI Intune dans la section des UTI importés du même fichier plist (nœud **UTImportedTypeDeclarations**) avant de lancer une nouvelle génération. Tous les UTI Intune commencent par le préfixe `com.microsoft.intune.mam`.

* Pour supprimer le plug-in Cordova du SDK d’application Intune de votre projet Cordova, vous devez également supprimer la plateforme iOS et la rajouter pour annuler certaines configurations Intune dans les fichiers .xcodeproj et .plist.
