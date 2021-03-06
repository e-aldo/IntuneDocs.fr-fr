---
title: Ajouter une application métier Windows Phone à Microsoft Intune
titlesuffix: ''
description: Découvrez comment ajouter une application métier Windows Phone à Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 25f71122fdcf932f0318923f44f3703700f48558
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Ajouter une application métier Windows Phone à Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Utilisez les informations contenues dans cet article pour ajouter une application métier Windows Phone à Microsoft Intune. Une application métier est une application que vous ajoutez à Intune à partir d’un fichier d’installation d’application. Les applications de ce genre sont généralement écrites en interne. Intune installe l’application métier sur l’appareil de l’utilisateur. 

## <a name="step-1-specify-the-software-setup-file"></a>Étape 1 : Spécifier le fichier d’installation du logiciel

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, sélectionnez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, sélectionnez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, sélectionnez **Ajouter**.
6. Dans le volet **Ajouter une application**, sélectionnez **Application métier**.

## <a name="step-2-configure-the-app-package-file"></a>Étape 2 : Configurer le fichier de package d’application

1. Dans le volet **Ajouter une application**, sélectionnez **Fichier de package d’application**.
2. Dans le volet **Fichier de package d’application**, sélectionnez le bouton Parcourir. Sélectionnez ensuite un fichier d’installation Windows Phone avec l’extension **.xap**.
3. Quand vous avez terminé, sélectionnez **OK**.


## <a name="step-3-configure-app-information"></a>Étape 3 : Configurer les informations sur l’application

1. Dans le volet **Ajouter une application**, sélectionnez **Informations sur l’application**.
2. Dans le volet **Informations sur l’application**, configurez les informations relatives à l’application. Selon l’application choisie, certaines valeurs de ce volet peuvent avoir été renseignées automatiquement.
    - **Nom** : entrez le nom de l’application tel qu’il apparaît dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d’application existe deux fois, une seule application apparaît dans le portail d’entreprise.
    - **Description** : entrez la description de l’application. La description apparaît dans le portail d’entreprise.
    - **Éditeur** : entrez le nom de l’éditeur de l’application.
    - **Ignorer la version de l’application** : choisissez **Oui** si le développeur met automatiquement à jour l’application.
    - **Catégorie** : sélectionnez une ou plusieurs catégories d’applications intégrées, ou sélectionnez une catégorie que vous avez créée. Les catégories permettent aux utilisateurs de trouver facilement l’application quand ils parcourent le portail d’entreprise.
    - **Proposer cette application dans le portail d’entreprise** : met en valeur l’application dans la page principale du portail d’entreprise quand les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, entrez l’URL d’un site web contenant des informations sur cette application. L’URL apparaît dans le portail d’entreprise.
    - **URL de confidentialité** : si vous le souhaitez, entrez l’URL d’un site web qui contient des informations de confidentialité pour cette application. L’URL apparaît dans le portail d’entreprise.
    - **Développeur** : si vous le souhaitez, entrez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, entrez le nom du propriétaire de cette application. Par exemple : **Ressources humaines**.
    - **Notes** : entrez les éventuelles notes à associer à cette application.
    - **Logo** : chargez une icône qui est associée à l’application. Cette icône s’affiche avec l’application quand les utilisateurs parcourent le portail d’entreprise.
3. Quand vous avez terminé, sélectionnez **OK**.

## <a name="step-4-finish-up"></a>Étape 4 : Terminer

1. Dans le volet **Ajouter une application**, vérifiez que les informations sont correctement configurées.
2. Sélectionnez **Ajouter** pour charger l’application sur Intune.

## <a name="next-steps"></a>Étapes suivantes

- L’application que vous avez créée apparaît dans la liste des applications. Vous pouvez maintenant l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).

- Découvrez plus d’informations sur les façons dont vous pouvez surveiller les propriétés et l’affectation de votre application. Consultez [Guide pratique pour surveiller les affectations et les informations d’applications](apps-monitor.md).

- Découvrez plus d’informations sur le contexte de votre application dans Intune. Consultez [Vue d’ensemble des cycles de vie des appareils et des applications](introduction-device-app-lifecycles.md).
