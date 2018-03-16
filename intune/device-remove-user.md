---
title: "Supprimer un utilisateur d’un appareil iOS avec Microsoft Intune"
titlesuffix: 
description: "Découvrez comment supprimer un utilisateur d’un appareil iOS partagé avec Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b2321de0c0541111fdf6f18345bd952ca8b5448
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Supprimer un utilisateur d’un appareil iOS partagé


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action **Supprimer l’utilisateur** supprime un utilisateur choisi dans le cache local sur un appareil iPad partagé et configuré pour gérer l’application iOS Classroom avec un [profil d’éducation iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Non prise en charge
- iOS - Prise en charge d’iOS 9.3 et ultérieur (appareils iPad partagés uniquement)
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="how-to-remove-a-user"></a>Comment supprimer un utilisateur

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil iOS.
6. Dans le panneau de cet appareil, choisissez **Utilisateurs**.
7. Dans la liste, cliquez avec le bouton droit sur l’utilisateur que vous souhaitez supprimer, puis choisissez **Supprimer l’utilisateur**.

## <a name="next-steps"></a>Étapes suivantes

Pour voir l’état de l’action que vous venez d’effectuer, dans le panneau **Appareils**, choisissez **Actions d’appareil**.
