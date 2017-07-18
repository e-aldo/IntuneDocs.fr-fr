---
title: "Bien démarrer avec les utilisateurs"
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
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc1c4f6d18fd78f455be8e333bb765080184c908
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="get-started-with-users"></a>Bien démarrer avec les utilisateurs

![Utilisateur générique dans Azure](/intune/media/generic-intune-user.png)

Azure AD gère les groupes d’objets de votre organisation, tels que les appareils et les applications, ainsi que les groupes d’utilisateurs. Vous pouvez regrouper des utilisateurs ou des appareils au lieu de devoir gérer individuellement chaque appareil. Cela vous permet d’affecter facilement des applications et des paramètres à un grand nombre d’utilisateurs et d’appareils.

## <a name="how-do-i-create-a-user"></a>Comment créer un utilisateur ?

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. À l’aide de **Rechercher des ressources**, recherchez **Utilisateurs et groupes**.
3. Une fois que vous avez ouvert le panneau **Utilisateurs et groupes**, sélectionnez **Tous les utilisateurs**, puis **+ Nouvel utilisateur**.
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
