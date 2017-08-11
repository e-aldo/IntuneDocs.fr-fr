---
title: "Portail de dépannage du centre de support technique"
titleSuffix: Intune on Azure
description: "Les équipes du centre de support technique utilisent le portail de dépannage pour résoudre les problèmes techniques des utilisateurs"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7aad054f0861522174faa01b979083a818c106af
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Guider les utilisateurs dans le portail de dépannage de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Le portail de résolution des problèmes permet aux opérateurs du support technique et aux administrateurs Intune d’afficher les informations utilisateur pour résoudre les demandes d’assistance utilisateur. Les organisations dont le personnel comprend des opérateurs de support technique peuvent affecter l’**opérateur de support technique** à un groupe d’utilisateurs, qui peuvent ensuite utiliser le panneau de résolution des problèmes pour aider les utilisateurs.

Par exemple, quand un utilisateur contacte le support technique pour signaler un problème avec Intune, l’opérateur entre le nom de l’utilisateur. Intune affiche les données utiles qui peuvent aider à résoudre de nombreux problèmes de niveau 1, y compris :
- État de l’utilisateur
- Attributions
- Échec d’installation d’application
- Problèmes de conformité
- L’appareil ne répond pas
-   L’appareil ne reçoit pas les paramètres VPN ou Wi-Fi
-   Échec d’installation de l’application


## <a name="add-help-desk-operators"></a>Ajouter des opérateurs de support technique
En tant qu’administrateur Intune, vous pouvez affecter le rôle d’opérateur de support technique à un groupe d’utilisateurs. Les membres de ce groupe peuvent utiliser le portail d’administration pour résoudre les problèmes des utilisateurs. Chaque opérateur de support technique doit avoir une licence Intune pour accéder au portail Intune. Découvrez comment [affecter des licences Intune](licenses-assign.md).

Pour ajouter des utilisateurs de support technique :
1. [Ajouter un utilisateur à Intune](users-add.md) si nécessaire
2. [Créer un groupe de support technique](groups-add.md) et lui ajouter des utilisateurs
3. [Attribuer le rôle d’opérateur de support technique RBAC](role-based-access-control.md#built-in-roles) ou [créer un rôle personnalisé](role-based-access-control.md#custom-roles) avec les autorisations suivantes :
  - Applications mobiles : Lecture
  - Applications gérées : Lecture
  - Appareils gérés : Lecture
  - Organisation : Lecture
  - DeviceCompliancePolices : Lecture
  - DeviceConfigurations : Lecture

  ![Capture d’écran du portail Intune montrant les rôles Intune en surbrillance et une liste de rôles intégrés, notamment l’opérateur de support technique](./media/help-desk-user-add.png)

4. Pour autoriser les opérateurs de support technique à afficher l’intégrité du service et à ouvrir les tickets de support pour Intune, [accorder aux utilisateurs des autorisations d’administrateur](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) en tant qu’**Administrateur de service**. Ne pas donner l’autorisation **Administrateur de Service Intune**, car ce rôle d’annuaire détient plus de droits que ceux nécessaires aux opérateurs de support technique.

## <a name="access-the-troubleshooting-portal"></a>Accès au portail de dépannage

Le personnel de support technique et les administrateurs Intune peuvent accéder au portail de dépannage de deux manières :
- Ouvrez [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) dans un navigateur web pour afficher uniquement le portail de résolution des problèmes.
  ![Capture d’écran de la console de dépannage](./media/help-desk-console.png)
- Connectez-vous au portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**, puis accédez à **Aide et support** > **Résoudre les problèmes**.

Cliquez sur **Sélectionner un utilisateur** pour afficher un utilisateur et les détails le concernant.

![Capture d’écran de la charge de travail Dépannage d’Intune avec le lien Sélectionner un utilisateur](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Utilisation du portail de dépannage

Dans le portail de dépannage, vous pouvez choisir **Sélectionner un utilisateur** pour afficher les informations d’un utilisateur. Les informations de l’utilisateur peuvent vous aider à comprendre l’état actuel des utilisateurs et de leurs appareils. Le portail de dépannage affiche les informations suivantes concernant le dépannage :
- **État du compte**
- **État de l’utilisateur**
- **Appareils** avec les actions de l’appareil
- **Appartenance au groupe**
- **État de protection des applications**
