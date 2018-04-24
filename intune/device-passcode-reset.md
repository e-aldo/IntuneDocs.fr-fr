---
title: Réinitialiser des codes secrets de l’appareil avec Microsoft Intune - Azure | Microsoft Docs
description: Supprimez ou réinitialisez le code secret à l’aide de l’action de suppression de code secret sur les appareils que vous gérez ou analysez avec Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 19b30315fa26dd53b5e383bc9e4bef5c65b89962
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Réinitialiser ou supprimer un code secret de l’appareil dans Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pour créer un nouveau code secret pour un appareil, utilisez l’action **Supprimer le code secret**.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Appareils Android inscrits avec un profil professionnel, version 7.0 et ultérieure
- Appareils Android version 6.0 ou antérieure
- iOS 
     
## <a name="unsupported-platforms"></a>Plateformes non prises en charge

- Appareils Android inscrits avec un profil professionnel, version 6.0 et antérieure
- Appareils Android version 7.0 ou supérieure
- macOS
- Windows

## <a name="reset-a-passcode"></a>Réinitialiser un code secret

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**, puis **Tous les appareils**.
4. Dans la liste des appareils que vous gérez, sélectionnez un appareil et choisissez **... Plus**. Ensuite, choisissez l’action à distance **Supprimer le code secret**.

## <a name="resetting-android-for-work-passcodes"></a>Réinitialisation des codes secrets Android for Work

Les appareils Android for Work pris en charge reçoivent un nouveau mot de passe de déverrouillage d’appareil ou une vérification du profil managé pour l’utilisateur final. Pour les appareils Android 7.0 ou version ultérieure avec des profils professionnels, les utilisateurs finaux reçoivent des notifications qui les invitent à activer leur jeton de réinitialisation de code secret juste après l’inscription. La notification s’affiche si un mot de passe de profil professionnel est imposé et défini. Une fois le code secret entré, la notification disparaît.

## <a name="resetting-ios-passcodes"></a>Réinitialisation des codes secrets iOS

Les codes secrets sont supprimés des appareils iOS. Si une stratégie de conformité relative au code secret est définie, l’appareil invite l’utilisateur à définir un nouveau mot de passe dans les paramètres. 

## <a name="next-steps"></a>Étapes suivantes

Pour afficher l’état de l’action que vous venez d’effectuer, dans **Appareils**, sélectionnez **Actions d’appareil**.
