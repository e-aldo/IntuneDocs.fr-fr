---
title: "Bien démarrer avec la gestion des utilisateurs"
titlesuffix: Microsoft Intune
description: "Ajouter un utilisateur à Intune et lui attribuer une licence pour qu’il puisse accéder aux ressources de l’entreprise sur des appareils mobiles."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e06b335c03caee0bd997748f9c48ed78d7d379b
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-managing-users"></a>Bien démarrer avec la gestion des utilisateurs

Prenez en compte toutes les personnes de votre organisation. Toutes les personnes qui utilisent des données d’entreprise ont besoin d’un utilisateur pour gérer l’accès à ces données dans Intune.

## <a name="how-do-i-create-a-user"></a>Comment créer un utilisateur ?

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. À l’aide de **Rechercher des ressources**, recherchez **Intune**.
3. Une fois que vous avez ouvert le panneau **Microsoft Intune**, sélectionnez **Utilisateurs**. Dans la page **Tous les utilisateurs**, sélectionnez **+ Nouvel utilisateur**.
4. Entrez les détails de l’utilisateur, tels que le **Nom** et le **Nom d’utilisateur**. La partie nom de domaine du nom d’utilisateur doit être le nom de domaine par défaut initial « contoso.onmicrosoft.com » ou un nom de domaine vérifié et non fédéré tel que « contoso.com ».
5. Sous **Groupes**, choisissez le groupe de test auquel ajouter l’utilisateur.
6. Enregistrez le mot de passe d’utilisateur généré automatiquement afin de pouvoir l’utiliser pour vous connecter à un appareil de test. Vous devez donner ce mot de passe aux utilisateurs pour qu’ils puissent le remplacer par un mot de passe normal et facile à mémoriser.
7. Dans le panneau **Utilisateur**, sélectionnez **Créer**.

## <a name="assigning-licenses-to-users"></a>Affectation de licences aux utilisateurs

Une fois que vous avez créé un utilisateur, vous devez utiliser le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pour lui affecter une licence Intune. Sans cette affectation, il ne pourra pas inscrire son appareil à la gestion.

1. Connectez-vous au [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) avec les mêmes informations d’identification que celles utilisées pour vous connecter à Intune.
2. Sélectionnez **Utilisateurs** > **Utilisateurs actifs**, puis sélectionnez l’utilisateur que vous avez créé précédemment.
3. Vous devrez peut-être patienter un instant avant que toutes les informations de l’utilisateur soient chargées. Après cela, sélectionnez **Modifier** pour les **Licences de produit** de l’utilisateur.
4. Affectez un **Lieu** à l’utilisateur, puis **activez** Intune.

 > [!NOTE]
 > Cela utilise l’une de vos licences pour cet utilisateur. Si vous utilisez votre environnement en production, vous pourrez désactiver l’utilisation de cette licence plus tard pour la réaffecter à un utilisateur réel.

5. Sélectionnez **Enregistrer**.

## <a name="next-steps"></a>Étapes suivantes

[Bien démarrer avec les groupes](get-started-groups.md) : Organisez les utilisateurs en groupes pour faciliter la gestion des stratégies et des applications auxquelles ils ont accès.
