---
# required metadata

title: Stratégies de conformité d’appareils | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: chrisgre
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Stratégies de conformité d’appareils dans Microsoft Intune
## Qu’est-ce qu’une stratégie de conformité ?
Pour protéger les données de l’entreprise, vous devez vérifier que les appareils utilisés pour accéder aux applications et aux données de l’entreprise respectent certaines règles, comme utiliser un code confidentiel pour accéder à l’appareil et chiffrer les données qui y sont stockées. Un ensemble de règles de ce type est appelé une stratégie de conformité.

## Comment dois-je utiliser les stratégies de conformité ?
Vous pouvez utiliser des stratégies de conformité avec des stratégies d’accès conditionnel pour permettre à des appareils qui sont conformes aux règles de stratégie de conformité d’accéder à des e-mails et à d’autres services. Lisez l’article [Restreindre l’accès aux services de messagerie et O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) pour comprendre comment les deux stratégies peuvent être utilisées ensemble.

Vous pouvez également utiliser des stratégies de conformité indépendamment de l’accès conditionnel. Quand elles sont utilisées indépendamment, les appareils ciblés sont évalués et signalés avec leur état de conformité. Par exemple, vous voulez connaître le nombre d’appareils qui ne sont pas chiffrés, ou les appareils qui sont jailbroken ou rootés. Cependant, quand elles sont utilisées indépendamment, aucune restriction d’accès aux ressources de l’entreprise n’est appliquée.

Vous déployez les stratégies de conformité sur les utilisateurs. Quand une stratégie de conformité est déployée sur un utilisateur, la conformité de ses appareils est vérifiée.

Le tableau suivant répertorie les appareils pris en charge par les stratégies de conformité et la façon dont les paramètres de non-conformité sont gérés quand la stratégie est utilisée avec une stratégie d'accès conditionnel.

--------------

|Paramètre de stratégie| Windows 8.1 et versions ultérieures| Windows Phone 8.1 et versions ultérieures| iOS 6.0 et versions ultérieures|Android 4.0 et versions ultérieures<br/>Samsung KNOX Standard 4.0 et versions ultérieures|
|-----|----|----|----|
|**Configuration d’un code confidentiel ou mot de passe** |Corrigé|Corrigé|Corrigé|En quarantaine|
|**Chiffrement de l'appareil**|N/A|Corrigé|Corrigé (en définissant le code confidentiel)|En quarantaine|
|**Appareil jailbroken ou rooté**|N/A|N/A|En quarantaine (pas un paramètre)|En quarantaine (pas un paramètre)|
|**Profil de messagerie**|N/A|N/A|En quarantaine|N/A|
|**Version minimale du système d’exploitation**|En quarantaine|En quarantaine|En quarantaine|En quarantaine|
|**Version maximale du système d’exploitation**|En quarantaine| En quarantaine| En quarantaine| En quarantaine|
|**Attestation de l’intégrité Windows**|Windows 10 et Windows 10 Mobile sont mis en quarantaine.<br /><br />Ce paramètre ne s’applique pas à Windows 8.1|N/A|N/A|N/A|
--------------
**Corrigé** = La conformité est appliquée par le système d’exploitation de l’appareil (par exemple, l’utilisateur est obligé de définir un code confidentiel).  Ce n’est jamais le cas quand la valeur est « non conforme ».

**En quarantaine** = Le système d’exploitation de l’appareil n’applique pas la conformité (par exemple, les appareils Android ne forcent pas l’utilisateur à chiffrer l’appareil). Quand l’appareil n’est pas conforme, les actions suivantes se produisent :

-   L'appareil est bloqué si l'utilisateur est ciblé par une stratégie d'accès conditionnel.

-   Le portail d’entreprise informe l’utilisateur des problèmes de conformité.

## Étapes suivantes
[Créer une stratégie de conformité des appareils](create-a-device-compliance-policy-in-microsoft-intune.md)

[Déployer et surveiller une stratégie de conformité des appareils](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Voir aussi
[Restreindre l’accès aux services de messagerie et O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


