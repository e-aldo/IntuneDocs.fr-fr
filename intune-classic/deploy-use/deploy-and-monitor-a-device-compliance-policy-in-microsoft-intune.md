---
title: Déployer et surveiller une stratégie de conformité
description: Suivez la procédure détaillée de cette rubrique pour déployer et surveiller une stratégie de conformité d’appareil.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7e3f67411a4eff357102756e785f4cbbff120d23
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31016065"
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a>Déployer et contrôler une stratégie de conformité d’appareils dans Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a>Déployer une stratégie de conformité
Déployez la stratégie de conformité que vous avez [créée](create-a-device-compliance-policy-in-microsoft-intune.md) sur un ou plusieurs groupes d’utilisateurs de votre organisation. Quand une stratégie de conformité est déployée sur un utilisateur, la conformité de ses appareils est vérifiée.

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.
![Capture d’écran de la page de stratégie de conformité montrant l’option de menu Gérer le déploiement en haut](./media/intune-sa-3c-deploy-compliance-policy2.png)

2.  Dans la boîte de dialogue **Gérer le déploiement**, choisissez un ou plusieurs groupes pour lesquels vous voulez déployer la stratégie, puis choisissez **Ajouter** > **OK**.
![Capture d’écran de la boîte de dialogue Gérer le déploiement](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Utilisez des groupes Active Directory que vous avez déjà créés et synchronisés avec Intune, ou créez ces groupes manuellement dans la console Intune. Pour en savoir plus sur la manière de déployer des stratégies, consultez [Déployer une stratégie de configuration](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Utilisez le récapitulatif de l’état et les alertes dans la page **Vue d’ensemble** de l’espace de travail **Stratégie** pour identifier les problèmes liés à la stratégie qui nécessitent votre attention. En outre, le **Tableau de bord** contient un récapitulatif de l'état.

> [!IMPORTANT]
> Si vous n’avez pas déployé de stratégie de conformité et que vous activez la stratégie d’accès conditionnel Exchange, l’accès sera disponible pour tous les appareils ciblés.

## <a name="monitor-the-compliance-policy"></a>Analyser la stratégie de conformité

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a>Pour afficher les appareils non conformes à une stratégie de conformité

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Groupes** > **Tous les appareils**.

2.  Double-cliquez sur le nom d’un appareil dans la liste des appareils.

3.  Choisissez l’onglet **Stratégie** pour afficher la liste des stratégies applicables à cet appareil.

4.  Dans la liste déroulante **Filtres**, choisissez **Non conforme à la stratégie de conformité**.
![Capture d’écran qui montre la liste des options dans la liste de filtres](./media/intune-sa-3e-view-device-noncompliance.png)

#### <a name="to-view-the-health-attestation-reports"></a>Pour afficher les rapports d’attestation d’intégrité

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Rapports**.

2.  Dans la page **Rapport d’attestation d’intégrité - Créer un rapport**, vous pouvez afficher un rapport avec toutes les données d’attestation de l’intégrité de Windows 10 recueillies par Intune. Vous pouvez aussi utiliser des filtres pour créer un rapport avec un sous-ensemble des données. Les filtres peuvent être basés sur le type d’appareil, le système d’exploitation ou seulement un sous-ensemble de points de données.

## <a name="how-intune-resolves-policy-conflicts"></a>Résolution des conflits de stratégie par Intune
Des conflits de stratégie peuvent se produire quand plusieurs stratégies Intune sont appliquées à un appareil. Si les paramètres de stratégie se chevauchent, Intune résout les conflits en appliquant les règles suivantes :

-   Si les paramètres en conflit proviennent d’une stratégie de configuration Intune et d’une stratégie de conformité, les paramètres de la stratégie de conformité sont prioritaires sur ceux de la stratégie de configuration. Cela est valable même si les paramètres de la stratégie de configuration sont plus sécurisés.

-   Si vous avez déployé plusieurs stratégies de conformité, Intune utilise la plus sécurisée d’entre elles.

## <a name="next-steps"></a>Étapes suivantes
Pour savoir comment utiliser la stratégie de conformité avec des stratégies d’accès conditionnel pour contrôler l’accès aux services de votre organisation, consultez [Restreindre l’accès aux services de messagerie et O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).


### <a name="see-also"></a>Voir aussi
[Introduction aux stratégies de conformité des appareils dans Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md)
