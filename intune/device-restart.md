---
title: Redémarrer à distance des appareils avec Intune
titlesuffix: Microsoft Intune
description: Apprenez à redémarrer à distance des appareils à l’aide de l’action de redémarrage d’appareil dans Microsoft Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bd5a01b8aac91c3bd6ea033d62d41e19aab65f8
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2018
---
# <a name="remotely-restart-devices-with-intune"></a>Redémarrer à distance des appareils avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Redémarrer** entraîne le redémarrage de l’appareil que vous choisissez. Le propriétaire de l’appareil n’est pas automatiquement informé du redémarrage, et peut ainsi perdre son travail.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Prise en charge de Windows 8.1 et ultérieur
- Windows Phone - Prise en charge de Windows Phone 8.1 et ultérieur
- iOS - Prise en charge

    > [!Note]  
    > Cette commande nécessite un appareil supervisé et le droit d’accès **Verrouillage de l’appareil**. L’appareil redémarre immédiatement. Après le redémarrage, les appareils iOS verrouillés par un code secret ne rejoignent pas un réseau Wi-Fi et peuvent se trouver dans l’impossibilité de communiquer avec le serveur.
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="how-to-restart-a-device"></a>Comment redémarrer un appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, choisissez **...Plus**, puis choisissez l’action à distance d’appareil **Redémarrer**.

## <a name="next-steps"></a>Étapes suivantes

Pour voir l’état de l’action que vous venez d’effectuer, dans le panneau **Appareils**, choisissez **Actions d’appareil**.
