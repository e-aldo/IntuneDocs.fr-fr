---
title: "Point de terminaison de l’API d’entrepôt de données Intune | Microsoft Docs"
description: "Cette rubrique de référence décrit la structure d’URL de l’API."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Point de terminaison de l’API d’entrepôt de données Intune

Pour utiliser l’API d’entrepôt de données Intune, vous devez disposer d’un compte avec des informations d’identification Azure AD et des contrôles d’accès en fonction du rôle spécifiques. Vous devez ensuite autoriser votre client REST auprès d’Azure AD à l’aide d’OAuth 2.0. Enfin, vous devez former une URL explicite pour appeler une ressource d’entrepôt de données.

## <a name="azure-ad-and-intune-credential-requirements"></a>Exigences liées aux informations d’identification Azure AD et Intune

L’authentification et l’autorisation sont basées sur les informations d’identification Azure AD et le contrôle d’accès en fonction du rôle (RBAC). Par défaut, tous les administrateurs généraux et les administrateurs de service Intune pour votre locataire ont accès à l’API. Pour autoriser davantage d’utilisateurs, utilisez les rôles Intune et octroyez l’accès à la **ressource Rapports**.

L’accès à l’API est soumis aux conditions suivantes :

  -  Une licence Intune doit être affectée à l’utilisateur
  -  L’utilisateur doit appartenir à l’une des catégories suivantes :
      -  Administrateur général Azure AD
      -  Administrateur de service Intune
      -  Utilisateur avec accès en fonction du rôle à la ressource **Rapports**

## <a name="authorization"></a>Autorisation

Azure Active Directory (Azure AD) utilise OAuth 2.0 pour vous permettre d'autoriser l'accès aux applications et API Web dans votre locataire Azure AD. Ce guide, indépendant du langage, décrit comment envoyer et recevoir des messages HTTP sans utiliser l’une de nos bibliothèques open source. Le flux du code d’autorisation OAuth 2.0 est décrit dans la [section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) de la spécification OAuth 2.0.

Pour plus d’informations, consultez [Autoriser l’accès aux applications web à l’aide d’OAuth 2.0 et d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Structure de l’URL de l’API

Les points de terminaison de l’API d’entrepôt de données lisent les entités pour chaque jeu. L’API prend en charge un verbe HHTP **GET** et un sous-ensemble d’options de requête.

L’URL pour Intune a le format suivant :  
https://fef.{***emplacement***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***collection_entités***}?api-version={***version_api***}

L’URL contient les éléments suivants :

| Élément | Exemple | Description |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| emplacement | msua06 | Pour trouver l’URL de base, examinez le panneau de l’API d’entrepôt de données dans le portail Azure. |
| collection_entités | dates | Nom de la collection d’entités OData. Pour plus d’informations sur les collections et entités du modèle de données, consultez [Modèle de données](reports-ref-data-model.md). |
| api-version | beta | Version de l’API à laquelle accéder. Pour plus d’informations, consultez [Version](#API-version-information). |


## <a name="api-version-information"></a>Informations sur la version de l’API

Version actuelle de l’API : `beta`. 

## <a name="odata-query-options"></a>Options de requête OData

La version actuelle prend en charge les paramètres de requête OData suivants : `$skip, $top, $filter, $orderby`.