---
title: Liaisons Xamarin du kit SDK d’application Microsoft Intune
description: Les liaisons Xamarin du kit SDK d’application Intune activent la stratégie de protection des applications Intune dans les applications iOS et Android générées avec Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9f9cc117925f59c9fb7c55d0ff10aedf09d26f93
ms.sourcegitcommit: b727b6bd6f138c5def7ac7bf1658068db30a0ec3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Liaisons Xamarin du kit SDK d’application Microsoft Intune

> [!NOTE]
> Vous pouvez d’abord lire l’article [Bien démarrer avec le SDK d’application Intune](app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.

## <a name="overview"></a>Vue d’ensemble
Les [liaisons Xamarin du kit SDK d’application Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) activent la [stratégie de protection des applications Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) dans les applications iOS et Android générées avec Xamarin. Les liaisons permettent aux développeurs de générer facilement des fonctionnalités de protection des applications Intune dans leur application Xamarin.

Les liaisons Xamarin du kit SDK d’application Microsoft Intune vous permettent d’incorporer des stratégies de protection des applications Intune (également appelées stratégies APP ou MAM) dans vos applications développées avec Xamarin. Une application prenant en charge la gestion MAM est une application intégrée au kit SDK d’application Intune. Les administrateurs informatiques peuvent déployer des stratégies de protection des applications sur votre application mobile quand celle-ci est activement gérée par Intune.

## <a name="whats-supported"></a>Ce qui est pris en charge

### <a name="developer-machines"></a>Ordinateurs de développement
* Windows
* macOS


### <a name="mobile-app-platforms"></a>Plateformes d’applications mobiles
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Scénarios de gestion des applications mobiles Intune

* Service APP-WE Intune (sans inscription d’appareils)
* Appareils inscrits auprès de MDM Intune
* Appareils inscrits auprès d’une gestion de la mobilité d’entreprise tierce

Les applications Xamarin générées avec les liaisons Xamarin du kit SDK d’application Intune peuvent désormais recevoir des stratégies de protection des applications Intune sur des appareils inscrits et non inscrits auprès de la solution MDM (gestion des appareils mobiles) Intune.

## <a name="prerequisites"></a>Prérequis

Consultez les [termes du contrat de licence](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20Xamarin%20Component.pdf). Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant les liaisons Xamarin du kit SDK d’application Intune, vous acceptez les termes du contrat de licence. Si vous ne les acceptez pas, n'utilisez pas le logiciel.

## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Activation des stratégies de protection des applications Intune dans votre application mobile iOS
1. Ajoutez le paquet NuGet [Microsoft.Intune.MAM.Xamarin.iOS](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.iOS) à votre projet Xamarin.iOS.
2.  Suivez les étapes générales requises pour l’intégration du Kit SDK d’application Intune dans une app mobile iOS. Vous pouvez commencer à l’étape 3 des instructions de l’intégration dans le [Guide du kit SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md#build-the-sdk-into-your-mobile-app). Vous pouvez ignorer l’étape finale indiquée dans cette section sur l’exécution de l’outil IntuneMAMConfigurator, car il est inclus dans le package Microsoft.Intune.MAM.Xamarin.iOS et il s’exécute automatiquement au moment de la génération.
    **Important** : l’activation du partage de trousseau pour une application est légèrement différente dans Visual Studio par rapport à Xcode. Ouvrez le fichier plist de droits de l’application et vérifiez que l’option « Activer le trousseau » est activée et que les groupes de partage de trousseau appropriés sont ajoutés dans cette section. Vérifiez ensuite que le fichier plist des droits est spécifié dans le champ « Droits personnalisés » des options « Signature du bundle iOS » du projet pour toutes les combinaisons de configuration/plate-forme appropriées.
3.  Une fois les liaisons ajoutées et l’application correctement configurée, celle-ci peut commencer à utiliser les API du kit SDK Intune. Pour cela, vous devez inclure l’espace de noms suivant :

      ```csharp
      using Microsoft.Intune.MAM;
      ```
4. Pour commencer à recevoir des stratégies de protection d’application, votre application doit s’inscrire auprès du service MAM Intune. Si votre application utilise déjà la bibliothèque d’authentification Azure Active Directory (ADAL) pour authentifier les utilisateurs, elle doit fournir l’UPN de l’utilisateur à la méthode de registerAndEnrollAccount de IntuneMAMEnrollmentManager une fois l’authentification correctement effectuée :
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Important** : veillez à remplacer les paramètres ADAL par défaut du SDK de l’application Intune par ceux de votre application. Vous pouvez le faire via le dictionnaire IntuneMAMSettings dans le fichier Info.plist de l’application, comme indiqué dans le [Guide du kit SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), ou vous pouvez utiliser les propriétés de substitution AAD de l’instance IntuneMAMPolicyManager. L’approche Info.plist est recommandée pour les applications dont les paramètres ADAL sont statiques, tandis que les propriétés de substitution sont recommandées pour les applications qui déterminent ces valeurs lors de l’exécution. 
      
      Si votre application n’utilise pas ADAL et que vous souhaitez utiliser le SDK Intune pour gérer l’authentification, votre application doit appeler la méthode loginAndEnrollAccount de IntuneMAMEnrollmentManager :
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Activation de stratégies de protection des applications dans votre application mobile Android
Ajoutez le paquet NuGet [Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) à votre projet Xamarin.Android.

Pour les applications Xamarin.Android, vous devez lire et suivre le [Guide du kit SDK d’application Intune pour les développeurs Android](app-sdk-android.md) en entier, et remplacer notamment la classe, les méthodes et les activités par leurs équivalents MAM en fonction du [tableau](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) inclus dans le guide. 

> [!NOTE]
> Si votre application ne définit pas de classe `android.app.Application`, vous devez en créer une et vérifier que vous héritez de `MAMApplication`.

> [!NOTE]
> Quand vous tentez de trouver des API équivalentes à partir du [Guide du kit SDK d’application Intune pour les développeurs Android](app-sdk-android.md) dans les liaisons `Microsoft.Intune.MAM.Xamarin.Android`, ou quand vous convertissez des extraits de code à partir du guide, sachez que le générateur de liaisons de Xamarin modifie les API Android comme suit :
> * Tous les identificateurs sont convertis en casse Pascal (com.microsoft.foo -> Com.Microsoft.Foo)
> * Toutes les opérations get/set sont converties en opérations de propriété (par exemple Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Les noms de toutes les interfaces sont précédés du caractère « I » (FooInterface -> IFooInterface)

Pour les applications utilisant Xamarin.Forms ou d’autres frameworks d’IU, nous avons fourni un outil appelé `Microsoft.Intune.MAM.Remapper`. Cet outil effectue le remplacement de la classe pour vous. Pour l’utiliser, procédez comme suit :

1.  Ajoutez le paquet NuGet [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) à votre projet.

2.  Affectez à l’action de génération du fichier `remapping-config.json` inclus dans le paquet NuGet la valeur **RemappingConfigFile**. Le fichier `remapping-config.json` inclus fonctionne uniquement avec Xamarin.Forms. Pour les autres frameworks d’interface utilisateur, consultez le fichier Lisez-moi inclus dans le package NuGet Remapper.

3.  Ajoutez un appel à Xamarin.Forms.Forms.Init(Context, Bundle) dans la fonction OnMAMCreate de votre MAMApplication. En effet, avec la gestion Intune, votre application peut démarrer en arrière-plan.

4.  Effectuez les étapes restantes du [Guide du kit SDK d’application Intune pour les développeurs Android](app-sdk-android.md), qui s’appliquent à votre application.

> [!NOTE]
> L’action de génération de remapping-config.json est parfois réinitialisée durant la mise à jour du paquet Microsoft.Intune.MAM.Remapper.Tasks, ce qui entraîne l’échec des builds.

## <a name="next-steps"></a>Étapes suivantes

Vous avez effectué les étapes de base de la configuration de votre application pour la gestion Intune. Vous pouvez désormais suivre les étapes incluses dans les guides d’intégration pour chacune des plateformes listées ci-dessus.

Si votre organisation est déjà un client Intune, contactez votre conseiller du support Microsoft pour ouvrir un ticket de support et créer un enregistrement [dans la page des problèmes GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). Nous vous aiderons dès que possible. 