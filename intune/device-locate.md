---
title: Rechercher des appareils iOS perdus avec Intune
titleSuffix: Intune on Azure
description: "Découvrez comment localiser les appareils iOS perdus ou volés avec Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 80aa0e5afd1f8862b181d455ff6b545e462f90c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localiser des appareils iOS perdus ou volés avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Localiser l’appareil** affiche l’emplacement d’un appareil iOS perdu ou volé sur une carte. L’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé. Avant que vous puissiez utiliser cette action, l’appareil doit être configuré en [mode Perdu](/intune-azure/manage-devices/lost-mode.md).

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil iOS, puis choisissez l’action à distance d’appareil **Localiser l’appareil**.
6. Une fois que l’appareil a été localisé, son emplacement s’affiche dans le panneau **Localiser l’appareil**.
    ![Panneau Localiser l’appareil](./media/locate-device.png)

>[!NOTE]
>Pour des raisons de confidentialité, le degré de zoom sur le plan est limité.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informations de sécurité et de confidentialité pour le mode Perdu et actions Localiser l’appareil
- Aucune information d’emplacement de l’appareil n’est envoyée à Intune tant que vous n’activez pas cette action.
- Lorsque vous utilisez l’action Localiser l’appareil, les coordonnées de latitude et de longitude de l’appareil sont envoyées à Intune et affichées dans le portail Azure.
- Les données sont stockées pendant 24 heures avant d’être supprimées. Vous ne pouvez pas supprimer manuellement les données d’emplacement.
- Les données d’emplacement sont chiffrées aussi bien pendant leur stockage que leur transmission.
- Lorsque vous configurez le mode Perdu, nous vous recommandons de rédiger le message qui s’affiche sur l’écran de verrouillage de façon à ce qu’il inclue des informations qui permettent à quelqu’un de rendre l’appareil.
