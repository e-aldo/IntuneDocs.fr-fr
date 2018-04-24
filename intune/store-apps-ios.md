---
title: Guide pratique pour ajouter des applications de l’App Store iOS à Microsoft Intune
titlesuffix: ''
description: Découvrez comment ajouter des applications de l’App Store iOS à Microsoft Intune.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4eaa4b279ab98c6fe41482628937e0f2b0dc70a5
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications de l’App Store iOS à Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aidez-vous des informations contenues dans cet article pour ajouter des applications de l’App Store iOS à Microsoft Intune. Les applications de l’App Store iOS sont des applications installées par Intune sur l’appareil d’un utilisateur. L’utilisateur fait partie du personnel de votre entreprise. Les applications de l’App Store iOS sont automatiquement mises à jour.

>[!NOTE]
>Bien que les utilisateurs d’appareils iOS puissent supprimer certaines applications iOS intégrées telles que Bourse et Plans, vous ne pouvez pas vous servir d’Intune pour redéployer ces applications. Si des utilisateurs finaux suppriment ces applications, ils doivent se rendre sur l’App Store et les réinstaller manuellement.

## <a name="before-you-start"></a>Avant de commencer

Vous pouvez uniquement affecter des applications à l’aide de cette méthode si elles sont gratuites dans l’App Store. Si vous souhaitez affecter des applications payantes à l’aide d’Intune, envisagez d’utiliser le [programme d’achat en volume (VPP) iOS](vpp-apps-ios.md).

>[!NOTE]
>Chrome et Microsoft Edge sont les navigateurs recommandés quand vous utilisez Microsoft Intune.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Applications** sous la section **Gérer**.
5. Choisissez **Ajouter** à droite du volet **Applications**.
6. Dans la liste **Type d’application**, sélectionnez **iOS** sous les types **Application de Store** disponibles.
7. Choisissez **Rechercher dans l’App Store**.
8. Dans le panneau **Rechercher dans l’App Store**, sélectionnez les paramètres régionaux du pays de l’App Store.
9. Dans la zone de recherche, tapez le nom (ou une partie du nom). Intune recherche le Store et retourne la liste des résultats pertinents.
10. Dans la liste, sélectionnez l’application souhaitée, puis cliquez sur **Sélectionner**.
11. Dans le panneau **Ajouter une application**, choisissez **Informations sur l’application** pour configurer l’application.
12. Renseignez le panneau **Informations sur l’application**. Selon l’application choisie, certaines valeurs de ce panneau peuvent avoir été renseignées automatiquement :
    - **Nom** : tapez le nom de l’application à afficher dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d’application existe en double, le portail d’entreprise ne montre qu’une seule application aux utilisateurs.
    - **Description** : tapez une description de l’application à afficher aux utilisateurs dans le portail d’entreprise.
    - **Éditeur :** : tapez le nom de l’éditeur de l’application.
    - **URL de l’App Store** : tapez l’URL de l’App Store que vous voulez créer.
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
13. Quand vous avez terminé, cliquez sur **OK** dans le panneau **Ajouter des informations**.
14. Cliquez sur **Ajouter** dans le panneau **Ajouter une application**.

L’application que vous avez créée apparaît dans la liste des applications, où vous pouvez l’affecter aux groupes de votre choix.

## <a name="next-steps"></a>Étapes suivantes

- [Guide pratique pour affecter des applications à des groupes](apps-deploy.md)
