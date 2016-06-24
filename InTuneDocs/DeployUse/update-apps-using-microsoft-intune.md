---
# required metadata

title: Mettre à jour des applications | Microsoft Intune
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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mettre à jour des applications à l'aide de Microsoft Intune
Microsoft Intune peut vous aider à gérer les mises à jour des applications. Utilisez les informations de cette rubrique pour découvrir comment mettre à jour des applications quand une nouvelle version est nécessaire.

## Mise à jour des applications
Quand une nouvelle version d’une application que vous avez déployée est publiée, Intune vous permet de mettre à jour et de déployer la version la plus récente de l’application. Vous pouvez uniquement remplacer un déploiement par une version plus récente de la même application (en utilisant le même identificateur). Vous ne pouvez pas utiliser les mises à jour d'application pour mettre à jour un déploiement avec un package d'application différent.

> [!IMPORTANT]
> Lorsque vous déployez une application avec une action de déploiement de type **Installation requise** et que vous changez ultérieurement l'action de déploiement en **Installation disponible**, les mises à jour de l'application ne sont pas installées automatiquement sur les appareils où l'application a été installée avant que la modification du déploiement n'ait eu lieu. Pour résoudre ce problème, vous pouvez procédez comme suit :
> 
> -   L'utilisateur de l'appareil doit accéder au portail d'entreprise, sélectionner l'application installée et cliquer sur **Installer**.
> -   Modifiez l'action de déploiement en **Désinstaller**et, une fois que l'application a été désinstallée, redéployez l'application avec une action de déploiement de type **Installation disponible**.

### Pour mettre à jour une application

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Applications** &gt; **Applications**.

2.  Dans la liste **Applications** , sélectionnez l'application à mettre à jour, puis cliquez sur **Modifier**.

3.  Dans l'Assistant **Modifier le logiciel** , fournissez les nouveaux détails du package d'application.

4.  Quand vous avez terminé, cliquez sur **Mettre à jour**.

La prochaine fois que les appareils vérifient si des applications sont disponibles, l'application est automatiquement mise à jour vers la dernière version.





<!--HONumber=Jun16_HO1-->


