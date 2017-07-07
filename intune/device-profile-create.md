---
title: "Création de profils de configuration d’appareil Intune"
titleSuffix: Intune on Azure
description: "Apprenez à créer des profils de configuration d’appareils dans Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6df6813667241d3ad5f8768585f2e1a34f0fe6e3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Guide pratique pour créer des profils de configuration d’appareil dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
2. Dans le volet présentant la liste de profils, choisissez **Créer un profil**.
3. Dans le panneau **Créer un profil**, spécifiez les éléments suivants :
    - **Nom** : attribuez un nom descriptif au nouveau profil.
    - **Description** : entrez une description facultative pour le profil.
    - **Plateforme** : sélectionnez le type de plateforme pour le profil que vous souhaitez créer.
    - **Type de profil** : sélectionnez le type de profil que vous souhaitez créer. La liste des types disponibles varie selon la plateforme que vous avez choisie.
    - **Paramètres** : consultez les rubriques suivantes pour plus d’informations sur les paramètres pour chaque type de profil :
        -  [Paramètres de fonctionnalité d’appareil](device-features-configure.md)
        -  [Paramètres de restriction d'appareil](device-restrictions-configure.md)
        -  [Paramètres de courrier électronique](email-settings-configure.md)
        -  [Paramètres VPN](vpn-settings-configure.md)
        -  [Paramètres Wi-Fi](wi-fi-settings-configure.md)
        -  [Paramètres de mise à niveau Windows 10](edition-upgrade-configure-windows-10.md)
        -  [Paramètres de certificat](certificates-configure.md)
        -  [Paramètres de Windows Information Protection](windows-information-protection-configure.md)
        -  [Paramètres de formation](education-settings-configure.md)
        -  [Paramètres personnalisés](custom-settings-configure.md)

    ![Créer un profil d’appareil](./media/create-device-profile.png)
4. Une fois que vous avez terminé la configuration des paramètres dans le panneau **Créer un profil**, choisissez **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).


### <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur la façon d’affecter des profils d'appareil, consultez [Guide pratique pour affecter des profils d'appareil avec Microsoft Intune](device-profile-assign.md).
