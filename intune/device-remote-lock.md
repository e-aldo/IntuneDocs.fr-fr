---
title: "Verrouiller des appareils avec Microsoft Intune - Azure | Microsoft Docs"
description: "Utilisez l’action de verrouillage à distance dans Microsoft Intune pour verrouiller un appareil protégé par un PIN ou un mot de passe."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Verrouiller à distance des appareils avec Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’appareil **Verrouillage à distance** verrouille l’appareil. Pour le déverrouiller, le propriétaire de l’appareil entre son code secret. Vous pouvez verrouiller des appareils à distance qui ont un PIN ou un mot de passe défini. Les appareils qui n’ont pas de PIN ni de code secret ne peuvent pas être verrouillés à distance.

## <a name="supported-platforms"></a>Plateformes prises en charge

Le verrouillage à distance est pris en charge pour les plateformes suivantes :

- Android
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 et versions ultérieures

Il n’est **pas** pris en charge pour :
- Windows 10 Desktop

> [!NOTE]
> Pour les appareils macOS, vous définissez un code PIN de récupération à 6 chiffres. Une fois verrouillé, la **Vue d’ensemble des appareils** affiche le PIN jusqu’à ce qu’une autre action d’appareil soit envoyée.

## <a name="remote-lock-a-device"></a>Verrouiller à distance un appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**, puis **Tous les appareils**.
4. Dans la liste des appareils, sélectionnez un appareil, puis l’action **Verrouillage à distance**.

## <a name="next-steps"></a>Étapes suivantes

Pour voir l’état de cette action, ouvrez **Actions de l’appareil** (Microsoft Intune > Appareils). Consultez [Actions disponibles](device-management.md) pour des actions supplémentaires afin d’aider à gérer vos appareils.