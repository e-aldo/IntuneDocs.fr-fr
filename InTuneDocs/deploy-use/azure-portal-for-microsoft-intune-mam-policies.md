---
title: "Portail Azure pour les stratégies de gestion des applications mobiles | Microsoft Docs"
description: "Créez des stratégies de gestion des applications mobiles à l’aide du portail Azure. Les stratégies que vous créez ici sont applicables aux appareils, qu’ils soient inscrits à Intune ou non."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e2503c44f434e67f45064f28d1e921eb5accb0b6
ms.openlocfilehash: 2707e3fae32e73aa17696886f493932e903ffc10


---

# <a name="azure-portal-for-intune-app-protection-policies"></a>Portail Azure pour les stratégies de protection des applications

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Le portail Azure permet de créer et de gérer des stratégies de protection des applications pour :

- Les applications qui s’exécutent sur des appareils **inscrits et gérés dans Intune**.

- Les applications qui s’exécutent sur des appareils qui ne sont inscrits dans **aucune** solution de gestion des appareils mobiles.
- Les applications qui s’exécutent sur des appareils qui sont **inscrits dans une solution de gestion des appareils mobiles tierce**.

>[!IMPORTANT]
> Le portail Azure est la nouvelle console d’administration permettant de créer des stratégies de protection des applications, mais vous pouvez également créer une stratégie de protection des applications qui prend en charge des applications pour les appareils inscrits dans Intune à l’aide de la [console d’administration Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) pour les scénarios de gestion des appareils mobiles.

> La console d’administration Intune peut ne pas afficher tous les paramètres de stratégie de protection des applications disponibles. En outre, si vous créez des stratégies de protection des applications dans la console d’administration Intune et le portail Azure, les stratégies créées dans le portail Azure remplacent celles créées dans la console d’administration Intune. Dans ce scénario, les stratégies de protection des applications du portail Azure sont appliquées aux applications et déployées sur les utilisateurs.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Se connecter au portail Azure et personnaliser la page de démarrage

1.  Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

    ![Capture d’écran de la page de connexion du portail Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Une fois correctement connecté, le **tableau de bord** apparaît. La page **Tableau de bord** peut être personnalisée.

    ![Capture d’écran du tableau de bord du portail Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Choisissez **Plus de services** dans le menu gauche, puis tapez **Intune** dans le filtre de zone de texte.

    ![Capture d’écran du menu Parcourir avec Intune mis en surbrillance](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Choisissez **Protection des applications Intune** > **Gestion des applications mobiles Intune** > **Tous les paramètres**.

    ![Capture d’écran du panneau Gestion des applications mobiles Intune](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Facultatif) : pour épingler un panneau sur la page de **démarrage**, vous pouvez utiliser l’option **épingler** du panneau. Cliquez sur l’icône représentant une épingle dans le **panneau de gestion des applications mobiles Intune**, pour épingler ce dernier sur la page de **démarrage**.

    ![Capture d’écran du panneau Gestion des applications mobiles Intune avec l’icône d’épingle en surbrillance](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Capture d’écran du tableau de bord avec la vignette Intune épinglée](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Étapes suivantes
[Préparation à la configuration de stratégies de protection d’applications](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Feb17_HO3-->


