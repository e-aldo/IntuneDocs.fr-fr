---
title: "Analyser les stratégies de gestion des applications mobiles avec Microsoft Intune | Microsoft Docs"
description: "Découvrez à combien d’utilisateurs s’applique la stratégie et explorez pour accéder à plus d’informations."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d80632aceaa675f08eb4b23ce59e3bcabb72b4d0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="monitor-app-protection-policies-with-microsoft-intune"></a>Surveiller les stratégies de protection des applications avec Microsoft Intune
Vous pouvez surveiller l’état de conformité des stratégies de protection des applications que vous avez appliquées aux utilisateurs. Vous pouvez trouver des informations sur les utilisateurs concernés par les stratégies de protection des applications, l’état de conformité et tous les problèmes que vos utilisateurs pourraient rencontrer.

Vous pouvez surveiller l’état de conformité à trois endroits différents :

-   Vue Résumé

-   Vue détaillée

-   Vue Rapports

## <a name="summary-view"></a>Vue Résumé

Suivez les trois étapes ci-dessous pour ouvrir la vue Résumé :

1. Accédez au [portail Azure](https://portal.azure.com) et entrez vos informations d’identification.
2. Choisissez **Plus de services** et saisissez **Intune** dans la zone de texte de filtre.
3. Choisissez **Protection des applications Intune**.

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

- Applications avec une stratégie de protection des applications sur l’appareil

- État :

  - **Activé** : la stratégie a été déployée pour l’utilisateur, et l’application a été utilisée au moins une fois dans le contexte professionnel.

  - **Non activé** : la stratégie a été déployée pour l’utilisateur, mais l’application n’a pas été utilisée au moins une fois dans le contexte professionnel depuis.

>[!NOTE]
> Si la stratégie de protection des applications n’est pas déployée sur l’utilisateur que vous recherchez, un message vous informe que l’utilisateur n’est ciblé par aucune des stratégies de protection des applications.

Pour afficher le rapport d’un utilisateur, procédez comme suit :

1.  Pour sélectionner un utilisateur, choisissez la vignette **Résumé**.

    ![Capture d’écran 3](../media/MAM-reporting-6.png)

2. Dans le panneau **Rapport d’application**, choisissez **Sélectionner un utilisateur** pour rechercher un utilisateur Azure Active Directory.

    ![Option Sélectionner un utilisateur dans le panneau Rapport d’application](../media/MAM-reporting-2.png)

3. Sélectionnez l’utilisateur dans la liste. Les détails de l’état de conformité pour cet utilisateur apparaissent.

### <a name="flagged-users"></a>Utilisateurs marqués d’un indicateur
La vue détaillée montre le message d’erreur, l’application à laquelle l’utilisateur a accédé quand l’erreur s’est produite, la plateforme de système d’exploitation de l’appareil concernée et un horodatage.

## <a name="reporting-view"></a>Vue Rapports

Vous trouverez les mêmes rapports dans la vue détaillée, plus d’autres rapports qui vous aideront pour l’état de conformité de la stratégie de protection des applications :

![Capture d’écran 4](../media/MAM-reporting-7.png)

-   **Rapport d’utilisateur de protection des applications :** il présente les mêmes informations qui figurent dans le rapport **État de l’utilisateur** sous la section Vue détaillée ci-dessus.

-   **Rapport d’application de protection des applications :** il fournit deux états de protection des applications différents que les administrateurs peuvent sélectionner avant de générer le rapport. Les états peuvent être protégés ou non protégés.

    -   État de l’utilisateur pour l’activité GAM gérée (protégé) : ce rapport présente l’activité de chaque application GAM gérée, par utilisateur.

        -   Il affiche toutes les applications ciblées par les stratégies de protection des applications de chaque utilisateur et détaille l’état de chaque application enregistrée dans les stratégies de protection des applications ou ciblée par une stratégie de protection des applications mais jamais enregistrée.
<br></br>
    -   État de l’utilisateur pour l’activité GAM non gérée (non protégé) : ce rapport présente l’activité des applications compatibles avec GAM qui ne sont actuellement pas gérées, par utilisateur. Cela peut se produire pour les raisons suivantes :

        -   Ces applications sont utilisées par un utilisateur ou une application qui n’est actuellement pas ciblée par une stratégie de protection des applications.

        -   Toutes les applications sont enregistrées, mais ne reçoivent aucune stratégie de protection des applications.

![Capture d’écran 2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Regroupement de tables

Une fois que les données du **rapport d’utilisateur de la protection des applications** s’affichent, vous pouvez les regrouper selon les éléments suivants :

- **Résultat de la validation :** les données s’affichent groupées selon l'état de protection de l’application, qui peut être réussite, avertissement ou échec.
- **Nom de l’application :** les données s’affichent regroupées par applications (le véritable nom de l’application) avec succès, avertissement ou échec.

## <a name="export-app-protection-activities-to-csv"></a>Exportation des activités de protection d’application au format CSV

Vous pouvez exporter toutes vos activités de stratégie de protection des applications vers un fichier .csv. Cela peut être utile pour analyser tous les états de protection des applications signalés par les utilisateurs.

Suivez ces étapes pour générer le rapport de protection des applications :

1. Dans le panneau Gestion des applications mobiles Intune, choisissez le rapport de protection des applications.

    ![Capture d’écran 6](../media/app-protection-report-csv-2.png)

2. Choisissez Oui pour enregistrer votre rapport, puis cliquez sur Enregistrer sous et sélectionnez le dossier dans lequel vous souhaitez enregistrer le rapport.

    ![Capture d’écran 7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Voir aussi
[Gérer les transferts de données entre applications iOS](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Ce qui se passe quand votre application Android est gérée par des stratégies de protection d'application](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Ce qui se passe quand votre application iOS est gérée par des stratégies de protection d'application](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)
