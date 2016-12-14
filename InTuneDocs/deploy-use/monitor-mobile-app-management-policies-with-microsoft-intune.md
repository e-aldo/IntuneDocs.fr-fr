---
title: "Analyser les stratégies de gestion des applications mobiles avec Microsoft Intune | Microsoft Intune"
description: "Découvrez à combien d’utilisateurs s’applique la stratégie et explorez pour accéder à plus d’informations."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 487fe778bae73c2ac5564f90c21328932060f576


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Analyser les stratégies de gestion des applications mobiles à l’aide de Microsoft Intune
Après avoir configuré une stratégie de gestion des applications mobiles (GAM) et l’avoir appliquée à des utilisateurs, vous pouvez surveiller l’état de conformité dans le [portail Azure](https://portal.azure.com). Le portail Azure inclut des informations sur les utilisateurs concernés par la stratégie, l’état de conformité et les problèmes que vos utilisateurs pourraient rencontrer.
## <a name="summary-view"></a>Vue Résumé
Dans le panneau **Gestion des applications mobiles Intune**, vous pouvez voir un résumé de l’état de conformité :


![Vignette Résumé sur le panneau Gestion des applications mobiles Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Utilisateurs** : le nombre total d’utilisateurs dans votre société qui utilisent les applications associées à la stratégie.

-   **GÉRÉ PAR STRATÉGIE** : le nombre d’utilisateurs ayant utilisé au moins l’une des applications dans un contexte professionnel.

-   **AUCUNE STRATÉGIE** : le nombre d’utilisateurs qui utilisent les applications associées à la stratégie, mais qui ne sont pas affectés par celle-ci. Vous pouvez envisager d’ajouter ces utilisateurs à la stratégie.

- **Utilisateurs marqués d’un indicateur** : le nombre d’utilisateurs ayant rencontré des problèmes. Seuls les utilisateurs avec des appareils jailbreakés sont répertoriés sous **Utilisateurs marqués d’un indicateur**.


## <a name="detailed-view"></a>Vue détaillée
Vous pouvez accéder à la vue détaillée du résumé en choisissant les vignettes **État de l’utilisateur** et **Utilisateurs marqués d’un indicateur**.

### <a name="user-status"></a>État de l’utilisateur
Vous pouvez rechercher un utilisateur et vérifier son état de conformité. Le panneau **Rapport d’application** montre les informations suivantes sur un utilisateur sélectionné :
- Les appareils associés au compte d’utilisateur

- Applications avec une stratégie GAM sur l’appareil

- État :

  - **Activé** : la stratégie a été déployée pour l’utilisateur, et l’application a été utilisée au moins une fois dans le contexte professionnel.

  - **Non activé** : la stratégie a été déployée pour l’utilisateur, mais l’application n’a pas été utilisée au moins une fois dans le contexte professionnel depuis.

>[!NOTE]
> Si la stratégie de gestion des applications mobiles n’est pas appliquée à l’utilisateur que vous recherchez, un message vous informe que l’utilisateur n’est ciblé par aucune des stratégies d’application.

Pour afficher le rapport d’un utilisateur, procédez comme suit :

1.  Pour sélectionner un utilisateur, choisissez la vignette **Résumé** ou choisissez l’option **RAPPORT D’APPLICATION PAR L’UTILISATEUR** dans le panneau **Paramètres** :

    ![Option de rapport d’application dans le panneau Paramètres](../media/mam-azure-portal-app-reporting-by-user-settings-blade.png)

2. Dans le panneau **Rapport d’application**, choisissez **Sélectionner un utilisateur** pour rechercher un utilisateur Azure Active Directory.

    ![Option Sélectionner un utilisateur dans le panneau Rapport d’application](../media/mam-azure-portal-app-reporting-select-user.png)

3. Sélectionnez l’utilisateur dans la liste. Les détails de l’état de conformité pour cet utilisateur apparaissent.

    ![Détails du rapport d’application](../media/mam-azure-portal-app-reporting-by-user.png)

### <a name="flagged-users"></a>Utilisateurs marqués d’un indicateur
La vue détaillée montre le message d’erreur, l’application à laquelle l’utilisateur a accédé quand l’erreur s’est produite, la plateforme de l’appareil et un horodatage.  

### <a name="see-also"></a>Voir aussi
[Gérer les transferts de données entre applications iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Ce qui se passe quand votre application Android est gérée par des stratégies GAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies GAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


