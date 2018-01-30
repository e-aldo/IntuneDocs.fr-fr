---
title: "Bien démarrer avec les groupes"
titleSuffix: Azure portal
description: "Organisez les utilisateurs en groupes pour faciliter la gestion des stratégies et des applications auxquelles ils ont accès."
keywords: 
author: arob98
ms.author: angrobe
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
ms.openlocfilehash: 63a35c04a14ebd79ac55f1dab2680d70008ee0ed
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-groups"></a>Bien démarrer avec les groupes

Les groupes sont utilisés pour gérer vos utilisateurs et contrôler l’accès des employés aux ressources de votre entreprise. Ces ressources peuvent faire partie de votre annuaire ou être externes, comme les applications SaaS ou les sites SharePoint.

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
