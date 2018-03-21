---
title: "Guide pratique pour ajouter des applications métier Windows à Microsoft Intune"
titlesuffix: 
description: "Découvrez comment ajouter des applications métier Windows à Microsoft Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e23ddb70bb2c12e1278f4167ec074972eeba3003
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications métier Windows à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Une application métier est une application que vous ajoutez à partir d’un fichier d’installation d’application. Ces types d’applications sont généralement écrites en interne. Les étapes suivantes fournissent des conseils pour vous aider à ajouter une application métier Windows à Microsoft Intune.

## <a name="step-1---specify-the-software-setup-file"></a>Étape 1 : spécifier le fichier d’installation de logiciel

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Monitoring + Gestion**.
3. Dans le volet **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le volet **Ajouter une application**, choisissez **Application métier**.

## <a name="step-2---configure-the-app-package-file"></a>Étape 2 : configurer le fichier de package d’application

1. Dans le volet **Ajouter une application**, choisissez le fichier **Package de l’application**.
2. Dans le volet du fichier **Package de l’application**, choisissez le bouton Parcourir et sélectionnez un fichier d’installation Windows avec l’extension **.msi**, **.appx** ou **.appxbundle**.
3. Quand vous avez terminé, cliquez sur **OK**.


## <a name="step-3---configure-app-information"></a>Étape 3 : configurer les informations de l’application

1. Dans le volet **Ajouter une application**, choisissez le fichier **Package de l’application**.
2. Dans le volet**Informations sur l’application**, configurez les informations suivantes (certaines valeurs de ce volet peuvent être complétées automatiquement) :
    - **Nom** : entrez le nom de l’application tel qu’il est affiché dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d’application existe deux fois, une seule application est proposée aux utilisateurs du portail d’entreprise.
    - **Description :** entrez la description de l’application. La description est présentée aux utilisateurs du portail d’entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **Ignorer la version de l’application** : définissez cette valeur sur **Oui** si l’application est automatiquement mise à jour par son développeur.
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

## <a name="step-4---finish-up"></a>Étape 4 : Terminer

1. Dans le volet **Ajouter une application**, vérifiez que vous avez correctement configuré les informations de l’application.
2. Sélectionnez **Ajouter** pour charger l’application sur Intune.

## <a name="step-5---update-a-line-of-business-app"></a>Étape 5 : Mise à jour d’une application métier

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configuring-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Configuration d’une application MSI mobile avec mise à jour automatique pour ignorer le processus de vérification de version

Vous pouvez configurer une application MSI mobile avec mise à jour automatique connue pour ignorer le processus de vérification de version. Certaines applications basées sur le programme d’installation MSI sont automatiquement mises à jour par le développeur de l’application. Pour ces applications MSI mises à jour automatiquement, vous pouvez configurer le paramètre **Ignorer la version de l’application** dans le panneau **Informations sur l’application**. Quand vous passez ce paramètre sur **Oui**, Microsoft Intune n’impose pas la version de l’application installée sur le client Windows. Cette fonctionnalité est utile pour éviter d’introduire une condition de concurrence. Par exemple, ce type de condition de concurrence peut se produire quand l’application est mise à jour automatiquement par le développeur de l’application et aussi par Intune. Les deux peuvent essayer d’appliquer une version de l’application sur un client Windows, générant ainsi un conflit.

## <a name="next-steps"></a>Étapes suivantes

- L’application que vous avez créée s’affiche dans la liste des applications. Vous pouvez maintenant l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).

- Découvrez plus d’informations sur les façons dont vous pouvez surveiller les propriétés et l’affectation de votre application. Pour plus d’informations, consultez [Guide pratique pour surveiller les affectations et les informations d’applications](apps-monitor.md).

- Découvrez plus d’informations sur le contexte de votre application dans Intune. Pour plus d’informations, consultez [Vue d’ensemble des cycles de vie des appareils et des applications](introduction-device-app-lifecycles.md).
