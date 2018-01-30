---
title: "Supprimer un utilisateur d’un appareil iOS avec Intune"
titlesuffix: Azure portal
description: "Découvrez comment supprimer un utilisateur d’un appareil iOS partagé avec Intune. »"
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 979614aaa450493ea0b5cc2a1baaccc10a6dd028
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Supprimer un utilisateur d’un appareil iOS partagé avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action **Supprimer l’utilisateur** supprime un utilisateur choisi dans le cache local sur un appareil iPad partagé et configuré pour gérer l’application iOS Classroom avec un [profil d’éducation iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Non prise en charge
- iOS - Prise en charge d’iOS 9.3 et ultérieur (appareils iPad partagés uniquement)
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="how-to-remove-a-user"></a>Comment supprimer un utilisateur

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil iOS.
6. Dans le panneau de cet appareil, choisissez **Utilisateurs**.
7. Dans la liste, cliquez avec le bouton droit sur l’utilisateur que vous souhaitez supprimer, puis choisissez **Supprimer l’utilisateur**.

## <a name="next-steps"></a>Étapes suivantes

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.
