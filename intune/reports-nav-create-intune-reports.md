---
title: "Utiliser l’entrepôt de données Intune | Microsoft Docs"
description: "Utilisez l’entrepôt de données Intune pour générer des rapports qui fournissent des insights sur l’environnement mobile de votre entreprise."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cb311429e0537709b3476154bdef24347cb99026
ms.sourcegitcommit: 294de4d4058de2c625abb8143e90880d27da9284
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/15/2017
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

> [!Important]  
> Utilisez la version bêta pour essayer les fonctionnalités les plus récentes de l’entrepôt de données. Pour accéder à la version bêta, votre URL doit contenir le paramètre de requête `api-version=beta`. La version bêta vous permet d’utiliser des fonctionnalités avant qu’elles ne soient disponibles dans le cadre d’un service pris en charge. À mesure que de nouvelles fonctionnalités sont ajoutées à Intune, le comportement et le contrat de données de la version bêta peuvent être amenés à changer. Il est possible que le code personnalisé ou les outils de génération de rapports qui dépendent de la version bêta ne fonctionnent plus après l’application de mises à jour. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Étapes suivantes**

- Obtenez un lien et utilisez Power BI pour obtenir des insights. Pour obtenir des instructions, consultez [Se connecter à l’entrepôt de données Intune avec Power BI](reports-proc-get-a-link-powerbi.md).
- Pour obtenir plus d’informations sur l’API d’entrepôt de données Intune, le modèle de données et les relations entre les entités<!-- , and an example of creating a custom client to retrieve data,-->, consultez [API d’entrepôt de données Intune](reports-nav-intune-data-warehouse.md).