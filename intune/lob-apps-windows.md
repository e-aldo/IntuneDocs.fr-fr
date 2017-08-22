---
title: "Guide pratique pour ajouter des applications métier Windows à Intune"
titleSuffix: Intune on Azure
description: "En savoir plus sur l’ajout des applications métier Windows à Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 94c8c2ac583cca88b051404999664bf93c02a9f5
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications métier Windows à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Étape 1 : spécifier le fichier d’installation de logiciel

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Application métier**.

## <a name="step-2---configure-the-app-package-file"></a>Étape 2 : configurer le fichier de package d’application

1. Dans le panneau **Ajouter une application**, choisissez **Package d’application**.
2. Dans le panneau de fichiers **Package d’application**, cliquez sur le bouton Parcourir et sélectionnez un fichier d’installation Windows avec l’extension **.msi**, **.appx** ou **.appxbundle**.
3. Quand vous avez terminé, cliquez sur **OK**.


## <a name="step-3---configure-app-information"></a>Étape 3 : configurer les informations de l’application

1. Dans le panneau **Ajouter une application**, choisissez **Package d’application**.
2. Dans le panneau **Informations sur l’application**, configurez les informations suivantes (certaines valeurs de ce panneau peuvent être complétées automatiquement) :
    - **Nom** : entrez le nom de l’application tel qu’il est affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d’application existe deux fois, une seule application est proposée aux utilisateurs du portail d’entreprise.
    - **Description :** entrez la description de l’application. La description est présentée aux utilisateurs du portail d’entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **Catégorie** : sélectionnez une ou plusieurs des catégories d’applications intégrées ou une catégorie que vous avez créée. En classant les applications par catégorie, vous facilitez la recherche de l’application pour les utilisateurs qui naviguent dans le portail d’entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **URL d’information** : si vous le souhaitez, entrez l’URL d’un site web qui contient des informations sur l’application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **URL de la déclaration de confidentialité** : si vous le souhaitez, entrez l’URL d’un site web qui contient des informations de confidentialité relatives à l’application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **Arguments de ligne de commande** : si vous le souhaitez, entrez tous les arguments de ligne de commande que vous voulez appliquer au fichier .msi pendant son exécution, comme **/q**.
    - **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Logo** : chargez l’icône qui est associée à l’application. Cette icône s’affiche avec l’application quand les utilisateurs parcourent le portail d'entreprise.
3. Quand vous avez terminé, cliquez sur **OK**.

## <a name="step-4---finish-up"></a>Étape 4 : terminer

1. Dans le panneau **Ajouter une application**, vérifiez que vous avez correctement configuré les informations de l’application.
2. Sélectionnez **Ajouter** pour charger l’application sur Intune.

## <a name="next-steps"></a>Étapes suivantes

L’application que vous avez créée s’affiche dans la liste des applications. Vous pouvez maintenant l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).
