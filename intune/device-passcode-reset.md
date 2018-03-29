---
title: Réinitialiser des codes secrets de l’appareil avec Microsoft Intune - Azure | Microsoft Docs
description: Supprimez ou réinitialisez le code secret à l’aide de l’action de suppression de code secret sur les appareils que vous gérez ou analysez avec Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cca5922f036711093469e71489e267af53f05a9
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/20/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Réinitialiser ou supprimer un code secret de l’appareil dans Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Pour créer un nouveau code secret pour un appareil, utilisez l’action **Supprimer le code secret**.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows Phone 8.1 (non joint à Azure Active Directory), notamment les versions jusqu’à Windows 10 Creators Update
- Windows 10 Creators Update et ultérieur
- iOS
- Android versions antérieures à Android 7

Cette fonctionnalité n’est pas prise en charge pour les systèmes suivants :

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Réinitialiser un code secret

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**, puis **Tous les appareils**.
4. Dans la liste des appareils que vous gérez, sélectionnez un appareil et choisissez **... Plus**. Ensuite, choisissez l’action à distance **Supprimer le code secret**.

## <a name="next-steps"></a>Étapes suivantes

Pour afficher l’état de l’action que vous venez d’effectuer, dans **Appareils**, sélectionnez **Actions d’appareil**.
