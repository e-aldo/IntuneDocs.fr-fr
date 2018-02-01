---
title: "Affectation d’applications à des appareils Android for Work"
titlesuffix: Azure portal
description: "Utilisez cette rubrique pour synchroniser, puis affecter des applications sur des appareils Android for Work à partir du Google Play for Work Store."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 248dcc978b5324733d5d640230aba2b6db1a2c62
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Guide pratique pour affecter des applications sur des appareils Android for Work avec Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’affectation d’applications sur des appareils Android for Work diffère de leur affectation sur des appareils Android standard. Toutes les applications que vous installez pour Android for Work proviennent du Google Play for Work Store. Vous vous connectez au Store, recherchez les applications souhaitées et les approuvez.
L’application apparaît ensuite dans le nœud **Applications sous licence** du portail Azure. À partir de là, vous pouvez gérer l’affectation de l’application de la même façon que pour toute autre application.

En outre, si vous avez créé vos propres applications métier, vous pouvez les affecter en procédant comme suit :
- Inscrivez-vous à un compte de développeur Google qui vous permet de publier des applications dans une zone privée dans Google Play.
- Synchronisez les applications avec Intune.

## <a name="before-you-start"></a>Avant de commencer

Vérifiez que vous avez configuré Intune et Android for Work pour qu’ils collaborent dans la charge de travail **Inscription de l’appareil** du portail Azure.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchroniser une application à partir du Google Play for Work Store

1. Accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
2. Dans le Store, recherchez l’application que vous souhaitez affecter à l’aide d’Intune.
3. Dans la page de l’application que vous avez choisie, choisissez **Approuver**. Dans cet exemple, vous avez choisi l’application Microsoft Excel.<br>
  ![Exemple d’approbation d’une application](media/approve.png)
4. Une fenêtre de l’application s’ouvre, vous demandant d’accorder des autorisations pour que l’application puisse effectuer diverses opérations. Choisissez **Approuver** pour continuer.<br>
  ![Exemple d’approbation d’autorisations pour une application](media/approve-app-permissions.png)
5. L’application est approuvée et s’affiche dans votre console d’administration informatique.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publier, puis synchroniser, une application métier à partir du Google Play for Work Store

1. Accédez à la Console développeur Google Play, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work. Si vous vous connectez pour la première fois, vous devez vous inscrire et payer des frais pour devenir membre du programme de développement Google.
3. Dans la console, sélectionnez **Ajouter une nouvelle application**.
4. Vous chargez votre application et fournissez des informations la concernant de la même manière que vous publiez une application sur le Google Play Store. Toutefois, vous devez sélectionner le paramètre **Mettre cette application à la disposition de mon organisation uniquement (<*nom de l’organisation*>)** :<br>
  ![Option permettant de mettre l’application à la disposition de votre organisation uniquement](media/restrict.png)<br>
Cette opération assure que l’application est uniquement disponible pour votre organisation et n’est pas disponible dans le Google Play Store public.
Pour plus d’informations sur la façon de charger et publier des applications Android, consultez l’[aide Google Developer Console](https://support.google.com/googleplay/android-developer/answer/113469).
5. Une fois que vous avez publié votre application, accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
6. Dans le nœud **Applications** du Store, vérifiez que vous pouvez voir l’application que vous avez publiée. L’application a été automatiquement approuvée pour être synchronisée avec Intune.

## <a name="assign-an-android-for-work-app"></a>Affecter une application Android for Work

Si vous avez approuvé une application à partir du Store et qu’elle ne trouve pas dans le nœud **Applications sous licence** de la charge de travail **Applications mobiles**, forcez une synchronisation immédiate en procédant comme suit :

1. Connectez-vous au portail Azure.
2. Dans le panneau **Intune**, choisissez **Applications mobiles**.
3. Dans la charge de travail **Applications mobiles**, choisissez **Installation** > **Android for Work**.
4. Dans le panneau Android for Work, choisissez **Synchroniser maintenant**.
5. La page affiche également l’heure et l’état de la dernière synchronisation.

Quand l’application s’affiche dans le nœud **Applications sous licence** de la charge de travail **Applications mobiles**, vous pouvez [l’affecter comme toute autre application](/intune-azure/manage-apps/deploy-apps). Vous pouvez affecter l’application sur des groupes d’utilisateurs uniquement.

Une fois l’application affectée, elle est installée sur les appareils que vous avez ciblés. L’utilisateur de l’appareil n’est pas invité à approuver l’installation.

## <a name="manage-android-for-work-app-permissions"></a>Gérer les autorisations des applications Android for Work
Android for Work nécessite que vous approuviez les applications dans la console web Google Play gérée avant de les synchroniser avec Intune et de les affecter à vos utilisateurs.  Étant donné qu’Android for Work vous permet de transmettre ces applications silencieusement et automatiquement aux appareils des utilisateurs, vous devez accepter les autorisations des applications au nom de tous vos utilisateurs.  Les utilisateurs finaux ne voient aucune des autorisations des applications lors de l’installation. Il est donc important que vous lisiez et compreniez ces autorisations.

Lorsqu’un développeur d’applications publie une nouvelle version d’une application avec des autorisations mises à jour, ces autorisations ne sont pas acceptées automatiquement, même si vous aviez approuvé les autorisations précédentes. Les appareils qui exécutent l’ancienne version de l’application peuvent continuer à l’utiliser. Toutefois, l’application n’est pas mise à niveau tant que les nouvelles autorisations ne sont pas approuvées. Les appareils sur lesquels l’application n’est pas installée ne procèdent pas à son installation jusqu’à ce que vous en approuviez les nouvelles autorisations.

### <a name="how-to-update-app-permissions"></a>Mise à jour des autorisations d’application

Consultez régulièrement la console Google Play gérée pour y rechercher l’existence de nouvelles autorisations. Vous pouvez configurer Google Play pour vous envoyer à vous-même ou à d’autres un message électronique lorsque de nouvelles autorisations sont requises pour une application approuvée. Si vous affectez une application et que vous constatez qu’elle n’est pas installée sur les appareils, recherchez de nouvelles autorisations en procédant comme suit :

1. Consultez la page http://play.google.com/work
2. Connectez-vous avec le compte Google que vous avez utilisé pour publier et approuver les applications.
3. Consultez l’onglet **Mises à jour** pour savoir si des applications nécessitent une mise à jour.  Les applications répertoriées nécessitent de nouvelles autorisations et ne sont pas affectées avant l’application de ces autorisations.  

Vous pouvez également configurer Google Play pour réapprouver automatiquement les autorisations d’application en fonction de l’application. 



