---
title: "Verrouiller à distance des appareils gérés avec Intune"
titlesuffix: Azure portal
description: "Découvrez comment utiliser Intune pour verrouiller à distance les appareils que vous gérez."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8905b97a5912010a2516788a8da66441fc6f89ae
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Verrouiller à distance des appareils gérés avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’appareil de **Verrouillage à distance** verrouille l’appareil sélectionné. Le propriétaire de l’appareil doit utiliser son code secret pour le déverrouiller. Vous pouvez verrouiller à distance uniquement les appareils avec un code confidentiel ou un mot de passe défini.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Prise en charge de Windows Phone 8.1 et ultérieur
- iOS - Prise en charge
- macOS - Prise en charge

    > [!Note]  
    > Définissez un code PIN de récupération à 6 chiffres. Une fois le verrouillage effectué, le panneau **Vue d’ensemble des appareils** affiche le code PIN jusqu’à ce qu’une autre action d’appareil soit envoyée.
- Android - Prise en charge

## <a name="how-to-remote-lock-a-device"></a>Comment verrouiller un appareil à distance

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, puis choisissez l’action à distance d’appareil **Verrouillage à distance**.

## <a name="next-steps"></a>Étapes suivantes

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.
