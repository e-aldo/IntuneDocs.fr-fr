---
title: "Installer Office 365 sur des appareils macOS à l’aide de Microsoft Intune"
titlesuffix: 
description: "Découvrez comment utiliser Microsoft Intune pour installer des applications Office 365 sur des appareils macOS."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Guide pratique pour affecter Office 365 à des appareils macOS avec Microsoft Intune

Le type **Application du Windows Store** vous permet d’affecter facilement des applications Office 365 à des appareils macOS. Ce type d’application vous permet d’installer Word, Excel, PowerPoint, Outlook et OneNote. Ces applications bénéficient également de Microsoft AutoUpdate (MAU) qui garantit que les applications sont sécurisées et à jour. Les applications souhaitées apparaissent sous la forme d’une application unique dans la liste des applications de la console Intune.


## <a name="before-you-start"></a>Avant de commencer

Avant d’ajouter Office 365 à des appareils macOS, vous devez comprendre les détails suivants :

- Les appareils sur lesquels vous déployez ces applications doivent exécuter macOS 10.10 ou ultérieur.
- Intune prend uniquement en charge l’ajout d’applications Office incluses dans la suite Office 2016 pour Mac.
- Si des applications Office sont ouvertes au moment où Intune installe la suite d’applications, les utilisateurs finaux risquent de perdre les données contenues dans des fichiers non enregistrés.

## <a name="create-and-configure-the-app-suite"></a>Créer et configurer la suite d’applications

Ajoutez Office 365 à l’aide du panneau **Apps**.
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Applications** dans la section **Gérer**. 
5. Choisissez **Ajouter** pour afficher le panneau **Ajouter une application**.
6. Dans la liste **Type d’application**, sélectionnez **macOS** dans le groupe **Suite Office 365**.
7. Sélectionnez **Informations sur la suite d’applications** pour fournir des informations sur la suite d’applications. Ces informations vous permettent d’identifier la suite d’applications dans Intune. Elles aident aussi les utilisateurs finaux à la trouver dans l’application Portail d’entreprise.
8.  Spécifiez les informations suivantes :
    - **Nom de la suite** : entrez le nom de la suite d’applications tel qu’il apparaît dans le portail d’entreprise. Vérifiez que chaque nom de suite que vous utilisez est unique. Si un même nom de suite d’applications est utilisé deux fois, une seule application est proposée aux utilisateurs du portail d’entreprise.
    - **Description de la suite** : entrez la description de la suite d’applications.
    - **Éditeur** : Microsoft apparaît comme éditeur.
    - **Catégorie** : sélectionnez une ou plusieurs des catégories d’applications intégrées ou une catégorie que vous avez créée. Ce paramètre permet de faciliter la recherche de la suite d’applications pour les utilisateurs qui naviguent dans le portail d’entreprise.
    - **Proposer cette application dans le portail d’entreprise** : ce paramètre met en avant la suite d’applications dans la page principale du portail d’entreprise quand les utilisateurs cherchent des applications.
    - **URL d’informations** (facultatif) : Entrez l’URL d’un site web qui contient des informations sur cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **URL de déclaration de confidentialité** (facultatif) : Entrez l’URL d’un site web qui contient des informations de confidentialité de cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **Développeur** : Microsoft apparaît comme développeur.
    - **Propriétaire** : Microsoft apparaît comme propriétaire.
    - **Notes** (facultatif) : Entrez les éventuelles remarques à associer à cette application.
    - **Logo** : le logo Office 365 est affiché avec l’application quand les utilisateurs naviguent dans le portail d’entreprise.
9.  Cliquez sur **OK** dans le panneau **Informations sur l’application**.
10. Cliquez sur **Ajouter** dans le panneau **Ajouter une application**.
    La suite apparaît dans la liste des applications en tant qu’entrée unique.

## <a name="configure-app-assignments"></a>Configurer les affectations d’applications

Dans cette étape, configurez les affectations de la suite d’applications. 

1. Sélectionnez la suite d’applications **Office 365** dans la liste des applications pour afficher le panneau de vue d’ensemble **Office 365**.
2. Cliquez sur **Affectations** dans le panneau **Office 365**.
3. Cliquez sur **Ajouter un groupe** pour ajouter un groupe pouvant utiliser la suite d’applications. Le panneau **Ajouter un groupe** s’affiche.
3. Affectez la valeur **Obligatoire** à **Type d’affectation**.
4. Affectez la suite aux groupes que vous choisissez. Pour plus d’informations, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](apps-deploy.md).

    >[!Note]
    > Pour tous les groupes pour lesquels la suite d’applications Office 365 est obligatoire, celle-ci ne peut pas être désinstallée par le biais de Microsoft Intune.

5. Sélectionnez **OK** dans le panneau **Affecter**.
6. Sélectionnez **OK** dans le panneau **Ajouter un groupe**.
7. Sélectionnez **Enregistrer** pour valider vos affectations.

## <a name="next-steps"></a>Étapes suivantes

- Pour en savoir plus sur l’ajout d’applications Office 365 à un appareil Windows 10, consultez [Guide pratique pour affecter des applications Office 365 ProPlus 2016 à des appareils Windows 10 avec Microsoft Intune](apps-add-office365.md).
- Pour en savoir plus sur l’inclusion et l’exclusion d’affectations d’application pour des groupes d’utilisateurs, consultez [Inclure et exclure des affectations d’applications](apps-inc-exl-assignments.md).
