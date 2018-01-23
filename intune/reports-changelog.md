---
title: "Journal des modifications de l’entrepôt de données Intune | Microsoft Docs"
description: "Liste des modifications dans l’API de l’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e17ca34897a707360d802e37ffe3fa91fad0860
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/16/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Journal des modifications pour l’API de l’entrepôt de données Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Suivez les mises à jour de l’entrepôt de données Intune.

## <a name="1710"></a>1710
_Publication : novembre 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Nouvelle collection d’entités, nommée Utilisateur actuel, limitée aux données des utilisateurs actuellement actifs<!-- 1544273 -->

La collecte d’entités **User** répertorie tous les utilisateurs Azure Active Directory (Azure AD) auxquels des licences ont été attribuées dans votre entreprise. Parmi ces enregistrements figurent les états utilisateurs de la période de collecte de données, même si l’utilisateur a été supprimé. Il est possible, par exemple, qu’un utilisateur soit ajouté à Intune, puis supprimé au cours du mois précédent. Cet utilisateur n’est pas présent au moment du rapport, mais lui et l’état apparaissent quand même dans les données. Vous pourriez créer un rapport qui afficherait la durée de la présence passée de l’utilisateur dans vos données.

En revanche, la nouvelle collection d’entités **Utilisateur actuel** contient uniquement les utilisateurs qui n’ont pas été supprimés. La collection d'entités **Utilisateur actuel** ne contient que des utilisateurs actuellement actifs. Pour plus d’informations sur la collection d’entités **Utilisateur actuel**, consultez la page [Informations de référence sur l’entité Utilisateur actuel](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Publication : octobre 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Collection d’entités Association appareil-utilisateur ajoutée au modèle de données de l’entrepôt de données Intune<!-- 1187917 -->

Vous pouvez désormais générer des rapports et des visualisations des données en utilisant les informations d’association appareil-utilisateur qui associent les collections d’entité utilisateur et appareil. Le modèle de données est accessible par le biais du fichier Power BI (PBIX) extrait de la page Intune Data Warehouse, via le point de terminaison OData, ou en développant un client personnalisé. Pour plus d’informations, consultez la page [Association appareil-utilisateur](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nouvelles entités dans le modèle de données de l’entrepôt de données <!-- 1479526 --><!-- -->

 - L’entité [**UserDeviceAssociation**](reports-ref-user-device.md) est ajoutée. **UserDeviceAssociation** contient les associations appareil-utilisateur dans votre organisation. Vous pouvez désormais générer des rapports et des visualisations des données en utilisant les informations d’association appareil-utilisateur qui associent les collections d’entité utilisateur et appareil.  
 - L’entité [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md) a été ajoutée. **IntuneManagementExtension** contient des entités pour les appareils mobiles qui effectuent le suivi d’informations telles que l’état d’installation et la version.

## <a name="next-steps"></a>Étapes suivantes
 - Découvrez les [nouveautés hebdomadaires dans Intune](whats-new.md). Vous pouvez également découvrir les modifications à venir, les annonces importantes sur le service et des informations sur les versions précédentes.
 - Consultez le [Blog de Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
