---
title: "Guide pratique pour ajouter des applications à Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Préversion Azure : Ces procédures vous aident à préparer vos applications dans Intune à être affectées aux utilisateurs et appareils. "
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e4a6aaa1a8e23dc2c58345f73ff8db86018843e1
ms.openlocfilehash: fe12a6b890c2d5cba874e820afbe7671b754deb5
ms.lasthandoff: 04/11/2017

---

# <a name="how-to-add-an-app-to-microsoft-intune"></a>Guide pratique pour ajouter une application à Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Avant de pouvoir gérer et attribuer des applications pour vos utilisateurs, vous devez les ajouter à Intune. Intune prend en charge un large éventail de types d’application différents, et les options peuvent être différentes pour chaque type.

Intune prend en charge l’ajout et l’affectation de ces types d’application :

![Types d’applications pris en charge par Intune](./media/app-types.png)

Les plateformes suivantes sont prises en charge. Cliquez sur une des rubriques pour plus d’informations sur l’ajout de chaque type d’application.

- [Applications de l’App Store Android](/intune-azure/manage-apps/android-store-app)
- [Applications de l’App Store iOS](/intune-azure/manage-apps/ios-store-app)
- [Applications Web (pour toutes les plateformes)](/intune-azure/manage-apps/web-app)
- [Application du Windows Phone 8.1 Store](/intune-azure/manage-apps/windows-phone-8-1-store-app)
- [Applications Windows Store](/intune-azure/manage-apps/windows-store-app)

> [!NOTE]
> Quand vous ajoutez et déployez une application à partir d’un app store, les utilisateurs finaux doivent avoir un compte sur ce store pour pouvoir installer l’application.

## <a name="cloud-storage-space"></a>Espace de stockage cloud
Toutes les applications que vous créez en utilisant le type d’installation de programme d’installation de logiciel (par exemple, une application métier) sont empaquetées et chargées dans le stockage cloud Microsoft Intune. Un abonnement d’essai à Intune inclut 2 Go de stockage cloud, utilisé pour stocker les applications gérées et les mises à jour. Votre abonnement complet inclut 20 Go d’espace de stockage.

Vous pouvez utiliser la méthode de paiement d’origine pour acheter du stockage supplémentaire pour Intune.  Si vous avez payé par facture ou carte de crédit, visitez le [portail Gestion des abonnements](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Dans le cas contraire, contactez votre partenaire ou vendeur.

La configuration requise pour l’espace de stockage cloud est la suivante :

-   Tous les fichiers d’installation de l’application doivent être dans le même dossier.
-   La taille maximale de chaque fichier que vous chargez s’élève à 2 Go.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Comment créer et modifier des catégories pour les applications 

Les catégories d’applications peuvent être utilisées pour vous aider à trier les applications pour les rendre plus faciles finaux à rechercher pour les utilisateurs dans le portail d’entreprise. Vous pouvez affecter une ou plusieurs catégories à une application, par exemple, **Applications pour développeurs** ou **Applications de communication**. Lorsque vous ajoutez une application à Intune, vous avez la possibilité de sélectionner la catégorie souhaitée. Utilisez les rubriques spécifiques à la plateforme pour ajouter une application et attribuer des catégories. Pour créer et modifier vos propres catégories, procédez comme suit : 

1. Connectez-vous au portail Azure. 
2. Choisissez **Plus de services** > **Surveillance + Gestion** > **Intune**. 
3. Dans le panneau **Intune**, choisissez **Gérer les applications**. 
4. Dans la charge de travail **Mobile Apps**, choisissez **Installation** > **Catégories d’application**. 
5. Dans le panneau **Catégories d’application**, la liste des catégories actuelles s’affiche. Sélectionnez une des actions suivantes : 
    - **Créer une catégorie** : dans le panneau **Créer une catégorie**, saisissez un nom pour la nouvelle catégorie. Les noms peuvent être entrés dans une seule langue et ne sont pas traduits par Intune. Quand vous avez terminé, cliquez sur **Créer**.
    - **Modifier une catégorie** : pour n’importe quelle catégorie dans la liste, choisissez «**...** ». Dans le panneau **Propriétés**, vous pouvez entrer un nouveau nom pour la catégorie, ou supprimer la catégorie.




