---
title: "Se connecter à l’entrepôt de données avec Power BI | Microsoft Docs"
description: "Vous pouvez télécharger un fichier destiné à Microsoft Power BI qui vous permet de charger des rapports interactifs et dynamiques pour votre locataire Intune."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b70bf3410e20dd792c0fcff050292ddea714d63e
ms.sourcegitcommit: 99ffed621855357de427d6fdf7b70d4e543197e9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Se connecter à l’entrepôt de données avec Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vous pouvez télécharger un fichier destiné à Microsoft Power BI qui vous permet de charger des rapports interactifs et dynamiques pour votre locataire Intune. Le fichier Power BI (pbix) d’entrepôt de données contient des paramètres de connexion à votre locataire ainsi que les exemples de rapports et de graphiques suivants :  

  -  Appareils
  -  Inscription
  -  Stratégie de protection des applications
  -  Stratégie de conformité
  -  Profils de configuration d’appareil
  -  Mises à jour logicielles
  -  Journaux d’inventaire des appareils

Les tendances sont également mises en évidence dans les catégories suivantes : inscription, conformité, profil de configuration d’appareil et mises à jour logicielles. Les exemples de graphiques et de rapports appliquent des filtres conviviaux au canevas. Pour utiliser des filtres avancés, explorez le volet **Filtre** dans Power BI Desktop. 

Les étapes suivantes vous montrent comment télécharger le fichier Power BI et comment utiliser le lien OData avec Power BI.

## <a name="install-power-bi"></a>Installer Power BI

Installez la dernière version de Power BI Desktop. Power BI Desktop est disponible en téléchargement à l’emplacement suivant : [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) 

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Charger les données et les rapports à l’aide du fichier Power BI (pbix)

Le fichier Power BI (pbix) contient les informations de connexion pour votre locataire et un ensemble de rapports prédéfinis basés sur le modèle de données de l’entrepôt de données. Ouvrez le fichier dans Power BI Desktop et connectez-vous à Azure AD. Le rapport charge les données de votre locataire Intune.

> [!Important]  
> Les fichiers Power BI (pbix) peuvent varier selon l’emplacement du locataire. Si vous gérez plusieurs locataires Intune, veillez à utiliser le fichier téléchargé à partir du portail Azure tout en étant connecté au locataire.  

1.  Connectez-vous au portail Azure et choisissez **Surveillance + gestion** > **Intune**. Vous pouvez aussi rechercher **Intune** dans les ressources.  
2.  Ouvrez le panneau **API d’entrepôt de données Microsoft Intune (préversion)**.
3.  Cliquez sur **Télécharger le fichier Power BI**. Un fichier portant l’extension pbix est téléchargé à l’emplacement indiqué.
4.  Ouvrez le fichier avec Power BI. Les *rapports de l’entrepôt de données Intune* se chargent, mais l’opération peut prendre quelques secondes le temps d’obtenir les données de votre locataire.
5.  Cliquez sur **Actualiser** pour charger les données de votre locataire et passer en revue les rapports.
6.  Si Power BI n’a pas été authentifié avec vos informations d’identification Azure Active Directory, vous êtes invité à les entrer. Quand vous sélectionnez vos informations d’identification, choisissez **Compte professionnel** comme méthode d’authentification.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Charger les données dans Power BI à l’aide du lien OData

Quand un client est authentifié auprès d’Azure AD, l’URL OData se connecte au point de terminaison RESTful dans l’API d’entrepôt de données qui expose le modèle de données à votre client de création de rapports. Pour utiliser Power BI Desktop pour vous connecter et créer vos propres rapports, suivez ces instructions. Vous n’êtes pas limité à Power BI Desktop. Vous pouvez utiliser votre outil d’analyse préféré avec l’URL OData, à condition toutefois que le client prenne en charge l’authentification OAUTH2.0 et la norme OData v4.0.

1.  Récupérez l’**URL OData** dans le panneau de création de rapports (par exemple, `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`).
2.  Ouvrez **Power BI Desktop**.
3.  Choisissez **Accueil** > **Obtenir des données**. Sélectionnez **Flux OData**.
4.  Choisissez **De base**.
5.  Tapez ou collez l’**URL OData** dans la zone URL.
6.  Cliquez sur **OK**.
7.  Si vous n’êtes pas authentifié auprès d’Azure AD pour votre locataire à partir du client Power BI Desktop, tapez vos informations d’identification.  
    a.  Sélectionnez **Compte professionnel**.  
    b.  Tapez vos nom d’utilisateur et mot de passe.  
    c.  Cliquez sur **Se connecter**.  
    d.  Cliquez sur **Connexion**.  
8.  Cliquez sur **Charger**.

## <a name="next-steps"></a>Étapes suivantes

Vous pouvez obtenir les réponses aux questions relatives à votre environnement, par exemple le nombre d’appareils inscrits par jour au cours de la semaine dernière. Vous pouvez obtenir des insights sur votre population de locataires et de clients Intune à l’aide des rapports basés sur le fichier Power BI (pbix) de l’entrepôt de données Intune récupéré à partir du panneau dans Azure. Toutefois, Intune vous propose plusieurs façons d’étendre ou de réutiliser les données. Power BI et l’API d’entrepôt de données Intune offrent bien d’autres fonctionnalités, par exemple :

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Les données du locataire sont organisées pour vous aider à obtenir des insights sur vos données. Pour plus d’informations sur la façon dont les données sont organisées, consultez [Modèle de données de l’entrepôt de données](reports-ref-data-model.md). 
<!-- -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md). -->