---
title: "Verrouiller à distance des appareils gérés avec Intune"
titlesuffix: Azure portal
description: "Découvrez comment utiliser Intune pour verrouiller à distance les appareils que vous gérez."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a8f3c93507cde4363570a9a39f8b3b1f69c07df
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Verrouiller à distance des appareils gérés avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’appareil de **Verrouillage à distance** verrouille l’appareil sélectionné. Le propriétaire de l’appareil doit utiliser son code secret pour le déverrouiller. Vous pouvez verrouiller à distance uniquement les appareils avec un code confidentiel ou un mot de passe défini.

## <a name="supported-platforms"></a>Plateformes prises en charge

Le verrouillage à distance est pris en charge pour les plateformes suivantes :

|Plate-forme|État de prise en charge|
|---|---|
|Android|Oui|
|iOS|Oui|
|macOS|Oui|
|Windows 10 Desktop|Non|
|Windows 10 Mobile|Oui|
|Windows Phone|Oui, pour Windows Phone 8.1 et les versions ultérieures|

> [!NOTE]  
> Pour les appareils macOS, vous définissez un code PIN de récupération à 6 chiffres. Une fois le verrouillage effectué, le panneau **Vue d’ensemble des appareils** affiche le code PIN jusqu’à ce qu’une autre action d’appareil soit envoyée.

## <a name="how-to-remote-lock-a-device"></a>Comment verrouiller un appareil à distance

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, puis choisissez l’action à distance d’appareil **Verrouillage à distance**.

## <a name="next-steps"></a>Étapes suivantes

Pour voir l’état de l’action que vous venez d’effectuer, dans le panneau **Appareils**, choisissez **Actions d’appareil**.
