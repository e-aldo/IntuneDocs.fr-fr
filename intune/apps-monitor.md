---
title: "Guide pratique pour surveiller les affectations et les informations d’applications"
titlesuffix: Microsoft Intune
description: "Une fois que vous avez affecté une application à des utilisateurs ou à des appareils, utilisez ces informations pour surveiller son état."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b88530ef790dd181e81e420c158867d29d1d0d58
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Guide pratique pour surveiller les affectations et les informations d’applications avec Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune propose plusieurs façons de surveiller les propriétés des applications que vous gérez, ainsi que leur état d’affectation.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Choisissez **Applications mobiles**, puis **Applications** dans le groupe **Gérer**.
5. Dans le panneau de la liste des applications, choisissez une application. Vous verrez alors le panneau <*nom_application*> **État de l’installation de l’appareil**.

## <a name="app-overview-blade"></a>Panneau Vue d’ensemble de l’application

Vous pouvez utiliser le panneau <*nom de l’application*> **État de l’installation de l’appareil** pour passer en revue les détails sur l’état d’une application dans votre environnement.

### <a name="essentials"></a>Base

La section **Bases** contient les informations suivantes sur l’application :

 - **Éditeur**  
Éditeur de l’application.
 - **Système d'exploitation**  
Système d’exploitation de l’application (Windows, iOS, Android, etc.)
 - **Créer**  
Heure de création de cette révision.
 - **Affecté**  
**Oui** ou **Non** si l’application a été affectée.

### <a name="status"></a>État
Chaque graphique affiche le nombre d’applications pour chacun des états suivants :

 - **Installé**  
Nombre d’applications installées.
 - **Non installé**  
Nombre d’applications non installées.
 - **Installation en attente**  
Nombre d’applications en passe d’être installées.
 - **Échec**  
Nombre d’installations ayant échoué.
 - **Inconnu.**  
Nombre d’applications avec un état inconnu.

### <a name="device-status"></a>État de l’appareil

État de l’appareil. Graphique en anneau qui affiche l’état d’installation de l’application sur les appareils. Cliquez sur le graphe pour ouvrir la liste des détails sur l’état de l’appareil. Le tableau des détails inclut les colonnes suivantes :

 - **Nom de l’appareil**  
Nom de l’appareil sur les plateformes qui autorisent le nommage d’un appareil. Sur d’autres plateformes, Intune crée un nom à partir d’autres propriétés. Cet attribut ne peut pas être disponible pour tous les appareils.
 - **Nom d’utilisateur**  
Nom de l’utilisateur.
 - **Plateforme**  
Système d’exploitation de l’appareil (Windows, iOS, Android, etc.)
 - **Version**  
Numéro de version de l’application. Pour les applications métier, le numéro de version complet de l’application s’affiche. Le numéro de version complet identifie une version spécifique de l’application. Le numéro apparaît sous la forme _Version_(_Build_). Par exemple, 2.2(2.2.17560800)
 - **Statut**  
État de l’application.
 - **Détails de l’état**  
Détails de l’état.
 - **Dernier archivage**  
Date de la dernière synchronisation de l’appareil avec Intune.


### <a name="user-status"></a>État de l’utilisateur

État de l’utilisateur. Graphique en anneau qui affiche l’état d’installation de l’application pour les utilisateurs. Cliquez sur le graphe pour ouvrir la liste des détails sur l’état de l’appareil. Le tableau des détails inclut les colonnes suivantes :
 - **Nom**  
Nom de l’utilisateur dans Azure AD.
 - **Nom d’utilisateur**  
Nom unique de l’utilisateur.
 - **Installations**  
Nombre d’installations d’applications utilisées par l’utilisateur.
 - **Échecs**  
Nombre d’installations ayant échoué effectuées par l’utilisateur.
 - **Non installé**  
Nombre d’installations non installées par l’utilisateur.


## <a name="next-steps"></a>Étapes suivantes

Pour en savoir plus sur l’utilisation de vos données Intune, consultez [Utiliser l’entrepôt de données Intune](reports-nav-create-intune-reports.md).
