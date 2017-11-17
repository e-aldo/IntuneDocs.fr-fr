---
title: "Ajouter des stratégies de configuration d’applications pour les appareils Android gérés | Microsoft Docs"
titlesuffix: Azure portal
description: "Découvrez comment utiliser des stratégies de configuration des applications pour fournir des données de configuration à une application Android for Work quand elle est exécutée."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f3fcc589010e9a153ee105aaf4b161ebcbcbfbb4
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Ajouter des stratégies de configuration d’applications pour les appareils Android gérés

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez des stratégies de configuration des applications dans Microsoft Intune pour fournir des paramètres quand les utilisateurs exécutent une application Android for Work. Vous n’affectez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt une stratégie à une application que vous affectez ensuite. Les paramètres de stratégie sont utilisés quand l’application les vérifie, en général, à sa première exécution.

> [!Note]  
> Toutes les applications ne prennent pas en charge la configuration d’application. Vérifiez auprès du développeur d’application si son application a été conçue pour prendre en charge les stratégies de configuration des applications.

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
3. Choisissez la charge de travail **Applications mobiles**.
4. Choisissez **Stratégies de configuration des applications** dans le groupe **Gérer**, puis choisissez **Ajouter**.
5. Définissez les détails suivants :
    - **Nom**  
      Nom du profil qui s’affiche dans le portail Azure.
    - **Description**  
      Description du profil qui s’affiche dans le portail Azure.
    - **Type d’inscription de l’appareil**  
      Choisissez **Appareils gérés**.
6. Sélectionnez **Android** comme **Plateforme**.
7. Sélectionnez **Application associée** pour choisir l’application pour laquelle vous souhaitez définir une stratégie de configuration d’applications. Sélectionnez parmi la liste d’applications Android for Work que vous avez approuvées et synchronisées avec Intune.
8. Sélectionnez **Paramètres de configuration**. Vous pouvez définir des configurations à l’aide de :
    - [Concepteur de configuration](#Use-the-configuration-designer)
    - [Éditeur JSON](#Enter-the-JSON-editor)
9. Choisissez **OK**, puis **Ajouter**.

## <a name="use-the-configuration-designer"></a>Utiliser le concepteur de configuration

Vous pouvez utiliser le concepteur de configuration pour les applications sur les appareils qui sont inscrits ou non inscrits dans Intune. Le concepteur vous permet de configurer des valeurs et des clés de configuration spécifiques. Vous devez également spécifier le type de données pour chaque valeur.

Pour chaque clé et valeur de la configuration, définissez les éléments suivants :

  - **Clé de configuration**  
     Clé qui identifie de façon unique la configuration des paramètres spécifique.
  - **Type de valeur**  
    Type de données de la valeur de configuration. Les types incluent Integer, Real, String ou Boolean.
  - **Valeur de configuration**  
    Valeur de la configuration. 

## <a name="enter-the-json-editor"></a>Utiliser l’éditeur JSON

Certains paramètres de configuration des applications (comme celles avec des types Bundle) ne peuvent pas être configurés avec le concepteur de configuration. Vous devez utiliser l’éditeur JSON pour ces valeurs. Les paramètres sont automatiquement fournis aux applications lors de leur installation.

1. Pour **Format des paramètres de configuration**, sélectionnez **Saisir dans l’éditeur JSON**.
2. Dans l’éditeur, vous pouvez définir des valeurs JSON pour les paramètres de configuration. Vous pouvez choisir **Télécharger un modèle JSON** pour télécharger un exemple de fichier que vous pouvez ensuite configurer.
3. Choisissez **OK**, puis **Ajouter**.

La stratégie est créée et s’affiche dans le panneau de liste des stratégies.

Quand l’application affectée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Préconfigurer l’état d’octroi d’autorisations pour les applications

Vous pouvez également préconfigurer l’autorisation pour les applications d’accéder aux fonctionnalités des appareils Android. Par défaut, les applications Android qui nécessitent des autorisations d’appareils (telles que l’accès à la géolocalisation ou à l’appareil photo) invitent les utilisateurs à accepter ou à refuser les autorisations. Par exemple, si une application utilise le microphone de l’appareil, l’utilisateur final est invité à autoriser l’application à utiliser le microphone.

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** + **Intune**.
3. Choisissez **Applications mobiles**. Sous **Gérer**, choisissez **Stratégies de configuration des applications**, puis **Ajouter**.
4. Définissez les détails suivants :
    - **Nom**. Nom du profil qui s’affiche dans le portail Azure.
    - **Description**. Description du profil qui s’affiche dans le portail Azure.
    - **Plateforme**. Sélectionnez **Android**.
    - **Type d’inscription de l’appareil**. **Appareils gérés** est présélectionné pour vous.
5. Sélectionnez **Application associée** pour choisir l’application pour laquelle vous souhaitez définir une stratégie de configuration. Sélectionnez parmi la liste d’applications Android for Work que vous avez approuvées et synchronisées avec Intune.
6. Sélectionnez **Autorisations**, puis **Ajouter**.
7. Effectuez votre sélection dans la liste des autorisations d’application disponibles, puis choisissez **OK**.
8. Sélectionnez une option pour chaque autorisation à accorder avec cette stratégie :
    - **Demander**. Inviter l’utilisateur à accepter ou à refuser
    - **Accorder automatiquement**. Approuver automatiquement sans avertir l’utilisateur.
    - **Refuser automatiquement**. Refuser automatiquement sans avertir l’utilisateur.
9. Pour affecter la stratégie de configuration d’application, sélectionnez la stratégie de configuration d’application, sélectionnez **Affectation**, puis choisissez **Sélectionner des groupes**.
10. Sélectionnez les groupes d’utilisateurs à affecter, puis choisissez **Sélectionner**.
11. Choisissez **Enregistrer** pour affecter la stratégie.

## <a name="next-steps"></a>Étapes suivantes

Continuez à [affecter](apps-deploy.md) et à [surveiller](apps-monitor.md) l’application.

