---
title: Guide pratique pour ajouter des applications web à Microsoft Intune
titleSuffix: ''
description: Découvrez comment ajouter des applications web à Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45253e061039198aee4aa49b2bf879a1b9929e35
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications web à Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune prend en charge divers types d’applications, y compris les applications web. Une application web est une application client-serveur. Le serveur fournit l’application web, qui englobe l’interface utilisateur, le contenu et les fonctionnalités. De plus, les plateformes d’hébergement web modernes offrent généralement, entre autres avantages, la sécurité et l’équilibrage de charge. Une application web est gérée séparément sur le web. Vous utilisez Microsoft Intune pour pointer vers ce type d’application. Vous affectez également les groupes d’utilisateurs qui peuvent accéder à cette application. 

Avant de pouvoir gérer et attribuer une application pour vos utilisateurs, ajoutez cette application à Intune. Intune crée un raccourci vers l’application web sur l’écran d’accueil de l’appareil de l’utilisateur.

> [!Note]
> Les applications web ne sont pas prises en charge sur les appareils Android for Work et macOS.

Procédez comme suit pour ajouter une application à Intune comme un raccourci vers une application sur le web :

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Monitoring + Gestion**.
3. Dans le volet **Microsoft Intune**, sélectionnez **Applications mobiles**.
4. Dans le volet **Applications mobiles**, sélectionnez **Applications**.
5. Au-dessus de la liste des applications, sélectionnez **Ajouter**. Le volet **Ajouter une application** s’affiche.
6. Dans le volet **Ajouter une application**, sélectionnez le type **Lien web** dans la liste déroulante **Type d’application**.
7. Sélectionnez l’option **Configurer** pour afficher le volet **Informations sur l’application**.
8. Dans le volet **Informations sur l’application**, ajoutez les informations suivantes :
    - **Nom** : entrez le nom de l’application tel qu’il sera affiché dans le portail d’entreprise.
    - **Description :** entrez la description de l’application. Ce libellé s'affiche dans le portail d'entreprise pour les utilisateurs finaux.
    - **Éditeur :** entrez le nom de l’éditeur de cette application.
    - **URL de l’application** : entrez l’URL du site web qui héberge l’application que vous souhaitez affecter.
    - **Catégorie** : (facultatif) sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Cette sélection permet aux utilisateurs de trouver aisément l'application lorsqu'ils parcourront le portail d'entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **Exiger l’ouverture de ce lien dans Managed Browser** : quand vous affectez un lien vers un site web ou une application web aux utilisateurs, ils peuvent l’ouvrir dans Intune Managed Browser. Ce navigateur doit être installé sur leur appareil.
    - **Logo** : chargez un logo associé à l’application. Il s’agit du logo affiché avec l’application quand les utilisateurs naviguent dans le portail d’entreprise.
9. Lorsque vous avez terminé, dans le volet **Ajouter des informations**, sélectionnez **Ok**.
10. Puis, dans le volet **Ajouter une application**, sélectionnez **Ajouter**.

> [!Note]
> Les utilisateurs doivent ajouter le widget Intune à leur écran d’accueil pour afficher les applications web qui ont été affectées à des appareils Android.

## <a name="next-steps"></a>Étapes suivantes

- L’application que vous avez créée s’affiche dans la liste des applications, où vous pouvez l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).