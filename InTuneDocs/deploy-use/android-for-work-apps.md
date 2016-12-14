---
title: "Déployer des applications sur des appareils Android for Work| Microsoft Intune"
description: "Utilisez cette rubrique pour synchroniser, puis déployer des applications sur des appareils Android for Work à partir du Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/6/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 35ee89248e42c67f48d4607f5d415896e35b90e9


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Comment déployer des applications sur des appareils Android for Work avec Microsoft Intune

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Le déploiement d’applications sur des appareils Android for Work diffère de leur déploiement sur des appareils Android standard. Toutes les applications que vous installez pour Android for Work proviennent du Google Play for Work Store. Vous vous connectez au Store, recherchez les applications souhaitées et les approuvez.
L’application apparaît ensuite dans le nœud **Applications achetées en volume** de la console Intune. À partir de là, vous pouvez gérer le déploiement de l’application de la même façon que pour toute autre application.
En outre, si vous avez créé vos propres applications métier, vous pouvez les déployer. Pour ce faire, vous devez vous inscrire pour obtenir un compte de développeur Google, qui vous permet de publier des applications sur une zone privée du Google Play Store, puis de les synchroniser avec Intune.

## <a name="before-you-start"></a>Avant de commencer

1. Vérifiez que vous avez configuré Intune et Android for Work pour qu’ils collaborent sous l’onglet **Admin** de la console Intune.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchroniser une application à partir du Google Play for Work Store


1. Accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
2. Dans le Store, recherchez l’application que vous souhaitez déployer à l’aide d’Intune.
3. Dans la page de l’application que vous avez choisie, choisissez **Approuver**. Dans cet exemple, vous avez choisi l’application Microsoft Excel.<br>
  ![Exemple d’approbation d’une application](/intune/deploy-use/media/approve.png)
4. Une fenêtre de l’application s’ouvre, vous demandant d’accorder des autorisations pour que l’application puisse effectuer diverses opérations. Vous devez choisir **Approuver** pour continuer.<br>
  ![Exemple d’approbation d’autorisations pour une application](/intune/deploy-use/media/approve-app-permissions.png)
5. Après quelques instants, un message de confirmation apparaît indiquant que l’application a été approuvée et qu’elle est disponible dans votre console d’administration informatique.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publier, puis synchroniser, une application métier à partir du Google Play for Work Store

1. Accédez à la Console développeur Google Play, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work. Si vous vous connectez pour la première fois, vous devez vous inscrire et payer des frais pour devenir membre du programme de développement Google.
3. Dans la console, sélectionnez **Ajouter une nouvelle application**.
4. Vous chargez votre application et fournissez des informations la concernant de la même manière que vous publiez une application sur le Google Play Store. Toutefois, vous devez sélectionner le paramètre **(<*nom de l’organisation*>) ** comme indiqué ci-dessous.<br>
  ![Option permettant de mettre l’application à la disposition de votre organisation uniquement](/intune/deploy-use/media/restrict.png)<br>
Ainsi, l’application est uniquement disponible pour votre organisation et n’est pas disponible dans le Google Play Store public.
Pour plus d’informations sur la façon de charger et publier des applications Android, consultez l’[aide Google Developer Console](https://support.google.com/googleplay/android-developer/answer/113469).
5. Une fois que vous avez publié votre application, accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
6. Dans le nœud **Applications** du Store, vérifiez que vous pouvez voir l’application que vous avez publiée. Notez qu’elle a été automatiquement approuvée pour être synchronisée avec Intune.

## <a name="deploy-an-android-for-work-app"></a>Déployer une application Android for Work

En règle générale, Intune se synchronise deux fois par jour avec le Google Play for Work Store. Si vous avez approuvé une application à partir du Store et qu’elle ne trouve pas encore dans le nœud **Applications achetées en volume** de l’espace de travail **Applications**, vous pouvez forcer une synchronisation immédiate comme suit :

1. Dans la [console Administrateur Intune](https://manage.microsoft.com), cliquez sur **Admin** > **Gestion des appareils mobiles** > **Android for Work**.
2. Dans la page **Configuration de la gestion des appareils mobiles Android for Work**, choisissez **Synchroniser maintenant**.
3. La page affiche également l’heure et l’état de la dernière synchronisation.

Quand l’application s’affiche dans le nœud **Applications achetées en volume** de l’espace de travail **Applications**, vous pouvez [la déployer comme toute autre application](deploy-apps-in-microsoft-intune.md). Vous pouvez déployer l’application sur des groupes d’utilisateurs uniquement. Vous ne pouvez sélectionner que les actions **Obligatoire** et **Désinstaller**. À compter d’octobre 2016, nous commençons à ajouter l’action de déploiement **Disponible** aux nouveaux clients.

Une fois l’application déployée, elle est installée sur les appareils que vous avez ciblés. L’utilisateur de l’appareil ne fait pas l’objet d’une demande d’approbation.



<!--HONumber=Dec16_HO2-->


