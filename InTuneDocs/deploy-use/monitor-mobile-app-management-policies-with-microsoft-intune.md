---
title: "Analyser les stratégies de gestion des applications mobiles avec Microsoft Intune | Microsoft Docs"
description: "Découvrez à combien d’utilisateurs s’applique la stratégie et explorez pour accéder à plus d’informations."
keywords: 
author: andredm7
ms.author: andredm
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
ms.sourcegitcommit: fe44466fbcef67d02b16d3d2d335f657251451d3
ms.openlocfilehash: e60d707833ee276971000411e50564f39b41b207


---

# <a name="monitor-mobile-app-management-policies-with-microsoft-intune"></a>Analyser les stratégies de gestion des applications mobiles à l’aide de Microsoft Intune
Vous pouvez surveiller l’état de conformité des stratégies de gestion des applications mobiles (GAM) que vous avez appliquées aux utilisateurs dans le panneau de protection des applications Intune dans le [portail Azure](https://portal.azure.com). Vous pouvez y trouver des informations sur les utilisateurs concernés par les stratégies GAM, l’état de conformité et tous les problèmes que vos utilisateurs pourraient rencontrer.

Vous pouvez surveiller l’état de conformité à trois endroits différents :

-   Vue Résumé

-   Vue détaillée

-   Vue Rapports

## <a name="summary-view"></a>Vue Résumé

Suivez les trois étapes ci-dessous pour ouvrir la vue Résumé :

1. Accédez au [portail Azure](https://portal.azure.com) et entrez vos informations d’identification.
2. Choisissez **Plus de services** et tapez « Intune ».
3. Choisissez **Intune App Protection** (Protection des applications Intune).

Dans le panneau **Gestion des applications mobiles Intune**, vous pouvez voir un résumé de l’état de conformité :

![Vignette Résumé sur le panneau Gestion des applications mobiles Intune](../media/mam-azure-portal-user-status-summary.png)

-   **Utilisateurs** : le nombre total d’utilisateurs dans votre société qui utilisent les applications associées à la stratégie.

-   **GÉRÉ PAR STRATÉGIE** : le nombre d’utilisateurs ayant utilisé au moins l’une des applications dans un contexte professionnel.

-   **AUCUNE STRATÉGIE** : le nombre d’utilisateurs qui utilisent les applications associées à la stratégie, mais qui ne sont pas affectés par celle-ci. Vous pouvez envisager d’ajouter ces utilisateurs à la stratégie.

- **Utilisateurs marqués d’un indicateur** : le nombre d’utilisateurs ayant rencontré des problèmes. Seuls les utilisateurs avec des appareils jailbreakés sont répertoriés sous **Utilisateurs marqués d’un indicateur**.


## <a name="detailed-view"></a>Vue détaillée
Vous pouvez accéder à la vue détaillée du résumé en choisissant les vignettes **État de l’utilisateur** (selon la plateforme de système d’exploitation de l’appareil) et **Utilisateurs marqués d’un indicateur**.

### <a name="user-status"></a>État de l’utilisateur
Vous pouvez rechercher un utilisateur et vérifier son état de conformité. Le panneau **Rapport d’application** montre les informations suivantes sur un utilisateur sélectionné :
- Les appareils associés au compte d’utilisateur

- Applications avec une stratégie GAM sur l’appareil

- État :

  - **Activé** : la stratégie a été déployée pour l’utilisateur, et l’application a été utilisée au moins une fois dans le contexte professionnel.

  - **Non activé** : la stratégie a été déployée pour l’utilisateur, mais l’application n’a pas été utilisée au moins une fois dans le contexte professionnel depuis.

>[!NOTE]
> Si la stratégie de gestion des applications mobiles n’est pas déployée sur l’utilisateur que vous recherchez, un message vous informe que l’utilisateur n’est ciblé par aucune des stratégies GAM.

Pour afficher le rapport d’un utilisateur, procédez comme suit :

1.  Pour sélectionner un utilisateur, choisissez la vignette **Résumé**.

    ![Capture d’écran 3](../media/MAM-reporting-6.png)

2. Dans le panneau **Rapport d’application**, choisissez **Sélectionner un utilisateur** pour rechercher un utilisateur Azure Active Directory.

    ![Option Sélectionner un utilisateur dans le panneau Rapport d’application](../media/MAM-reporting-2.png)

3. Sélectionnez l’utilisateur dans la liste. Les détails de l’état de conformité pour cet utilisateur apparaissent.

### <a name="flagged-users"></a>Utilisateurs marqués d’un indicateur
La vue détaillée montre le message d’erreur, l’application à laquelle l’utilisateur a accédé quand l’erreur s’est produite, la plateforme de système d’exploitation de l’appareil concernée et un horodatage.

## <a name="reporting-view"></a>Vue Rapports

Vous trouverez les mêmes rapports dans la vue détaillée, plus d’autres rapports qui vous aideront pour l’état de conformité de la stratégie GAM :

![Capture d’écran 4](../media/MAM-reporting-7.png)

-   **Rapport d’utilisateur de protection des applications :** il présente les mêmes informations qui figurent dans le rapport **État de l’utilisateur** sous la section Vue détaillée ci-dessus.

-   **Rapport d’application de protection des applications :** il fournit deux états de protection des applications différents que les administrateurs peuvent sélectionner avant de générer le rapport. Les états peuvent être protégés ou non protégés.

    ![Capture d’écran 1](../media/MAM-reporting-1.png)

    -   État de l’utilisateur pour l’activité GAM gérée (protégé) : ce rapport présente l’activité de chaque application GAM gérée, par utilisateur.

        -   Il affiche toutes les applications ciblées par les stratégies GAM de chaque utilisateur et détaille l’état de chaque application enregistrée dans les stratégies GAM ou ciblée par une stratégie GAM mais jamais enregistrée.
<br></br>
    -   État de l’utilisateur pour l’activité GAM non gérée (non protégé) : ce rapport présente l’activité des applications compatibles avec GAM qui ne sont actuellement pas gérées, par utilisateur. Cela peut se produire pour les raisons suivantes :

        -   Ces applications sont utilisées par un utilisateur ou une application qui n’est actuellement pas ciblée par une stratégie GAM.

        -   Toutes les applications sont enregistrées, mais ne reçoivent aucune stratégie GAM.

![Capture d’écran 2](../media/MAM-reporting-4.png)

## <a name="see-also"></a>Voir aussi
[Gérer les transferts de données entre applications iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Ce qui se passe quand votre application Android est gérée par des stratégies GAM](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies GAM](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)



<!--HONumber=Jan17_HO2-->


