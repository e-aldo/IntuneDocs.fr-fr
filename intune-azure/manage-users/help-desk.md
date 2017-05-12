---
title: "Portail de dépannage du centre de support technique | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Les équipes du centre de support technique utilisent le portail de dépannage pour résoudre les problèmes techniques des utilisateurs"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: 8cf12e434518c9f06c105a22f3b7aef2613fcdb0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Guider les utilisateurs dans le portail de dépannage de Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Le portail de dépannage permet aux opérateurs du centre de support technique et aux administrateurs Intune de visualiser les utilisateurs et leurs appareils, et d’effectuer des tâches pour résoudre les problèmes techniques liés à Intune.

## <a name="add-help-desk-operators"></a>Ajouter des opérateurs de support technique
Un administrateur Intune peut attribuer des autorisations d’opérateur de support technique à des utilisateurs. Les utilisateurs du support technique peuvent ensuite consulter le portail Intune, mais ils ne peuvent ni afficher ni exécuter des tâches administratives en dehors de la charge de travail du dépannage.

1. Connectez-vous au [portail Azure](https:portal.azure.com) en tant qu’administrateur Intune, puis sélectionnez **Plus de services** > **Surveillance + gestion** > **Intune**.
2. Dans le panneau de navigation de gauche, sélectionnez **Rôles Intune**.
3. Dans la charge de travail **Rôles Intune**, sélectionnez **Help Desk Operator** (Opérateur de support technique), puis sélectionnez **Affecter**.
4. Entrez un **nom d’affectation** (obligatoire), une **description de l’affectation** (facultatif), puis attribuez des **membres (groupes)** et une **étendue (groupes)**.
5. Les membres du rôle d’opérateur de support technique peuvent maintenant utiliser le portail de dépannage.

Pour plus d’informations sur les rôles Intune, consultez [Rôles Intune (RBAC)](../access-control/role-based-access-control.md).

## <a name="access-the-troubleshooting-portal"></a>Accès au portail de dépannage

Le personnel de support technique et les administrateurs Intune peuvent accéder au portail de dépannage de deux manières :
- Dans le [portail Azure](https://portal.azure.com), sélectionnez **Plus de services** > **Surveillance + gestion** > **Intune**, puis, dans le volet de navigation de gauche, sélectionnez **Résoudre les problèmes**. D’autres charges de travail sont visibles dans le panneau de navigation de gauche, mais elles ne sont pas disponibles.

![Capture d’écran de la charge de travail Dépannage d’Intune avec le lien Sélectionner utilisateur](media/help-desk-user.png)
- Ouvrez [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) dans un navigateur web. Seul le portail de dépannage est visible.

## <a name="use-the-troubleshooting-portal"></a>Utilisation du portail de dépannage

Dans le portail de dépannage, vous pouvez choisir **Sélectionner un utilisateur** pour afficher les informations d’un utilisateur. Les informations de l’utilisateur peuvent vous aider à comprendre l’état actuel des utilisateurs et de leurs appareils. Le portail de dépannage affiche les informations suivantes concernant l’utilisateur Intune on appareil :
- Informations de compte utilisateur
- Appartenance au groupe d’utilisateurs
- Détails sur l'appareil

Les utilisateurs du support technique peuvent également effectuer des tâches à distance sur des appareils, par exemple exécuter un **verrouillage à distance**.

