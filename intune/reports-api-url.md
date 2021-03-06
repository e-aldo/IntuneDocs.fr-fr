---
title: Point de terminaison de l’API d’entrepôt de données Intune
titlesuffix: Microsoft Intune
description: La rubrique de référence décrit la structure de l’URL de l’API d’entrepôt de données Intune.
keywords: Entrepôt de données Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b25140cb5c3c8c70ff42186352362c57dcf6ee7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a>Point de terminaison de l’API d’entrepôt de données Intune

Pour utiliser l’API d’entrepôt de données Intune, vous devez disposer d’un compte avec des informations d’identification Azure AD et des contrôles d’accès en fonction du rôle spécifiques. Vous devez ensuite autoriser votre client REST auprès d’Azure AD à l’aide d’OAuth 2.0. Enfin, vous devez former une URL explicite pour appeler une ressource d’entrepôt de données.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorisation

Azure Active Directory (Azure AD) utilise OAuth 2.0 pour vous permettre d'autoriser l'accès aux applications et API Web dans votre locataire Azure AD. Ce guide, indépendant du langage, décrit comment envoyer et recevoir des messages HTTP sans utiliser l’une de nos bibliothèques open source. Le flux du code d’autorisation OAuth 2.0 est décrit dans la [section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) de la spécification OAuth 2.0.

Pour plus d’informations, consultez [Autoriser l’accès aux applications web à l’aide d’OAuth 2.0 et d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Structure de l’URL de l’API

Les points de terminaison de l’API d’entrepôt de données lisent les entités pour chaque jeu. L’API prend en charge un verbe HHTP **GET** et un sous-ensemble d’options de requête.

L’URL pour Intune a le format suivant :  
https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}

L’URL contient les éléments suivants :

| Élément | Exemple | Description |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| emplacement | msua06 | Pour trouver l’URL de base, examinez le panneau de l’API d’entrepôt de données dans le portail Azure. |
| collection_entités | dates | Nom de la collection d’entités OData. Pour plus d’informations sur les collections et entités du modèle de données, consultez [Modèle de données](reports-ref-data-model.md). |
| api-version | beta | Version de l’API à laquelle accéder. Pour plus d’informations, consultez [Version](#API-version-information). |


## <a name="api-version-information"></a>Informations sur la version de l’API

Version actuelle de l’API : `beta`. 

## <a name="odata-query-options"></a>Options de requête OData

La version actuelle prend en charge les paramètres de requête OData suivants : `$filter, $orderby, $select, $skip,` et `$top`.