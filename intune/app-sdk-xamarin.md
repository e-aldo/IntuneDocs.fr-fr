---
title: Liaisons Xamarin du kit SDK d’application Microsoft Intune
description: Les liaisons Xamarin du kit SDK d’application Intune activent la stratégie de protection des applications Intune dans les applications iOS et Android générées avec Xamarin.
keywords: sdk, Xamarin, intune
author: Erikre
manager: dougeby
ms.author: erikre
ms.date: 06/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f8f5e397c314088c7b26edba486f9cbaf9718096
ms.sourcegitcommit: 1eddded65ae9e442dd3bebd16b9428af76a67f34
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2018
ms.locfileid: "35250942"
---
# <a name="microsoft-intune-app-sdk-xamarin-bindings"></a>Liaisons Xamarin du kit SDK d’application Microsoft Intune

> [!NOTE]
> Vous pouvez d’abord lire l’article [Bien démarrer avec le SDK d’application Intune](app-sdk-get-started.md), qui explique comment préparer l’intégration sur chaque plateforme prise en charge.

## <a name="overview"></a>Vue d’ensemble
Les [liaisons Xamarin du kit SDK d’application Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) activent la [stratégie de protection des applications Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) dans les applications iOS et Android générées avec Xamarin. Les liaisons permettent aux développeurs de générer facilement des fonctionnalités de protection des applications Intune dans leur application Xamarin.

