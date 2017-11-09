---
title: "Guide pratique pour surveiller les affectations et les informations d’applications"
titlesuffix: Azure portal
description: "Une fois que vous avez affecté une application à des utilisateurs ou des appareils, utilisez ces informations pour surveiller son état."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Guide pratique pour surveiller les affectations et les informations d’applications avec Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune propose plusieurs façons de surveiller les propriétés des applications que vous gérez, ainsi que leur état d’affectation.

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
3. Dans la charge de travail **Applications mobiles**, choisissez **Applications** dans le groupe **Gérer**.
     
    ![Panneau d’état de l’installation de l’application.](./media/monitor-apps.png)
5. Dans le panneau de la liste des applications, choisissez une application. Vous verrez alors le panneau <*nom_application*> **État de l’installation de l’appareil**.

Le rapport sur l’état de l’installation de l’appareil contient les colonnes suivantes :

1.  **Nom de l’appareil** Nom du type d’appareil.
2.  **Nom d’utilisateur** Nom de l’utilisateur.
3.   **Plateforme** Système d’exploitation installé sur l’appareil.
4.  **Version** Numéro de version de l’application.
5.   **État** Les états possibles des applications sont : **Installé**, **Non installé**, **Installation en attente** et **Erreur**.
6. **Détails du statut** Description explicite du statut de l’application sur l’appareil.
7. **Dernier archivage** Date du dernier archivage de l’appareil dans Intune.

Effectuez ensuite l’une des actions suivantes pour en savoir plus sur vos applications et leurs affectations.

## <a name="general"></a>Général

- **Vue d’ensemble** : fournit une vue d’ensemble de l’application et des informations sur l’état des affectations de cette application. Vous pouvez choisir l’un des graphiques pour ouvrir le panneau **État de l’installation de l’appareil** ou **État de l’installation de l’utilisateur** afin d’obtenir des informations plus détaillées.

## <a name="manage"></a>Gérer

- **Propriétés** : vous permet d’afficher et de changer les informations sur l’application sélectionnée. Pour plus d’informations sur les propriétés des applications, consultez le [Guide pratique pour ajouter une application à Microsoft Intune](apps-add.md).
- **Affectations** : fournit des informations sur les affectations de cette application. Pour plus d’informations, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Surveillance

- **État de l’installation de l’appareil** : fournit des informations détaillées pour chaque appareil auquel vous avez affecté l’application sélectionnée, notamment le nom de l’appareil, le système d’exploitation, la date du dernier archivage de l’appareil dans Intune et l’état de l’installation de l’application.
- **État de l’installation de l’utilisateur** : fournit des informations détaillées sur l’utilisateur auquel vous avez affecté l’application sélectionnée, notamment le nombre d’installations de l’application dont l’utilisateur dispose sur tous ses appareils et des informations sur les éventuels échecs d’installation.