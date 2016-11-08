---
title: "Prise en main du Kit SDK d’application Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# <a name="getting-started-with-the-microsoft-intune-app-sdk"></a>Prise en main du Kit SDK d’application Microsoft Intune

Ce guide de prise en main va vous permettre d’activer rapidement la gestion des applications mobiles dans votre application mobile avec Microsoft Intune. Il peut s’avérer utile de comprendre d’abord les avantages du SDK d’application Intune, tels qu’ils sont énumérés dans la [présentation du Kit SDK d’application Intune](intune-app-sdk.md).

Ce guide décrit les principales étapes nécessaires pour activer la gestion des applications mobiles dans votre application avec Microsoft Intune. Le SDK d’application Intune, qui prend en charge des scénarios similaires sur différentes plateformes, est destiné à créer une expérience cohérente entre les plateformes pour les administrateurs informatiques. Cependant, en raison des limitations de chaque plateforme, il existe de petites différences dans la prise en charge de certaines fonctionnalités.

# <a name="getting-started"></a>Prise en main

## <a name="register-your-store-app-with-microsoft"></a>Inscrire votre application de Store auprès de Microsoft

**Si votre application est interne à votre entreprise et qu’elle ne sera pas rendue disponible pour un App Store public** :

Vous **n’avez pas besoin** d’inscrire votre application. Pour les applications métier internes, l’administrateur informatique déploie l’application en interne. Intune détecte que l’application a été créée avec le SDK et autorise l’administrateur informatique à lui appliquer des paramètres de stratégie GAM. Vous pouvez passer à la section [Activer votre application mobile iOS ou Android pour la gestion des applications mobiles avec le SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Si votre application doit être publiée sur un App Store public, comme l’Apple App Store ou Google Play** : 

Vous **devez** d’abord inscrire votre application auprès de Microsoft Intune et accepter les conditions d’inscription. Après l’inscription, les administrateurs informatiques peuvent appliquer des paramètres de stratégie GAM Intune à l’application concernée, qui apparaît comme un partenaire d’application Intune. Tant que l’inscription n’est pas terminée et confirmée par l’équipe de Microsoft Intune, les administrateurs Intune ne peuvent pas appliquer une stratégie GAM au lien ciblé de votre application. Microsoft ajoute également votre application à sa page [Partenaires Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps), où l’icône de l’application est affichée pour indiquer qu’elle prend en charge la stratégie GAM Microsoft Intune.

Pour commencer le processus d’inscription, remplissez le **[questionnaire de partenariat d’application Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)**. 

Microsoft utilise les adresses e-mail répertoriées dans les réponses du questionnaire pour communiquer et continuer le processus d’inscription. Nous utilisons aussi cette adresse pour vous contacter en cas de problèmes.

> [!NOTE]
> Toutes les informations collectées dans le formulaire ci-dessus et par le biais des e-mails échangés avec l’équipe Microsoft Intune respectent la [déclaration de confidentialité Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

**Ce qui se passe dans le processus d’inscription** : 

1. Après l’envoi de votre questionnaire, Microsoft vous contacte via votre adresse e-mail d’inscription pour confirmer la bonne réception de votre formulaire ou vous demander des informations supplémentaires pour terminer l’inscription. 
2. Une fois reçues toutes les informations nécessaires de votre part, nous vous enverrons le contrat de partenariat de l’application Microsoft Intune à signer. Ce contrat décrit les conditions que votre entreprise doit accepter avant de devenir partenaire de l’application Microsoft Intune. 
3. Microsoft vous avertira également quand votre application sera inscrite auprès du service Microsoft Intune et quand elle sera proposée sur le site des [partenaires Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). 
4. Enfin, le lien ciblé de votre application sera ajouté à la prochaine mise à jour mensuelle du service Intune. Par exemple, si les informations d’inscription sont complétées en juillet, le lien ciblé de l’application sera pris en charge à la mi-août. 

Si le lien ciblé de votre application de Store vient à changer, vous devrez réinscrire votre application. En outre, veillez à nous prévenir si vous mettez à jour votre application avec une nouvelle version du SDK d’application Intune.



## <a name="download-the-sdk-files"></a>Télécharger les fichiers du SDK

Les SDK d’application Intune pour iOS et Android natifs sont hébergés sur un compte Microsoft GitHub. Les dépôts publics ci-dessous contiennent les fichiers du SDK pour iOS et Android, respectivement :

* [SDK d’application Intune pour iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK d’application Intune pour Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Si votre application est une application Xamarin ou Cordova, utilisez les outils de développement ci-dessous** :

* [Composant Xamarin du SDK d’application Intune](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Plug-in Cordova du SDK d’application Intune](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Nous vous recommandons de vous créer un compte GitHub que vous pouvez utiliser pour créer des copies et faire des extractions depuis nos dépôts. GitHub permet aux développeurs de communiquer avec notre équipe produit, d’ouvrir des problèmes et recevoir des réponses rapides, consulter les notes de publication et fournir des commentaires à Microsoft. Pour toute question sur les dépôts et les comptes GitHub, contactez msintuneappsdk@microsoft.com.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Activer votre application mobile iOS ou Android pour la gestion des applications mobiles avec le SDK

Pour intégrer le SDK d’application Intune à votre application iOS native, vous avez besoin des éléments suivants : 

* **[Guide du Kit SDK d’application Intune pour les développeurs iOS](intune-app-sdk-ios.md)** : ce document vous guide tout au long des étapes à suivre pour activer votre application mobile iOS avec le SDK d’application Intune. 


Pour intégrer le SDK d’application Intune à votre application Android native, vous avez besoin des éléments suivants :

* **[Guide du Kit SDK d’application Intune pour les développeurs Android](intune-app-sdk-android.md)** : ce document vous guide tout au long des étapes à suivre pour activer votre application mobile Android avec le SDK d’application Intune. 

Vous trouverez la documentation pour le composant Xamarin du SDK d’application Intune et pour le plug-in Cordova du SDK d’application Intune dans leurs dépôts GitHub respectifs. 


## <a name="configuring-telemetry-for-your-app"></a>Configuration de la télémétrie pour votre application

Microsoft Intune collecte des données sur les statistiques d’utilisation pour votre application.

* **SDK d’application Intune pour iOS** : le SDK enregistre par défaut les données de télémétrie du SDK sur les événements d’utilisation. Ces données sont envoyées à Microsoft Intune.

    * Si vous choisissez de ne pas envoyer les données de télémétrie du SDK à Microsoft Intune à partir de votre application, vous devez désactiver la transmission de la télémétrie du SDK en définissant la propriété `MAMTelemetryDisabled` sur « YES » dans le dictionnaire IntuneMAMSettings.

* **SDK d’application Intune pour Android** : les données de télémétrie ne sont pas enregistrées via le SDK.

## <a name="test-your-mam-enabled-app-with-microsoft-intune"></a>Tester votre application compatible avec la gestion des applications mobiles avec Microsoft Intune

Après avoir terminé les étapes nécessaires pour intégrer votre application iOS ou Android au SDK d’application Intune, vous devez vérifier que toutes les stratégies de gestion d’application sont activées et opérationnelles pour l’utilisateur final et l’administrateur informatique. Pour tester votre application intégrée, vous avez besoin des éléments suivants :

<!--TODO-->

* **Test de votre application compatible GAM avec Microsoft Intune** : ce document vous guide tout au long des étapes nécessaires pour tester vos applications iOS ou Android compatibles GAM avec Microsoft Intune. Vous pouvez trouver ce document dans les dépôts GitHub des SDK.

* **Compte Microsoft Intune** : pour tester vos applications compatibles MAM avec Microsoft Intune, vous avez besoin d’un compte Microsoft Intune. 
    * Si vous êtes un éditeur de logiciels indépendant et que vous configurez vos applications de Store iOS ou Android pour qu’elles prennent en charge la gestion des applications mobiles Intune, vous recevez un code promotionnel à l’issue de votre inscription auprès de Microsoft Intune, comme indiqué durant l’étape d’inscription. Ce code promotionnel vous permettra de vous inscrire à une version d’évaluation de Microsoft Intune valable un an. 
    * Si vous développez une application métier qui n’est pas destinée au magasin, vous êtes tenu d’avoir accès à Microsoft Intune dans votre organisation. Vous pouvez aussi vous inscrire à une version d’évaluation gratuite de [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) valable un mois.




<!--HONumber=Nov16_HO1-->


