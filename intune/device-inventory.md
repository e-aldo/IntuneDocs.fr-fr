---
title: "Afficher vos appareils avec Microsoft Intune - Azure | Microsoft Docs"
description: "Affichez les détails de votre appareil, y compris les systèmes d’exploitation, l’espace de stockage, le fabricant et le modèle et bien plus encore. Obtenez une liste des applications installées, vérifiez les stratégies de conformité, configurez TeamViewer et plus encore avec Microsoft Intune dans Azure. Identique à l’affichage de l’inventaire des appareils gérés."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 934ba0853f8bee851f7027580c276a9fff911b7f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="see-device-details-in-intune"></a>Consultez les détails de l’appareil dans Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

La fonctionnalité **Appareils** fournit des détails supplémentaires dans les appareils que vous gérez, notamment le matériel et les applications installées. 

Cet article vous explique comment afficher tous les appareils, ainsi que leurs propriétés dans le portail Azure.

## <a name="view-your-device-details"></a>Afficher les détails de l'appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**. Dans Appareils, vous disposez de plusieurs options :

  - **Vue d’ensemble** : obtenez des informations sur les appareils inscrits, et les systèmes d’exploitation que chaque appareil s’exécute.
  - **Gérer** : choisissez **Tous les appareils** ou **Appareils Azure AD** pour afficher la liste de tous les appareils que vous gérez.
    Dans la liste, sélectionnez un des appareils. Cette étape permet d’ouvrir le <*nom de l’appareil*> **Vue d’ensemble**, où vous pouvez sélectionner les éléments suivants :
    - **Vue d’ensemble** : consultez le nom de l’appareil, le propriétaire, s’il s’agit d’un appareil BYOD (Apportez votre propre appareil), la date de son archivage et plus de détails
    - **Matériel** : consultez l’espace de stockage libre, le modèle et le fabricant et plus de détails sur l’appareil
    - **Applications découvertes** : affiche une liste de toutes les applications qu’Intune a trouvées installées sur l’appareil
    - **Conformité des appareils** : affiche l’état de toutes les stratégies de conformité assignées à l’appareil
    - **Configuration de l’appareil** : affiche l’état de conformité de toutes les stratégies de configuration des appareil assignées à l’appareil
- **Analyser** : choisissez **Actions sur l’appareil** pour afficher une liste des actions effectuées sur l’appareil que vous gérez et leur état actuel. **Journaux d’audit** afficher l’état des différentes tâches.
- **Installation** > **Connecteur TeamViewer** : configurer l’administration à distance sur les appareils à l’aide du logiciel TeamViewer. Pour plus d’informations, consultez [Fournir une assistance à distance pour les appareils Android gérés par Intune](device-profile-android-teamviewer.md).

Intune collecte une liste des applications uniquement sur les appareils appartenant à l’entreprise. Les applications ne sont pas vérifiées sur les appareils personnels. Pour les PC Windows 10, seules les applications modernes sont répertoriées pour les appareils appartenant à l’entreprise. Intune ne collecte pas d’informations concernant les applications Win32 sur l’appareil. En fonction de l’utilisation de l’opérateur par les appareils, toutes les applications peuvent ne pas être collectées.

## <a name="next-steps"></a>Étapes suivantes
Consultez ce que vous pouvez faire d’autre pour [gérer vos appareils](device-management.md) avec Intune.
