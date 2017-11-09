---
title: "Journal des modifications de l’entrepôt de données Intune | Microsoft Docs"
description: "Liste des modifications dans l’API de l’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b81846c2e45f968184d50d2ea7c50aabb86b4964
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/02/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Journal des modifications pour l’API de l’entrepôt de données Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Suivez les mises à jour de l’entrepôt de données Intune.

## <a name="1710"></a>1710
_Publication : octobre 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>L’entité Utilisateur contient les données utilisateur les plus récentes dans le modèle de données de l’entrepôt de données <!-- 1544273 -->

La première version du modèle de données de l’entrepôt de données Intune ne contenait que des données Intune historiques récentes. Les auteurs de rapports ne pouvaient pas capturer l’état actuel d’un utilisateur. Dans cette mise à jour, [**l’entité Utilisateur**](reports-ref-user.md) est renseignée avec les données utilisateur les plus récentes.

### <a name="new-entity-in-the-in-data-warehouse-data-model----1479526---"></a>Nouvelle entité dans le modèle de données de l’entrepôt de données <!-- 1479526 -->

L’entité [**UserDeviceAssociation**](reports-ref-user-device.md) est ajoutée. **UserDeviceAssociation** contient les associations appareil-utilisateur dans votre organisation.

## <a name="next-steps"></a>Étapes suivantes
 - Découvrez les [nouveautés hebdomadaires dans Intune](whats-new.md). Vous pouvez également découvrir les modifications à venir, les annonces importantes sur le service et des informations sur les versions précédentes. 
 - Consultez le [Blog de Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).