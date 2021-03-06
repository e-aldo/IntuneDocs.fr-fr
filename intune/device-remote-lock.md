---
title: Verrouiller des appareils avec Microsoft Intune - Azure | Microsoft Docs
description: Utilisez l’action de verrouillage à distance dans Microsoft Intune pour verrouiller un appareil protégé par un code PIN ou un mot de passe.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45ab6434245c0dd412b2e9d23e394f72871a459a
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Verrouiller à distance des appareils avec Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Verrouillage à distance** verrouille l’appareil. Pour déverrouiller l’appareil, son propriétaire entre son code secret. Vous pouvez verrouiller des appareils à distance qui ont un PIN ou un mot de passe défini. Les appareils qui n’ont pas de code PIN ni de mot de passe ne peuvent pas être verrouillés à distance.

## <a name="supported-platforms"></a>Plateformes prises en charge

Le **verrouillage à distance** est pris en charge pour les plateformes suivantes :

- Android
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 et versions ultérieures

Le **verrouillage à distance** n’est *pas* pris en charge pour :
- Windows 10 Desktop

> [!NOTE]
> Pour les appareils macOS, vous définissez un code PIN de récupération à 6 chiffres. Une fois l’appareil verrouillé, la **Vue d’ensemble des appareils** affiche le code PIN jusqu’à ce qu’une autre action d’appareil soit envoyée.

## <a name="remote-lock-a-device"></a>Verrouiller à distance un appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils** > **Tous les appareils**.
4. Dans la liste des appareils, sélectionnez un appareil, puis l’action **Verrouillage à distance**.

## <a name="next-steps"></a>Étapes suivantes

- Pour consulter l’état de cette action, sélectionnez **Microsoft Intune** > **Appareils** > **Actions de l’appareil**). 
- Pour découvrir plus d’actions qui peuvent vous aider à gérer vos appareils, consultez [Actions disponibles](device-management.md).
