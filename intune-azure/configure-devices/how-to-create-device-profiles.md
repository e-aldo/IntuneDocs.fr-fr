---
title: "Création de profils de configuration d’appareil Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : apprenez à créer des profils de configuration d’appareil Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 6c6ac8112a6b6413df635607a24d0d06466c0b88


---

# <a name="how-to-create-device-configuration-profiles"></a>Guide pratique de création de profils de configuration d’appareil 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Analyse + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
2. Dans le volet présentant la liste de profils, choisissez **Créer un profil**.
3. Dans le panneau **Créer un profil**, spécifiez les valeurs suivantes :
    - **Nom** : attribuez un nom descriptif au nouveau profil.
    - **Description** : entrez une description facultative pour le profil.
    - **Plateforme** : sélectionnez le type de plateforme pour le profil que vous souhaitez créer.
    - **Type de profil** : sélectionnez le type de profil que vous souhaitez créer. La liste des types disponibles varie selon la plateforme que vous avez choisie.
    - **Paramètres** : consultez les rubriques suivantes pour plus d’informations sur les paramètres pour chaque type de profil :
        -  [Paramètres de restriction d'appareil](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [Paramètres de courrier électronique](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [Paramètres VPN](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Paramètres Wi-Fi](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Paramètres de mise à niveau Windows 10](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Paramètres de certificat](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Paramètres de Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Paramètres de formation](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Paramètres personnalisés](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Créer un profil d’appareil](./media/create-device-profile.png)
4. Une fois que vous avez terminé la configuration des paramètres dans le panneau **Créer un profil**, choisissez **Créer**.

Le profil est créé et s’affiche dans le volet de la liste des profils.
Si vous souhaitez continuer et affecter ce profil à des groupes, consultez [Guide pratique d’affectation des profils d'appareil](how-to-assign-device-profiles.md).


### <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur la façon d’affecter des profils d'appareil, consultez [Guide pratique d’affectation des profils d'appareil avec Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles).



<!--HONumber=Feb17_HO1-->


