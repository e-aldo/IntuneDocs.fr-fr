---
title: "Utilisateur - Entrepôt de données Intune | Microsoft Docs"
description: "Rubrique de référence sur la catégorie Utilisateur de collections d’entités dans l’API d’entrepôt de données Intune."
keywords: "Entrepôt de données Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f321a3a9ac09c004639a3db15df280fbdb5be3c
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-current-user-entity"></a>Informations de référence sur l’entité d’utilisateur actuel

La catégorie **Utilisateur actuel** contient les propriétés des utilisateurs et des agents dans le modèle de données. La collection d’entités **Utilisateur actuel** est limitée aux utilisateurs actuellement actifs. L’entité contient tous les utilisateurs Azure Active Directory qui disposent actuellement d’une licence. Il peut s’agir d’une licence Intune, d’une licence hybride ou d’une licence Microsoft Office 365. Les utilisateurs supprimés ne sont pas représentées pour la période de collecte de données. Pour créer une collection qui contient un historique des modifications de l’état utilisateur, consultez la page [Informations de référence sur l’entité Utilisateur](reports-ref-user.md).


## <a name="user"></a>Utilisateur

L’entité **User** répertorie tous les utilisateurs Azure Active Directory (Azure AD) auxquels des licences ont été attribuées dans votre entreprise.

| Propriété  | Description | Exemple |
|---------|------------|--------|
| UserKey |Identificateur unique de l’utilisateur dans l’entrepôt de données (clé de substitution). |123 |
| UserId |Identificateur unique de l’utilisateur (semblable à UserKey, mais il s’agit d’une clé naturelle). |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Adresse e-mail de l’utilisateur. |John@constoso.com |
| UPN | Nom d'utilisateur principal de l'utilisateur. | John@constoso.com |
| DisplayName |Nom d’affichage de l’utilisateur. |Jean |
| IntuneLicensed |Spécifie si cet utilisateur dispose d’une licence Intune ou non. |Vrai/Faux |
| StartDateInclusiveUTC |Date et heure UTC de création de cet utilisateur dans l’entrepôt de données. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Date et heure UTC de la dernière modification de cet utilisateur dans l’entrepôt de données. |11/23/2016 12:00:00 AM |

## <a name="next-steps"></a>Étapes suivantes
 - Il est possible d’utiliser la collection d’entités **Utilisateurs** pour étendre les données utilisateurs aux utilisateurs qui ne sont pas actifs actuellement. Pour plus d’informations, consultez la page [Informations de référence sur l’entité Utilisateur](reports-ref-user.md). 
 - Pour plus d’informations sur la façon dont l’entrepôt de données effectue le suivi de la durée de vie des utilisateurs dans Intune, consultez la page [Représentation de la durée de vie des utilisateurs dans l’entrepôt de données Intune](reports-ref-user-timeline.md).