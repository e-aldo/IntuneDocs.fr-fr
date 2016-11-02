---
title: "Portail Azure pour les stratégies de gestion des applications mobiles | Microsoft Intune"
description: "Créez des stratégies de gestion des applications mobiles à l’aide du portail Azure. Les stratégies que vous créez ici sont applicables aux appareils, qu’ils soient inscrits à Intune ou non."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9eb7e79bee2bc36dffab97ffdb6f665218bc739e
ms.openlocfilehash: 0acef421f179ebf922ec8af71ba336e3e5f96bd2


---

# Portail Azure pour les stratégies de gestion des applications mobiles Microsoft Intune
## Utiliser le portail Azure
Le portail Azure permet de créer et de gérer des stratégies de gestion des applications mobiles (GAM).

Il prend en charge la création de stratégies de gestion des applications mobiles pour :
- Les applications qui s’exécutent sur des appareils **inscrits et gérés dans Intune**.
- Les applications qui s’exécutent sur des appareils qui ne sont inscrits dans **aucune** solution de gestion des appareils mobiles.
- Les applications qui s’exécutent sur des appareils qui sont **inscrits dans une solution de gestion des appareils mobiles tierce**.

>[!IMPORTANT]

> Si vous utilisez la console d’administration Intune pour gérer vos appareils, vous pouvez créer une stratégie de gestion des applications mobiles qui prend en charge des applications pour les appareils inscrits dans Intune à l’aide de la [console d’administration Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> La console d’administration Intune peut ne pas afficher tous les paramètres de stratégie de gestion des applications mobiles. Le portail Azure est la nouvelle console d’administration pour créer des stratégies de gestion des applications mobiles. Si vous créez ces stratégies à la fois sur la console d’administration Intune et le portail Azure, la stratégie dans le portail Azure est appliquée aux applications et déployée sur les utilisateurs.

## Se connecter au portail Azure et personnaliser la page de démarrage

1.  Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Capture d’écran de la page de connexion du portail Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Une fois que vous êtes connecté, la page **Tableau de bord** apparaît. La page **Tableau de bord** peut être personnalisée.

    ![Capture d’écran du tableau de bord du portail Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Dans le menu **Parcourir**, recherchez **Intune**.![Capture d’écran du menu Parcourir avec Intune mis en surbrillance](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Choisissez **Intune** > **Gestion des applications mobiles Intune** > **Paramètres**.

    ![Capture d’écran du panneau Gestion des applications mobiles Intune](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Pour épingler un panneau sur la page de **démarrage**, choisissez l’icône représentant une épingle dans le panneau **Gestion des applications mobiles Intune**.

    ![Capture d’écran du panneau Gestion des applications mobiles Intune avec l’icône d’épingle en surbrillance](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Capture d’écran du tableau de bord avec la vignette Intune épinglée](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Étapes suivantes
[Préparez-vous à configurer des stratégies de gestion des applications mobiles](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


