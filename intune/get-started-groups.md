---
title: "Bien démarrer avec les groupes"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 04843a918a3c661ab69dfa711f4d22a8feedf5f3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-groups"></a>Bien démarrer avec les groupes

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

[](./media/generic-users-groups.png)

Microsoft Intune utilise Azure Active Directory (Azure AD) pour [gérer l’accès aux ressources d’entreprise](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups). Cet accès est contrôlé à l’aide de rôles dans l’annuaire. Intune gère ensuite cet accès pour les appareils mobiles, ce qui permet aux membres de ce groupe d’accéder aux ressources.

__Comment créer un groupe ?__

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. À l’aide de **Rechercher des ressources**, recherchez **Utilisateurs et groupes**.
3. Une fois que vous avez ouvert le panneau **Utilisateurs et groupes**, sélectionnez **Tous les groupes**.
4. Dans le panneau **Utilisateurs et groupes – Tous les groupes**, sélectionnez la commande **Nouveau groupe**.
5. Dans le panneau **Groupe**, ajoutez un **Nom** et une **Description** pour le groupe.
6. Sélectionnez **Affecté** comme **Type d’appartenance**. Vous ne devez pas **Activer les fonctionnalités Office** pour le groupe de test.
7. Cliquez sur **Créer**.

Si vous avez réussi à créer un groupe, il doit apparaître dans la liste de **Tous les groupes**. S’il ne figure pas dans cette liste, essayez de créer un autre groupe.
