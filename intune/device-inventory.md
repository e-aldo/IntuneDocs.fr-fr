---
title: Afficher les détails de l’appareil avec Microsoft Intune - Azure | Microsoft Docs
description: Affichez les détails de votre appareil, notamment les systèmes d’exploitation, l’espace de stockage, le fabricant et le modèle. Obtenez une liste des applications installées, vérifiez les stratégies de conformité et configurez TeamViewer avec Microsoft Intune dans Azure. Identique à l’affichage de l’inventaire des appareils gérés.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a40b855d1dbaeece1dc91648866285c0a01fb338
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="see-device-details-in-intune"></a>Consultez les détails de l’appareil dans Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

La fonctionnalité **Appareils** fournit des détails supplémentaires sur les appareils que vous gérez, notamment le matériel et les applications installées.

Cet article vous explique comment afficher tous les appareils, ainsi que leurs propriétés dans le portail Azure.

## <a name="view-the-device-details"></a>Afficher les détails de l’appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils** > **Tous les appareils** > sélectionnez l’un des appareils listés pour afficher les détails correspondants :

   - **Vue d’ensemble** permet d’afficher le nom de l’appareil et de lister certaines de ses propriétés clés, notamment s’il s’agit d’un appareil BYOD (« Apportez votre propre appareil »), la date/heure de son enregistrement, etc. Sélectionnez **Plus** pour effectuer d’autres actions :
     - Supprimer les données d’entreprise
     - Supprimer l’appareil
     - Verrouiller l’appareil à distance
     - Effacer
     - Démarrer une session d’assistance à distance
   - Utilisez **Propriétés** pour affecter une [catégorie d’appareil créée](device-group-mapping.md) et changer le type de propriété d’un appareil. Par exemple, remplacez un appareil personnel par un appareil d’entreprise.
   - **Matériel** comprend de nombreux détails sur l’appareil, notamment l’ID, le système d’exploitation et la version, l’espace de stockage, le modèle et le fabricant, les paramètres d’accès conditionnel et bien d’autres informations.
   - **Applications découvertes** permet de lister toutes les applications dont Intune a détecté l’installation sur l’appareil, ainsi que leurs versions. Vous pouvez également **Exporter** la liste des applications dans un fichier .csv.
   - **Conformité de l’appareil** permet de lister toutes les stratégies de conformité affectées, et de déterminer si l’appareil est conforme ou non conforme.
   - **Configuration de l’appareil** permet d’afficher toutes les stratégies de configuration affectées à l’appareil, et de déterminer si la stratégie a réussi ou non.

Intune collecte une liste des applications uniquement sur les appareils appartenant à l’entreprise. Les applications ne sont pas vérifiées sur les appareils personnels. Pour les PC Windows 10, seules les applications modernes sont répertoriées pour les appareils appartenant à l’entreprise. Intune ne collecte pas d’informations concernant les applications Win32 sur l’appareil. En fonction de l’opérateur utilisé par les appareils, toutes les applications peuvent ne pas être collectées.

## <a name="next-steps"></a>Étapes suivantes
Consultez ce que vous pouvez faire d’autre pour [gérer vos appareils](device-management.md) avec Intune.