---
title: "Composant Xamarin du SDK d’application Microsoft Intune"
description: 
keywords: sdk, Xamarin, intune
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c5645e337e34c6310c82a76d537fe6539e04e71e
ms.sourcegitcommit: 5ecb0d6625e6972cc5ccdca7538f41f4aa8da46a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Composant Xamarin du SDK d’application Microsoft Intune

> [!NOTE]
> Vous pouvez d’abord lire l’article [Bien démarrer avec le SDK d’application Intune](app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.



## <a name="overview"></a>Vue d’ensemble
Le [composant Xamarin du SDK d’application Intune](https://components.xamarin.com/view/microsoft.intune.mam) active la [stratégie de protection des applications Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) dans les applications Android et iOS développées avec Xamarin. Le composant permet aux développeurs de générer facilement des fonctionnalités de protection des données dans leur application Xamarin.

> [!NOTE]
> La prise en charge du SDK Intune pour Xamarin est disponible en préversion. 

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
1.  Suivez les étapes générales requises pour l’intégration du Kit SDK d’application Intune dans une app mobile iOS. Vous pouvez commencer à l’étape 3 des instructions de l’intégration dans le [Guide du kit SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app).
    **Important** : l’activation du partage de trousseau pour une application est légèrement différente dans Visual Studio par rapport à Xcode. Ouvrez le fichier plist de droits de l’application et vérifiez que l’option « Activer le trousseau » est activée et que les groupes de partage de trousseau appropriés sont ajoutés dans cette section. Vérifiez ensuite que le fichier plist des droits est spécifié dans le champ « Droits personnalisés » des options « Signature du bundle iOS » du projet pour toutes les combinaisons de configuration/plate-forme appropriées.
2.  Une fois que composant ajouté et l’application correctement configurée, votre application peut commencer à utiliser les API du Kit SDK d’Intune. Pour cela, vous devez inclure l’espace de noms suivant :

      ```csharp
      using Microsoft.Intune.MAM;
      ```
3.    Pour commencer à recevoir des stratégies de protection d’application, votre application doit s’inscrire auprès du service GAM d’Intune. Si votre application utilise déjà la bibliothèque d’authentification Azure Active Directory (ADAL) pour authentifier les utilisateurs, elle doit fournir l’UPN de l’utilisateur à la méthode de registerAndEnrollAccount de IntuneMAMEnrollmentManager une fois l’authentification correctement effectuée :
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Important** : veillez à remplacer les paramètres ADAL par défaut du SDK de l’application Intune par ceux de votre application. Vous pouvez le faire via le dictionnaire IntuneMAMSettings dans le fichier Info.plist de l’application, comme indiqué dans le [Guide du kit SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), ou vous pouvez utiliser les propriétés de substitution AAD de l’instance IntuneMAMPolicyManager. L’approche Info.plist est recommandée pour les applications dont les paramètres ADAL sont statiques, tandis que les propriétés de substitution sont recommandées pour les applications qui déterminent ces valeurs lors de l’exécution. 
      
      Si votre application n’utilise pas ADAL et que vous souhaitez utiliser le SDK Intune pour gérer l’authentification, votre application doit appeler la méthode loginAndEnrollAccount de IntuneMAMEnrollmentManager :
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

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
