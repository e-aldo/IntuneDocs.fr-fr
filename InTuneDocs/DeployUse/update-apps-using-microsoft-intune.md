---
title: "Mettre à jour des applications | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: 0581d1476fba5bedcdd4446df20f8f92b151f41b
ms.openlocfilehash: 9e5b8f4a467e8e58cc2f8fa495b5f008eee7e35b


---

# Mettre à jour des applications à l'aide de Microsoft Intune
Microsoft Intune peut vous aider à gérer les mises à jour des applications. Utilisez les informations de cette rubrique pour découvrir comment mettre à jour des applications quand une nouvelle version est nécessaire.

## Mise à jour des applications
Quand une nouvelle version d’une application que vous avez déployée est publiée, Intune vous permet de mettre à jour et de déployer la version la plus récente de l’application. Vous pouvez uniquement remplacer un déploiement par une version plus récente de la même application (en utilisant le même identificateur). Vous ne pouvez pas utiliser les mises à jour d'application pour mettre à jour un déploiement avec un package d'application différent.

> [!IMPORTANT]
> Lorsque vous déployez une application avec une action de déploiement de type **Installation requise** et que vous changez ultérieurement l'action de déploiement en **Installation disponible**, les mises à jour de l'application ne sont pas installées automatiquement sur les appareils où l'application a été installée avant que la modification du déploiement n'ait eu lieu. Pour résoudre ce problème, vous pouvez procédez comme suit :
> 
> -   L’utilisateur de l’appareil doit accéder au portail d’entreprise, sélectionner l’application installée et choisir **Installer**.
> -   Modifiez l'action de déploiement en **Désinstaller**et, une fois que l'application a été désinstallée, redéployez l'application avec une action de déploiement de type **Installation disponible**.

### Pour mettre à jour une application

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Applications** &gt; **Applications**.

2.  Dans la liste **Applications** , sélectionnez l’application à mettre à jour, puis choisissez **Modifier**.

3.  Dans l'Assistant **Modifier le logiciel** , fournissez les nouveaux détails du package d'application.

4.  Quand vous avez terminé, choisissez **Mettre à jour**.

La prochaine fois que les appareils vérifient si des applications sont disponibles, l'application est automatiquement mise à jour vers la dernière version.
Pour les applications installées à partir d’un package d’application (applications cœur de métier), l’application est automatiquement mise à niveau pour les déploiements obligatoires et disponibles, à condition que l’application ait le même identificateur.
Pour les applications déployées via un lien redirigeant vers un magasin, la mise à jour est gérée par le magasin d’origine de l’application.






<!--HONumber=Jul16_HO2-->


