---
title: Guide pratique pour surveiller les affectations et les informations d’applications
titlesuffix: Microsoft Intune
description: Une fois que vous avez affecté une application à des utilisateurs ou à des appareils, utilisez ces informations pour surveiller son état.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01b7972a6a4dbb641f4c656190324d8572f9010c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Guide pratique pour surveiller les affectations et les informations d’applications avec Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune propose plusieurs façons de surveiller les propriétés des applications que vous gérez, ainsi que leur état d’affectation.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans le groupe **Surveillance + Gestion**.
3. Choisissez **Applications mobiles**, puis **Applications** dans le groupe **Gérer**.
5. Dans la liste des applications, choisissez une application à surveiller. Le panneau de l’application apparaît avec une vue d’ensemble de l’état de l’appareil et de l’état de l’utilisateur.

## <a name="app-overview-blade"></a>Panneau Vue d’ensemble de l’application

Vous pouvez utiliser le panneau de cette application particulière pour passer en revue les détails sur l’état d’une application dans votre environnement.

### <a name="essentials"></a>Base
La section **Bases** contient les informations suivantes sur l’application :

 | **Détails de l’application**            | **Description**                                                      |
|------------------------|------------------------------------------------------------------|
| **Éditeur**          | Éditeur de l’application.                                            |
| **Système d'exploitation**   | Système d’exploitation de l’application (Windows, iOS, Android, etc.) |
| **Créé le**             | Date et heure de création de cette révision.                         |
| **Affecté**           | **Oui** ou **Non** si l’application a été affectée.                  |

### <a name="device-and-user-status-graphs"></a>Graphiques des états de l’appareil et de l’utilisateur
Les graphiques présente les chiffres liés aux états suivants :

| **État de l’appareil**       | **Description**                                       |
|-----------------------|-------------------------------------------------------|
| **Installé**         | Nombre d’applications installées.                         |
| **Non installé**     | Nombre d’applications non installées.                     |
| **Échec**            | Nombre d’installations ayant échoué.                   |
| **Installation en attente**   | Nombre d’applications en passe d’être installées. |
| **Non applicable**           | Nombre d’applications où l’état n’est pas applicable.            |

### <a name="device-install-status"></a>État de l’installation de l’appareil

La liste des états de l’appareil s’affiche quand vous sélectionnez **État de l’installation de l’appareil** dans la section **Surveiller**. Le tableau des détails inclut les colonnes suivantes :

| **Colonne de l’appareil**      | **Description**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nom de l’appareil**      | Nom de l’appareil sur les plateformes qui autorisent le nommage d’un appareil. Sur d’autres plateformes, Intune crée un nom à partir d’autres propriétés. Cet attribut ne peut pas être disponible pour tous les appareils.                                                                       |
| **Nom d’utilisateur**        | Le nom de l'utilisateur.                                                                                                                                                                                                                                      |
| **Plateforme**         | Système d’exploitation de l’appareil (Windows, iOS, Android, etc.)                                                                                                                                                                                           |
| **Version**          | Numéro de version de l’application. Pour les applications métier, le numéro de version complet de l’application s’affiche. Le numéro de version complet identifie une version spécifique de l’application. Le numéro apparaît sous la forme _Version_(_Build_). Par exemple, 2.2(2.2.17560800). |
| **Statut**           | État de l’application.                                                                                                                                                                                                                                     |
| **Détails de l’état**   | Détails de l’état.                                                                                                                                                                                                                                     |
| **Dernier archivage**    | Date de la dernière synchronisation de l’appareil avec Intune.                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>État de l’installation de l’utilisateur

La liste des états de l’utilisateur s’affiche quand vous sélectionnez **État de l’installation de l’utilisateur** dans la section **Surveiller**. Le tableau des détails inclut les colonnes suivantes :

| **Colonne de l’utilisateur**     | **Description**                           |
|---------------------|-------------------------------------------|
| **Nom**            | Nom de l’utilisateur dans Azure AD.         |
| **Nom d’utilisateur**       | Nom unique de l’utilisateur.              |
| **Installations**   | Nombre d’installations d’applications utilisées par l’utilisateur. |
| **Échecs**        | Nombre d’installations ayant échoué effectuées par l’utilisateur.     |
| **Non installé**   | Nombre d’installations non installées par l’utilisateur. |


## <a name="next-steps"></a>Étapes suivantes

- Pour en savoir plus sur l’utilisation de vos données Intune, consultez [Utiliser l’entrepôt de données Intune](reports-nav-create-intune-reports.md).
- Pour en savoir plus sur les stratégies de configuration d’applications, consultez [Stratégies de configuration d’applications pour Intune](app-configuration-policies-overview.md).