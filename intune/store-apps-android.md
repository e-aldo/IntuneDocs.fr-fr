---
title: "Guide pratique pour ajouter des applications Android Store à Microsoft Intune"
titleSuffix: 
description: "Découvrez plus d’informations sur l’ajout d’applications du store Android dans Microsoft Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 87fea551dea1f80ee071fe6b477b84729e000874
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications Android Store à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Avant d’affecter une application à un appareil ou un groupe d’utilisateurs, vous devez d’abord l’ajouter à Microsoft Intune. Les étapes suivantes permettent d’ajouter une application du store Android à Intune à partir du portail Azure.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Monitoring + Gestion**.
3. Dans le volet **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Applications** sous la section **Gérer**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le volet **Ajouter une application**, sélectionnez **Android** sous les types **application Store** disponibles.
7. Sélectionnez **Configurer** pour configurer les informations sur l’application suivantes : en fonction de l’application que vous avez choisie, certaines valeurs de ce volet peuvent avoir été automatiquement renseignées :
    - **Nom** : entrez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description :** entrez la description de l’application. Cette description est visible par les utilisateurs dans le portail d'entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **URL de l’App Store** : Entrez l’URL de l’App Store que vous voulez créer.
    - **Système d’exploitation minimal** : Dans la liste, choisissez la version de système d’exploitation minimale sur laquelle l’application peut être installée. Si vous affectez l’application à un appareil avec un système d’exploitation antérieur, elle ne sera pas installée.
    - **Catégorie** (facultatif) : sélectionnez une ou plusieurs des catégories de l’application intégrée, ou une catégorie que vous avez créée. Cela permettra aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **URL d’informations** (facultatif) : Entrez l’URL d’un site web qui contient des informations sur cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **URL de déclaration de confidentialité** (facultatif) : Entrez l’URL d’un site web qui contient des informations de confidentialité de cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **Développeur** (facultatif) : Entrez le nom du développeur de l’application.
    - **Propriétaire** (facultatif) : Entrez un nom pour le propriétaire de cette application, par exemple, **Service des ressources humaines**.
    - **Notes** (facultatif) : Entrez les éventuelles remarques à associer à cette application.
    - **Logo** (facultatif) : Chargez une icône à associer à l’application. Cette icône s’affiche avec l’application quand les utilisateurs parcourent le portail d’entreprise.
8. Cliquez sur **OK** une fois les informations définies pour l’application.
9. Cliquez sur **Ajouter** pour ajouter l’application.

L’application créée s’affiche dans la liste des applications, où vous pouvez l’affecter aux groupes de votre choix. 

##<a name="next-steps"></a>Étapes suivantes

- [Guide pratique pour affecter des applications à des groupes](apps-deploy.md)