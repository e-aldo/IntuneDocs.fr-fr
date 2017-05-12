---
title: "Créer des profils de configuration d’appareil Intune | Préversion Intune Azure"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Apprenez à créer des profils de configuration d’appareil Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 74a905ed2ba9ec04ae14df96fcd3f6b6caf1241c
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Guide pratique pour créer des profils de configuration d’appareil dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
2. Dans le volet présentant la liste de profils, choisissez **Créer un profil**.
3. Dans le panneau **Créer un profil**, spécifiez les valeurs suivantes :
    - **Nom** : attribuez un nom descriptif au nouveau profil.
    - **Description** : entrez une description facultative pour le profil.
    - **Plateforme** : sélectionnez le type de plateforme pour le profil que vous souhaitez créer.
    - **Type de profil** : sélectionnez le type de profil que vous souhaitez créer. La liste des types disponibles varie selon la plateforme que vous avez choisie.
    - **Paramètres** : consultez les rubriques suivantes pour plus d’informations sur les paramètres pour chaque type de profil :
        -  [Paramètres de fonctionnalité d’appareil](how-to-configure-device-features.md)
        -  [Paramètres de restriction d'appareil](how-to-configure-device-restrictions.md)
        -  [Paramètres de courrier électronique](how-to-configure-email-settings.md)
        -  [Paramètres VPN](how-to-configure-vpn-settings.md)
        -  [Paramètres Wi-Fi](how-to-configure-wi-fi-settings.md)
        -  [Paramètres de mise à niveau Windows 10](how-to-configure-windows-10-edition-upgrade.md)
        -  [Paramètres de certificat](how-to-configure-certificates.md)
        -  [Paramètres de Windows Information Protection](how-to-configure-windows-information-protection.md)
        -  [Paramètres de formation](how-to-configure-education-settings.md)
        -  [Paramètres personnalisés](how-to-configure-custom-settings.md)

    ![Créer un profil d’appareil](./media/create-device-profile.png)
4. Une fois que vous avez terminé la configuration des paramètres dans le panneau **Créer un profil**, choisissez **Créer**.

Le profil est créé et s’affiche dans le volet de la liste des profils.
Si vous souhaitez continuer et affecter ce profil à des groupes, consultez [Guide pratique pour affecter des profils d'appareil](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur la façon d’affecter des profils d'appareil, consultez [Guide pratique pour affecter des profils d'appareil avec Microsoft Intune](how-to-assign-device-profiles.md).

