---
title: "Utiliser l’entrepôt de données Intune | Microsoft Docs"
description: "Utilisez l’entrepôt de données Intune pour générer des rapports qui fournissent des insights sur l’environnement mobile de votre entreprise."
keywords: "Entrepôt de données Intune"
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 910d279b57c885040d2ad092e460d3e7ca71090e
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2018
---
# <a name="use-the-intune-data-warehouse"></a>Utiliser l’entrepôt de données Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez l’entrepôt de données Intune pour générer des rapports qui fournissent des insights sur l’environnement mobile de votre entreprise. Voici quelques-uns des rapports générés :
-   Tendance des inscriptions d’utilisateurs dans Intune pour vous permettre d’optimiser vos achats de licences
-   Répartition des versions des applications et des systèmes d’exploitation pour vous permettre d’examiner l’état des appareils mobiles
-   Tendance des inscriptions et de la conformité des appareils pour vous permettre de déployer facilement les mises à jour de la stratégie

L’entrepôt de données vous donne plus d’informations sur votre environnement mobile que le portail Azure. Grâce à l’entrepôt de données Intune, vous pouvez accéder à ce qui suit :

  -  Données d’historique Intune
  -  Données actualisées quotidiennement
  -  Modèle de données utilisant la norme OData

> [!Note]
> Si vous utilisez une gestion des appareils mobiles (MDM) hybride avec System Center Configuration Manager et Microsoft Intune, vous pouvez récupérer vos données de SCCM. L’entrepôt de données Intune ne contient que des données Intune. Vous pouvez utiliser un tableau de bord SCCM Power BI pour vos rapports personnalisés. Pour plus d’informations, consultez [Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template) (Annonce du modèle de solution Power BI pour System Center Configuration Manager) et [Créer un rapport et un tableau de bord Power BI](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard).


> [!Important]  
> Utilisez la version bêta pour essayer les fonctionnalités les plus récentes de l’entrepôt de données. Pour accéder à la version bêta, votre URL doit contenir le paramètre de requête `api-version=beta`. La version bêta vous permet d’utiliser des fonctionnalités avant qu’elles ne soient disponibles dans le cadre d’un service pris en charge. À mesure que de nouvelles fonctionnalités sont ajoutées à Intune, le comportement et le contrat de données de la version bêta peuvent être amenés à changer. Il est possible que le code personnalisé ou les outils de génération de rapports qui dépendent de la version bêta ne fonctionnent plus après l’application de mises à jour.

**Étapes suivantes**

- Obtenez un lien et utilisez Power BI pour obtenir des insights. Pour obtenir des instructions, consultez [Se connecter à l’entrepôt de données Intune avec Power BI](reports-proc-get-a-link-powerbi.md).
- Avec votre lien, créez un rapport personnalisé à l’aide de Power BI. Pour obtenir des instructions, consultez [Créer un rapport à partir du flux OData avec Power BI](reports-proc-create-with-odata.md).
- Pour obtenir plus d’informations sur l’API d’entrepôt de données Intune, le modèle de données et les relations entre les entités<!-- , and an example of creating a custom client to retrieve data,-->, consultez [API d’entrepôt de données Intune](reports-nav-intune-data-warehouse.md).