---
title: "Protéger les applications métier sur des appareils non inscrits | Microsoft Intune"
description: "Cette rubrique décrit la procédure à suivre pour préparer vos applications métier personnalisées afin d’appliquer des stratégies de gestion des applications mobiles qui peuvent éviter de perdre des données."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6ff74f0b46baf384dbdedf13ad75538dd33a089
ms.openlocfilehash: bc1efb1e0c62e6bd52658690db95901c70403d4d


---

# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a>Protéger les données et applications métier sur des appareils non inscrits dans Microsoft Intune

Les stratégies de gestion des applications mobiles protègent les données de l’entreprise en limitant les actions qui pourraient provoquer une fuite des données de l’entreprise et en appliquant des exigences pour l’accès aux données, comme le code confidentiel d’une application. Pour appliquer des stratégies de gestion des applications mobiles à des applications métier iOS et Android, vous devez d’abord encapsuler l’application avec l’outil de création de package de restrictions d’application Microsoft Intune. L’encapsulation d’application est le processus visant à appliquer une couche de gestion à une application mobile sans exiger la moindre modification de l’application sous-jacente. Une fois l’application encapsulée, vous pouvez lui appliquer des stratégies de gestion des applications mobiles et la distribuer aux utilisateurs.  

Cette rubrique décrit les étapes nécessaires pour appliquer des stratégies de gestion des applications mobiles pour les applications accessibles sur les **appareils personnels des employés qui ne sont pas gérés** et les appareils qui sont gérés par une **solution de gestion des appareils mobiles tierce**.  Pour préparer vos applications métier qui s’exécutent sur des **appareils inscrits dans la gestion des appareils mobiles Intune**, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).


##  <a name="step-1-prepare-the-app"></a>Étape 1: Préparer l’application

Avant de pouvoir appliquer les stratégies de gestion des applications mobiles à une application, vous devez tout d’abord encapsuler l’application à l’aide de l’outil de création de package de restrictions d’application Microsoft Intune pour [iOS](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md) et [Android](prepare-android-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md), ou utiliser le [SDK d’application Intune](../develop/intune-app-sdk.md) pour intégrer les fonctionnalités de protection des applications Intune manuellement.

Pour plus d’informations sur l’utilisation de l’outil de création de package de restrictions d’application par rapport au SDK d’application Intune, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).

## <a name="step-2-add-the-app"></a>Étape 2 : Ajouter l’application

Pour associer votre application métier aux stratégies de gestion des applications mobiles, vous devez ajouter les détails de l’application à votre abonnement/client Intune en procédant comme suit :

1. Dans le [portail Azure](https://portal.azure.com/), accédez à **Gestion des applications mobiles Intune** > **Paramètres** et choisissez **Applications métier**.

  ![Capture d’écran du panneau Paramètres avec l’option métier](../media/mam-azure-portal-lob-on-settings.png)

2. Dans le panneau **Applications métier**, choisissez **Ajouter une application personnalisée**.

  ![Capture d’écran du panneau Applications métier avec le bouton Ajouter une application personnalisée en haut](../media/mam-azure-portal-add-lob-app-action.png)
3.  Fournissez un nom pour l’application, l’identificateur de lot dans le champ Identificateur de l’application et la plateforme (iOS ou Android).

  ![Capture d’écran du panneau Ajouter une application personnalisée](../media/mam-azure-portal-add-app-details.png)

  Cette étape permet de créer une description unique de votre application. L’application est également affichée dans la liste des applications ciblées pour une stratégie de gestion des applications mobiles pour votre client, telle que décrite à l’étape suivante.

## <a name="step-3-apply-mam-policies"></a>Étape 3 : Appliquer des stratégies GAM
Une fois que les métadonnées de l’application sont chargées sur le service, l’application s’affiche dans la liste des applications. Vous pouvez à présent [créer une stratégie ou utiliser une stratégie existante](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) et l’appliquer à l’application métier que vous avez ajoutée à l’étape 2.

>[!IMPORTANT]
>La stratégie GAM doit être appliquée pour les utilisateurs qui s’apprêtent à utiliser l’application encapsulée.  Les utilisateurs pour lesquels cette stratégie n’a pas été déployée ne peuvent pas utiliser l’application.


  ![Capture d’écran du panneau de la liste des applications ciblées avec la nouvelle application métier affichée](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a>Étape 4 : Distribuer l’application
Vous pouvez déployer des applications sur vos utilisateurs de diverses manières :
* Pour les appareils inscrits dans une solution de gestion des appareils mobiles tierce, vous pouvez distribuer les applications via votre solution de gestion des appareils mobiles.
* Pour les appareils non gérés par une solution de gestion des appareils mobiles, vous avez besoin d’une solution personnalisée. Les utilisateurs doivent télécharger et installer l’application sur leur appareil.

## <a name="change-the-metadata"></a>Modifier les métadonnées
Si vous devez modifier les détails de l’application, tels que le nom de l’application ou l’identificateur de lot, vous devez [supprimer l’application](#remove-apps) et [l’ajouter](#step-2-add-the-app) avec les nouvelles métadonnées.

##  <a name="remove-apps"></a>Supprimer des applications
Vous pouvez supprimer une application métier de la liste des applications. Cela supprime l’application de la liste ainsi que l’association aux stratégies de gestion des applications mobiles, mais ne supprime ni ne désinstalle l’application de l’appareil de l’utilisateur.  

1.  Dans le [portail Azure](https://portal.azure.com/), accédez à **Gestion des applications mobiles Intune** > **Paramètres**. Dans le panneau **Paramètres**, choisissez **Activité commerciale** pour ouvrir la liste des applications existantes.  
2.  Choisissez l’application à supprimer, puis le menu contextuel **(...)**.

  ![Capture d’écran du panneau Applications métier avec les points de suspension](../media/mam-azure-portal-lob-context-menu.png)
3.  Choisissez **Supprimer l’application** pour supprimer l’application.

  ![Capture d’écran du panneau Applications métier avec l’option de suppression d’application](../media/mam-azure-portal-delete-app.png)

  Cela supprime les applications de la liste des applications métier et de la liste des applications ciblées dans la stratégie de gestion des applications mobiles.



<!--HONumber=Dec16_HO2-->


