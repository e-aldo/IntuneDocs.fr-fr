---
title: "Guide pratique pour ajouter des applications de l’App Store iOS à Intune | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez comment ajouter des applications de l’App Store iOS à Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 011f33d1d8569a079f73baaca6ba2a665131691d
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications de l’App Store iOS à Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="before-you-start"></a>Avant de commencer

Vous pouvez uniquement affecter des applications à l’aide de cette méthode si elles sont gratuites dans l’App Store. Si vous souhaitez affecter des applications payantes à l’aide d’Intune, envisagez d’utiliser le [programme d’achat en volume (VPP) iOS](ios-vpp-apps.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Étape 1 : recherche de l’application dans la boutique

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Mobile Apps**, choisissez **Gérer** > Applications.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Rechercher sur l’App Store**.
7. Dans le panneau **Apple App Store**, entrez le nom (ou une partie du nom) dans la zone de recherche. Intune recherche le magasin et renvoie la liste des résultats pertinents.
8. Dans la liste, sélectionnez l’application souhaitée, puis cliquez sur **OK**.

## <a name="step-2---configure-app-information"></a>Étape 2 : configurer les informations de l’application

1. Dans le panneau **Ajouter une application**, choisissez **Informations de l’application**.
2. Dans le panneau **Modifier l’application**, configurez les informations suivantes. Une fois cela fait, cliquez sur **Ajouter**. Selon l’application choisie, certaines valeurs de ce panneau peuvent avoir été renseignées automatiquement :
- **Nom de l’application** : saisissez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description de l’application :** saisissez la description de l’application. Ce libellé s'affichera dans le portail d'entreprise.
- **Éditeur :** entrez le nom de l’éditeur de l’application.
- **URL de la boutique d’applications** : saisissez l’URL de la boutique d’applications que vous souhaitez créer.
- **Système d’exploitation minimal** : dans la liste, choisissez le système d’exploitation minimal sur lequel l’application peut être installée. Si vous affectez l’application à un appareil avec un système d’exploitation antérieur, elle ne sera pas installée.
- **Catégorie** (facultatif). Sélectionnez une ou plusieurs des catégories d’applications intégrées ou une catégorie que vous avez créée. Cela permettra aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
- **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
- **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL s'affichera dans le portail d'entreprise.
- **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL s'affichera dans le portail d'entreprise.
- **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
- **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
- **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
- **Télécharger icône** : téléchargez une icône qui sera associée à l'application. Il s'agit de l'icône qui s'affichera avec l'application lorsque les utilisateurs parcourront le portail d'entreprise.
3. Lorsque vous avez terminé, dans le panneau **Ajouter une application**, choisissez **Enregistrer**.

L’application que vous avez créée s’affichera dans la liste des applications, où vous pouvez l’affecter aux groupes que vous choisissez. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](deploy-apps.md).

