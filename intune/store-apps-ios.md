---
title: "Guide pratique pour ajouter des applications de l’App Store iOS à Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Découvrez comment ajouter des applications de l’App Store iOS à Intune."
keywords: Intune
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7dcb857127b3c36d2b90208aac9b8ad901e31d89
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/04/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications de l’App Store iOS à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Aidez-vous des informations contenues dans cette rubrique pour ajouter des applications de l’App Store iOS à Intune.

>[!NOTE]
>Bien que les utilisateurs d’appareils iOS puissent supprimer certaines applications iOS intégrées telles que Bourse et Plans, vous ne pouvez pas vous servir de Microsoft Intune pour redéployer ces applications. Si des utilisateurs finaux suppriment ces applications, ils doivent se rendre sur l’App Store et les réinstaller manuellement.

## <a name="before-you-start"></a>Avant de commencer

Vous pouvez uniquement affecter des applications à l’aide de cette méthode si elles sont gratuites dans l’App Store. Si vous souhaitez affecter des applications payantes à l’aide d’Intune, envisagez d’utiliser le [programme d’achat en volume (VPP) iOS](vpp-apps-ios.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Étape 1 : Rechercher l’application dans le Store

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > Applications.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Rechercher sur l’App Store**.
7. Dans le panneau **Apple App Store**, sélectionnez les paramètres régionaux du pays de l’App Store.
8. Dans la zone de recherche, tapez le nom (ou une partie du nom). Intune recherche le Store et retourne la liste des résultats pertinents.
9. Dans la liste, sélectionnez l’application souhaitée, puis cliquez sur **OK**.

## <a name="step-2---configure-app-information"></a>Étape 2 : Configurer les informations de l’application

1. Dans le panneau **Ajouter une application**, choisissez **Informations de l’application**.
2. Dans le panneau **Modifier l’application**, configurez les informations de l’application. Une fois cela fait, cliquez sur **Ajouter**. Selon l’application choisie, certaines valeurs de ce panneau peuvent avoir été renseignées automatiquement :
- **Nom** : tapez le nom de l’application à afficher dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d’application existe en double, le portail d’entreprise ne montre qu’une seule application aux utilisateurs.
- **Description** : tapez une description de l’application à afficher aux utilisateurs dans le portail d’entreprise.
- **Éditeur :** : tapez le nom de l’éditeur de l’application.
- **URL de l’App Store** : tapez l’URL de l’App Store que vous voulez créer.
- **Pays/région du Store** : sélectionnez les paramètres régionaux du pays de l’App Store.
- **Système d’exploitation minimal** : dans la liste, choisissez le système d’exploitation minimal sur lequel l’application peut être installée. L’application ne sera pas installée sur un appareil avec un système d’exploitation antérieur.
- **Type d’appareil applicable** : dans la liste, choisissez les appareils qui sont utilisés par l’application.
- **Catégorie** (facultatif). Sélectionnez une ou plusieurs des catégories d’applications intégrées ou une catégorie que vous avez créée. Les catégories permettent aux utilisateurs de trouver facilement l’application quand ils parcourent le portail d’entreprise.
- **Proposer cette application dans le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise quand les utilisateurs cherchent des applications.
- **URL d’informations** : si vous le souhaitez, tapez l’URL d’un site web qui contient des informations sur cette application. L’URL est présentée aux utilisateurs dans le portail d’entreprise.
- **URL de la déclaration de confidentialité** : si vous le souhaitez, tapez l’URL d’un site web qui contient des informations sur la confidentialité pour cette application. L’URL est présentée aux utilisateurs dans le portail d’entreprise.
- **Développeur** : si vous le souhaitez, tapez le nom du développeur de l’application. Ce champ est visible seulement par un administrateur ; les utilisateurs finaux ne le voient pas.
- **Propriétaire** : si vous le souhaitez, tapez un nom pour le propriétaire de cette application, par exemple **Département des ressources humaines**.  Ce champ est visible seulement par un administrateur ; les utilisateurs finaux ne le voient pas.
- **Remarques** : tapez les éventuelles remarques que vous voulez associer à cette application. Ce champ est visible seulement par un administrateur ; les utilisateurs finaux ne le voient pas.
- **Logo** : chargez une icône qui est associée à l’application. Cette icône s’affiche avec l’application quand les utilisateurs parcourent le portail d'entreprise.
3. Quand vous avez terminé, dans le panneau **Ajouter une application**, choisissez **OK**.

L’application que vous avez créée apparaît dans la liste des applications, où vous pouvez l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).
