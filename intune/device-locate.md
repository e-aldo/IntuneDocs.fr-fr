---
title: Rechercher des appareils iOS perdus avec Intune
titlesuffix: Azure portal
description: "Découvrez comment localiser les appareils iOS perdus ou volés avec Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 864d528091de7a6113485347304b0dc254af2c7d
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localiser des appareils iOS perdus ou volés avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Localiser l’appareil** affiche l’emplacement d’un appareil iOS perdu ou volé sur une carte. L’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé. Avant que vous puissiez utiliser cette action, l’appareil doit être configuré en [mode Perdu](device-lost-mode.md).

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Non prise en charge
- iOS - Prise en charge sur iOS 9.3 et ultérieur (mode Perdu), en mode supervisé et appartenant à l’entreprise
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Comment localiser un appareil perdu ou volé

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil iOS, choisissez **...Plus**, puis choisissez l’action à distance **Localiser l’appareil**.
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


## <a name="next-steps"></a>Étapes suivantes

Pour voir l’état de l’action que vous venez d’effectuer, dans le panneau **Appareils**, choisissez **Actions d’appareil**.