---
title: "Déployer des applications | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
ms.sourcegitcommit: e6b995118e66fd146a68b49ce4decdcbd1fe3572
ms.openlocfilehash: a68cb85602bd585539147c7d7d38c0d906f2b1f7


---

# Déployer des applications avec Microsoft Intune

Cette rubrique décrit certains des concepts que vous devez comprendre avant de commencer à déployer des applications avec Microsoft Intune.


## Actions de déploiement d’applications
Quand vous déployez des applications, vous pouvez choisir parmi les actions de déploiement suivantes :

-   **Installation requise** : l’application est installée sur l’appareil, sans intervention de l’utilisateur final.

    > [!TIP]
    > [!TIP] Pour les appareils iOS qui ne sont pas en mode supervisé et pour tous les appareils Android, l’utilisateur doit accepter l’offre de l’application avant son installation.
    > 
    >  Si un utilisateur final désinstalle une application que vous avez déployée comme installation requise, Intune réinstalle automatiquement l’application après le cycle d’inventaire suivant, qui se produit généralement tous les 7 jours.

-   **Installation disponible** : l’application s’affiche sur le portail d’entreprise et les utilisateurs finaux peuvent l’installer à la demande.

-   **Désinstaller** : l'application est désinstallée de l'appareil.

-   **Non applicable** : l'application n'est pas affichée dans le portail d'entreprise et n'est pas installée sur les appareils.

#### Comprendre quelles actions de déploiement sont disponibles pour chaque type de programme d’installation

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
> [!TIP] Quand vous déployez des applications, si vous sélectionnez à la fois des groupes d’utilisateurs et des groupes d’appareils, vous pouvez déployer l’application seulement comme **Installation disponible**.

## Conflits de déploiement
Quand deux déploiements avec la même action de déploiement sont reçus par un appareil, les règles suivantes s'appliquent :

-   Les déploiements sur un groupe d'appareils ont la priorité sur les déploiements sur un groupe d'utilisateurs. Toutefois, si une application est déployée sur un groupe d'utilisateurs avec une action de déploiement **Disponible** et que la même application est également déployée sur un groupe d'appareils avec une action de déploiement **Non applicable**, l'application est disponible sur le portail d'entreprise pour que les utilisateurs puissent l'installer.

-   Une action d’installation est prioritaire sur une action de désinstallation.

-   Si une installation requise et une installation disponible sont reçues par un appareil, les actions sont combinées (l’application est à la fois requise et disponible ; en d’autres termes, l’utilisateur final peut l’installer à partir du portail d’entreprise avant le début de l’installation requise).


## Étapes suivantes

Découvrez comment [déployer des applications dans Microsoft Intune](deploy-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO2-->


