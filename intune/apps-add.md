---
title: "Guide pratique pour ajouter des applications à Microsoft Intune"
titleSuffix: Intune on Azure
description: "Ces procédures vous aident à préparer vos applications dans Intune à être affectées aux utilisateurs et appareils. \""
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6a4dfa9e0066a2ac6f410aa9f8e4d77a40484ea5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Guide pratique pour ajouter une application à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Avant de pouvoir gérer et attribuer des applications pour vos utilisateurs, vous devez les ajouter à Intune. Intune prend en charge un large éventail de types d’application différents, et les options peuvent être différentes pour chaque type.

Intune vous permet d’ajouter et d’affecter les types d’application suivants :

![Types d’applications pris en charge par Intune](./media/app-types.png)

Les plateformes suivantes sont prises en charge.

- Applications de l’App Store Android
- Applications métier Android
- Applications de l’App Store iOS
- Applications métier iOS
- Applications web
- Application du Windows Phone 8.1 Store
- Applications métier Windows Phone (fichiers .xap)
- Applications du Windows Store
- Applications métier Windows (fichiers .msi uniquement)

>[!TIP]
> Une application métier est une application que vous n’installez pas à partir d’un App Store mais à partir du fichier d’installation de l’application. Par exemple, pour installer une application métier iOS, vous ajoutez le fichier d’archive de l’application (portant l’extension .ipa). Il s’agit généralement d’applications que vous avez développées en interne.

## <a name="before-you-start"></a>Avant de commencer

Tenez compte des points suivants avant de commencer à ajouter et affecter des applications.

- Quand vous ajoutez et affectez une application à partir d’un Store, les utilisateurs finaux doivent avoir un compte sur ce Store pour pouvoir installer l’application.
- Certaines applications ou certains éléments que vous affectez peuvent dépendre d’applications iOS intégrées. Par exemple, si vous affectez un livre à partir de l’App Store iOS, l’application iBooks doit être présente sur l’appareil. Si vous avez supprimé l’application iBook intégrée, vous ne pouvez pas utiliser Intune pour la réactiver.

## <a name="cloud-storage-space"></a>Espace de stockage cloud
Toutes les applications que vous créez en utilisant le type d’installation de programme d’installation de logiciel (par exemple, une application métier) sont empaquetées et chargées dans le stockage cloud Intune. Un abonnement d’essai à Intune inclut 2 Go de stockage cloud, utilisé pour stocker les applications gérées et les mises à jour. Un abonnement complet inclut 20 Go d’espace de stockage.

Vous pouvez utiliser la méthode de paiement d’origine pour acheter du stockage supplémentaire pour Intune.  Si vous avez payé par facture ou carte de crédit, visitez le [portail Gestion des abonnements](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Dans le cas contraire, contactez votre partenaire ou vendeur.

La configuration requise pour l’espace de stockage cloud est la suivante :

-   Tous les fichiers d’installation de l’application doivent être dans le même dossier.
-   La taille maximale de chaque fichier que vous chargez s’élève à 2 Go.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Comment créer et modifier des catégories pour les applications

Vous pouvez utiliser les catégories d’applications pour trier les applications, afin que les utilisateurs finaux puissent les trouver plus facilement dans le portail d’entreprise. Vous pouvez affecter une ou plusieurs catégories à une application, par exemple, **Applications pour développeurs** ou **Applications de communication**.
Lorsque vous ajoutez une application à Intune, vous avez la possibilité de sélectionner la catégorie souhaitée. Utilisez les rubriques spécifiques à la plateforme pour ajouter une application et attribuer des catégories. Pour créer et modifier vos propres catégories, procédez comme suit :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Mobile Apps**, choisissez **Installation** > **Catégories d’application**.
5. Dans le panneau **Catégories d’application**, la liste des catégories actuelles s’affiche. Sélectionnez une des actions suivantes :
    - **Créer une catégorie** : dans le panneau **Créer une catégorie**, saisissez un nom pour la nouvelle catégorie. Les noms peuvent être entrés dans une seule langue et ne sont pas traduits par Intune. Quand vous avez terminé, cliquez sur **Créer**.
    - **Modifier une catégorie** : pour n’importe quelle catégorie dans la liste, choisissez «**...**  ». Dans le panneau **Propriétés**, vous pouvez entrer un nouveau nom pour la catégorie, ou supprimer la catégorie.


## <a name="apps-added-automatically-by-intune"></a>Applications automatiquement ajoutées par Intune

Les applications suivantes, publiées par Microsoft, sont intégrées à Intune et prêtes à être affectées :

|||
|-|-|
|Nom|Plate-forme|Type d’application|
|Azure Information Protection|Android|Managed Android store app|
|Dynamics CRM for Phones|Android|Managed Android store app|
|Dynamics CRM for Tablets|Android|Managed Android store app|
|Excel|iOS|Managed iOS store app|
|Excel|Android|Managed Android store app|
|Managed Browser|Android|Managed Android store app|
|Managed Browser|iOS|Managed iOS store app|
|Microsoft Dynamics CRM on Phones|iOS|Managed iOS store app|
|Microsoft Dynamics CRM on Tablets|iOS|Managed iOS store app|
|Microsoft Power BI|iOS|Managed iOS store app|
|Microsoft Power BI|Android|Managed Android store app|
|Microsoft SharePoint|iOS|Managed iOS store app|
|Microsoft SharePoint|Android|Managed Android store app|
|Microsoft Teams|Android|Managed Android store app|
|Microsoft Teams|iOS|Managed iOS store app|
|OneDrive Entreprise|iOS|Managed iOS store app|
|OneDrive Entreprise|Android|Managed Android store app|
|OneNote|iOS|Managed iOS store app|
|Outlook|Android|Managed Android store app|
|Outlook|iOS|Managed iOS store app|
|Groupes Outlook|Android|Managed Android store app|
|Groupes Outlook|iOS|Managed iOS store app|
|PowerPoint|iOS|Managed iOS store app|

## <a name="next-steps"></a>Étapes suivantes

Choisissez une des rubriques suivantes afin de savoir comment ajouter à Intune des applications pour chaque plateforme :

- [Applications de l’App Store Android](store-apps-android.md)
- [Applications métier Android](lob-apps-android.md)
- [Applications de l’App Store iOS](store-apps-ios.md)
- [Applications métier iOS](lob-apps-ios.md)
- [Applications Web (pour toutes les plateformes)](web-app.md)
- [Application du Windows Phone 8.1 Store](store-apps-windows-phone-8-1.md)
- [Applications métier Windows Phone](lob-apps-windows-phone.md)
- [Applications Windows Store](store-apps-windows.md)
- [Application métier Windows](lob-apps-windows.md)

