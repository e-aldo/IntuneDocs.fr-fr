---
title: Synchroniser des appareils avec Intune
titlesuffix: Azure portal
description: "Découvrez comment synchroniser des appareils avec Intune pour obtenir les stratégies et les actions les plus récentes."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f784143535188c6bee2082c5717b752f08c5490
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchroniser des appareils avec Intune pour obtenir les stratégies et les actions les plus récentes


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Synchroniser** force l’appareil sélectionné à s’enregistrer immédiatement auprès d’Intune. Quand un appareil s’enregistre, il reçoit immédiatement les actions ou les stratégies en attente qui lui ont été affectées.  Cette action peut vous aider à valider et corriger immédiatement les stratégies que vous avez affectées, sans attendre le prochain enregistrement planifié.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>Comment synchroniser un appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil, puis l’action à distance **Synchroniser**.
7. Choisissez **Oui** pour confirmer l’action.


## <a name="retriable-error-codes"></a>Codes d’erreur pouvant faire l’objet d’une nouvelle tentative

Quand un administrateur exécute l’action d’appareil **Synchroniser**, les applications iOS et Android qui ont rencontré un échec mais généré un code d’erreur pouvant faire l’objet d’une nouvelle tentative sont disponibles sur l’appareil. Cependant, les applications qui ont généré un code d’erreur ne pouvant pas faire l’objet d’une nouvelle tentative doivent attendre sept jours avant d’être à nouveau disponibles sur l’appareil.


| Code d'erreur  | Description suggérée                                                                                                                  | Peut faire l’objet d’une nouvelle tentative |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Une erreur inconnue s'est produite.                                                                                                             | Non        |
| 2016330897 | Votre connexion à Intune a expiré. Réinitialisez votre connexion                                                                             | Oui       |
| 2016330896 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion.                                                                            | Oui       |
| 2016330895 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion.                                                                            | Oui       |
| 2016330894 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion.                                                                            | Oui       |
| 2016330893 | Vous avez perdu la connexion à Internet. Réinitialisez votre connexion.                                                                            | Oui       |
| 2016330892 | L’itinérance internationale est désactivée.                                                                                                     | Non        |
| 2016330891 | La connexion de données mobiles pour cet appareil n’est pas accessible pendant un appel téléphonique. Attendez la fin de l’appel téléphonique. | Oui       |
| 2016330890 | Réseau mobile pour cet appareil. Ces appareils ne peut pas être utilisés pour l’instant.                                                   | Non        |
| 2016330889 | Échec de la connexion sécurisée. Réinitialisez votre connexion.                                                                                   | Oui       |
| 2016330888 | Échec de l’évaluation de la confiance du serveur.                                                                                                | Non        |

## <a name="next-steps"></a>Étapes suivantes

Choisissez **Actions de l’appareil** pour connaître l’état de l’action de synchronisation. 
