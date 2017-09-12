---
title: Synchroniser des appareils avec Intune
titlesuffix: Azure portal
description: "Découvrez comment synchroniser des appareils avec Intune pour obtenir les stratégies et les actions les plus récentes."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3906b567935f026202ccf0e81424a1bb36e376ef
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchroniser des appareils avec Intune pour obtenir les stratégies et les actions les plus récentes


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Synchroniser** force l’appareil sélectionné à s’enregistrer immédiatement auprès d’Intune. Quand un appareil s’enregistre, il reçoit immédiatement les actions ou les stratégies en attente qui lui ont été affectées.  Cette action peut vous aider à valider et corriger immédiatement les stratégies que vous avez affectées, sans attendre le prochain enregistrement planifié.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Prise en charge
- Windows Phone - Prise en charge
- iOS - Prise en charge
- macOS - Prise en charge
- Android - Prise en charge

## <a name="how-to-sync-a-device"></a>Comment synchroniser un appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, puis l’action à distance **Synchroniser**.
7. Choisissez **Oui** pour confirmer l’action.

## <a name="next-steps"></a>Étapes suivantes

Choisissez **Actions de l’appareil** pour connaître l’état de l’action de synchronisation. 
