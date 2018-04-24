---
title: Guide de création de profils VPN personnalisés avec Microsoft Intune
titleSuffix: ''
description: Utilisez des configurations personnalisées pour créer des profils VPN dans Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec9b959d086051985287a62f7d10fe8d4cbad7e9
ms.sourcegitcommit: 28ed8902a11500b195fff839d59b90c16af6e743
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Guide pratique pour créer des profils VPN personnalisés dans Microsoft Intune

Vous pouvez utiliser des stratégies de configuration personnalisées Intune afin de créer des profils VPN pour les plateformes suivantes :

* Android 4 et versions ultérieures
* Appareils inscrits qui exécutent Windows 8.1 et versions ultérieures
* Windows Phone 8.1 et versions ultérieures
* Appareils inscrits qui exécutent Windows 10 Desktop 
* Windows 10 Mobile

Ce type de stratégie peut être utile quand les stratégies VPN Intune standard ne comprennent pas les paramètres que vous souhaitez utiliser.

## <a name="to-create-a-custom-configuration-policy"></a>Pour créer une stratégie de configuration personnalisée :

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le volet **Configuration de l’appareil**, sous la section **Gérer**, choisissez **Profils**.
5. Dans le volet de profils, choisissez **Créer un profil**.
6. Dans le volet **Créer un profil**, entrez un **Nom** et la **Description** du profil VPN.
7. À partir de la liste déroulante **Plateforme**, sélectionnez la plateforme de l’appareil auquel vous souhaitez appliquer les paramètres VPN. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres personnalisés :
    - **Android**
    - **Android for Work**
    - **iOS** (configuré à l’aide d’un fichier que vous avez exporté à partir d’Apple Configurator).
    - **macOS** (configuré à l’aide d’un fichier que vous avez exporté à partir d’Apple Configurator).
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Personnalisé**.
7. Dans le volet **Paramètres OMA-URI personnalisés**, choisissez **Ajouter** pour chaque paramètre d’URI que vous souhaitez spécifier, fournissez les informations demandées, puis choisissez **OK**. Voici un exemple :

   ![Boîte de dialogue de configuration personnalisée de profil VPN](./media/Intune_Add_VPN_URI.png)

4.  Une fois que vous avez entré tous les paramètres des URI dont vous avez besoin, choisissez **OK** puis, dans le volet **Créer un profil**, choisissez **Créer**.

Le profil est créé et apparaît dans le volet de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).




