---
title: "Préparer la configuration des stratégies de protection d’application pour Windows 10"
titlesuffix: Azure portal
description: Configuration du fournisseur de gestion des applications mobiles dans Azure AD
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 91e26256d220ba70e5ad6daa3910d34eea8bb5ed
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Préparer la configuration des stratégies de protection d’application pour Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Activez la gestion des applications mobiles (GAM) pour Windows 10 en définissant le fournisseur GAM dans Azure AD. La définition d’un fournisseur GAM dans Azure AD vous permet de définir l’état d’inscription durant la création d’une nouvelle stratégie de Protection des informations Windows (WIP) avec Intune. L’état de l’inscription peut être MAM ou gestion des appareils mobiles (MDM).

> [!NOTE]
> Les appareils avec un état d’inscription de gestion des applications mobiles doivent être joints à Azure AD.

## <a name="to-configure-the-mam-provider"></a>Pour configurer le fournisseur MAM

1. Connectez-vous au portail Azure et sélectionnez **Azure Active Directory**.

2. Sélectionnez **Mobilité (MDM et GAM)** dans le groupe **Gérer**.

3. Cliquez sur **Microsoft Intune**.

4. Configurez les paramètres dans le groupe **Restaurer les URL Gestion des applications mobiles par défaut** du panneau **Configurer**.

    **Portée de l'utilisateur Gestion des applications mobiles**  
      Utilisez l’inscription automatique GAM pour gérer les données d’entreprise sur les périphériques Windows de vos employés. L’inscription automatique GAM sera configurée pour des scénarios BYOD (Apportez votre propre appareil).<ul><li>**Aucun**<br>Sélectionnez cette option si tous les utilisateurs peuvent être inscrits dans GAM.</li><li>**Quelques-uns**<br>Sélectionnez les groupes Azure AD qui contiennent les utilisateurs qui seront inscrits dans GAM.</li><li>**Tous**<br>Sélectionnez cette option si tous les utilisateurs peuvent être inscrits dans GAM.</li></ul>

    **URL des conditions d'utilisation de GAM**  
     Il s’agit de l’URL du point de terminaison des conditions d’utilisation du service GAM. Le point de terminaison des conditions d’utilisation sert à afficher les conditions d’utilisation aux utilisateurs finaux avant l’inscription de leurs appareils à gérer. Les conditions d’utilisation informent les utilisateurs sur les stratégies appliquées aux appareils mobiles.

    **URL de détection de GAM**  
    Il s’agit de l’URL du point de terminaison d’inscription du service GAM. Le point de terminaison sert à inscrire des appareils à gérer à travers le service GAM.

    **URL de conformité GAM**  
      Il s’agit de l’URL du point de terminaison de conformité du service GAM. Quand un utilisateur se voit refuser l’accès à une ressource à partir d’un appareil non conforme, un lien vers l’URL de conformité lui est indiqué. Les utilisateurs peuvent accéder à cette URL hébergée par le service GAM pour savoir pourquoi leur appareil est considéré comme non conforme. Les utilisateurs peuvent également effectuer une correction libre-service pour rendre leurs appareils conformes et pouvoir continuer à accéder aux ressources.

5.  Cliquez sur **Enregistrer**.

## <a name="next-steps"></a>Étapes suivantes

[Créer une stratégie de protection d’application WIP](windows-information-protection-policy-create.md)
