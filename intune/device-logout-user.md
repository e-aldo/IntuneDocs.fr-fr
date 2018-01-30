---
title: "Déconnecter l’utilisateur d’un appareil iOS avec Intune"
titlesuffix: Azure portal
description: "Découvrez comment déconnecter l’utilisateur actuel d’un appareil iOS avec Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e59eee3660f56fdd967237563e69324b8307e3a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
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
