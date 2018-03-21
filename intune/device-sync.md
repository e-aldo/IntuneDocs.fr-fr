---
title: "Synchroniser des appareils avec Microsoft Intune - Azure | Microsoft Docs"
description: "Synchronisez des appareils enregistrés ou gérés avec Microsoft Intune pour obtenir les stratégies et les actions les plus récentes. Inclut les étapes permettant de synchroniser à l’aide du portail Azure et répertorie les codes d’erreur qui peuvent être retentée."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d2d13ce2ed06549a6cd09fd766a0072b15fcd067
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="sync-devices-to-get-the-latest-policies-and-actions---intune"></a>Synchroniser des appareils pour obtenir les stratégies et les actions les plus récentes - Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Synchroniser** force l’appareil sélectionné à s’enregistrer immédiatement auprès d’Intune. Quand un appareil s’enregistre, il reçoit immédiatement les actions ou les stratégies en attente qui lui ont été affectées. Cette fonctionnalité peut vous aider à valider et dépanner immédiatement les stratégies que vous avez assignées, sans attendre la prochaine vérification planifiée.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="sync-a-device"></a>Synchroniser un appareil

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**. 
3. Dans **Intune**, sélectionnez **Appareils** puis **Tous les appareils**.
4. Dans la liste des appareils que vous gérez, choisissez un appareil, choisissez **...Plus**, puis sélectionnez l’action **Synchroniser**.
5. Cliquez sur **Oui** pour confirmer la suppression.


## <a name="retryable-error-codes"></a>Codes d’erreur renouvelable

Quand un administrateur exécute l’action d’appareil **Synchroniser**, les applications iOS et Android qui ont rencontré un échec et généré un code d’erreur renouvelable sont toujours disponibles sur l’appareil. Cependant, les applications qui ont généré un code d’erreur non renouvelable, doivent attendre sept jours avant d’être à nouveau disponibles sur l’appareil.


| Code d'erreur  | Description suggérée | Renouvelable |
|---|---|---|
| 2016330898 | Une erreur inconnue s'est produite. | Non |
| 2016330897 | Votre connexion à Intune a expiré. Réinitialisez votre connexion. | Oui |
| 2016330896 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion. | Oui |
| 2016330895 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion. | Oui |
| 2016330894 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion. | Oui |
| 2016330893 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion. | Oui|
| 2016330892 | L’itinérance internationale est désactivée. | Non|
| 2016330891 | La connexion de données mobiles pour cet appareil n’est pas accessible pendant un appel téléphonique. Attendez la fin de l’appel téléphonique. | Oui|
| 2016330890 | Réseau mobile pour cet appareil. Ces appareils ne peut pas être utilisés pour l’instant. | Non|
| 2016330889 | Échec de la connexion sécurisée. Réinitialisez votre connexion. | Oui|
| 2016330888 | Échec de l’évaluation de la confiance du serveur. | Non|

## <a name="next-step"></a>Étape suivante

Choisissez **Actions de l’appareil** pour voir l’état de l’action de synchronisation. 