Les liaisons Xamarin du kit SDK d’application Microsoft Intune vous permettent d’incorporer des stratégies de protection des applications Intune (également appelées stratégies APP ou MAM) dans vos applications développées avec Xamarin. Une application prenant en charge la gestion GAM est une application intégrée au kit SDK d’application Intune. Les administrateurs informatiques peuvent déployer des stratégies de protection des applications sur votre application mobile quand celle-ci est activement gérée par Intune.

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
4. Pour commencer à recevoir des stratégies de protection d’application, votre application doit s’inscrire auprès du service GAM d’Intune. Si votre application utilise déjà la bibliothèque d’authentification Azure Active Directory (ADAL) pour authentifier les utilisateurs, elle doit fournir l’UPN de l’utilisateur à la méthode de registerAndEnrollAccount de IntuneMAMEnrollmentManager une fois l’authentification correctement effectuée :
      ```csharp
      IntuneMAMEnrollmentManager.Instance.RegisterAndEnrollAccount(string identity);
      ```
      **Important** : veillez à remplacer les paramètres ADAL par défaut du SDK de l’application Intune par ceux de votre application. Vous pouvez le faire via le dictionnaire IntuneMAMSettings dans le fichier Info.plist de l’application, comme indiqué dans le [Guide du kit SDK d’application Intune pour les développeurs iOS](app-sdk-ios.md#configure-settings-for-the-intune-app-sdk), ou vous pouvez utiliser les propriétés de substitution AAD de l’instance IntuneMAMPolicyManager. L’approche Info.plist est recommandée pour les applications dont les paramètres ADAL sont statiques, tandis que les propriétés de substitution sont recommandées pour les applications qui déterminent ces valeurs lors de l’exécution. 
      
      Si votre application n’utilise pas ADAL et que vous souhaitez utiliser le SDK Intune pour gérer l’authentification, votre application doit appeler la méthode loginAndEnrollAccount de IntuneMAMEnrollmentManager :
      ```csharp
       IntuneMAMEnrollmentManager.Instance.LoginAndEnrollAccount([NullAllowed] string identity);
      ```
      
> [!NOTE] 
> Il n’existe pas de remappeur pour iOS. L’intégration dans une application Xamarin.Forms doit être la même que pour un projet Xamarin.iOS normal. 

## <a name="enabling-intune-app-protection-policies-in-your-android-mobile-app"></a>Activation de stratégies de protection des applications Intune dans votre application mobile Android

### <a name="xamarinandroid-integration"></a>Intégration de Xamarin.Android

1. Ajoutez la dernière version du [paquet NuGet Microsoft.Intune.MAM.Xamarin.Android](https://www.nuget.org/packages/Microsoft.Intune.MAM.Xamarin.Android) à votre projet Xamarin.Android. Vous disposerez ainsi des références nécessaires à Intune pour activer votre application.

2. Lisez et suivez le [Guide du kit SDK d’application Intune pour les développeurs Android](app-sdk-android.md) en intégralité. Soyez particulièrement attentifs aux sections suivantes :
    1. [Remplacement des classes et des méthodes](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent). 
    2. [MAMApplication](app-sdk-android.md#mamapplication). Vérifiez que votre sous-classe est correctement décorée avec l’attribut `[Application]` et qu’elle se substitue au constructeur `(IntPtr, JniHandleOwnership)`.
    3. [Intégration à ADAL](app-sdk-android.md#configure-azure-active-directory-authentication-library-adal) si votre application effectue l’authentification auprès d’AAD.
    4. [Inscription à MAM-WE](app-sdk-android.md#app-protection-policy-without-device-enrollment) si vous prévoyez d’obtenir une stratégie à partir du service MAM dans votre application.

> [!NOTE]
> Quand vous tentez de trouver des API équivalentes à partir du [Guide du SDK d’application Intune pour les développeurs Android](app-sdk-android.md) dans les liaisons `Microsoft.Intune.MAM.Xamarin.Android`, ou quand vous convertissez des extraits de code à partir du guide, sachez que le générateur de liaisons de Xamarin modifie les API Android comme suit :
> * Tous les identificateurs sont convertis en casse Pascal (com.foo.bar -> Com.Foo.Bar)
> * Toutes les opérations get/set sont converties en opérations de propriété (par exemple, Foo.getBar() -> Foo.Bar, Foo.setBar("zap") -> Foo.Bar = "zap")
> * Les noms de toutes les interfaces sont précédés du caractère « I » (FooInterface -> IFooInterface)

### <a name="xamarinforms-integration"></a>Intégration de Xamarin.Forms

**En plus des étapes ci-dessus**, nous fournissons le paquet `Xamarin.Forms` pour les applications `Microsoft.Intune.MAM.Remapper`. Ce paquet accomplit pour vous le remplacement de classe en injectant des classes `MAM` dans la hiérarchie des classes `Xamarin.Forms` couramment utilisées comme `FormsAppCompatActivity` et `FormsApplicationActivity`. Vous pouvez donc continuer à utiliser ces classes en fournissant des substitutions pour les fonctions MAM équivalentes comme `OnMAMCreate` et `OnMAMResume`. Pour l’utiliser, procédez comme suit :

1.  Ajoutez le paquet NuGet [Microsoft.Intune.MAM.Remapper.Tasks](https://www.nuget.org/packages/Microsoft.Intune.MAM.Remapper.Tasks) à votre projet. Des liaisons Xamarin du SDK d’application Intune sont automatiquement ajoutées si elle n’ont pas déjà été incluses.

2.  Ajoutez un appel à `Xamarin.Forms.Forms.Init(Context, Bundle)` dans la fonction `OnMAMCreate` de la classe `MAMApplication` que vous avez créée à l’étape 2.2 ci-dessus. Cette opération est nécessaire, car avec Intune, la gestion de votre application peut être démarrée en arrière-plan.

> [!NOTE]
> Étant donné que cette opération réécrit une dépendance que Visual Studio utilise pour la saisie semi-automatique Intellisense, vous devrez peut-être redémarrer Visual Studio après la première exécution du remappeur pour qu’Intellisense reconnaisse correctement les changements. 


## <a name="support"></a>Prise en charge

Si votre organisation est déjà un client Intune, contactez votre conseiller du support Microsoft pour ouvrir un ticket de support et créer un enregistrement [dans la page des problèmes GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin/issues). Nous vous aiderons dès que possible. 
