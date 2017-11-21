---
title: "Accès conditionnel avec Intune"
titlesuffix: Azure portal
description: "Apprenez à définir les conditions que les utilisateurs et appareils doivent respecter pour accéder aux ressources d’entreprise dans la Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1cd12a105142d5e537da487e3bd9297ef83ddcb3
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2017
---
# <a name="whats-conditional-access"></a>Qu’est-ce que l’accès conditionnel ?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique décrit l’accès conditionnel qui s’applique à Enterprise Mobility + Security (EMS) puis présente des scénarios courants d’accès conditionnel avec Intune.

L’accès conditionnel d’Enterprise Mobility + Security (EMS) n’est pas un produit autonome, il s’agit d’une solution qui tire parti de tous les services et produits qui font partie de la suite EMS. Il offre un contrôle d’accès granulaire pour sécuriser vos données d’entreprise, tout en donnant aux utilisateurs une expérience qui leur permet d’effectuer leur travail au mieux à partir de n’importe quel appareil et de n’importe quel emplacement.

Vous pouvez définir des conditions qui contrôlent l’accès à vos données d’entreprise en fonction de l’emplacement, l’état de l'appareil et de l’utilisateur, et la sensibilité de l’application.

> [!NOTE] 
> L’accès conditionnel étend également ses fonctionnalités aux [services Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Diagramme architectural de l’accès conditionnel](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Accès conditionnel avec Intune

Intune ajoute des stratégies de conformité des appareils mobiles et de gestion des applications pour prendre en charge la solution d’accès conditionnel d’EMS.

![Intune et accès conditionnel lors de l’utilisation d’EMS](./media/intune-with-ca-1.png)

Moyens d’utilisation de l’accès conditionnel avec Intune :

-   **Accès conditionnel basé sur l’appareil**

    -   Accès conditionnel pour Exchange sur site

    -   Accès conditionnel basé sur le contrôle d’accès réseau

    -   Accès conditionnel basé sur les risques que présente l’appareil

    -   Accès conditionnel pour les PC Windows

        -   Appartenant à l’entreprise

        -   Apportez votre propre appareil (BYOD)

-   **Accès conditionnel basé sur l’application**

## <a name="next-steps"></a>Étapes suivantes

[Utilisations courantes de l’accès conditionnel avec Intune](conditional-access-intune-common-ways-use.md)
