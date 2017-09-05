---
title: "Réinitialiser les appareils aux paramètres d’usine avec Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment réinitialiser les appareils que vous gérez avec Intune à leurs paramètres d’usine."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fd7273d6c5f75a675d7b01df4225a96fd3a5f821
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Réinitialiser les appareils gérés par Intune aux paramètres d’usine


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Réinitialisation aux paramètres d’usine** réinitialise l’appareil à ses paramètres par défaut. L’appareil n’est plus géré par Intune et les données personnelles et d’entreprise sont supprimées. Vous ne pouvez pas annuler cette action.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Prise en charge de Windows 8.1 et ultérieur (pas les appareils gérés par EAS)
- Windows Phone - Prise en charge
- iOS - Prise en charge
- macOS - Non prise en charge
- Android - Prise en charge (Android for Work n’est pas pris en charge)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Comment réinitialiser un appareil aux paramètres d’usine

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, puis choisissez l’action à distance d’appareil **Réinitialisation des paramètres d’usine**.

## <a name="next-steps"></a>Étapes suivantes

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.
