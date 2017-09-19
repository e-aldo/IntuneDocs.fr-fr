---
title: "Afficher l’inventaire des appareils Intune"
titlesuffix: Azure portal
description: "Découvrez comment afficher les appareils que vous gérez avec Intune et comprenez leur matériel et leurs applications installées."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3e74651acf11ff0ea88531460d030e03749520a
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-view-intune-device-inventory"></a>Guide d’affichage de l’inventaire des appareils Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

La charge de travail **Appareils** vous fournit des informations sur les appareils que vous gérez, notamment leurs capacités matérielles et les applications installées dessus. 

Pour afficher l’inventaire des appareils .

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.

Choisissez maintenant l’une des options suivantes :

- **Vue d’ensemble** : obtenez des informations sur les appareils inscrits, et les systèmes d’exploitation que chaque appareil s’exécute.
- **Gérer** : choisissez **Tous les appareils** pour afficher la liste de tous les appareils que vous gérez.
    Sélectionnez un de ces appareils dans la liste pour ouvrir le panneau <*Nom de l’appareil*> **Vue d’ensemble** où vous pouvez sélectionner un des éléments suivants :
    - **Vue d’ensemble** : informations générales sur l’appareil, notamment son nom, son propriétaire, s’il s’agit d’un appareil BYOD, son dernier archivage, et bien plus encore.
    ![Vue d’ensemble de l’appareil](./media/device-overview.png)
    - **Matériel** : informations plus détaillées sur l’appareil, notamment son espace de stockage libre, son modèle, son fabricant, et bien plus encore.
    ![Inventaire matériel des appareils gérés](./media/hardware-inventory.png)
    - **Applications détectées** : affiche une liste de toutes les applications qu’Intune a détectées comme étant installées sur l’appareil.
    ![Nœud Applications découvertes](./media/detected-applications.png)
    


    - **Conformité de l’appareil** : affiche l’état de conformité de toutes les stratégies de conformité qui ont été affectées à l’appareil.
    - **Configuration de l’appareil** : affiche l’état de conformité de toutes les stratégies de configuration d’appareil qui ont été affectées à l’appareil.
- **Moniteur** : choisissez **Actions d’appareil** pour afficher une liste d’actions d’appareil qui ont été effectuées sur les appareils que vous gérez et leur état actuel.
- **Installation** > **Connecteur TeamViewer** : vous permet de configurer l’administration à distance sur les appareils à l’aide du logiciel TeamViewer. Pour plus d’informations, consultez [Fournir une assistance à distance pour les appareils Android gérés par Intune](/intune/device-profile-android-teamviewer).

>[!NOTE]
> Intune collecte l’inventaire des applications uniquement sur les appareils appartenant à l’entreprise. Les applications ne sont pas inventoriées sur les appareils personnels. Pour les PC Windows 10, seul l’inventaire des applications modernes est collecté sur les appareils appartenant à l’entreprise. Intune ne collecte pas d’informations concernant les applications Win32 sur l’appareil.
> Selon l’opérateur que vous utilisez avec les appareils, certains éléments du parc peuvent ne pas être collectés.
