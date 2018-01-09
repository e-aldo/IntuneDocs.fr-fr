---
title: "Guide pratique d’ajout d’applications de la boutique d’applications Windows Phone 8.1 à Intune"
titleSuffix: Azure portal
description: "Découvrez comment ajouter des applications de Windows Phone 8.1 Store pour Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b5ee86715338bd7df432e9f7007ad0be211d3130
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-add-windows-phone-81-store-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications du Windows Phone 8.1 Store à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Informations de l’application**.
7. Dans le panneau **Modifier l’application**, configurez les informations suivantes. Une fois cela fait, cliquez sur **Ajouter**. Selon l’application choisie, certaines valeurs de ce panneau peuvent avoir été renseignées automatiquement :
    - **Nom de l’application** : saisissez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description de l’application :** saisissez la description de l’application. Ce libellé s'affichera dans le portail d'entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **URL de l’App Store** : entrez l’URL de l’App Store que vous souhaitez créer.
    - **Système d’exploitation minimal** : dans la liste, choisissez le système d’exploitation minimal sur lequel l’application peut être installée. Si vous affectez l’application à un appareil avec un système d’exploitation antérieur, elle ne sera pas installée.
    - **Catégorie** : (facultatif) sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Cela permettra aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Charger l’icône** : chargez une icône qui sera associée à l'application. Il s'agit de l'icône qui s'affichera avec l'application lorsque les utilisateurs parcourront le portail d'entreprise.
8. Lorsque vous avez terminé, dans le panneau **Ajouter une application**, choisissez **Enregistrer**.

L’application que vous avez créée s’affichera dans la liste des applications, où vous pouvez l’affecter aux groupes que vous choisissez. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).