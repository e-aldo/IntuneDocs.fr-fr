---
title: Supprimer un utilisateur d’un appareil iOS avec Microsoft Intune
titlesuffix: ''
description: Découvrez comment supprimer un utilisateur d’un appareil iOS partagé avec Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67a5f60e0877ebc8994ed7d3191a81f51d19c40a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Supprimer un utilisateur d’un appareil iOS partagé


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

L’action **Supprimer l’utilisateur** supprime un utilisateur que vous sélectionnez dans le cache local sur un iPad partagé. L’iPad doit être configuré pour gérer l’application iOS Classroom à l’aide d’un [profil Éducation iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Non prise en charge
- iOS - Prise en charge d’iOS 9.3 et ultérieur (appareils iPad partagés uniquement)
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="remove-a-user"></a>Supprimer un utilisateur

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, sélectionnez **Appareils**.
4. Dans le volet **Appareils**, sélectionnez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, sélectionnez un appareil iOS.
6. Dans le volet de l’appareil, sélectionnez **Utilisateurs**.
7. Dans la liste, cliquez avec le bouton droit sur l’utilisateur que vous souhaitez supprimer, puis sélectionnez **Supprimer l’utilisateur**.

## <a name="next-steps"></a>Étapes suivantes

- Pour consulter l’état de l’action **Supprimer l’utilisateur**, sélectionnez **Appareils** > **Actions de l’appareil**.
