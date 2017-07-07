---
title: "Utiliser des stratégies de configuration d’application Intune pour Android for Work"
titleSuffix: Intune on Azure
description: "Apprenez à utiliser les stratégies de configuration d’application pour fournir des données de configuration à une application Android for Work lorsqu’elle est exécutée."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9ea697cafa0f277c176e55443250d32ca378dbb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a>Guide pratique pour utiliser des stratégies de configuration d’application Microsoft Intune pour Android for Work

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez des stratégies de configuration d’application dans Microsoft Intune pour fournir les paramètres pouvant être disponibles quand les utilisateurs exécutent une application Android for Work. Toutes les applications ne prennent pas en charge la configuration de l’application. Vérifiez auprès du développeur de l’application que son application a été conçue pour prendre en charge les stratégies de configuration des applications.

Les stratégies de configuration des applications peuvent vous aider à configurer les paramètres d’application disponibles pour vos utilisateurs avant d’exécuter l’application. Certaines applications Android prennent en charge des options de configuration gérée que vous pouvez configurer dans la console Intune avec le [concepteur de configuration](#use-configuration-designer). Certains paramètres de configuration des applications (comme celles avec des types Bundle) ne peuvent pas être configurés avec le concepteur de configuration.  Vous devez utiliser [l’éditeur JSON](#use-json-editor) pour ces valeurs.   Les paramètres sont automatiquement fournis aux applications lors de leur installation.

Vous n’affectez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt une stratégie à une application que vous affectez ensuite. Les paramètres de stratégie sont utilisés quand l’application les vérifie (en général, lors de sa première exécution).

## <a name="use-configuration-designer"></a>Utiliser le concepteur de configuration

1. Dans le portail Intune, choisissez **Applications mobiles**. Sous **Gérer**, choisissez **Stratégies de configuration des applications** puis cliquez sur **Ajouter**.
2. Définissez les détails suivants :
    - **Nom** - le nom du profil qui s’affiche dans la console Intune
    - **Description** - la description du profil qui s’affiche dans la console Intune
    - **Plateforme** : sélectionnez **Android**
    - **Type d’inscription d’appareil** - **Inscrit avec Intune** est présélectionné pour vous.
3. Sélectionnez **Application associée** pour choisir l’application pour laquelle vous souhaitez définir une stratégie de configuration.  Sélectionnez parmi la liste d’applications Android for Work que vous avez approuvées et synchronisées avec Intune
4. Sélectionnez **Paramètres de configuration**.
5. Pour **Format des paramètres de configuration**, sélectionnez **Utilisez le concepteur de configuration**.
6. Choisissez **Ajouter**. Une liste de paramètres de configuration disponibles s’affiche. La liste comprend :
    - **Clés de configuration** : nom du paramètre.
    - **Type de valeur** : ce paramètre peut être configuré, par exemple sur **Booléen** ou **Chaîne**.
    - **Description** : une description du paramètre de configuration.
7. Activez les cases à cocher des paramètres que vous souhaitez configurer avec ce profil, puis cliquez sur **OK**.
8. Une liste de vos paramètres sélectionnés s’affiche avec les **valeur de configuration** disponibles. Spécifiez une valeur pour chaque paramètre, puis cliquez sur **OK**.

## <a name="use-json-editor"></a>Utiliser l’éditeur JSON

1. Dans le portail Intune, choisissez **Applications mobiles**. Sous **Gérer**, choisissez **Stratégies de configuration des applications** puis cliquez sur **Ajouter**.
2. Définissez les détails suivants :
    - **Nom** - le nom du profil qui s’affiche dans la console Intune
    - **Description** - la description du profil qui s’affiche dans la console Intune
    - **Plateforme** : sélectionnez **Android**
    - **Type d’inscription d’appareil** - **Inscrit avec Intune** est présélectionné pour vous.
3. Sélectionnez **Application associée** pour choisir l’application pour laquelle vous souhaitez définir une stratégie de configuration.  Sélectionnez parmi la liste d’applications Android for Work que vous avez approuvées et synchronisées avec Intune.
5. Sélectionnez **Paramètres de configuration**.
6. Pour **Format des paramètres de configuration**, sélectionnez **Saisir dans l’éditeur JSON**.
7. Dans l’éditeur, vous pouvez définir des valeurs JSON pour les paramètres de configuration. Vous pouvez choisir **Télécharger un modèle JSON** pour télécharger un exemple de fichier que vous pouvez ensuite configurer.
8. Lorsque vous avez terminé, choisissez **OK**, puis cliquez sur **Ajouter**.

La stratégie est créée et s’affiche dans le panneau de liste des stratégies.

Ensuite, continuez à [Affecter](apps-deploy.md) et [Surveiller](apps-monitor.md) l’application comme d’habitude.

Quand l’application affectée est exécutée sur un appareil, elle s’exécute avec les paramètres que vous avez configurés dans la stratégie de configuration des applications.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Préconfigurer l’état d’octroi d’autorisations pour les applications

Vous pouvez également préconfigurer l’autorisation pour les applications d’accéder aux fonctionnalités des appareils Android. Par défaut, les applications Android qui nécessitent des autorisations d’appareils telles que l’accès à l’emplacement ou à l’appareil photo invitent les utilisateurs à accepter ou à refuser les autorisations. Par exemple, si une application utilise le microphone de l’appareil, l’utilisateur final est invité à autoriser l’application à utiliser le microphone.

1. Dans le portail Intune, choisissez **Applications mobiles**. Sous **Gérer**, choisissez **Stratégies de configuration des applications** puis cliquez sur **Ajouter**.
2. Définissez les détails suivants :
    - **Nom** - le nom du profil qui s’affiche dans la console Intune
    - **Description** - la description du profil qui s’affiche dans la console Intune
    - **Plateforme** : sélectionnez **Android**
    - **Type d’inscription d’appareil** - **Inscrit avec Intune** est présélectionné pour vous.
3. Sélectionnez **Application associée** pour choisir l’application pour laquelle vous souhaitez définir une stratégie de configuration.  Sélectionnez parmi la liste d’applications Android for Work que vous avez approuvées et synchronisées avec Intune.
5. Sélectionnez **Autorisations**, puis **Ajouter**.
6. Effectuez votre sélection dans la liste des autorisations d’application disponibles, puis choisissez **OK**.
7. Sélectionnez une option pour chaque autorisation à accorder avec cette stratégie :
    - **Invite** : Inviter l’utilisateur à accepter ou à refuser
    - **Accorder automatiquement** - Approuver automatiquement sans avertir l’utilisateur.
    - **Refuser automatiquement** - Refuser automatiquement sans avertir l’utilisateur
8. Pour affecter la stratégie de configuration d’application, sélectionnez la stratégie de configuration d’application, sélectionnez **Affectation**, puis choisissez **Sélectionner des groupes**.
9. Sélectionnez les groupes d’utilisateurs à affecter, puis choisissez **Sélectionner**.
10. Choisissez **Enregistrer** pour affecter la stratégie.
