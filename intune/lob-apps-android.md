---
title: "Guide pratique pour ajouter des applications métier Android à Intune"
titlesuffix: Azure portal
description: "Découvrez comment ajouter des applications métier Android à Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b2aa6893e1d01fe83e92c711c7a487f49b92706
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Guide pratique pour ajouter des applications métier Android à Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Étape 1 : spécifier le fichier d’installation de logiciel

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
5. Au-dessus de la liste des applications, choisissez **Ajouter**.
6. Dans le panneau **Ajouter une application**, choisissez **Application métier**.

## <a name="step-2---configure-the-app-package-file"></a>Étape 2 : configurer le fichier de package d’application

1. Dans le panneau **Ajouter une application**, choisissez **Package d’application**.
2. Dans le panneau **Package d’application**, cliquez sur le bouton Parcourir et sélectionnez un fichier d’installation Android avec l’extension **.apk**.
3. Quand vous avez terminé, cliquez sur **OK**.


## <a name="step-3---configure-app-information"></a>Étape 3 : configurer les informations de l’application

1. Dans le panneau **Ajouter une application**, choisissez **Package d’application**.
2. Dans le panneau **Informations sur l’application**, ajoutez les détails nécessaires pour votre application. Selon l’application choisie, certaines valeurs de ce panneau peuvent avoir été renseignées automatiquement :
    - **Nom** : entrez le nom de l’application à afficher dans le portail d’entreprise. Assurez-vous que tous les noms d'application que vous utilisez sont uniques. Si le même nom d'application existe deux fois, seule l'une des applications sera proposée aux utilisateurs du portail d'entreprise.
    - **Description** : entrez la description de l’application à afficher aux utilisateurs dans le portail d’entreprise.
    - **Éditeur :** entrez le nom de l’éditeur de l’application.
    - **Système d’exploitation minimal** : dans la liste, choisissez le système d’exploitation minimal sur lequel l’application peut être installée. Si vous affectez l’application à un appareil avec un système d’exploitation antérieur, elle ne sera pas installée.
    - **Catégorie** : sélectionnez une ou plusieurs des catégories d’applications intégrées ou une catégorie que vous avez créée. Ceci facilite la recherche de l’application pour les utilisateurs qui naviguent dans le portail d’entreprise.
    - **Afficher comme application en une sur le portail d’entreprise** : met en valeur l’application sur la page principale du portail d’entreprise lorsque les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **Développeur** : si vous le souhaitez, saisissez le nom du développeur de l’application.
    - **Propriétaire** : si vous le souhaitez, saisissez un nom pour le propriétaire de cette application, par exemple, **Département des ressources humaines**.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Logo** : chargez l’icône qui est associée à l’application. Il s’agit de l’icône qui est affichée avec l’application quand les utilisateurs naviguent dans le portail d’entreprise.
3. Quand vous avez terminé, cliquez sur **OK**.

## <a name="step-4---finish-up"></a>Étape 4 : Terminer

1. Dans le panneau **Ajouter une application**, vérifiez les détails de votre application.
2. Sélectionnez **Ajouter** pour charger l’application sur Intune.

L’application que vous avez créée s’affichera dans la liste des applications, où vous pouvez l’affecter aux groupes que vous choisissez. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).

## <a name="step-5---update-a-line-of-business-app"></a>Étape 5 : Mise à jour d’une application métier

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]Remarque : Pour que le service Intune parvienne à déployer un nouveau fichier APK sur l’appareil, il faut incrémenter la chaîne android:versionCode dans le fichier AndroidManifest.xml du package APK.

## <a name="next-steps"></a>Étapes suivantes

L’application que vous avez créée s’affiche dans la liste des applications. Vous pouvez maintenant l’affecter aux groupes de votre choix. Pour plus d’aide, consultez [Guide pratique pour attribuer des applications à des groupes](apps-deploy.md).

Découvrez plus d’informations sur les façons dont vous pouvez surveiller les propriétés et l’affectation de votre application. Pour plus d’informations, consultez [Guide pratique pour surveiller les affectations et les informations d’applications](apps-monitor.md).

Découvrez plus d’informations sur le contexte de votre application dans Intune. Pour plus d’informations, consultez [Vue d’ensemble des cycles de vie des appareils et des applications](introduction-device-app-lifecycles.md).
