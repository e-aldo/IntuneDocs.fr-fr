---
title: "Paramètres de restriction d’appareil Intune pour Windows Holographic for Business"
titlesuffix: Azure portal
description: "Découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 1/19/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 300ddb15f2d7b8f2fc6ab4a0e9e32852e0604e0a
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2018
---
# <a name="windows-holographic-for-business-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction d’appareil Windows Holographic for Business dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les paramètres de restriction d’appareil suivants sont pris en charge sur les appareils exécutant Windows Holographic for Business, comme Microsoft Hololens.

## <a name="general"></a>Général

- **Inscription manuelle** - Permet à l’utilisateur de supprimer manuellement le compte d’espace de travail de l’appareil.
- **Cortana** - Active ou désactive l’assistant vocal Cortana.
- **Géolocalisation** - Spécifie si l’appareil peut utiliser les informations des services d’emplacement.



## <a name="password"></a>Mot de passe
-   **Mot de passe** - Demande à l’utilisateur final d’entrer un mot de passe pour accéder à l’appareil.
    -   **Exiger un mot de passe quand l'appareil sort d'un état d'inactivité** : Spécifie que l’utilisateur doit entrer un mot de passe pour déverrouiller l’appareil.



## <a name="app-store"></a>App Store

-   **App Store** : Active ou bloque l’utilisation de l’App Store sur les appareils.
-   **Mettre à jour automatiquement les applications du Windows store** - Permet aux applications installées à partir du Microsoft Store d’être automatiquement mises à jour.
-   **Installation d’applications approuvées** - Permet de charger indépendamment les applications signées avec un certificat approuvé.
-   **Déverrouillage de développement** - Autorise les paramètres de développement Windows, par exemple pour autoriser l’utilisateur à modifier des applications qui ont été chargées indépendamment.

## <a name="edge-browser"></a>Navigateur Edge

-   **Navigateur Microsoft Edge** : Autorise l’utilisation du navigateur web Edge sur l’appareil.
-   **Cookies** - Permet au navigateur d’enregistrer les cookies internet sur l’appareil.
-   **Fenêtres contextuelles** : Bloque les fenêtres publicitaires dans le navigateur (s’applique à Windows 10 Desktop uniquement).
-   **Suggestions de recherche** - Permet à votre moteur de recherche de suggérer des sites à mesure que vous saisissez des expressions de recherche.
-   **Gestionnaire de mots de passe** - Activer ou désactiver la fonctionnalité Gestionnaire de mots de passe Microsoft Edge.
- **Envoyer un en-tête Do Not Track** - Configure le navigateur Microsoft Edge pour envoyer des en-êtes Do Not Track aux sites web que les utilisateurs visitent.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen pour Microsoft Edge** - Activer Edge SmartScreen pour accéder au site et aux téléchargements de fichiers.

## <a name="search"></a>Recherche
- **Emplacement de recherche** : Spécifie si la recherche peut utiliser l’emplacement. Informations


## <a name="cloud-and-storage"></a>Cloud et stockage
-   **Compte Microsoft** - Permet à l’utilisateur d’associer un compte Microsoft à l’appareil.

## <a name="cellular-and-connectivity"></a>Cellulaire et connectivité

-   **Bluetooth** - Contrôle si l’utilisateur peut activer et configurer la fonction Bluetooth sur l’appareil.
-   **Détectabilité de Bluetooth** - Permet à cet appareil d’être découvert par d’autres appareils Bluetooth.
-   **Publicité Bluetooth** - Permet à l’appareil de recevoir des publications via Bluetooth.

## <a name="control-panel-and-settings"></a>Panneau de configuration et paramètres

- **Modification de l’heure système** - Empêche l’utilisateur final de modifier la date et l’heure de l’appareil.

## <a name="reporting-and-telemetry"></a>Création de rapports et les données de télémétrie

- **Partager les données d’utilisation** - Sélectionner le niveau d'envoi des données de diagnostic.