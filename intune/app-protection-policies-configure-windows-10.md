---
title: "Préparer la configuration des stratégies de protection d’application pour Windows 10"
titleSuffix: Intune on Azure
description: Configuration du fournisseur de gestion des applications mobiles dans Azure AD
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bf56d3a80f0d167baa95e9dfdb20d08e02590984
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Préparer la configuration des stratégies de protection d’application pour Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Avant de créer une stratégie de protection d’application Windows 10, vous devez activer la gestion des applications mobiles (MAM) pour Windows 10 en définissant le fournisseur MAM dans Azure AD. Cette configuration vous permet de définir l’état d’inscription lors de la création d’une nouvelle stratégie de Protection des informations Windows (WIP) avec Intune.

> [!NOTE]
> L’état de l’inscription peut être MAM ou gestion des appareils mobiles (MDM).

## <a name="to-configure-the-mam-provider"></a>Pour configurer le fournisseur MAM

1.  Accédez au [portail Azure](https://portal.azure.com/) et connectez-vous avec vos informations d’identification Intune.

2.  Dans le menu de gauche, choisissez **Azure Active Directory**.

    ![Configuration du fournisseur MAM](./media/mam-provider-sc-1.png)

3.  Le panneau **Azure AD** s’ouvre, choisissez **Mobilité (MDM et MAM)**, puis cliquez sur **Microsoft Intune**.

    ![Mobilité (gestion des données de référence et gestion des applications mobiles)](./media/mam-provider-sc-1.png)

4.  Le volet Configuration s’ouvre, choisissez d’abord **Restaurer les URL MAM par défaut**, puis configurez ce qui suit :

    a.  Étendue des utilisateurs MAM : vous pouvez utiliser MAM pour protéger des données d’entreprise sur un groupe spécifique d’utilisateurs qui utilisent des appareils Windows 10, ou tous les utilisateurs.

    b.  URL de conditions d’utilisation de MAM : l’URL des conditions d’utilisation du service MAM. Permet d’afficher les conditions de service MAM pour les utilisateurs finaux.

    c.  URL de découverte MAM : il s’agit de l’URL que les appareils recherchent lorsqu’ils ont besoin appliquer des stratégies de protection d’application.

    d.  URL de conformité MAM :

5.  Une fois ces paramètres configurés, cliquez sur **Enregistrer**.

## <a name="next-steps"></a>Étapes suivantes

[Créer une stratégie de protection d’application WIP](windows-information-protection-policy-create.md)
