---
title: "Guide d’évaluation de Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 619a1d11-3d22-4635-8f70-770eba3e1712
ms.reviewer: jeffgilb
ms.suite: ems
ms.sourcegitcommit: 4af13629986e7cef814104f3d1f298eb2be240ac
ms.openlocfilehash: 26ecc3dfe8816da9f30829901d929af53b1bedc0


---

# Guide d'évaluation de Microsoft Intune
La configuration d’une version d’évaluation gratuite de 30 jours de Microsoft Intune pour gérer vos ordinateurs et appareils mobiles est une tâche simple et rapide. Quelques étapes simples suffisent pour ajouter jusqu’à 100 utilisateurs et appareils, configurer des groupes, configurer des stratégies de conformité, et inscrire et gérer des ordinateurs et appareils mobiles.

Dans cette rubrique, vous allez découvrir comment obtenir une version d’évaluation d’Intune opérationnelle, tandis qu’une vue d’ensemble du service vous aidera à évaluer au mieux les fonctionnalités d’Intune.

Regardez la vidéo de démonstration de cinq minutes suivante pour découvrir combien il est facile de démarrer avec une version d’évaluation gratuite de Microsoft Intune et de gérer vos appareils. La première partie de la vidéo mentionne un portail qui a fait l’objet d’une « mise hors service » ; toutefois, les étapes seront essentiellement les mêmes dans votre cas, malgré l’utilisation d’un autre portail. Pour en savoir plus sur le portail, cliquez [ici](https://docs.microsoft.com/intune/deploy-use/account-portal-merged-with-Office-365).

<iframe width="675" height="480" src="https://www.youtube.com/embed/ltcZvm4VOFU" frameborder="0" allowfullscreen></iframe>

## Avant de commencer
Avant de commencer à utiliser Intune, vous aurez besoin des éléments suivants :

-   Un appareil doté d’un navigateur web compatible Silverlight qui vous permet d’accéder aux sites web sur lesquels vous prévoyez de créer des comptes d’utilisateur Intune (**Centre d’administration Office 365**) et de gérer des appareils, des groupes et des stratégies (**console d’administration Intune**).

-   Un deuxième appareil doté d’un navigateur web que vous utiliserez pour tester la façon dont les utilisateurs Intune inscrivent et gèrent leurs appareils dans le portail d’entreprise. Vous testerez aussi comment les utilisateurs recherchent et installent les applications, et comment ils demandent de l'aide auprès des administrateurs. Si vous n’avez pas un deuxième appareil, vous pouvez utiliser le paramètre « mode de confidentialité » sur le navigateur dont vous vous servez pour administrer Intune (par exemple : dans Internet Explorer, vous pouvez cliquer sur **Outils** &gt; **Navigation InPrivate**).

-   Si vous avez un compte Microsoft Online Services, vous aurez besoin des informations d'identification de l'administrateur de ce compte. Si vous n'avez pas un tel compte ou si vous souhaitez utiliser ce client Intune à des fins d'évaluation, vous n'avez pas besoin de ces informations d'identification d'administrateur.

-   Si vous prévoyez de gérer des appareils iOS ou Windows Phone avec la version d’évaluation d’Intune, vous aurez besoin de certificats (ou clés) et de comptes pour récupérer ces certificats (consultez le tableau suivant). Les appareils Android n'ont pas besoin de certificats supplémentaires.

    |Plateforme|Certificats requis|Plus d'informations|
    |------------|----------------------------|--------------------|
    |Windows Phone 8.1 et Windows Phone 8 |Aucun certificat n’est nécessaire pour les utilisateurs Windows Phone 8.1 qui installent l’application de portail d’entreprise à partir du Store. Un certificat Symantec est nécessaire pour Windows Phone 8.0 ou pour déployer l’application de portail d’entreprise sur des appareils Windows Phone 8.1 à l’aide d’Intune.|Cette recommandation part du principe que vos utilisateurs se procurent l’application de portail d’entreprise via le Store sur un appareil Windows Phone version 8.1 ou ultérieure. Pour plus d’informations sur la prise en charge de Windows Phone 8.0, consultez [Configurer la gestion de Windows Phone avec Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).|
    |Windows 10, Windows RT 8.1, Windows RT, ou appareils Windows 8.1|Aucun certificat n'est requis pour l'inscription d'appareils Windows RT et Windows.|[Installer le client de PC Windows avec Microsoft Intune](/Intune/Deploy-Use/install-the-windows-pc-client-with-microsoft-intune).|
    |iOS 7.1 ou version ultérieure|Obtenir un certificat des services de notification Push Apple.|Demandez un certificat de services de notifications Push Apple auprès d’Apple, comme décrit ici : [Configurer la gestion iOS et MAC avec Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).|

## Étapes de l’exécution d’une version d’évaluation de 30 jours d’Intune
- [Étape 1 : Se connecter ou s’inscrire à une version d’évaluation de 30 jours](get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md). Avant de vous inscrire ou de vous connecter à Intune, vous devez déterminer si vous vous connectez à l’aide d’un compte existant ou si vous créez un compte temporaire à utiliser uniquement pour l’évaluation de 30 jours de Microsoft Intune.
- [Étape 2 : Ajouter des utilisateurs](get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md) Maintenant que vous avez configuré votre compte, vous allez ajouter des comptes d’utilisateur individuels à Intune ou ajouter des utilisateurs en bloc (consultez les instructions dans cette section). Avant de commencer, il est important de comprendre comment Intune gère les comptes d'administrateur.
- [Étape 3 : Créer des groupes pour organiser les utilisateurs et les appareils](get-started-with-a-30-day-trial-of-microsoft-intune-step-3.md). Les groupes dans Intune vous permettent de gérer les utilisateurs et appareils avec une grande souplesse. Vous pouvez configurer des groupes qui répondent aux besoins de votre organisation (par exemple, en fonction de l'emplacement géographique, du service ou de caractéristiques matérielles) et les utiliser pour effectuer diverses tâches d'administration à grande échelle, de la définition de stratégies pour un ensemble d'utilisateurs au déploiement d'applications sur un ensemble d'appareils.
- [Étape 4 : Créer des stratégies et publier une application](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md). Les stratégies Intune fournissent des paramètres qui vous permettent de contrôler les paramètres de sécurité des appareils mobiles, de gérer les paramètres du Pare-feu Windows et d’Endpoint Protection pour les ordinateurs, et de déployer des applications.
- [Étape 5 : Inscrire des appareils mobiles et installer une application](get-started-with-a-30-day-trial-of-microsoft-intune-step-5.md). Pour configurer la gestion des appareils mobiles avec Intune, vous devez définir l’autorité de gestion des appareils mobiles, activer la gestion de plateformes d’appareils spécifiques, puis inscrire vos appareils à l’aide de l’application de portail d’entreprise. Vous pouvez ensuite déployer l'application Microsoft Skype que vous avez publiée.
- [Étape 6 : Options et fonctionnalités supplémentaires](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md). Choisissez comment utiliser les alertes, rapports et autres fonctionnalités Intune pour répondre aux besoins de votre entreprise.
- [Étape 7 : Étapes suivantes](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md) Préparez-vous à passer à un abonnement Intune payant et à bénéficier de l’offre du centre FastTrack pour Intune.


### Étapes suivantes
Il est temps de prendre en main votre abonnement à la version d’évaluation de 30 jours !

>[!div class="step-by-step"]
[**S’inscrire à Intune** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-1.md)

### Voir aussi
[Guide de démarrage rapide pour Intune](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune)



<!--HONumber=Jul16_HO2-->


