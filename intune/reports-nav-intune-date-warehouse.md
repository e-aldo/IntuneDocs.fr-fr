---
title: "API d’entrepôt de données Intune | Microsoft Docs"
description: "Vous pouvez utiliser l’API pour générer des rapports qui fournissent des insights sur l’environnement mobile de votre entreprise."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f03fd3a1557ef5d013fe695016ed0e3b119ee62
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/04/2017
---
#  <a name="intune-data-warehouse-api"></a>API d’entrepôt de données Intune

L’API d’entrepôt de données Intune vous permet d’accéder à vos données Intune dans un format lisible par ordinateur et de les utiliser dans votre outil d’analyse préféré. Vous pouvez utiliser l’API pour générer des rapports qui fournissent des insights sur l’environnement mobile de votre entreprise. L’API utilise le protocole OData qui respecte des modèles standard dans les domaines suivants :

  -   En-têtes de demande et de réponse
  -   Codes d’état
  -   Méthodes HTTP
  -   Conventions d’URL
  -   Types de médias
  -   Formats de charge utile
  -   Options de requête

OData (Open Data Protocol) est une norme OASIS (Organization for the Advancement of Structured Information Standards) qui définit les bonnes pratiques à suivre pour la création et l’utilisation d’API RESTful. L’entrepôt de données Intune utilise OData version 4.0.

Cette section de référence fournit une vue d’ensemble des points de terminaison, des méthodes HTTP prises en charge et des formats de charge utile de retour. Elle contient aussi des informations sur le modèle de données de l’entrepôt de données Intune.

> [!Important]  
> Utilisez la version bêta pour essayer les fonctionnalités les plus récentes de l’entrepôt de données. Pour accéder à la version bêta, votre URL doit contenir le paramètre de requête `api-version=beta`. La version bêta vous permet d’utiliser des fonctionnalités avant qu’elles ne soient disponibles dans le cadre d’un service pris en charge. À mesure que de nouvelles fonctionnalités sont ajoutées à Intune, le comportement et le contrat de données de la version bêta peuvent être amenés à changer. Il est possible que le code personnalisé ou les outils de génération de rapports qui dépendent de la version bêta ne fonctionnent plus après l’application de mises à jour. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

<!-- ## OData custom client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a web app and a client app in Azure, grant permissions to the client. Your local client will get authorization, can then communicate with the Data Warehouse endpoints.

For more information, see [Get data from the Data Warehouse API with a REST client](Get-data-REST.md) -->

## <a name="interacting-with-the-api"></a>Interaction avec l’API

L’API nécessite une autorisation auprès d’Azure AD. Azure AD utilise OAuth 2.0. Une fois l’autorisation obtenue, utilisez un verbe HTTP GET et contactez les collections d’entités exposées pour obtenir des données de l’API. Pour plus d'informations, consultez le site Internet suivant :

 -  [Autorisation](reports-api-url.md)
 -  [Structure de l’URL de l’API](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Modèle de données de l’entrepôt de données Intune

OData définit un modèle de données abstrait et un protocole qui permettent à tout client d’accéder aux informations exposées par n’importe quelle source de données. La rubrique consacrée au modèle de données contient une explication des espaces de noms, des entités et des objets de retour inclus dans le modèle de données de l’entrepôt de données Intune. Pour plus d’informations, consultez [Modèle de données de l’entrepôt de données](reports-ref-data-model.md).

## <a name="for-more-information"></a>Pour plus d'informations

[Scénarios d’authentification pour Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[OData version 4.0](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  