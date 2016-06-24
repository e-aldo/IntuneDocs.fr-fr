---
# required metadata

title: Prise en main du Kit SDK de l’application Microsoft Intune | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Prise en main du Kit de développement logiciel (SDK) de l’application Microsoft Intune

Ce guide de prise en main va vous permettre d’activer rapidement la gestion des applications mobiles dans votre application mobile avec Microsoft Intune. Il peut s’avérer utile de comprendre d’abord les avantages du SDK de l’application Intune, tels qu’ils sont énumérés dans la [présentation du Kit de développement logiciel (SDK) de l’application Intune](intune-app-sdk.md).

Ce guide décrit les principales étapes nécessaires pour activer la gestion des applications mobiles dans votre application avec Microsoft Intune. Le SDK de l’application Intune, qui prend en charge des scénarios similaires sur différentes plateformes, est destiné à créer une expérience cohérente entre les plateformes pour les administrateurs informatiques. Cependant, en raison des limitations de chaque plateforme, il existe de petites différences dans la prise en charge de certaines fonctionnalités.

# Prise en main

## S’inscrire à Microsoft Connect

Pour accéder au SDK de l’application Intune, vous devez tout d’abord vous inscrire sur le site Microsoft Connect. Pour cela, ouvrez un [compte Microsoft](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X) en utilisant votre adresse de messagerie d’entreprise.

Votre demande d’inscription est alors mise en suspens jusqu’à son examen par l’équipe Intune. Le temps de réponse est généralement de 2 à 3 jours ouvrés. Une fois votre demande approuvée, vous recevrez un message électronique de notification avec un ou plusieurs liens pour télécharger le SDK de l’application Intune pour vos plateformes et tous les guides connexes. Ces guides sont également accessibles sur le site MSDN.

## Inscrire votre application de Store auprès de Microsoft Intune

