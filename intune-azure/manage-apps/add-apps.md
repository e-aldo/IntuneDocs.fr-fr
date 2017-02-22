---
title: "Guide pratique d’ajout d’applications à Microsoft Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : ces procédures vous aident à préparer vos applications dans Intune à être affectées aux utilisateurs et appareils. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 969ce8deae9142944f3481172277dc252baa5779
ms.openlocfilehash: a7838f57b2eb8bd36a875f7b5b001b12eafcbf8d

---

# <a name="how-to-add-an-app"></a>Guide pratique d’ajout d’une application 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Avant de pouvoir gérer et attribuer des applications pour vos utilisateurs, vous devez les ajouter à Intune. Intune prend en charge un large éventail de types d’application différents, et les options peuvent être différentes pour chaque type.

Intune prend en charge l’ajout et l’affectation de ces types d’application :

![Types d’applications pris en charge par Intune](./media/app-types.png)

Les plateformes suivantes sont prises en charge. Cliquez sur une des rubriques pour plus d’informations sur l’ajout de chaque type d’application.

- [Applications métier Android](/intune-azure/manage-apps/android-lob-app)
- [Applications de l’App Store Android](/intune-azure/manage-apps/android-store-app)
- [Applications métier iOS](/intune-azure/manage-apps/ios-lob-app)
- [Applications de l’App Store iOS](/intune-azure/manage-apps/ios-store-app)
- [Applications Web (pour toutes les plateformes)](/intune-azure/manage-apps/web-app)
- [Application du Windows Phone 8.1 Store](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Applications Windows Store](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Quand vous ajoutez et déployez une application à partir d’un app store, les utilisateurs finaux doivent avoir un compte sur ce store pour pouvoir installer l’application.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Guide pratique de création et modification des catégories pour les applications 

Les catégories d’applications peuvent être utilisées pour vous aider à trier les applications pour les rendre plus faciles finaux à rechercher pour les utilisateurs dans le portail d’entreprise. Vous pouvez affecter une ou plusieurs catégories à une application, par exemple, **Applications pour développeurs** ou **Applications de communication**. Lorsque vous ajoutez une application à Intune, vous avez la possibilité de sélectionner la catégorie souhaitée. Utilisez les rubriques spécifiques à la plateforme pour ajouter une application et attribuer des catégories. Pour créer et modifier vos propres catégories, procédez comme suit : 

1. Connectez-vous au portail Azure. 
2. Choisissez **Plus de services** > **Analyse + Gestion** > **Intune**. 
3. Dans le panneau **Intune**, choisissez **Gérer les applications**. 
4. Dans la charge de travail **Mobile Apps**, choisissez **Installation** > **Catégories d’application**. 
5. Dans le panneau **Catégories d’application**, la liste des catégories actuelles s’affiche. Sélectionnez une des actions suivantes : 
    - **Créer une catégorie** : dans le panneau **Créer une catégorie**, saisissez un nom pour la nouvelle catégorie. Les noms peuvent être entrés dans une seule langue et ne sont pas traduits par Intune. Quand vous avez terminé, cliquez sur **Créer**.
    - **Modifier une catégorie** : pour n’importe quelle catégorie dans la liste, choisissez «**... ** ». Dans le panneau **Propriétés**, vous pouvez entrer un nouveau nom pour la catégorie, ou supprimer la catégorie. --->






<!--HONumber=Feb17_HO1-->


