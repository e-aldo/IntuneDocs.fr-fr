---
title: "Créer un groupe dans Microsoft Intune"
titleSuffix: 
description: "Organisez les utilisateurs en groupes pour faciliter la gestion des stratégies et des applications auxquelles ils ont accès."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e052f7c8d5742859d009816473fe97a98c499b17
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Créer un groupe pour gérer vos utilisateurs et l’accès aux données

Les groupes permettent de gérer vos utilisateurs et de contrôler l’accès des employés aux ressources de votre entreprise. Ces ressources peuvent faire partie de votre annuaire ou être externes, comme les applications SaaS ou les sites SharePoint.

Microsoft Intune utilise Azure Active Directory (Azure AD) pour gérer l’accès aux ressources d’entreprise. Cet accès est contrôlé à l’aide de rôles dans l’annuaire. Intune gère ensuite cet accès pour les appareils mobiles, ce qui permet aux membres de ce groupe d’accéder aux ressources.

## <a name="how-do-i-create-a-group"></a>Comment créer un groupe ?

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. À l’aide de **Rechercher des ressources**, recherchez **Intune**.
3. Une fois que vous avez ouvert le panneau **Microsoft Intune**, sélectionnez **Groupes**.
4. Dans le panneau **Utilisateurs et groupes – Tous les groupes**, sélectionnez la commande **Nouveau groupe**.
5. Dans le panneau **Groupe**, ajoutez un **Nom** et une **Description** pour le groupe.
6. Sélectionnez **Affecté** comme **Type d’appartenance**. Vous ne devez pas **Activer les fonctionnalités Office** pour le groupe de test.
7. Cliquez sur **Créer**.

Si vous avez réussi à créer un groupe, il doit apparaître dans la liste de **Tous les groupes**. S’il ne figure pas dans cette liste, essayez de créer un autre groupe.

## <a name="next-steps"></a>Étapes suivantes

[Bien démarrer avec les stratégies](get-started-policies.md) : Créez des stratégies pour empêcher les utilisateurs d’exécuter des actions non autorisées avec leurs appareils.

## <a name="learn-more"></a>En savoir plus

* [Définir des restrictions d’inscription à l’aide de groupes dans Intune](groups-add.md)
* [Gérer l’accès aux ressources d’entreprise à l’aide de groupes dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
