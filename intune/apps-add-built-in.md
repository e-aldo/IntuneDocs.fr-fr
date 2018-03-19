---
title: "Ajouter des applications intégrées sur des appareils mobiles à l’aide de Microsoft Intune"
titlesuffix: 
description: "Découvrez comment utiliser Intune pour faciliter l’installation d’applications intégrées sur des appareils mobiles."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7d90f86babc2f73acd5ccd1b454c636c6d4f79b2
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Comment ajouter des applications intégrées à Microsoft Intune

Le type d’application **Intégré** vous permet d’attribuer facilement des applications gérées organisées, comme les applications Office 365, à des appareils iOS et Android. Vous pouvez affecter des applications spécifiques à ce type d’application, comme Excel, OneDrive, Outlook, Skype et d’autres. Après avoir ajouté une application, son type est **Application iOS intégrée** ou **Application Android intégrée**. En utilisant le type d’application Intégré, vous pouvez choisir les applications spécifiques à publier pour les utilisateurs d’appareil.

 Dans les éditions antérieures de la console Intune, Intune fournissait plusieurs applications Office 365 gérées par défaut, comme Outlook et OneDrive. Le type de ces applications gérées était « Application de l’App Store iOS gérée » ou « Application Android gérée ». Nous vous recommandons d’utiliser le type d’application intégrée au lieu de « Application de l’App Store iOS gérée » ou « Application Android gérée ». Le type d’application intégrée fournit davantage de flexibilité pour modifier et supprimer des applications Office 365.

>[!NOTE]
>Les applications Office 365 par défaut marquées comme « Application de l’App Store iOS gérée » et « Application Android gérée » sont supprimées de la liste d’applications quand toutes les affectations sont supprimées.

## <a name="add-built-in-app"></a>Ajouter une application intégrée

Les étapes suivantes vous permettent d’ajouter une application intégrée à vos applications disponibles dans Microsoft Intune.
1.  Connectez-vous au portail Azure.
2.  Affichez le panneau Microsoft Intune :choisissez **Plus de services** > **Monitoring + Gestion** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Applications mobiles**.
4.  Dans le panneau **Applications mobiles**, choisissez **Applications** sous le groupe **Gérer**.
5.  Choisissez **Ajouter** pour ajouter une nouvelle application.
6.  Dans le panneau **Ajouter** une application, choisissez **Application intégrée** dans la liste **Type d’application**.
7.  Cliquez sur **Sélectionner une application** pour choisir les applications intégrées à ajouter.
8.  Dans le panneau des applications intégrées, sélectionnez les applications à ajouter.
9.  Dans le panneau **Ajouter une application**, cliquez sur **Ajouter** pour inclure les applications.


## <a name="configure-app-information"></a>Configurer les informations de l’application

Vous pouvez modifier les informations de l’application intégrée. Ces informations vous permettent d’identifier l’application dans Intune. Elles aident aussi les utilisateurs finaux à trouver l’application dans l’application Portail d’entreprise.
1.  Dans le panneau **Applications mobiles - Applications**, choisissez l’application intégrée à modifier. Un panneau s’affiche pour l’application intégrée.
2.  Sélectionnez l’option **Propriétés** dans le groupe **Gérer**.
3.  Sélectionnez l’option **Configurer** pour modifier les informations de l’application intégrée.
4.  Dans le panneau **Informations sur l’application**, configurez les informations suivantes :
    -   **Nom** : Entrez le nom de l’application intégrée tel qu’il est affiché dans le portail d’entreprise. Tous les noms que vous utilisez doivent être uniques. Si le même nom d’application existe deux fois, une seule application est proposée aux utilisateurs du portail d’entreprise.
    -   **Description :** entrez la description de l’application. 
    -   **Éditeur :** entrez le nom de l’éditeur de l’application.
    -   **Catégorie** : Facultatif, sélectionnez une ou plusieurs des catégories d’applications intégrées. La définition de cette option facilite la recherche de l’application pour les utilisateurs qui naviguent dans le portail d’entreprise.
    -   **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    -   **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    -   **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    -   **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    -   **Propriétaire** : Si vous le souhaitez, entrez un nom pour le propriétaire de cette application, par exemple, Département des ressources humaines.
    -   **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    -   **Charger l’icône** : chargez une icône qui s’affiche avec l’application quand les utilisateurs parcourent le portail d’entreprise.
3.  Quand vous avez terminé, cliquez sur **OK** dans le panneau **Informations sur l’application**.
4.  Cliquez sur **Enregistrer** dans le panneau **Propriétés**.

## <a name="next-steps"></a>Étapes suivantes

- Vous pouvez maintenant affecter les applications aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).
