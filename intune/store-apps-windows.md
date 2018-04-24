---
title: Guide pratique pour ajouter des applications du Microsoft Store à Microsoft Intune
titleSuffix: ''
description: Découvrez comment ajouter des applications du Microsoft Store (Windows Store) à Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 511cf2e01a2f5db93f0e0db9dbe2a32326c17723
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Ajouter des applications du Microsoft Store à Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pour pouvoir affecter, surveiller, configurer ou protéger des applications, vous devez les ajouter à Intune. Les étapes suivantes vous permettent d’ajouter une application du Microsoft Store à Microsoft Intune.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le volet **Ajouter une application**, choisissez un **Type d’application** de **Windows**, puis choisissez **Informations sur l’application**.
7. Dans le volet **Informations sur l’application**, configurez les informations suivantes. Une fois terminé, cliquez sur **OK**. Selon l’application choisie, certaines valeurs de ce volet peuvent avoir été renseignées automatiquement :
    - **Nom** : entrez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description** : Entrez une description de l’application à afficher aux utilisateurs dans le portail d’entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **URL de l’App Store** : Entrez l’URL de l’App Store que vous voulez créer.
    - **Catégorie (facultatif)** : sélectionnez une ou plusieurs des catégories d’applications intégrées ou une catégorie que vous avez créée, ce qui permet aux utilisateurs de rechercher plus facilement l’application lorsqu’ils parcourent le portail de l’entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL s'affichera dans le portail d'entreprise.
    - **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Logo** : chargez une icône qui est associée à l’application. Cette icône qui s’affiche avec l’application quand les utilisateurs parcourent le portail d’entreprise.
8. Quand vous avez terminé, dans le volet **Ajouter une application**, choisissez **Ajouter**.

L’application que vous avez créée s’affichera dans la liste des applications, où vous pouvez l’affecter aux groupes que vous choisissez. 

## <a name="next-steps"></a>Étapes suivantes
- [Guide pratique pour affecter des applications à des groupes](apps-deploy.md)