---
title: "Guide pratique d’ajout d’applications web à Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : en savoir plus sur l’ajout d’applications web à Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4188957e263717d416853f308a50e3dbd7a9244a
ms.openlocfilehash: 4f8af0008300550d284957c1002be779e0e53f79

---

# <a name="how-to-add-web-apps-to-intune"></a>Guide pratique d’ajout d’applications web à Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Analyse + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Informations de l’application**.
7. Dans le panneau **Modifier l’application**, configurez les informations suivantes. Quand vous avez terminé, cliquez sur **Ajouter** :
    - **URL de l’application** : entrez l’URL du site web qui héberge l’application que vous souhaitez déployer.
    - **Nom de l’application** : saisissez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise.
    - **Description de l’application :** saisissez la description de l’application. Ce libellé s'affichera dans le portail d'entreprise pour les utilisateurs finaux.
    - **Éditeur :** entrez le nom de l’éditeur de cette application.
    - **Catégorie** : (facultatif) sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Cela permettra aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **Exiger l'ouverture de ce lien dans Managed Browser** : lorsque vous déployez un lien vers un site web ou une application web pour les utilisateurs, ils ne peuvent l’ouvrir que dans le navigateur géré Intune. Ce navigateur doit être installé sur leur appareil.
    - **Télécharger icône** : téléchargez une icône qui sera associée à l'application. Il s'agit de l'icône qui s'affichera avec l'application lorsque les utilisateurs parcourront le portail d'entreprise.
8. Lorsque vous avez terminé, dans le panneau **Ajouter une application**, choisissez **Enregistrer**.

L’application que vous avez créée s’affichera dans la liste des applications, où vous pouvez l’affecter aux groupes que vous choisissez. Pour plus d’aide, consultez [Guide pratique d’affectation d’applications à des groupes](/intune-azure/manage-apps/deploy-apps).


<!--HONumber=Feb17_HO1-->


