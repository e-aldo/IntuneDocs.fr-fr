---
title: "Guide pratique pour surveiller les affectations et les informations d’applications | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Une fois que vous avez affecté une application à des utilisateurs ou des appareils, utilisez ces informations pour surveiller son état."
keywords: 
author: robstackmsft
ms.author: robstack
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7c39c904cd2a7bd20525d9072067c6e484b4437a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Guide pratique pour surveiller les affectations et les informations d’applications avec Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

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
