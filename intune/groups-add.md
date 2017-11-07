---
title: "Définir des restrictions d’inscription dans Intune"
titlesuffix: Azure portal
description: "Restriction de l’inscription par la plateforme et définition d’une limite d’inscriptions d’appareils dans Intune. \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ddf5cc624685e684973b0e4ee85de609845f3bd
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/01/2017
---
# <a name="add-groups-in-intune"></a>Ajouter des groupes dans Intune
Intune utilise les groupes Azure Active Directory (AD) pour gérer les utilisateurs et les appareils. En tant qu’administrateur Intune, vous pouvez configurer des groupes en fonction des besoins de votre organisation. Créez des groupes pour organiser les utilisateurs ou appareils par emplacement géographique, service ou spécification matérielle. Utilisez des groupes pour gérer les tâches à l’échelle. Par exemple, vous pouvez définir des stratégies pour de nombreux utilisateurs ou déployer des applications sur un ensemble d’appareils.

Cette rubrique explique comment ajouter des groupes à utiliser dans Intune.

Vous pouvez ajouter les types de groupes suivants :
- **Groupes affectés** : ajoutez manuellement des utilisateurs ou des appareils à un groupe statique
- **Groupes dynamiques** (avec Azure Active Directory Premium) : vous permettent de générer de manière dynamique des groupes d’utilisateurs ou d’appareils définis avec des règles simples ou avancées

## <a name="add-a-new-group"></a>Ajouter un nouveau groupe

Utilisez les étapes ci-après pour créer un groupe.
1. Dans le portail Azure, accédez à **Groupes**, puis choisissez **Nouveau groupe** dans le panneau **Tous les groupes**.
  ![Capture d’écran du portail Azure avec l’option Nouveau groupe sélectionnée](./media/groups-add-new.png)
2. Spécifiez le **Nom** et la **Description** du nouveau groupe. Ces propriétés s’affichent uniquement dans le portail de gestion et ne sont pas visibles pour les utilisateurs.

3. Choisissez **Type d’appartenance** :
  - **Affecté** pour créer un groupe avec des membres affectés manuellement. En savoir plus sur les [groupes affectés Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Utilisateur dynamique** pour créer un groupe d’utilisateurs défini avec une **requête dynamique**.
  - **Appareil dynamique** pour créer un groupe d’appareils défini avec une **requête dynamique**.

  ![Capture d’écran des propriétés du groupe Intune avec Nom, Description, Type d’appartenance, Activer les fonctionnalités Office et Membres](./media/groups-add-properties.png)

  Azure AD vous permet de créer des groupes dynamiques en fonction des règles qui définissent l’appartenance. Découvrez comment [créer des groupes dynamiques basés sur des attributs](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Vous pouvez sélectionner **Activer les fonctionnalités Office** pour permettre aux membres du groupe d’utilisateurs d’accéder à des applications Office 365 partagées. En savoir plus sur les [groupes Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Choisissez **Créer** pour ajouter le nouveau groupe.

## <a name="see-also"></a>Voir aussi
- [Gérer l’accès aux ressources avec les groupes Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Groupes classiques Intune dans le portail Azure](groups-get-started.md)