**Si votre application compatible est interne à votre entreprise et qu’elle ne sera pas proposée dans le magasin d’applications Apple ou Google**: il est inutile d’inscrire votre application. L’administrateur informatique peut charger directement ces applications internes dans la console Microsoft Intune à des fins de déploiement. Intune détecte alors que les applications ont été créées avec le SDK et offre à l’administrateur la possibilité d’appliquer la stratégie de gestion des applications mobiles (MAM) à celle-ci. Vous pouvez passer à la section intitulée [Activer votre application mobile iOS ou Android pour la gestion des applications mobiles avec le SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Si, en tant qu’éditeur de logiciels indépendant (ISV), vous développez une application qui sera accessible aux clients via le magasin d’applications Apple ou Google**: vous devez tout d’abord inscrire votre application auprès de Microsoft Intune et accepter les conditions d’inscription. Vous pouvez fournir le lien ciblé de l’application à ce stade. Par la suite, un administrateur informatique pourra appliquer la stratégie de gestion des applications mobiles Intune à l’application. Tant que l’inscription n’est pas terminée et confirmée par l’équipe de Microsoft Intune, le lien ciblé de votre application ne pourra pas appliquer la stratégie de gestion des applications mobiles dans la console d’administration. L’application sera aussi inscrite sur un site web de partenaires Microsoft Intune géré par Microsoft. Les clients sauront ainsi que l’application prend en charge la stratégie de gestion des applications mobiles Microsoft Intune.

Pour commencer le processus d’inscription, **examinez et signez** l’[accord de partenariat Microsoft Intune](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Ce contrat décrit les conditions que votre entreprise doit accepter avant de devenir partenaire de l’application Microsoft Intune. Vous devez vous connecter pour consulter ce document. Le contrat se trouve dans le site Microsoft Connect du SDK de l’application Intune, sous l’onglet des questionnaires. Vous devez aussi fournir le nom de l’application, le nom de votre entreprise, ainsi que le lien ciblé du magasin Google ou iTunes vers votre application.

![Microsoft Connect](../media/microsoft-connect.png)

Nous utilisons l’adresse de messagerie que vous avez entrée lors de l’inscription pour confirmer la réception du formulaire d’inscription. Nous utilisons aussi cette adresse pour vous contacter en cas de problèmes.

**Déroulement du processus d’inscription**: après l’envoi de votre formulaire, Microsoft vous contactera à l’adresse de messagerie que vous avez entrée lors de l’inscription pour confirmer la bonne réception de votre formulaire ou vous demander des informations supplémentaires en vue de terminer l’inscription. Microsoft vous contactera également quand votre application sera inscrite auprès de Microsoft Intune et quand elle sera proposée sur le site des partenaires Microsoft Intune. Après confirmation de la réception des informations, le lien ciblé de votre application sera inclus dans la prochaine mise à jour mensuelle du service Intune. Par exemple, si les informations d’inscription sont complétées en juillet, le lien ciblé de l’application sera pris en charge à la mi-août. Si le lien ciblé de votre application de Store vient à changer, vous devrez réinscrire votre application. Veillez également à nous prévenir si vous mettez à jour votre application avec une nouvelle version du SDK de l’application Intune.

**Remarque**: toutes les informations collectées dans le formulaire ci-dessus et par le biais des messages électroniques échangés avec l’équipe Intune respectent la [déclaration de confidentialité Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Activer votre application mobile iOS ou Android pour la gestion des applications mobiles avec le SDK

Pour activer votre application mobile iOS, vous avez besoin des éléments suivants :

1. **[Guide du Kit SDK de l’application Intune pour les développeurs iOS](intune-app-sdk-ios.md)** : ce document vous guide tout au long des étapes à suivre pour activer votre application mobile iOS avec le Kit SDK de l’application Intune. Vous trouverez ce document dans le dossier de documentation que vous avez téléchargé avec le package SDK de l’application Intune.
2. **SDK de l’application Intune pour iOS**: dans le cadre du package SDK de l’application Intune que vous avez téléchargé à partir de Microsoft Intune, vous trouverez un dossier signé intitulé « Intune App SDK for iOS ». Ce dossier comprend la totalité du contenu du SDK de l’application Intune pour iOS.

Pour activer votre application mobile Android avec le SDK de l’application Intune, vous avez besoin des éléments suivants :

1. **[Guide du Kit SDK de l’application Intune pour les développeurs Android](intune-app-sdk-android.md)** : ce document vous guide tout au long des étapes à suivre pour activer votre application mobile Android avec le Kit SDK de l’application Intune. Vous trouverez ce document dans le dossier de documentation que vous avez téléchargé avec le package SDK de l’application Intune.
2. **SDK de l’application Intune pour Android**: dans le cadre du package SDK de l’application Intune que vous avez téléchargé à partir de Microsoft Intune, vous trouverez un dossier signé intitulé « Intune App SDK for Android ». Ce dossier comprend la totalité du contenu du SDK de l’application Intune pour Android.

## Désactivation de la télémétrie pour votre application

**SDK d’application Intune pour iOS** : le SDK enregistre par défaut les données de télémétrie du SDK sur les événements d’utilisation. Ces données sont envoyées à Microsoft Intune.

Si vous choisissez de ne pas envoyer les données de télémétrie du SDK à Microsoft Intune à partir de votre application, vous **devez désactiver** la transmission de la télémétrie du SDK en affectant à la propriété `MAMTelemetryDisabled` la valeur « YES » dans `IntuneMAMSettings`.

**SDK d’application Intune pour Android** : les données de télémétrie du SDK ne sont pas enregistrées via le SDK.

## Tester votre application compatible avec la gestion des applications mobiles avec Microsoft Intune

Après avoir terminé les étapes nécessaires pour vérifier la compatibilité (intégrer le SDK de l’application Intune) du SDK de l’application Intune iOS ou Android, vous devez vous assurer que toutes les stratégies de gestion d’application sont activées et opérationnelles pour l’utilisateur final et l’administrateur informatique. Pour tester votre application compatible, vous avez besoin des éléments suivants :

1. **Test de votre application compatible MAM à l’aide de Microsoft Intune** : ce document vous guide tout au long des étapes nécessaires pour tester vos applications iOS ou Android compatibles MAM avec Microsoft Intune. Vous trouverez ce document dans le dossier de documentation que vous avez téléchargé avec le package SDK de l’application Intune.
2. **Compte Microsoft Intune** : pour tester vos applications compatibles MAM avec Microsoft Intune, vous avez besoin d’un compte Microsoft Intune. Si vous êtes un éditeur de logiciels indépendant et que vous configurez vos applications de Store iOS ou Android pour qu’elles prennent en charge la gestion des applications mobiles, vous recevrez un code promotionnel à l’issue de votre inscription auprès de Microsoft Intune, comme indiqué durant l’étape d’inscription. Ce code promotionnel vous permettra de vous inscrire à une version d’évaluation de Microsoft Intune valable un an. Si vous développez une application métier qui n’est pas destinée au magasin, vous êtes tenu d’avoir accès à Microsoft Intune dans votre organisation. Vous pouvez aussi vous inscrire à une version d’évaluation gratuite de [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) valable un mois.



<!--HONumber=Jun16_HO1-->


