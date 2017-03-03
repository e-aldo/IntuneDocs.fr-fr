---
title: "Stratégies de conformité d’appareils | Microsoft Docs"
description: "Cette rubrique explique la nature des stratégies de conformité des appareils et comment elles fonctionnent."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 7b91e52d72704b6beb79a1b35bb1a24ebb340a4b
ms.lasthandoff: 12/10/2016


---

# <a name="device-compliance-policies-in-microsoft-intune"></a>Stratégies de conformité d’appareils dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="what-is-a-compliance-policy"></a>Qu’est-ce qu’une stratégie de conformité ?
Pour protéger les données de l’entreprise, vous devez vérifier que les appareils utilisés pour accéder aux données et applications d’entreprise respectent certaines règles. Ces règles peuvent inclure l’utilisation d’un code confidentiel pour accéder aux appareils et le chiffrement des données stockées sur les appareils. Un ensemble de règles de ce type est appelé une stratégie de conformité.

## <a name="how-should-i-use-compliance-policies"></a>Comment dois-je utiliser les stratégies de conformité ?
Vous pouvez utiliser des stratégies de conformité avec des stratégies d’accès conditionnel pour permettre uniquement à des appareils qui sont conformes aux règles de stratégie de conformité d’accéder à des e-mails et à d’autres services. Pour savoir comment les deux stratégies peuvent être utilisées ensemble, lisez l’article [Restreindre l’accès aux services de messagerie et O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

Vous pouvez également utiliser des stratégies de conformité indépendamment de l’accès conditionnel. Quand vous utilisez des stratégies de conformité indépendamment, les appareils ciblés sont évalués et signalés avec leur état de conformité. Par exemple, vous voulez connaître le nombre d’appareils qui ne sont pas chiffrés, ou les appareils qui sont jailbreakés ou rootés. Mais quand vous utilisez des stratégies de conformité indépendamment, aucune restriction d’accès aux ressources de l’entreprise n’est appliquée.

Vous déployez les stratégies de conformité sur les utilisateurs. Quand une stratégie de conformité est déployée sur un utilisateur, la conformité de ses appareils est vérifiée.
Si vous voulez en savoir plus sur le temps nécessaire pour que les appareils mobiles reçoivent une stratégie une fois celle-ci déployée, consultez [Gérer des paramètres et des fonctionnalités sur vos appareils](https://docs.microsoft.com/en-us/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#frequently-asked-questions-about-intune-policies).

Le tableau suivant répertorie les types d’appareils pris en charge par les stratégies de conformité. Il décrit également la façon dont les paramètres de non-conformité sont gérés quand une stratégie de conformité est utilisée avec une stratégie d’accès conditionnel.

-----------------------------

|Paramètre de stratégie| Windows 8.1 et versions ultérieures| Windows Phone 8.1 et versions ultérieures| iOS 8.0 et versions ultérieures|Android 4.0 et versions ultérieures<br/>Samsung Knox Standard 4.0 et versions ultérieures|
|-----|----|----|----|----|
|**Configuration d’un code confidentiel ou mot de passe** |Corrigé|Corrigé|Corrigé|En quarantaine|
|**Chiffrement de l’appareil**|Non applicable|Corrigé|Corrigé (en définissant le code confidentiel)|En quarantaine|
|**Appareil jailbroken ou rooté**|Non applicable|Non applicable|En quarantaine (pas un paramètre)|En quarantaine (pas un paramètre)|
|**Profil de messagerie**|Non applicable|Non applicable|En quarantaine|Non applicable|
|**Version minimale du système d’exploitation**|En quarantaine|En quarantaine|En quarantaine|En quarantaine|
|**Version maximale du système d’exploitation**|En quarantaine|En quarantaine|En quarantaine|En quarantaine|
|**Attestation de l’intégrité Windows**|En quarantaine : Windows 10 et Windows 10 Mobile<br /><br />Non applicable : Windows 8.1|Non applicable|Non applicable|Non applicable|

------------------------------

**Corrigé** : le système d’exploitation de l’appareil applique la conformité. (Par exemple, l’utilisateur est obligé de définir un code confidentiel.)

**En quarantaine** : le système d’exploitation de l’appareil n’applique pas la conformité. (Par exemple, les appareils Android n’obligent pas l’utilisateur à chiffrer l’appareil.) Quand l’appareil n’est pas conforme, les actions suivantes se produisent :

-   L’appareil est bloqué si une stratégie d’accès conditionnel s’applique à l’utilisateur.

-   Le portail d’entreprise informe l’utilisateur des problèmes de conformité.

## <a name="next-steps"></a>Étapes suivantes
[Créer une stratégie de conformité des appareils](create-a-device-compliance-policy-in-microsoft-intune.md)

[Déployer et surveiller une stratégie de conformité des appareils](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### <a name="see-also"></a>Voir aussi
[Restreindre l’accès aux services de messagerie et O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)

