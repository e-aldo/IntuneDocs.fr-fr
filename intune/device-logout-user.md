---
title: "Déconnecter l’utilisateur d’un appareil iOS avec Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment déconnecter l’utilisateur actuel d’un appareil iOS avec Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1de2069b7b25ee5e5c21a8e4caa7512f13d4ca0e
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/09/2017
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a>Déconnecter l’utilisateur actuel sur les appareils iOS gérés par Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


L’action **Déconnecter l’utilisateur actuel** déconnecte l’utilisateur actuel sur un appareil iPad partagé et configuré pour gérer l’application iOS Classroom avec un [profil d’éducation iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Non prise en charge
- iOS - Prise en charge d’iOS 9.3 et ultérieur (appareils iPad partagés uniquement)
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="how-to-logout-the-current-user"></a>Comment déconnecter l’utilisateur actuel

1.  Connectez-vous au portail Azure.
2.  Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3.  Dans le panneau **Intune**, choisissez **Appareils**.
4.  Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5.  Dans la liste des appareils que vous gérez, choisissez un appareil iOS, puis choisissez l’action à distance **Déconnecter l’utilisateur actuel**.

## <a name="next-steps"></a>Étapes suivantes

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.
