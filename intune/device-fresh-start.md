---
title: "Réinitialiser les appareils Windows 10 avec Intune"
titleSuffix: Intune on Azure
description: "Apprenez à utiliser Fresh Start pour réinitialiser les PC Windows 10 exécutant Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44633f244536a0033dd51fc06e1dba09c0490500
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/09/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Utiliser Fresh Start pour réinitialiser les appareils Windows 10 avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Fresh Start** supprime toutes les applications qui ont été installées sur un PC Windows 10 exécutant Creators Update, puis met à jour automatiquement le PC vers la dernière version de Windows.
Vous pouvez ainsi supprimer des applications (OEM) préinstallées, comme celles qui sont souvent fournies avec un nouveau PC. Vous pouvez configurer si les données utilisateur sont conservées quand cette action est exécutée sur l’appareil. Dans ce cas, les applications et les paramètres sont supprimés, mais le contenu du dossier personnel des utilisateurs est conservé.

## <a name="how-to-use-fresh-start"></a>Comment utiliser le redémarrage à zéro

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil de bureau Windows 10, puis choisissez l’action à distance d’appareil **Fresh Start**.

## <a name="next-steps"></a>Étapes suivantes

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.

