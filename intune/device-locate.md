---
title: Rechercher des appareils iOS perdus avec Microsoft Intune - Azure | Microsoft Docs
description: "Recherchez ou localisez des appareils iOS perdus ou volés à l’aide de la fonctionnalité Localiser l’appareil dans Microsoft Intune ; et obtenez plus d’informations sur la sécurité et les informations de confidentialité lors de l’utilisation de l’action Localiser l’appareil."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Localiser des appareils iOS perdus ou volés avec Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pour obtenir l’emplacement d’un appareil iOS perdu ou volé sur une carte, utiliser l’action **Localiser l’appareil**. L’appareil doit être un appareil iOS appartenant à l’entreprise, inscrit via le programme d’inscription des appareils (DEP) et être en mode Supervisé. Avant d’utiliser cette action, veillez à ce que l’appareil soit en [mode Perdu](device-lost-mode.md).

## <a name="supported-platforms"></a>Plateformes prises en charge

- iOS 9.3 et version ultérieure

Cette fonctionnalité n'est **pas** prise en charge pour les systèmes suivants : 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Localiser un appareil perdu ou volé

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**, puis **Tous les appareils**.
4. Dans la liste des appareils que vous gérez, choisissez un appareil iOS, choisissez **...Plus**, puis choisissez l’action à distance **Localiser l’appareil**.
5. Une fois que l’appareil est localisé, son emplacement s’affiche dans **Localiser l’appareil**.
    ![Localiser l’appareil à l’aide d’Intune dans Azure](./media/locate-device.png)

>[!NOTE]
>Pour des raisons de confidentialité, le degré de zoom sur le plan est limité.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Informations de sécurité et de confidentialité pour les actions Mode Perdu et Localiser l’appareil
- Aucune information sur l’emplacement de l’appareil n’est envoyée à Intune tant que vous n’activez pas cette action.
- Lorsque vous utilisez l’action Localiser l’appareil, les coordonnées de latitude et de longitude de l’appareil sont envoyées à Intune et affichées dans le portail Azure.
- Les données sont stockées pendant 24 heures avant d’être supprimées. Vous ne pouvez pas supprimer manuellement les données d’emplacement.
- Les données d’emplacement sont chiffrées aussi bien pendant leur stockage que leur transmission.
- Lorsque vous configurez le mode Perdu, vous pouvez personnaliser un message qui s’affiche sur l’écran de verrouillage. Afin d’aider la personne qui trouve l’appareil, veillez à inclure dans le message des détails spécifiques pour retourner l’appareil perdu.

## <a name="next-steps"></a>Étapes suivantes

Pour afficher l’état d’activation du mode Perdu, ouvrez **Appareils**, puis sélectionnez **Actions de l’appareil**.
