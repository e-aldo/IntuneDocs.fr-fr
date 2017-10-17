---
title: "Protéger l’accès à la messagerie et à Office 365"
description: "Cette rubrique décrit comment utiliser l’accès conditionnel pour autoriser uniquement les appareils compatibles à accéder à la messagerie et aux données de votre entreprise sur SharePoint Online et d’autres services."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab45292734c39d3eaf4a5f0403cbff6e77d9d7e6
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a>Protéger l’accès à la messagerie, à Office 365 et à d’autres services avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez protéger l’accès à la messagerie de votre entreprise, aux services Office 365 comme **Exchange sur site**, **Exchange Online**, **Exchange Online Dedicated**, **SharePoint Online**, **Skype Entreprise Online** et d’autres services à l’aide de l’accès conditionnel Enterprise Mobility + Security (EMS). Cette fonctionnalité vous permet de vous assurer que l’accès à la messagerie de votre entreprise et aux services Office 365 est limité aux appareils qui respectent les règles d'accès conditionnel que vous avez définies dans la console d'administration Intune ou sur le portai Azure Classic.
## <a name="how-does-conditional-access-work"></a>Comment fonctionne l’accès conditionnel ?
Vous pouvez utiliser les paramètres de la stratégie de conformité pour évaluer la conformité d’un appareil. Une stratégie d’accès conditionnel utilise l’évaluation pour bloquer ou autoriser l’accès à un service spécifique. Quand vous utilisez une stratégie d’accès conditionnel avec une stratégie de conformité d'appareil, seuls les appareils conformes peuvent accéder au service. La stratégie de conformité et la stratégie d’accès conditionnel sont déployées pour l’utilisateur. La conformité avec les stratégies de chaque appareil que l’utilisateur utilise pour accéder aux services est contrôlée.

> [!IMPORTANT]
> Gardez à l’esprit que l’utilisateur de l’appareil doit déployer une stratégie de conformité sur l’appareil afin que sa conformité soit évaluée.
> Si aucune stratégie de conformité n’est déployée sur l’utilisateur, l’appareil est considéré comme conforme et aucune restriction d’accès ne s’applique.

Quand un appareil ne remplit pas les conditions définies dans les stratégies, l’utilisateur final est guidé tout au long du processus d’inscription de cet appareil et du processus de résolution du problème qui empêche l’appareil d’être conforme.

Voici un flux typique d’accès conditionnel :

![Diagramme qui montre les points de décision utilisés pour déterminer si un appareil est autorisé ou non à accéder à un service](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a>Considérations relatives à l'installation

### <a name="licensing"></a>Licences

Microsoft Intune et Azure Active Directory (Azure AD) Premium fonctionnent en parfaite synergie pour fournir plusieurs couches de contrôle d’accès conditionnel EMS. Si vous souhaitez déployer des stratégies d’accès conditionnel à l'aide d'Intune, vous devez disposer d'une licence pour ces deux produits.

Les **licences Azure AD Premium** peuvent être achetées en tant que service autonome ou dans le cadre de l’accord d’entreprise (avec Intune). Si vous avez déployé des stratégies d’accès conditionnel avec Intune, veuillez vous assurer que vous avez obtenu les bonnes licences Azure AD Premium ou **EMS**.

- Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

En outre, assurez-vous que les utilisateurs pour lesquels vous envisagez d’appliquer des stratégies d’accès conditionnel [disposent de licences Azure AD Premium ou EMS](/intune/licenses-assign).

### <a name="device-compliance-settings"></a>Paramètres de conformité des appareils

Pour mettre en place l’accès conditionnel, configurez une stratégie de conformité des appareils et une stratégie d’accès conditionnel. La stratégie de conformité inclut des paramètres tels que le mot de passe, le chiffrement et le jailbreak de l’appareil. L’appareil doit respecter ces règles pour être considéré comme conforme.

- Découvrez plus en détail la [stratégie de conformité des appareils et son fonctionnement](introduction-to-device-compliance-policies-in-microsoft-intune.md).

### <a name="conditional-access-policy"></a>Stratégie d’accès conditionnel

Vous pouvez définir une stratégie d’accès conditionnel pour protéger l’accès en fonction de :
- L’état de conformité de l’appareil.
- La plateforme exécutée sur l’appareil.
- Le type des applications utilisées pour accéder aux services.

Contrairement à d’autres stratégies Intune, vous ne déployez pas de stratégies d’accès conditionnel. Au lieu de cela, une fois que vous avez configuré la stratégie et sélectionné les utilisateurs concernés, la stratégie est appliquée à tous les utilisateurs ciblés. Quand un utilisateur est ciblé par une stratégie, chaque appareil qu’il utilise doit être conforme à cette stratégie pour qu’il puisse accéder aux ressources.


## <a name="next-steps"></a>Étapes suivantes


2. [Créer une stratégie de conformité des appareils](create-a-device-compliance-policy-in-microsoft-intune.md).

2.  Créer une stratégie d’accès conditionnel pour l’un des services cloud/produits Microsoft suivants :

  - [Créer une stratégie d’accès conditionnel à Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Créer une stratégie d’accès conditionnel à Exchange sur site](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Créer une stratégie d’accès conditionnel à Exchange Online Dedicated](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [Créer une stratégie d’accès conditionnel à Exchange Online Dedicated (environnement hérité)](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [Créer une stratégie d’accès conditionnel pour SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [Créer une stratégie d’accès conditionnel pour Skype Entreprise Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [Créer une stratégie d’accès conditionnel pour Dynamics CRM Online](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
