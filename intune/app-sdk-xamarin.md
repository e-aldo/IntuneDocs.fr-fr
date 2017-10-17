---
title: "Composant Xamarin du SDK d’application Microsoft Intune"
description: 
keywords: sdk, Xamarin, intune
author: mattbriggs
manager: angrobe
ms.author: mabriggs
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8ab9807d22aa1a5c232b595df2bd999c0c178b16
ms.sourcegitcommit: f3b8fb8c47fd2c9941ebbe2c047b7d0a093e5a83
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/11/2017
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Composant Xamarin du SDK d’application Microsoft Intune

> [!NOTE]
> Vous pouvez d’abord lire l’article [Bien démarrer avec le SDK d’application Intune](app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.



## <a name="overview"></a>Vue d’ensemble
Le [composant Xamarin du SDK d’application Intune](https://components.xamarin.com/view/microsoft.intune.mam) active la [stratégie de protection des applications Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) dans les applications Android et iOS développées avec Xamarin. Le composant permet aux développeurs de générer facilement des fonctionnalités de protection des données dans leur application Xamarin.

Le composant Xamarin du SDK d’application Microsoft Intune vous permet d’incorporer des stratégies de protection des applications Intune (également appelées stratégies APP ou GAM) dans vos applications développées avec Xamarin. Une application prenant en charge la gestion GAM est une application intégrée au kit SDK d’application Intune. Les administrateurs informatiques peuvent déployer des stratégies de protection des applications sur votre application mobile quand celle-ci est activement gérée par Intune.

## <a name="whats-supported"></a>Ce qui est pris en charge

### <a name="developer-machines"></a>Ordinateurs de développement
* macOS


### <a name="mobile-app-platforms"></a>Plateformes d’applications mobiles
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scénarios de gestion des applications mobiles Intune

* Appareils inscrits auprès de MDM Intune
* Appareils inscrits auprès d’une gestion de la mobilité d’entreprise tierce
* Appareils non gérés (non inscrits auprès de MDM)

Les applications Xamarin développées avec le composant Xamarin du SDK d’application Intune peuvent maintenant recevoir des stratégies de protection des applications Intune sur des appareils inscrits et non inscrits à la gestion des appareils mobiles (GAM) Intune.

## <a name="prerequisites"></a>Prérequis

* **[Android uniquement]** La dernière application Portail d’entreprise Microsoft Intune doit être installée sur l’appareil.

## <a name="get-started"></a>Prise en main

1.  Téléchargez **Xamarin-component.exe** [ici](https://components.xamarin.com/submit/xpkg) et extrayez-le.

2. Lisez les [termes du contrat de licence](https://components.xamarin.com/license/microsoft.intune.mam) du composant Xamarin de la GAM Microsoft Intune.

3.  Téléchargez le dossier Composant Xamarin du SDK d’application Intune depuis [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) ou [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) et extrayez-le. Les deux fichiers téléchargés aux étapes 1 et 3 doivent être dans le même niveau de répertoire.

4.  Dans la ligne de commande, exécutez `Xamarin.Component.exe install <.xam> file` comme administrateur.

5.  Dans Visual Studio, cliquez avec le bouton droit sur **composants** dans votre projet Xamarin créé précédemment.

6.  Sélectionnez **Modifier les composants** et ajoutez le composant SDK d’application Intune que vous avez téléchargé localement sur votre ordinateur.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Activation des stratégies de protection des applications Intune dans votre application mobile iOS
1.  Pour initialiser le SDK d’application Intune, vous devez appeler une API dans la classe `AppDelegate.cs`. Exemple :

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Maintenant que le composant est ajouté et initialisé, vous pouvez suivre les étapes générales requises pour intégrer le SDK d’application à une application mobile iOS. Vous trouverez la documentation complète pour l’activation des applications natives iOS dans le [Guide du SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md).
3. **Important** : Il existe plusieurs modifications propres aux applications iOS basées sur Xamarin. Par exemple, quand vous activez des groupes de trousseaux, vous devez ajouter le code suivant pour inclure l’exemple d’application Xamarin que nous avons inclus dans le composant. Voici un exemple des groupes requis dans vos groupes de trousseaux d’accès :

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Vous avez terminé les étapes nécessaires pour générer le composant dans votre application iOS basée sur Xamarin. Si vous utilisez Xcode pour générer votre projet, vous pouvez utiliser `Intune App SDK Settings.bundle`. Ainsi, vous pouvez activer et désactiver les paramètres de stratégie Intune quand vous générez votre projet à des fins de test et de débogage. Pour tirer parti de cet ensemble d’applications, suivez les étapes décrites dans le [Guide du SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md) et lisez la section sur le [débogage dans Xcode](app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Activation de stratégies de protection des applications dans votre application mobile Android
Pour les applications Android basées sur Xamarin qui n’utilisent pas un framework d’interface utilisateur, vous devez lire et suivre le [Guide du kit SDK d’application Intune pour les développeurs Android](app-sdk-android.md). Pour votre application Android basée sur Xamarin, vous devez remplacer la classe, les méthodes et les activités par leurs équivalents GAM conformément au [tableau](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) inclus dans le guide. Si votre application ne définit pas de classe `android.app.Application`, vous devez en créer une et vérifier que vous héritez de `MAMApplication`.

Pour les formulaires Xamarin et d’autres framework d’interface utilisateur, nous avons fourni un outil appelé `MAM.Remapper`. Cet outil effectue le remplacement de la classe pour vous. Toutefois, vous devez effectuer les étapes suivantes :

1.  Ajoutez une référence au package NuGet `Microsoft.Intune.MAM.Remapper.Tasks` version 0.1.0.0 ou supérieure.

2.  Ajoutez la ligne suivante à votre csproj Android :
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  Affectez à l’action de génération du fichier `remapping-config.json` la valeur **RemappingConfigFile**. Le fichier `remapping-config.json` inclus fonctionne uniquement avec Xamarin.Forms. Pour les autres frameworks d’interface utilisateur, consultez le fichier Lisez-moi inclus dans le package NuGet Remapper.

## <a name="next-steps"></a>Étapes suivantes

Vous avez terminé les étapes élémentaires de la génération du composant dans votre application. Maintenant, vous pouvez suivre les étapes incluses dans l’exemple d’application Android. Nous avons fourni deux exemples, un pour Xamarin.Forms et un autre pour Android.