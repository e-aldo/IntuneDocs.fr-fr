---
title: "Guide pratique pour surveiller les affectations et les informations d’applications"
titleSuffix: Intune on Azure
description: "Une fois que vous avez affecté une application à des utilisateurs ou des appareils, utilisez ces informations pour surveiller son état."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a558c7d7c804b62535b2223cde9c409c56f22f6
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Guide pratique pour surveiller les affectations et les informations d’applications avec Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune propose plusieurs façons de surveiller les propriétés des applications que vous gérez, ainsi que leur état d’affectation.

1. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
2. Dans le panneau de liste d’applications, choisissez l’application pour laquelle vous souhaitez voir les informations. Vous verrez alors le panneau <*nom_application*> **État de l’installation de l’appareil** : ![Panneau État de l’installation de l’application.](./media/monitor-apps.png)

Effectuez ensuite l’une des actions suivantes pour en savoir plus sur vos applications et leurs affectations.

## <a name="general"></a>Général

- **Vue d’ensemble** : fournit une vue d’ensemble de l’application et des informations sur l’état des affectations de cette application. Vous pouvez choisir l’un des graphiques pour ouvrir le panneau **État de l’installation de l’appareil** ou **État de l’installation de l’utilisateur** afin d’obtenir des informations plus détaillées.

## <a name="manage"></a>Gérer

- **Propriétés** : vous permet d’afficher et de changer les informations sur l’application sélectionnée. Pour plus d’informations sur les propriétés des applications, consultez le [Guide pratique pour ajouter une application à Microsoft Intune](apps-add.md).
- **Affectations** : fournit des informations sur les affectations de cette application. Pour plus d’informations, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](apps-deploy.md).

## <a name="monitor"></a>Surveillance

- **État de l’installation de l’appareil** : fournit des informations détaillées pour chaque appareil auquel vous avez affecté l’application sélectionnée, notamment le nom de l’appareil, le système d’exploitation, la date du dernier archivage de l’appareil dans Intune et l’état de l’installation de l’application.
- **État de l’installation de l’utilisateur** : fournit des informations détaillées sur l’utilisateur auquel vous avez affecté l’application sélectionnée, notamment le nombre d’installations de l’application dont l’utilisateur dispose sur tous ses appareils et des informations sur les éventuels échecs d’installation.