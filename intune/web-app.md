---
title: "Guide pratique pour ajouter des applications web à Intune"
titleSuffix: Azure portal
description: "En savoir plus sur l’ajout d’applications web à Intune."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6da1441b16a43b5e22bedd9e87970f3388b11b9e
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/30/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications web à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Avant de pouvoir gérer et attribuer une application pour vos utilisateurs, ajoutez cette application à Intune. Intune prend en charge divers types d’applications, y compris les applications web.

> [!Note]
> Les applications web ne sont pas prises en charge sur les appareils Android for Work.

Procédez comme suit pour ajouter une application à Intune comme un raccourci vers une application sur le web :

1. Connectez-vous au portail Azure.
2. Dans **Ressources complémentaires**, recherchez et sélectionnez **Intune**.
3. Dans le panneau **Microsoft Intune**, sélectionnez **Applications mobiles**.
4. Dans le panneau **Applications mobiles**, sélectionnez **Applications**.
5. Au-dessus de la liste des applications, sélectionnez **Ajouter**. Le panneau **Ajouter une application** s’affiche.
6. Dans le panneau **Ajouter une application**, sélectionnez le type **Application web** dans la liste déroulante **Type d’application**.
7. Sélectionnez l’option **Configurer** pour afficher le panneau **Informations sur l’application**.
8. Dans le panneau **Informations sur l’application**, ajoutez les informations suivantes :
    - **Nom** : entrez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise.
    - **Description :** entrez la description de l’application. Ce libellé s'affiche dans le portail d'entreprise pour les utilisateurs finaux.
    - **Éditeur :** entrez le nom de l’éditeur de cette application.
    - **URL de l’application** : entrez l’URL du site web qui héberge l’application que vous souhaitez affecter.
    - **Catégorie** : (facultatif) sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Cette sélection permet aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **Exiger l’ouverture de ce lien dans Managed Browser** : quand vous affectez un lien vers un site web ou une application web aux utilisateurs, ils peuvent l’ouvrir dans Intune Managed Browser. Ce navigateur doit être installé sur leur appareil.
    - **Logo** : chargez un logo associé à l’application. Il s’agit du logo affiché avec l’application quand les utilisateurs naviguent dans le portail d’entreprise.
9. Lorsque vous avez terminé, dans le panneau **Ajouter des informations**, sélectionnez **Ok**.
10. Puis, dans le panneau **Ajouter une application**, sélectionnez **Ajouter**.

L’application que vous avez créée s’affiche dans la liste des applications, où vous pouvez l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).