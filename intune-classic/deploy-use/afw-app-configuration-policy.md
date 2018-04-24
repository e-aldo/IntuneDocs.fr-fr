---
title: Stratégie de configuration des applications Android for Work
description: Utilisez des stratégies de configuration d’application mobile dans Intune pour fournir les paramètres pouvant être nécessaires quand les utilisateurs exécutent une application Android for Work.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 02/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7bebf6137b7378c52741195a1dce048caaa03e3d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a>Configurer des applications Android for Work avec des stratégies de configuration des applications mobiles dans Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Utilisez des stratégies de configuration des applications mobiles dans Microsoft Intune pour fournir les paramètres pouvant être nécessaires quand les utilisateurs exécutent une application. Par exemple, une application peut exiger que les utilisateurs spécifient les paramètres suivants :

-   Un numéro de port personnalisé
-   Paramètres de langue
-   Paramètres de personnalisation comme le logo de l’entreprise

Si les utilisateurs n’entrent pas correctement ces paramètres, ils occasionnent plus de travail à votre support technique et ralentissent l’adoption des nouvelles applications.

Les stratégies de configuration des applications mobiles vous permettent de déployer ces paramètres sur les appareils avant que les utilisateurs n’exécutent l’application. Les paramètres sont fournis automatiquement et les utilisateurs n’ont aucune action à effectuer.

Pour utiliser les stratégies de configuration des applications, le développeur de l’application doit avoir exposé les configurations d’application de l’entreprise quand il a créé l’application. Par exemple, Google Chrome expose des paramètres qui vous permettent de définir des signets par défaut, les sites autorisés et refusés et bien plus encore. Contactez le développeur de l’application pour voir si ces paramètres sont pris en charge et comment les spécifier dans la stratégie.

Vous déployez la stratégie de configuration des applications pour les utilisateurs pour lesquels vous avez déployé l’application que vous souhaitez configurer. Les paramètres d’application sont pris en compte quand l’application est exécutée.

## <a name="configure-a-mobile-app-configuration-policy"></a>Configurer une stratégie de configuration des applications mobiles

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Stratégie** &gt; **Vue d’ensemble** &gt; **Ajouter une stratégie**.

2.  Dans la liste des stratégies, développez **Android for Work**, choisissez **Stratégie de configuration des applications mobiles (Android for Work)**, puis **Créer une stratégie**.

    > [!TIP]
    > Vous ne pouvez configurer des paramètres personnalisés que pour ce type de stratégie. Les paramètres recommandés ne sont pas disponibles.

3.  Dans la section **Général** de la page **Créer une stratégie**, fournissez un nom et éventuellement une description de la stratégie de configuration des applications mobiles.

4. Dans la section **Stratégie de configuration d’appareils mobiles** de la page, spécifiez les informations suivantes :
    - **ID de package de l’application à laquelle s’applique cette configuration** : l’ID de package se trouve dans la section « id= » de l’URL de l’application sur sa page Google Play. Par exemple, l’ID de package pour l’application Microsoft Excel est **com.microsoft.office.excel**.
    - Dans la zone de texte, entrez les données pour les paramètres d’application que vous souhaitez configurer. Vous obtenez ces paramètres auprès du fournisseur de l’application. Toutes les applications ne prennent pas en charge ces paramètres.
5.  Cliquez sur **Valider** pour vérifier que le format de liste de propriétés des données entrées est valide.

    > [!IMPORTANT]
    > Quand vous cliquez sur **Valider**, Intune vérifie que le format des données de configuration entrées est valide. Il ne vérifie pas que les données fonctionnent avec l’application à laquelle elles sont associées.

6.  Une fois terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s’affiche dans le nœud **Stratégies de configuration** .


## <a name="deploy-the-app-configuration-policy"></a>Déployer la stratégie de configuration des applications
Après avoir créé une stratégie de configuration des applications mobiles, vous devez la déployer pour les utilisateurs pour lesquels vous déployez l’application à laquelle s’appliquent les paramètres.

Pour plus d’informations sur la manière de déployer des stratégies, consultez [Déployer une stratégie de configuration](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).

Pour plus d’informations sur le déploiement des applications sur les appareils Android for Work, consultez [Comment déployer des applications Android for Work avec Intune](android-for-work-apps.md).

Quand l’application déployée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications mobiles.

> [!TIP]
> Déployez uniquement une stratégie de configuration des applications par application sur un utilisateur.
