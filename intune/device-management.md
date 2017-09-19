---
title: "Gérer des appareils avec Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment afficher les appareils que vous gérez avec Intune et effectuer diverses opérations dessus."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0686b3ece3a929cb06a29f4e58046872b70ec926
ms.sourcegitcommit: b8987b8dfb009ea55678d7f640ac5f18a6ab167e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/13/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Qu’est-ce que la gestion des appareils Microsoft Intune ?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur informatique, vous devez vous assurer que les appareils gérés fournissent les ressources dont vos utilisateurs finaux ont besoin pour effectuer leur travail, tout en protégeant les données contre les risques.

La charge de travail **Appareils** vous donne des informations sur les appareils que vous gérez et vous permet de procéder à des tâches à distance sur ces appareils. Pour accéder à la charge de travail :

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans **Intune**, choisissez **Appareils**.
4. Vous pouvez afficher des informations sur les appareils et effectuer les actions suivantes sur les appareils à distance :
    - **Vue d’ensemble** : aperçu des appareils inscrits que vous gérez.
    - **Tous les appareils** : liste des appareils inscrits que vous gérez. Choisissez **Filtre** ou **Colonnes** pour affiner les informations affichées. Sélectionnez un appareil pour [voir le parc des appareils](device-inventory.md).
    - **Appareils Azure AD** : liste des appareils inscrits ou joints à Azure Active Directory (AD). Découvrez plus d’informations sur la [gestion des appareils dans Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Actions des appareils** : historique des actions à distance effectuées sur les appareils, notamment l’action, son état, la personne qui a lancé l’action et l’heure.

    ![Surveiller les actions des appareils](./media/monitor-device-actions.png)

    - **TeamViewer** : le service TeamViewer permet aux utilisateurs d’appareils Android gérés par Intune d’obtenir une assistance à distance auprès de leur administrateur informatique. Découvrez plus d’informations sur [TeamViewer](device-profile-android-teamviewer.md).

## <a name="available-device-actions"></a>Actions d’appareils disponibles
Les actions disponibles varient selon la plateforme et la configuration de l’appareil.

- [Afficher l’inventaire des appareils](device-inventory.md)
- Effectuez les actions d’appareil à distance :
    - [Supprimer les données d’entreprise](devices-wipe.md#remove-company-data)
    - [Réinitialisation aux paramètres d’usine](devices-wipe.md#factory-reset)
    - [Verrouillage à distance](device-remote-lock.md)
    - [Réinitialiser le code secret](device-passcode-reset.md)
    - [Contourner le verrouillage d’activation](device-activation-lock-bypass.md) (iOS uniquement)
    - [Redémarrage à zéro](device-fresh-start.md) (Windows uniquement)
    - [Mode Perdu](device-lost-mode.md) (iOS uniquement)
    - [Localiser l’appareil](device-locate.md) (iOS uniquement)
    - [Redémarrer](device-restart.md) (Windows uniquement)
    - [Réinitialisation du code PIN Windows 10](device-windows-pin-reset.md)
    - [Contrôle à distance pour Android](device-profile-android-teamviewer.md)
    - [Synchroniser l’appareil](device-sync.md)


## <a name="next-steps"></a>Étapes suivantes

- Choisissez **Actions de l’appareil** pour connaître l’état des actions effectuées sur les appareils que vous gérez.
