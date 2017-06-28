---
title: "Guide de création de profils VPN personnalisés avec Microsoft Intune"
titleSuffix: Intune on Azure
description: "Utilisez des configurations personnalisées pour créer des profils VPN dans Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 11da0d31a9a00364a6105006c3e75b6bb6f2cb77
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017


---

# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Guide pratique pour créer des profils VPN personnalisés dans Microsoft Intune

## <a name="create-a-custom-configuration"></a>Créer une configuration personnalisée
Vous pouvez utiliser des stratégies de configuration personnalisées Intune afin de créer des profils VPN pour :

* Appareils qui exécutent Android 4 et versions ultérieures
* Appareils inscrits qui exécutent Windows 8.1 et versions ultérieures
* Appareils qui exécutent Windows Phone 8.1 et versions ultérieures
* Appareils inscrits qui exécutent Windows 10 Desktop 
* Appareils exécutant Windows 10 Mobile

Ce type de stratégie peut être utile lorsque les stratégies VPN Intune standard n'incluent pas les paramètres que vous souhaitez utiliser.

## <a name="to-create-a-custom-configuration-policy"></a>Pour créer une stratégie de configuration personnalisée :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
4. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
5. Dans le panneau des profils, sélectionnez **Créer un profil**.
6. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour votre profil VPN.
7. À partir de la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil à laquelle vous souhaitez appliquer les paramètres VPN. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres personnalisés :
    - **Android**
    - **iOS** (configuré à l’aide d’un fichier que vous avez exporté à partir d’Apple Configurator).
    - **macOS** (configuré à l’aide d’un fichier que vous avez exporté à partir d’Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Personnalisé**.
7. Dans le panneau **Paramètres OMA-URI personnalisés**, choisissez **Ajouter** pour chaque paramètre d’URI que vous souhaitez spécifier, fournissez les informations demandées, puis choisissez **OK**. Voici un exemple :

   ![Boîte de dialogue de configuration personnalisée de profil VPN](./media/Intune_Add_VPN_URI.png)

4.  Une fois que vous avez entré tous les paramètres des URI dont vous avez besoin, choisissez **OK**, puis, dans le panneau **Créer un profil**, choisissez **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).





