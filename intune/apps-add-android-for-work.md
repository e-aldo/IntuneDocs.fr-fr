---
title: Affecter des applications sur des appareils Android for Work| Microsoft Docs
titleSuffix: Intune Azure preview
description: "Préversion d’Intune Azure : Utilisez cette rubrique pour synchroniser, puis affecter des applications sur des appareils Android for Work à partir du Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 49e86ab665d9022739c0330092734ba897ea3b02
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Guide pratique pour affecter des applications sur des appareils Android for Work avec Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

L’affectation d’applications sur des appareils Android for Work diffère de leur affectation sur des appareils Android standard. Toutes les applications que vous installez pour Android for Work proviennent du Google Play for Work Store. Vous vous connectez au Store, recherchez les applications souhaitées et les approuvez.
L’application apparaît ensuite dans le nœud **Applications sous licence** du portail Intune. À partir de là, vous pouvez gérer l’affectation de l’application de la même façon que pour toute autre application.

En outre, si vous avez créé vos propres applications métier, vous pouvez les affecter. Pour ce faire, vous devez vous inscrire pour obtenir un compte de développeur Google, qui vous permet de publier des applications sur une zone privée du Google Play Store, puis de les synchroniser avec Intune.

## <a name="before-you-start"></a>Avant de commencer

Vérifiez que vous avez configuré Intune et Android for Work pour qu’ils collaborent dans la charge de travail **Inscription de l’appareil** du portail Intune.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchroniser une application à partir du Google Play for Work Store


1. Accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
2. Dans le Store, recherchez l’application que vous souhaitez affecter à l’aide d’Intune.
3. Dans la page de l’application que vous avez choisie, choisissez **Approuver**. Dans cet exemple, vous avez choisi l’application Microsoft Excel.<br>
  ![Exemple d’approbation d’une application](media/approve.png)
4. Une fenêtre de l’application s’ouvre, vous demandant d’accorder des autorisations pour que l’application puisse effectuer diverses opérations. Vous devez choisir **Approuver** pour continuer.<br>
  ![Exemple d’approbation d’autorisations pour une application](media/approve-app-permissions.png)
5. Après quelques instants, un message de confirmation apparaît indiquant que l’application a été approuvée et qu’elle est disponible dans votre console d’administration informatique.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publier, puis synchroniser, une application métier à partir du Google Play for Work Store

1. Accédez à la Console développeur Google Play, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work. Si vous vous connectez pour la première fois, vous devez vous inscrire et payer des frais pour devenir membre du programme de développement Google.
3. Dans la console, sélectionnez **Ajouter une nouvelle application**.
4. Vous chargez votre application et fournissez des informations la concernant de la même manière que vous publiez une application sur le Google Play Store. Toutefois, vous devez sélectionner le paramètre **(<*nom de l’organisation*>)** comme indiqué ci-dessous.<br>
  ![Option permettant de mettre l’application à la disposition de votre organisation uniquement](media/restrict.png)<br>
Ainsi, l’application est uniquement disponible pour votre organisation et n’est pas disponible dans le Google Play Store public.
Pour plus d’informations sur la façon de charger et publier des applications Android, consultez l’[aide Google Developer Console](https://support.google.com/googleplay/android-developer/answer/113469).
5. Une fois que vous avez publié votre application, accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
6. Dans le nœud **Applications** du Store, vérifiez que vous pouvez voir l’application que vous avez publiée. Notez qu’elle a été automatiquement approuvée pour être synchronisée avec Intune.

## <a name="assign-an-android-for-work-app"></a>Affecter une application Android for Work

Si vous avez approuvé une application à partir du Store et qu’elle ne trouve pas encore dans le nœud **Applications sous licence** de la charge de travail **Applications mobiles**, vous pouvez forcer une synchronisation immédiate comme suit :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Installation** > **Android for Work**.
5. Dans le panneau Android for Work, choisissez **Synchroniser maintenant**.
6. La page affiche également l’heure et l’état de la dernière synchronisation.

Quand l’application s’affiche dans le nœud **Applications sous licence** de la charge de travail **Applications mobiles**, vous pouvez [l’affecter comme toute autre application](/intune-azure/manage-apps/deploy-apps). Vous pouvez affecter l’application sur des groupes d’utilisateurs uniquement.

Une fois l’application affectée, elle est installée sur les appareils que vous avez ciblés. L’utilisateur de l’appareil ne sera pas invité à approuver l’installation.

## <a name="manage-app-permissions"></a>Gérer les autorisations d’applications
Android for Work nécessite que vous approuviez les applications dans la console web Google Play gérée avant de les synchroniser avec Intune et de les affecter à vos utilisateurs.  Étant donné qu’Android for Work vous permet de transmettre ces applications silencieusement et automatiquement aux appareils des utilisateurs, vous devez accepter les autorisations des applications au nom de tous vos utilisateurs.  Les utilisateurs finaux ne verront aucune des autorisations des applications lors de l’installation. Il est donc important que vous lisiez et compreniez ces autorisations.

Lorsqu’un développeur d’applications publie une nouvelle version d’une application avec des autorisations mises à jour, ces autorisations ne sont pas acceptées automatiquement, même si vous aviez approuvé les autorisations précédentes. Les appareils qui exécutent l’ancienne version de l’application peuvent continuer à l’utiliser, mais l’application ne sera pas mise à niveau tant que ses nouvelles autorisations n’auront pas été approuvées. Les appareils sur lesquels l’application n’est pas installée ne pourront pas procéder à son installation jusqu’à ce que vous en approuviez les nouvelles autorisations.

### <a name="how-to-update-app-permissions"></a>Mise à jour des autorisations d’application

Consultez régulièrement la console Google Play gérée pour y rechercher l’existence de nouvelles autorisations. Si vous affectez une application et que vous constatez qu’elle n’est pas installée sur les appareils, recherchez de nouvelles autorisations en procédant comme suit :

1. Consultez la page http://play.google.com/work
2. Connectez-vous avec le compte Google que vous avez utilisé pour publier et approuver les applications.
3. Consultez l’onglet **Mises à jour** pour savoir si des applications nécessitent une mise à jour.  Les applications répertoriées nécessitent de nouvelles autorisations et ne seront pas affectées avant l’application de ces autorisations.  

