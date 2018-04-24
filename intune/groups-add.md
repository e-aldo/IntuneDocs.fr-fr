---
title: Ajouter des groupes pour organiser des utilisateurs et des appareils
titlesuffix: Microsoft Intune
description: Ajoutez des groupes pour organiser des utilisateurs et des appareils par zone géographique, service ou caractéristique matérielle.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 613d64e396e969b8b6bde76ee6c4474a60be8ba9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Ajouter des groupes pour organiser des utilisateurs et des appareils
Intune utilise les groupes Azure Active Directory (AD) pour gérer les utilisateurs et les appareils. En tant qu’administrateur Intune, vous pouvez configurer des groupes en fonction des besoins de votre organisation. Créez des groupes pour organiser les utilisateurs ou appareils par emplacement géographique, service ou spécification matérielle. Utilisez des groupes pour gérer les tâches à l’échelle. Par exemple, vous pouvez définir des stratégies pour de nombreux utilisateurs ou déployer des applications sur un ensemble d’appareils.

Cette rubrique explique comment ajouter des groupes à utiliser dans Intune.

Vous pouvez ajouter les types de groupes suivants :
- **Groupes affectés** : ajoutez manuellement des utilisateurs ou des appareils à un groupe statique
- **Groupes dynamiques** (avec Azure Active Directory Premium) : vous permettent de générer de manière dynamique des groupes d’utilisateurs ou d’appareils définis avec des règles simples ou avancées

## <a name="add-a-new-group"></a>Ajouter un nouveau groupe

Utilisez les étapes ci-après pour créer un groupe.
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Groupes** puis **Nouveau groupe** dans le volet **Tous les groupes**.
   ![Capture d’écran du portail Azure avec l’option Nouveau groupe sélectionnée](./media/groups-add-new.png)
4. Spécifiez un **Type de groupe**, le **Nom** et la **Description** du nouveau groupe. Ces propriétés s’affichent uniquement dans le portail de gestion et ne sont pas visibles pour les utilisateurs.

5. Choisissez **Type d’appartenance** :
   - **Affecté** pour créer un groupe avec des membres affectés manuellement. En savoir plus sur les [groupes affectés Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
   - **Utilisateur dynamique** pour créer un groupe d’utilisateurs défini avec une **requête dynamique**.
   - **Appareil dynamique** pour créer un groupe d’appareils défini avec une **requête dynamique**.

   ![Capture d’écran des propriétés du groupe Intune](./media/groups-add-properties.png)

   Azure AD vous permet de créer des groupes dynamiques en fonction des règles qui définissent l’appartenance. Découvrez comment [créer des groupes dynamiques basés sur des attributs](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

6. Vous pouvez sélectionner **Activer les fonctionnalités Office** pour permettre aux membres du groupe d’utilisateurs d’accéder à des applications Office 365 partagées. En savoir plus sur les [groupes Office 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
7. Choisissez **Créer** pour ajouter le nouveau groupe.

## <a name="see-also"></a>Voir aussi
- [Gérer l’accès aux ressources avec les groupes Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Groupes classiques Intune dans le portail Azure](groups-get-started.md)
