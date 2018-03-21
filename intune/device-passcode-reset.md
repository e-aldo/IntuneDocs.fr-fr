---
title: "Réinitialiser des codes secrets de l’appareil avec Microsoft Intune - Azure | Microsoft Docs"
description: "Supprimez ou réinitialisez le code secret à l’aide de l’action de code Supprimer le code secret sur les appareils que vous gérez ou analysez avec Intune."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f23a79bbe72d12750ef642226aefd1e11dcac24
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Réinitialiser ou supprimer un code secret de l’appareil dans Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pour créer un nouveau code secret pour un appareil, utilisez l’action **Supprimer le code secret**.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows Phone 8.1 vers Windows 10 Creators Update non joint à Azure AD et Windows 10 Creators Update et version ultérieure
- iOS
- Android versions antérieures à Android 7

Cette fonctionnalité n'est **pas** prise en charge pour les systèmes suivants :

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Réinitialiser un code secret

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**, puis **Tous les appareils**.
4. Dans la liste des appareils que vous gérez, choisissez un appareil, choisissez **...Plus**, puis choisissez l’action à distance d’appareil **Supprimer le code secret**.

## <a name="next-steps"></a>Étapes suivantes

Pour afficher l’état de l’action que vous venez d’effectuer, dans **Appareils**, sélectionnez **Actions d’appareil**.
