---
title: "Guide de démarrage rapide pour Intune | Microsoft Intune"
description: "Configuration requise et conditions préalables avant de commencer à utiliser votre abonnement Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: d10bb6ce48ba000154d117b2481690a198d25e49


---


# Guide de démarrage rapide pour Intune
Ce guide de démarrage rapide vous guide lors des étapes de configuration d’un abonnement payant à Microsoft Intune pour gérer rapidement et facilement les appareils mobiles et ordinateurs Windows utilisés par votre entreprise. Vous pouvez suivre chaque étape dans l’ordre ou ignorer une étape si elle ne s’applique pas aux besoins de votre environnement ou de votre entreprise.

>[!NOTE]
>Cet article se concentre sur la configuration d’Intune tant que service autonome. Si vous utilisez actuellement Microsoft System Center Configuration Manager pour gérer vos ordinateurs et serveurs, vous pouvez également [étendre Configuration Manager pour gérer les appareils mobiles](https://technet.microsoft.com/library/jj884158.aspx). Pour cela, connectez-vous à Intune à l’aide de Configuration Manager dans un déploiement de gestion d’appareil mobile hybride.

Les étapes décrites dans ce guide de démarrage rapide sont relativement similaires à la procédure décrite dans le [guide d’évaluation Intune](/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune). Toutefois, après l’évaluation, et lorsque vous êtes prêt à commencer à gérer vos appareils mobiles, vous devez répondre à plusieurs exigences supplémentaires :

-   Synchronisez des comptes Active Directory locaux avec Intune et Azure Active Directory.

-   Mettez à jour des enregistrements de service DNS et du domaine public avec votre bureau d’enregistrement de domaines.

-   Personnalisez des fonctionnalités Intune pour la production.

>[!TIP]
>Si vous achetez au moins 150 licences pour Microsoft Intune dans un plan éligible, vous pouvez utiliser le service *FastTrack Center Benefit*, qui vous permet d’obtenir l’aide de spécialistes Microsoft pour préparer votre environnement pour Intune. Consultez [Description de l’offre de service Microsoft Intune](https://technet.microsoft.com/library/mt228265.aspx).


## Avant de commencer
Utilisez ce guide si vous débutez avec un abonnement payant et que vous êtes prêt à déployer Intune et à apporter des modifications à votre infrastructure réseau existante. Ces tâches peuvent consister simplement à ajouter ou à mettre à jour vos enregistrements DNS internes ou externes ou à synchroniser vos comptes d’utilisateurs Active Directory existants à Azure Active Directory. Quelle que soit la combinaison de fonctionnalités de gestion d’appareils mobiles Intune que vous choisissez, vous devez prévoir avec soin la façon dont Intune interagit avec vos composants et services réseau existants. Voici plus précisément les points que vous devez examiner :

-   **Gestion de votre identité utilisateur** : pour la plupart des organisations de taille moyenne à grande, la façon la plus appropriée et la plus pratique de gérer les identités des utilisateurs avec Intune est de connecter les services d’annuaire existants à Intune par le biais d’Azure Active Directory. Ceci est d'autant plus vrai si vous utilisez déjà d'autres services cloud Microsoft, tels qu'Office 365 ou Exchange Online. La synchronisation de vos comptes d’utilisateurs existants à l’aide de [Microsoft Azure Active Directory Connect](https://www.microsoft.com/download/details.aspx?id=47594) vous offre un moyen simple et rapide de connecter votre instance locale Active Directory à Azure Active Directory et de configurer une expérience d’authentification unique pour vos utilisateurs.

-   **Nature de l’impact sur DNS** : si vous souhaitez utiliser votre propre nom de domaine au lieu du domaine onmicrosoft.com par défaut que vous obtenez lors de la première inscription à Intune, vous devez effectuer des mises à jour d’enregistrements DNS publics. Ces mises à jour sont requises afin que les appareils mobiles puissent localiser le service Intune et pour vous assurer que le service de gestion de votre abonnement fonctionne correctement afin de gérer tous les appareils utilisés dans votre entreprise.

## Faites-en sorte d’avoir les éléments suivants à portée de main
Prêt à vous lancer ? Voici les éléments dont vous avez besoin au début de l’utilisation de votre abonnement payant Intune :

### Un appareil avec un navigateur web compatible Silverlight
Vous en avez besoin pour accéder à la console d’administration Intune où vous pouvez gérer les appareils, les applications et les stratégies. Vous avez également besoin d’un navigateur web pour accéder au Portail d’entreprise Intune basé sur le web si vous n’accédez pas à l’application Portail d’entreprise sur un appareil mobile. Pour simplifier les choses, vous pouvez utiliser le paramètre « mode de confidentialité » sur le navigateur dont vous vous servez pour administrer Intune (par exemple : dans Internet Explorer, vous pouvez cliquer sur **Outils** &gt; **Navigation InPrivate**).

>[!TIP]
>En raison de cette exigence, le navigateur Edge de Microsoft n’est pas pris en charge pour l’accès à la console d’administration Intune.


### Certificats pour les appareils mobiles
Si vous gérez des appareils iOS ou Windows Phone avec Intune, vous avez besoin de certificats et de comptes pour récupérer ces certificats. Les appareils Android n’ont pas besoin de certificats supplémentaires.

- Aucun certificat n’est nécessaire pour les utilisateurs **Windows Phone 8.1** qui installent l’application de portail d’entreprise à partir du Store. Toutefois, un [certificat de signature de code Symantec](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do) est nécessaire pour **Windows Phone 8.0** ou pour déployer l’application Portail d’entreprise sur des appareils Windows Phone 8.1 à l’aide d’Intune.

>[!NOTE]
>Ce guide de démarrage rapide part du principe que vos utilisateurs se procurent l’application Portail d’entreprise via le Store sur un appareil Windows Phone version 8.1 ou ultérieure. Pour plus d’informations sur la prise en charge de Windows Phone 8.0, consultez [Configurer la gestion de Windows Phone 8.0 avec Microsoft Intune](/Intune/deploy-use/set-up-windows-phone-8.0-management-with-microsoft-intune).

- Il n’existe aucune exigence de certificat pour les **PC Windows** ou les **appareils Windows RT** lors de l’inscription de PC Windows en tant qu’appareils ou l’[installation du client PC Windows pour Microsoft Intune](/intune/deploy-use/install-the-windows-pc-client-with-microsoft-intune).

- Pour les appareils **iOS** ou **Mac OS X**, vous devez demander un certificat de service de notifications Push Apple auprès d’Apple, comme décrit à l’étape 3 de la rubrique [Configurer la gestion des appareils iOS et Mac avec Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

## Étapes suivantes
Il est temps de vous familiariser avec le guide de démarrage rapide Intune !

>[!div class="step-by-step"]
[**Se connecter à Intune** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)



<!--HONumber=Jul16_HO4-->


