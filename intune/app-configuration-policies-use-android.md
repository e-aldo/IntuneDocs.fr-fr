---
title: Ajouter des stratégies de configuration d’applications pour les appareils Android gérés
titlesuffix: Microsoft Intune
description: Utilisez des stratégies de configuration des applications dans Microsoft Intune pour fournir des paramètres quand les utilisateurs exécutent une application Android for Work.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6fbf70630124614aa1ed302a41d6e3f33c10c63d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a>Ajouter des stratégies de configuration d’applications pour les appareils Android gérés

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Utilisez des stratégies de configuration des applications dans Microsoft Intune pour fournir des paramètres aux applications Android for Work. Le développeur d’applications doit exposer les paramètres de configuration d’application gérés Android pour spécifier les paramètres de configuration de l’application. Affectez la stratégie de configuration d’applications au groupe d’utilisateurs pour lequel vous souhaitez appliquer les paramètres.  Les paramètres de stratégie sont utilisés quand l’application les vérifie, en général, à sa première exécution.

> [!Note]  
> Toutes les applications ne prennent pas en charge la configuration d’application. Vérifiez auprès du développeur d’application si son application a été conçue pour prendre en charge les stratégies de configuration des applications.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Choisissez la charge de travail **Applications mobiles**.
4. Choisissez **Stratégies de configuration des applications** dans le groupe **Gérer**, puis choisissez **Ajouter**.
5. Définissez les détails suivants :
    - **Nom**  
      Nom du profil qui s’affiche dans le portail Azure.
    - **Description**  
      Description du profil qui s’affiche dans le portail Azure.
    - **Type d’inscription de l’appareil**  
      Choisissez **Appareils gérés**.
6. Sélectionnez **Android for Work** comme **Plateforme**.
7. Sélectionnez **Application associée** pour choisir l’application pour laquelle vous souhaitez définir une stratégie de configuration d’applications. Sélectionnez parmi la liste d’applications Android for Work que vous avez approuvées et synchronisées avec Intune.
8. Sélectionnez **Paramètres de configuration**. Vous pouvez définir des configurations à l’aide de :
    - [Concepteur de configuration](#Use-the-configuration-designer)
    - [Éditeur JSON](#Enter-the-JSON-editor)
9. Choisissez **OK**, puis **Ajouter**.

## <a name="use-the-configuration-designer"></a>Utiliser le concepteur de configuration

Vous pouvez utiliser le concepteur de configuration pour les applications Android qui prennent en charge la configuration. La configuration s’appliquera aux appareils qui sont inscrits dans Intune. Le concepteur vous permet de configurer des valeurs de configuration spécifiques pour les paramètres qu’une application expose.

Sélectionnez **Ajouter** pour sélectionner la liste de paramètres de configuration que vous souhaitez spécifier pour l’application.  
Pour chaque clé et valeur de la configuration, définissez les éléments suivants :

  - **Type de valeur**  
    Type de données de la valeur de configuration. Pour les types de valeur String, vous pouvez éventuellement choisir un profil de certificat ou une variable comme type de valeur.
  - **Valeur de configuration**  
    Valeur de la configuration. Si vous sélectionnez une variable ou un certificat pour le type de valeur, vous pouvez choisir parmi une liste de variables ou de profils de certificat dans la liste déroulante des valeurs de configuration.  Si vous choisissez un certificat, l’alias de certificat du certificat déployé sur l’appareil est renseigné lors de l’exécution.
    
### <a name="supported-variables-for-configuration-values"></a>Variables prises en charge pour les valeurs de configuration

Vous pouvez choisir les options suivantes si vous choisissez une variable comme type de valeur :
- Nom d’utilisateur principal — par exemple, **John@contoso.com**
- Courrier — par exemple, **John@contoso.com**
- UPN partiel — par exemple, **John**
- ID de compte — par exemple, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- ID d’appareil — par exemple, **b9841cd9-9843-405f-be28-b2265c59ef97**
- ID d’utilisateur — par exemple, **3ec2c00f-b125-4519-acf0-302ac3761822**
- Nom d’utilisateur —par exemple, **John Doe**


## <a name="enter-the-json-editor"></a>Utiliser l’éditeur JSON

Certains paramètres de configuration des applications (comme celles avec des types Bundle) ne peuvent pas être configurés avec le concepteur de configuration. Vous devez utiliser l’éditeur JSON pour ces valeurs. Les paramètres sont automatiquement fournis aux applications lors de leur installation.

1. Pour **Format des paramètres de configuration**, sélectionnez **Saisir dans l’éditeur JSON**.
2. Dans l’éditeur, vous pouvez définir des valeurs JSON pour les paramètres de configuration. Vous pouvez choisir **Télécharger un modèle JSON** pour télécharger un exemple de fichier que vous pouvez ensuite configurer.
3. Choisissez **OK**, puis **Ajouter**.

La stratégie est créée et s’affiche dans le panneau de liste des stratégies.

Quand l’application affectée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications.

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a>Préconfigurer l’état d’octroi d’autorisations pour les applications

Vous pouvez également préconfigurer l’autorisation pour les applications d’accéder aux fonctionnalités des appareils Android. Par défaut, les applications Android qui nécessitent des autorisations d’appareils (telles que l’accès à la géolocalisation ou à l’appareil photo) invitent les utilisateurs à accepter ou à refuser les autorisations. Par exemple, si une application utilise le microphone de l’appareil, l’utilisateur final est invité à autoriser l’application à utiliser le microphone.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Choisissez **Applications mobiles**.
3. Sous **Gérer**, choisissez **Stratégies de configuration des applications**, puis **Ajouter**.
4. Définissez les détails suivants :
    - **Nom**. Nom du profil qui s’affiche dans le portail Azure.
    - **Description**. Description du profil qui s’affiche dans le portail Azure.
    - **Type d’inscription de l’appareil**. Sélectionnez **Appareils gérés**.
    - **Plateforme**. Sélectionnez **Android for Work**.
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

