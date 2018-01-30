---
title: "Installer Office 365 sur des appareils macOS à l’aide d’Intune"
titlesuffix: Azure portal
description: "Découvrez comment utiliser Intune pour faciliter l’installation d’applications Office 365 sur des appareils macOS."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1573a6a2ca78489df46c9e08ebbfe9a16b0731c7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Guide pratique pour affecter Office 365 à des appareils macOS avec Microsoft Intune

Ce type d’application vous permet d’affecter facilement des applications Office 365 à des appareils macOS. Ce nouveau type d’application vous permet d’installer Word, Excel, PowerPoint, Outlook et OneNote. Ces applications bénéficient également de Microsoft AutoUpdate (MAU) qui garantit que les applications sont sécurisées et à jour. Les applications souhaitées apparaissent sous la forme d’une application unique dans la liste des applications de la console Intune.


## <a name="before-you-start"></a>Avant de commencer

- Les appareils sur lesquels vous déployez ces applications doivent exécuter macOS 10.10 ou ultérieur.
- Intune prend uniquement en charge l’ajout d’applications Office incluses dans la suite Office 2016 pour Mac.
- Si des applications Office sont ouvertes au moment où Intune installe la suite d’applications, les utilisateurs finaux risquent de perdre les données contenues dans des fichiers non enregistrés.


## <a name="get-started"></a>Mise en route
Ajoutez Office 365 à l’aide du panneau **Apps**.
1.  Connectez-vous au portail Azure.
2.  Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Applications mobiles**.
4.  Dans la charge de travail **Applications mobiles**, choisissez **Applications** dans le groupe **Gérer**. Choisissez **Ajouter**.
5.  Dans le panneau **Ajouter une application**, choisissez **Office 365** > **macOS**.
6.  Sélectionnez **Ajouter**.

## <a name="configure-the-app-suite"></a>Configurer la suite d’applications

Indiquez des informations sur la suite d’applications. Ces informations vous permettent d’identifier la suite dans Intune. Elles aident aussi les utilisateurs finaux à trouver la suite dans l’application Portail d’entreprise.

1.  Dans le panneau **Ajouter une application**, choisissez **Informations sur la suite d’applications**.
2.  Spécifiez les informations suivantes :
    - **Nom de la suite** : entrez le nom de la suite d’applications tel qu’il apparaît dans le portail d’entreprise. Vérifiez que chaque nom de suite que vous utilisez est unique. Si un même nom de suite d’applications est utilisé deux fois, une seule application est proposée aux utilisateurs du portail d’entreprise.
    - **Description de la suite** : entrez la description de la suite d’applications.
    - **Éditeur** : Microsoft apparaît comme éditeur.
    - **Catégorie** : si vous le souhaitez, sélectionnez une ou plusieurs des catégories d’applications intégrées ou que vous avez créées. Ceci permet de faciliter la recherche de la suite d’applications pour les utilisateurs qui naviguent dans le portail d’entreprise.
    - **Proposer cette application dans le portail d’entreprise** : met en avant la suite d’applications dans la page principale du portail d’entreprise quand les utilisateurs cherchent des applications.
    - **URL d’informations** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations sur cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **URL de confidentialité** : si vous le souhaitez, saisissez l’URL d’un site Web qui contient des informations de confidentialité pour cette application. Cette URL est présentée aux utilisateurs du portail d’entreprise.
    - **Développeur** : Microsoft apparaît comme développeur.
    - **Propriétaire** - Microsoft apparaît comme propriétaire.
    - **Notes** : saisissez les éventuelles notes que vous souhaitez associer à cette application.
    - **Charger l’icône** : chargez une icône qui s’affiche avec l’application quand les utilisateurs parcourent le portail d’entreprise.
3.  Sélectionnez **OK**. La suite apparaît dans la liste des applications en tant qu’entrée unique.

## <a name="configure-app-assignments"></a>Configurer les affectations d’applications

Dans cette étape, configurez les affectations de la suite d’applications. Notez que le type d’app disponible sera bientôt proposé.

1.  Sélectionnez la suite d’applications dans la liste des applications, puis sélectionnez **Affectations**.
2.  Choisissez **Sélectionner des groupes**.
3.  Affectez la suite aux groupes que vous choisissez. Pour plus d’informations, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](/intune/apps-deploy).
4.  Pour chaque groupe, sélectionnez **Installation requise**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Sélectionnez **Enregistrer** pour valider vos affectations.

## <a name="next-steps"></a>Étapes suivantes

Pour en savoir plus sur l’ajout d’applications Office 365 à un appareil Windows 10, consultez [Guide pratique pour affecter des applications Office 365 ProPlus 2016 à des appareils Windows 10 avec Microsoft Intune](/intune/apps-add-office365).
