---
title: "Déployer des applications sur des appareils Android for Work"
description: "Utilisez cette rubrique pour synchroniser, puis déployer des applications sur des appareils Android for Work à partir du Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: adc4a343e610a1a75f8a5bc51a1894f6fcf998bb
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2017
---
# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Comment déployer des applications sur des appareils Android for Work avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Le déploiement d’applications sur des appareils Android for Work diffère de leur déploiement sur des appareils Android standard. Toutes les applications que vous installez pour Android for Work proviennent du Google Play for Work Store. Vous vous connectez au Store, recherchez les applications souhaitées et les approuvez.
L’application apparaît ensuite dans le nœud **Applications achetées en volume** de la console Intune. À partir de là, vous pouvez gérer le déploiement de l’application de la même façon que pour toute autre application.

En outre, si vous avez créé vos propres applications métier, vous pouvez les déployer en procédant comme suit :
- Inscrivez-vous à un compte de développeur Google qui vous permet de publier des applications dans une zone privée dans Google Play.
- Synchronisez les applications avec Intune.

## <a name="before-you-start"></a>Avant de commencer

Vérifiez que vous avez configuré Intune et Android for Work pour qu’ils collaborent sous l’onglet **Admin** de la console Intune.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchroniser une application à partir du Google Play for Work Store


1. Accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
2. Dans le Store, recherchez l’application que vous souhaitez déployer à l’aide d’Intune.
3. Dans la page de l’application que vous avez choisie, choisissez **Approuver**. Dans cet exemple, vous avez choisi l’application Microsoft Excel.<br>
  ![Exemple d’approbation d’une application](media/approve.png)
4. Une fenêtre de l’application s’ouvre, vous demandant d’accorder des autorisations pour que l’application puisse effectuer diverses opérations. Choisissez **Approuver** pour continuer.<br>
  ![Exemple d’approbation d’autorisations pour une application](media/approve-app-permissions.png)
5. L’application est approuvée et s’affiche dans votre console d’administration informatique.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publier, puis synchroniser, une application métier à partir du Google Play for Work Store

1. Accédez à la Console développeur Google Play, [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work. Si vous vous connectez pour la première fois, vous devez vous inscrire et payer des frais pour devenir membre du programme de développement Google.
3. Dans la console, sélectionnez **Ajouter une nouvelle application**.
4. Vous chargez votre application et fournissez des informations la concernant de la même manière que vous publiez une application sur le Google Play Store. Toutefois, vous devez sélectionner le paramètre **(<*nom de l’organisation*>)** :<br>
  ![Option permettant de mettre l’application à la disposition de votre organisation uniquement](media/restrict.png)<br>
Cette opération assure que l’application est uniquement disponible pour votre organisation et n’est pas disponible dans le Google Play Store public.
Pour plus d’informations sur la façon de charger et publier des applications Android, consultez l’[aide Google Developer Console](https://support.google.com/googleplay/android-developer/answer/113469).
5. Une fois que vous avez publié votre application, accédez au [Google Play for Work Store](https://play.google.com/work). Connectez-vous avec le compte que vous avez utilisé pour configurer la connexion entre Intune et Android for Work.
6. Dans le nœud **Applications** du Store, vérifiez que vous pouvez voir l’application que vous avez publiée. Elle est automatiquement approuvée pour la synchronisation avec Intune.

## <a name="deploy-an-android-for-work-app"></a>Déployer une application Android for Work

Si vous avez approuvé une application à partir du Store et qu’elle ne trouve pas dans le nœud **Applications achetées en volume** de l’espace de travail **Applications**, forcez une synchronisation immédiate en procédant comme suit :

1. Dans la [console Administrateur Intune](https://manage.microsoft.com), cliquez sur **Admin** > **Gestion des appareils mobiles** > **Android for Work**.
2. Dans la page **Configuration de la gestion des appareils mobiles Android for Work**, choisissez **Synchroniser maintenant**.
3. La page affiche également l’heure et l’état de la dernière synchronisation.

Quand l’application s’affiche dans le nœud **Applications achetées en volume** de l’espace de travail **Applications**, vous pouvez [la déployer comme vous le feriez pour toute autre application](deploy-apps-in-microsoft-intune.md). Vous pouvez déployer l’application sur des groupes d’utilisateurs uniquement. Vous ne pouvez sélectionner que les actions **Obligatoire** et **Désinstaller**.

La possibilité de déployer une application comme **Disponible** applique la nouvelle expérience de regroupement et de ciblage. Les comptes de service Intune nouvellement approvisionnés peuvent utiliser cette fonctionnalité dès son lancement. Les clients Intune existants peuvent utiliser cette fonctionnalité une fois que leur locataire a fait l’objet d’une migration vers le portail Intune Azure. Les clients existants peuvent créer un compte Intune d’évaluation pour planifier et tester cette fonctionnalité jusqu’à ce que leur locataire ait été migré.

Une fois l’application déployée, elle est installée sur les appareils que vous avez ciblés. L’utilisateur de l’appareil ne fait pas l’objet d’une demande d’approbation.

## <a name="manage-app-permissions"></a>Gérer les autorisations d’applications
Android for Work nécessite que vous approuviez les applications dans la console web Google Play gérée avant de les synchroniser avec Intune et de les déployer sur l’appareil de vos utilisateurs.  Étant donné qu’Android for Work vous permet de transmettre ces applications silencieusement et automatiquement aux appareils des utilisateurs, vous devez accepter les autorisations des applications au nom de tous vos utilisateurs.  Les utilisateurs finaux ne voient aucune des autorisations des applications lors de l’installation. Il est donc important que vous lisiez et compreniez ces autorisations.

Lorsqu’un développeur d’applications publie une nouvelle version d’une application avec des autorisations mises à jour, ces autorisations ne sont pas acceptées automatiquement, même si vous aviez approuvé les autorisations précédentes. Les appareils qui exécutent l’ancienne version de l’application peuvent continuer à l’utiliser, mais l’application n’est pas mise à niveau tant que ses nouvelles autorisations n’auront pas été approuvées. Les appareils sur lesquels l’application n’est pas installée ne pourront pas procéder à son installation jusqu’à ce que vous en approuviez les nouvelles autorisations.

### <a name="how-to-update-app-permissions"></a>Mise à jour des autorisations d’application

Consultez régulièrement la console Google Play gérée pour y rechercher l’existence de nouvelles autorisations. Vous pouvez configurer Google Play pour vous envoyer à vous-même ou à d’autres un message électronique lorsque de nouvelles autorisations sont requises pour une application approuvée. Si vous affectez une application et que vous constatez qu’elle n’est pas installée sur les appareils, recherchez de nouvelles autorisations en procédant comme suit :

1. Consultez la page http://play.google.com/work
2. Connectez-vous avec le compte Google que vous avez utilisé pour publier et approuver les applications.
3. Consultez l’onglet **Mises à jour** pour savoir si des applications nécessitent une mise à jour.  Les applications répertoriées nécessitent de nouvelles autorisations et ne sont pas affectées avant l’application de ces autorisations.  

Vous pouvez également configurer Google Play pour réapprouver automatiquement les autorisations d’application en fonction de l’application. 
