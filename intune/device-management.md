---
title: "Gérer des appareils avec Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment afficher les appareils que vous gérez avec Intune et effectuer diverses opérations dessus."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Qu’est-ce que la gestion des appareils Microsoft Intune ?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

La charge de travail **Appareils** vous donne des informations sur les appareils que vous gérez et vous permet de procéder à des tâches à distance sur ces appareils. Pour accéder à la charge de travail :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.

Maintenant, vous pouvez effectuer les actions suivantes :

- [Afficher l’inventaire des appareils](device-inventory.md)
- Effectuez les actions d’appareil à distance :
    - [Supprimer les données d’entreprise](device-company-data-remove.md) 
    - [Réinitialisation aux paramètres d’usine](device-factory-reset.md)
    - [Verrouillage à distance](device-remote-lock.md)
    - [Réinitialiser le code secret](device-passcode-reset.md)
    - [Contourner le verrou d’activation](device-activation-lock-bypass.md)
    - [Redémarrage à zéro](device-fresh-start.md)
    - [Mode Perdu](device-lost-mode.md)
    - [Localiser l’appareil](device-locate.md)
    - [Redémarrer](device-restart.md)
    - [Réinitialisation du code PIN Windows 10](device-windows-pin-reset.md)
    - [Contrôle à distance pour Android](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>Prise en charge de chaque action de l’appareil

Utilisez le tableau suivant pour connaître les plateformes d’appareils qui sont prises en charge par chaque action.

|||||||
|-|-|-|-|-|-|
|Action de l’appareil|Windows|Windows Phone|iOS|macOS|Android|
|**Supprimer les données d’entreprise**|Oui|Oui|Oui|Oui|Oui|
|**Réinitialisation aux paramètres d’usine**|Windows 8.1 et versions ultérieures (pas les appareils gérés par EAS)|Oui|Oui|Non|Android for Work non pris en charge|
|**Supprimer**|Oui|Oui|Oui|Oui|Oui|
|**Verrouillage à distance**|Non|Windows Phone 8.1 et versions ultérieures|Oui|Non|Oui|
|**Réinitialiser le code secret**|Non|Windows Phone 8.1 vers Windows 10 Creators Update non joint à Azure AD, Windows 10 Creators Update et versions ultérieures : tous|Oui|Non|Avant Android 7, Android for Work non pris en charge|
|**Nouveau code secret** (pour les appareils Windows 10)|Non|Windows 10 Creators Update et versions ultérieures (joint à Azure AD)|Non|Non|Android for Work non pris en charge|
|**Contourner le verrou d’activation**|Non|Non|Appareils appartenant à l’entreprise uniquement|Non|Non|
|**Mode Perdu**|Non|Non|iOS 9.3 et versions ultérieures, supervisé et appartenant à l’entreprise|Non|Non|
|**Localiser l’appareil**|Non|Non|iOS 9.3 et versions ultérieures en mode Perdu, supervisé et appartenant à l’entreprise|Non|Non|
|**Déconnecter l’utilisateur actuel**|Non|Non|iOS 9.3 et versions ultérieures (appareils iPad partagés uniquement)|Non|Non|
|**Redémarrer**|Windows 8.1 et versions ultérieures|Windows Phone 8.1 et versions ultérieures|Non|Non|Non|
|**Redémarrage à zéro**|Windows 10 Creators Update et versions ultérieures|Non|Non|Non|Non|
|**Nouvelle session d’assistance à distance**|Non|Non|Non|Non|Oui|
|**Supprimer l’utilisateur**|Non|Non|iOS 9.3 et versions ultérieures (appareils iPad partagés uniquement)|Non|Non|

## <a name="next-steps"></a>Étapes suivantes

- Choisissez **Actions de l’appareil** pour connaître l’état des actions effectuées sur les appareils que vous gérez. 
![Surveiller les actions des appareils](./media/monitor-device-actions.png)