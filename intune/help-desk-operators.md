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
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Guider les utilisateurs dans le portail de dépannage de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Le portail de résolution des problèmes permet aux opérateurs du support technique et aux administrateurs Intune d’afficher les informations utilisateur pour résoudre les demandes d’assistance utilisateur. Les organisations dont le personnel comprend des opérateurs de support technique peuvent affecter l’**opérateur de support technique** à un groupe d’utilisateurs, qui peuvent ensuite utiliser le panneau de résolution des problèmes pour aider les utilisateurs.

Par exemple, quand un utilisateur contacte le support technique pour signaler un problème avec Intune, l’opérateur entre le nom de l’utilisateur. Intune affiche des informations pertinentes qui peuvent aider à résoudre de nombreux problèmes de niveau 1 tels que l’état de l’utilisateur, l’échec de l’installation de l’application ou des problèmes de conformité. Exemples de problèmes résolus :
- L’appareil ne répond pas
-   L’appareil ne reçoit pas les paramètres VPN ou Wi-Fi
-   Échec d’installation de l’application


## <a name="add-help-desk-operators"></a>Ajouter des opérateurs de support technique
Un administrateur Intune peut attribuer des autorisations d’opérateur de support technique à des utilisateurs de deux manières :
- Affecter le rôle intégré **Opérateur de support technique**
- Créer et affecter un rôle personnalisé

## <a name="assign-help-desk-operator-role"></a>Affecter le rôle d’opérateur de support technique
En tant qu’administrateur Intune, vous pouvez affecter le rôle d’opérateur de support technique à un groupe d’utilisateurs. Les membres de ce groupe peuvent utiliser le portail d’administration. Chaque opérateur de support technique doit avoir une licence Intune pour accéder au portail Intune. Découvrez comment [affecter des licences Intune](licenses-assign.md).

1. En tant qu’administrateur Intune, connectez-vous au portail Intune et sélectionnez **Rôles Intune**.
2. Dans la charge de travail **Rôles Intune**, sélectionnez **Opérateur de support technique** > **Affectations**, puis sélectionnez **Affecter**.
  ![Capture d’écran de portail affichant les rôles Intune mis en surbrillance et une liste de rôles intégrés, y compris opérateur support aide affectations mis en surbrillance et une zone rouge autour d’affecter](./media/help-desk-user-assign.png)
3. Entrez un **nom d’affectation** (obligatoire), une **description de l’affectation** (facultatif), puis attribuez des **membres (groupes)** et une **étendue (groupes)**.
4. Les membres du rôle d’opérateur de support technique peuvent maintenant utiliser le portail de dépannage.

Pour plus d’informations sur les rôles Intune, consultez [Rôles Intune (RBAC)](role-based-access-control.md).

## <a name="create-a-custom-role-for-troubleshooting"></a>Créer un rôle personnalisé pour la résolution des problèmes
Si vous êtes administrateur Intune, vous pouvez créer un rôle personnalisé qui permet aux utilisateurs d’utiliser le portail de résolution des problèmes avec des autorisations en fonction des besoins de votre organisation. Pour plus d’informations sur les rôles Intune, consultez [Rôles Intune (RBAC)](role-based-access-control.md).

![Capture d’écran du portail Intune montrant les rôles Intune en surbrillance et une liste de rôles intégrés, notamment l’opérateur de support technique](./media/help-desk-user-add.png)

Pour utiliser la console Intune pour une vue de support technique, un rôle de support technique personnalisé doit disposer des autorisations suivantes :
- Applications mobiles : Lecture
- Applications gérées : Lecture
- Appareils gérés : Lecture
- Organisation : Lecture

## <a name="access-the-troubleshooting-portal"></a>Accès au portail de dépannage

Le personnel de support technique et les administrateurs Intune peuvent accéder au portail de dépannage de deux manières :
- Ouvrez [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) dans un navigateur web.
- Dans le portail Intune, accédez à **Aide et Support** > **Dépanner**.

![Capture d’écran de la charge de travail Dépannage d’Intune avec le lien Sélectionner un utilisateur](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Utilisation du portail de dépannage

Dans le portail de dépannage, vous pouvez choisir **Sélectionner un utilisateur** pour afficher les informations d’un utilisateur. Les informations de l’utilisateur peuvent vous aider à comprendre l’état actuel des utilisateurs et de leurs appareils. Le portail de dépannage affiche les informations suivantes concernant le dépannage :
- **État du client**
- **État de l’utilisateur**
- **Appareils** et les actions de l’appareil
- **Appartenance au groupe**
- **État de protection des applications**
