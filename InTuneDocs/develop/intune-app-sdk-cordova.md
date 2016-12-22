---
title: "Plug-in Cordova du SDK d’application Microsoft Intune | Documentation Microsoft"
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: 9ef09f43e6c878af689a500457bab578149de499


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Plug-in Cordova du SDK d’application Microsoft Intune

> [!NOTE]
> Vous pouvez d’abord lire l’article [Bien démarrer avec le SDK d’application Intune](intune-app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.


## <a name="overview"></a>Vue d’ensemble

Le [plug-in Cordova du SDK d’application Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) permet d’activer les [fonctionnalités de gestion des applications mobiles Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) dans les applications Android et iOS développées avec Cordova. Le plug-in permet aux développeurs d’intégrer des fonctionnalités de protection des données et des applications Intune à leur application Cordova.

Comme vous pourrez le constater, il est possible d’activer des fonctionnalités du SDK sans modifier le comportement de votre application. Une fois que vous avez créé le plug-in dans votre application mobile iOS ou Android, l’administrateur informatique peut déployer la stratégie par le biais de la gestion des applications mobiles (GAM) Microsoft Intune en prenant en charge un ensemble de fonctionnalités de protection des données. Nous avons conçu le plug-in afin que la plupart des étapes s’effectuent automatiquement au cours du processus de génération Cordova. Ainsi, vous devriez être en mesure d’activer rapidement votre application pour la gestion. Pour démarrer, suivez les étapes ci-dessous, selon votre plateforme cible.




## <a name="whats-supported"></a>Ce qui est pris en charge

### <a name="developer-machines"></a>Ordinateurs de développement
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Plateformes d’applications mobiles
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Scénarios de gestion des applications mobiles Intune

* Appareils inscrits auprès de MDM Intune
* Appareils inscrits auprès d’une gestion de la mobilité d’entreprise tierce
* Appareils non gérés (non inscrits auprès de MDM)

Les applications Cordova développées avec le plug-in Cordova du SDK d’application Intune peuvent maintenant recevoir des stratégies de gestion des applications mobiles (GAM) sur des appareils inscrits et non inscrits à la gestion des appareils mobiles (MDM) Intune.



## <a name="prerequisites"></a>Conditions préalables

### <a name="technical-prerequisites"></a>Prérequis techniques

* **[Android uniquement]** La dernière application Portail d’entreprise Microsoft Intune doit toujours être installée sur l’appareil.


* La version 0.8.0+ du [plug-in Azure Active Directory Authentication Libraries (ADAL) pour Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) est obligatoire.
  * **Important :** En raison d’un bogue Apache Cordova décrit [ici](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), les applications qui disposent déjà de la dépendance du plug-in ne mettent pas automatiquement à niveau le plug-in avec la version demandée.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Avant d’installer et d’utiliser le plug-in Cordova du SDK d’application Microsoft Intune, vous **devez** effectuer ce qui suit :

* Consultez les [termes du contrat de licence du plug-in Cordova du SDL d’application Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf).

* Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant le plug-in Cordova du SDK d’application Intune, vous acceptez les termes de ce contrat de licence.  Si vous ne les acceptez pas, n'utilisez pas le logiciel.


## <a name="quick-start"></a>Démarrage rapide

1. Mettez à jour votre version ADAL :

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. Ajoutez le plug-in Cordova du SDK d’application Intune :

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>Guide pratique pour générer le plug-in dans votre application iOS

Vous devez suivre quelques étapes pour activer la gestion des applications mobiles (GAM) d’Intune dans votre application. Par souci pratique, ces étapes s’effectuent automatiquement pendant le processus de génération Cordova comme hook de prébuild. Ainsi, les étapes automatisées modifient vos fichiers `*.pbxproj`, `*-Info.plist` et `*.entitlements` associés à une configuration de projet. Si votre projet ne contient pas de fichier de droits, le plug-in en crée automatiquement un.

Ce programme d’installation prend en charge une seule cible et effectue la configuration sur la première cible trouvée s’il en existe plusieurs. Si le processus échoue, vérifiez les points suivants :

1. Le projet Xcode de votre application est `[name].xcodeproj` où `[name]` correspond à la valeur définie dans `config.xml`.
2. Votre projet utilise la [structure de répertoires d’application Cordova standard](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).

## <a name="how-to-build-the-plugin-into-your-android-app"></a>Guide pratique pour générer le plug-in dans votre application Android

1. Importez ce plug-in avec les derniers outils Cordova. Le plug-in est automatiquement appelé dans le cadre d’une étape `after_compile`.

2. Le plug-in crée une version GAM d’un APK généré (API Android 14+) à la fin du processus de génération. La sortie de génération contient un `[Project]-intunewrapped-[Build_Configuration].apk` (par exemple, `helloWorld-intunewrapped-debug.apk`).

Le plug-in prend uniquement en charge les builds Gradle.

En raison d’un bogue Cordova répertorié [ici](https://issues.apache.org/jira/browse/CB-9434) qui fait que certains hooks Cordova sont ignorés sur `cordova run`, vous devez procéder comme suit pour exécuter l’application encapsulée à partir de la ligne de commande :

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Signature de votre application Android
Pour ajouter des informations de signature à l’APK encapsulé, modifiez `build.json` comme vous le feriez normalement pour ajouter des informations de signature. Exemple :
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Build à des fins de test Android uniquement

1. Ajoutez `android:testOnly="true"` au nœud d’application du fichier `AndroidManifest.xml`.


2. **Cordova 6.x.x :** dans `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js`, remplacez la ligne 60

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    par
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

L’effet consiste à exécuter `adb install` avec l’indicateur « t » car il n’est pas possible d’installer des applications `testOnly` sans lui.

### <a name="debugging-from-visual-studio"></a>Débogage à partir de Visual Studio
Après avoir lancé l’application pour la première fois, une boîte de dialogue vous informant que l’application est gérée par Intune doit apparaître. Appuyez sur « Ne plus afficher » et cliquez sur le bouton de débogage/exécution une nouvelle fois à partir de Visual Studio pour atteindre les points d’arrêt.

## <a name="known-limitations"></a>Limitations connues
### <a name="android"></a>Android
* La prise en charge MultiDex est incomplète.
* L’application doit cibler Android 4.0 (API Android 14) ou ultérieur.

### <a name="ios"></a>iOS
* Chaque fois que vous modifiez la liste des UTI sous le nœud **CFBundleDocumentTypes** du fichier **Info.plist**, vous devez effacer les UTI Intune dans la section des UTI importés du même fichier plist (nœud **UTImportedTypeDeclarations**) avant de lancer une nouvelle génération. Tous les UTI Intune commencent par le préfixe `com.microsoft.intune.mam`.

* Pour supprimer le plug-in Intune de votre projet Cordova, vous devez également supprimer la plateforme iOS et la rajouter pour annuler certaines configurations Intune dans les fichiers .xcodeproj et .plist.



<!--HONumber=Dec16_HO2-->


