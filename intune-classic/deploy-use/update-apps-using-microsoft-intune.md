---
title: "Mettre à jour des applications"
description: "Utilisez les informations de cette rubrique pour découvrir comment mettre à jour des applications quand une nouvelle version est nécessaire."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c643ea0e75a3376a30d43fc0c5ac4ef421c65bea
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="update-apps-using-microsoft-intune"></a>Mettre à jour des applications à l'aide de Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune peut vous aider à gérer les mises à jour des applications. Utilisez les informations de cette rubrique pour découvrir comment mettre à jour des applications quand une nouvelle version est nécessaire.

## <a name="how-to-update-apps"></a>Mise à jour des applications
Quand une nouvelle version d’une application que vous avez déployée est publiée, Intune vous permet de mettre à jour et de déployer la version la plus récente de l’application. Vous pouvez uniquement remplacer un déploiement par une version plus récente de la même application (ayant le même identificateur). Vous ne pouvez pas utiliser les mises à jour d'application pour mettre à jour un déploiement avec un package d'application différent.

### <a name="app-identifiers"></a>Identificateurs d’application
L’identificateur d’application est une propriété qui identifie une application de façon unique. Vous ne pouvez pas installer plusieurs copies d’une application ayant le même identificateur. Voici quelques exemples d’identificateurs d’applications :

- **iOS** : ID de lot (par exemple : com.microsoft.excel)
- **Android** : ID de package (par exemple : com.microsoft.excel)
- **Windows Phone** : (programme d’installation xap) ; utilisez l’ID de produit (GUID)
- **Windows** : (appx/appxbundle) ; utilisez le nom complet du package



> [!IMPORTANT]
> Lorsque vous déployez une application avec une action de déploiement de type **Installation requise** et que vous changez ultérieurement l'action de déploiement en **Installation disponible**, les mises à jour de l'application ne sont pas installées automatiquement sur les appareils où l'application a été installée avant que la modification du déploiement n'ait eu lieu. Pour résoudre ce problème, vous pouvez procédez comme suit :
>
> -   L’utilisateur de l’appareil doit accéder au portail d’entreprise, sélectionner l’application installée et choisir **Installer**.
> -   Modifiez l'action de déploiement en **Désinstaller**et, une fois que l'application a été désinstallée, redéployez l'application avec une action de déploiement de type **Installation disponible**.

### <a name="to-update-an-app"></a>Pour mettre à jour une application

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Applications** &gt; **Applications**.

2.  Dans la liste **Applications** , sélectionnez l’application à mettre à jour, puis choisissez **Modifier**.

3.  Dans l'Assistant **Modifier le logiciel** , fournissez les nouveaux détails du package d'application.

4.  Quand vous avez terminé, choisissez **Mettre à jour**.

La prochaine fois que les appareils vérifient si des applications sont disponibles, l'application est automatiquement mise à jour vers la dernière version.
Pour les applications installées à partir d’un package d’application (applications cœur de métier), l’application est automatiquement mise à niveau pour les déploiements obligatoires et disponibles, à condition que l’application ait le même identificateur.

Pour les applications déployées via un lien redirigeant vers un magasin, la mise à jour est gérée par le magasin d’origine de l’application.
