---
title: Déployer des applications
description: Cette rubrique décrit des concepts que vous devez comprendre avant de commencer à déployer des applications avec Intune.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9762c20abb9e4eedded50c92fb10ffb6119be63e
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="deploy-apps-with-microsoft-intune"></a>Déployer des applications avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique décrit certains des concepts que vous devez comprendre avant de commencer à déployer des applications avec Microsoft Intune.


## <a name="app-deployment-actions"></a>Actions de déploiement d’applications
Quand vous déployez des applications, vous pouvez choisir parmi les actions de déploiement suivantes :

-   **Installation requise** : l’application est installée sur l’appareil sans intervention de l’utilisateur.

    > [!TIP]
    > Pour les appareils iOS qui ne sont pas en mode supervisé et pour tous les appareils Android, l’utilisateur doit accepter l’offre de l’application avant son installation.
    >
    >  Si un utilisateur désinstalle une application que vous avez déployée comme installation requise, Intune réinstalle automatiquement l’application après le prochain cycle d’inventaire, qui se produit généralement tous les sept jours.

-   **Installation disponible** : l’application s’affiche sur le portail d’entreprise et les utilisateurs peuvent l’installer à la demande.

-   **Désinstaller** : l'application est désinstallée de l'appareil.

-   **Non applicable** : l’application n'est pas affichée dans le portail d'entreprise et n’est pas installée sur les appareils.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>Comprendre quelles actions de déploiement sont disponibles pour chaque type de programme d’installation

|Type de programme d’installation|Installation requise|Installation disponible|Désinstaller|Non applicable|
|------------------|--------------------|---------------------|-------------|------------------|
|Package d'application Windows (déployé sur un groupe d'utilisateurs)|Oui|Oui|Oui|Oui|
|Package d’application Windows (déployé sur un groupe d’appareils)|Oui|Non|Oui|Oui|
|Package d'application pour les appareils mobiles (déployé sur un groupe d'utilisateurs)|Oui|Oui|Oui|Oui|
|Package d'application pour les appareils mobiles (déployé sur un groupe d'appareils)|Oui|Non|Oui|Oui|
|Windows Installer (déployé sur un groupe d'utilisateurs)|Non|Oui|Non|Oui|
|Windows Installer (déployé sur un groupe d'appareils)|Oui|Non|Oui|Oui|
|Lien externe (déployé sur un groupe d'utilisateurs)|Non|Oui|Non|Oui|
|Lien externe (déployé sur un groupe d'appareils)|Non|Non|Non|Non|
|Application iOS gérée à partir de l'App Store (déployée sur un groupe d'utilisateurs)|Oui|Oui|Oui|Oui|
|Application iOS gérée à partir de l'App Store (déployée sur un groupe d'appareils)|Oui|Non|Oui|Oui|
> [!TIP]
> Quand vous déployez des applications, si vous sélectionnez à la fois des groupes d’utilisateurs et des groupes d’appareils, vous pouvez déployer l’application seulement comme **Installation disponible**.

## <a name="deployment-conflicts"></a>Conflits de déploiement
Quand un appareil reçoit deux déploiements avec la même action de déploiement, les règles suivantes s'appliquent :

-   Les déploiements sur un groupe d'appareils ont la priorité sur les déploiements sur un groupe d'utilisateurs. Toutefois, si une application est déployée sur un groupe d’utilisateurs avec une action de déploiement **Disponible** et que la même application est également déployée sur un groupe d’appareils avec une action de déploiement **Non applicable**, l’application est disponible sur le portail d’entreprise pour que les utilisateurs puissent l’installer.

-   Une action d’installation est prioritaire sur une action de désinstallation.

-   Si un appareil reçoit une installation requise et une installation disponible, les actions sont combinées. En d’autres termes, l’utilisateur peut installer l’application disponible à partir du portail d’entreprise avant que l’installation requise ne commence.


## <a name="next-steps"></a>Étapes suivantes

Découvrez comment [déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).
