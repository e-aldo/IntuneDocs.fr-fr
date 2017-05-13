---
title: "Préparer la configuration des stratégies de protection d’application pour Windows 10 | Microsoft Docs"
description: Configuration du fournisseur de gestion des applications mobiles dans Azure AD
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 86a59771fc57971a626f71083e81cd4b7d858cfa
ms.contentlocale: fr-fr
ms.lasthandoff: 04/25/2017


---

# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Préparer la configuration des stratégies de protection d’application pour Windows 10

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Avant de créer une stratégie de protection d’application Windows 10, vous devez activer la gestion des applications mobiles (MAM) pour Windows 10 en définissant le fournisseur MAM dans Azure AD. Cette configuration vous permet de définir l’état d’inscription lors de la création d’une nouvelle stratégie de Protection des informations Windows (WIP) avec Intune.

> [!NOTE]
> L’état de l’inscription peut être MAM ou gestion des appareils mobiles (MDM).

## <a name="to-configure-the-mam-provider"></a>Pour configurer le fournisseur MAM

1.  Accédez au [portail Azure](https://portal.azure.com/) et connectez-vous avec vos informations d’identification Intune.

2.  Dans le menu de gauche, choisissez **Azure Active Directory**.

    ![Configuration du fournisseur MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  Le panneau **Azure AD** s’ouvre, choisissez **Mobilité (MDM et MAM)**, puis cliquez sur **Microsoft Intune**.

    ![Mobilité (gestion des données de référence et gestion des applications mobiles)](../media/AppManagement/mam-provider-sc-2.png)

4.  Le volet Configuration s’ouvre, choisissez d’abord **Restaurer les URL MAM par défaut**, puis configurez ce qui suit :

    a.  Étendue des utilisateurs MAM : vous pouvez utiliser MAM pour protéger des données d’entreprise sur un groupe spécifique d’utilisateurs qui utilisent des appareils Windows 10, ou tous les utilisateurs.

    b.  URL de conditions d’utilisation de MAM : l’URL des conditions d’utilisation du service MAM. Permet d’afficher les conditions de service MAM pour les utilisateurs finaux.

    c.  URL de découverte MAM : il s’agit de l’URL que les appareils recherchent lorsqu’ils ont besoin appliquer des stratégies de protection d’application.

    d.  URL de conformité MAM :

5.  Une fois ces paramètres configurés, cliquez sur **Enregistrer**.

## <a name="next-steps"></a>Étapes suivantes

[Créer une stratégie de protection d’application WIP](https://docs.microsoft.com/intune/deploy-use/create-windows-information-protection-policy-with-intune)

