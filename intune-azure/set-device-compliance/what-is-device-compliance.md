---
title: "Conformité de l’appareil"
titleSuffix: Intune Azure preview
description: "Version préliminaire d&quot;Intune Azure : utilisez cette rubrique pour en savoir plus sur la conformité dans Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: cddeb6bf854b9ffbbc1744d5d164c8ceea34ff49
ms.openlocfilehash: 7d5a1859ef1a373ce424dd4f351fc137c6052fb7
ms.lasthandoff: 03/10/2017


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Quelle est la conformité des appareils dans la version préliminaire d'Intune Azure ?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Les stratégies de conformité des appareils dans Intune définissent les règles et les paramètres qu’un appareil doit respecter pour être considéré comme conforme par les stratégies d’accès conditionnel EMS et Intune. Vous pouvez également utiliser des stratégies de conformité d’appareil pour surveiller et corriger les problèmes de conformité avec les appareils. 

Ces règles sont les suivantes :

- Utiliser un mot de passe pour accéder aux appareils
- Chiffrement
- Si l’appareil est jailbroken ou rooté
- Version minimale du système d’exploitation requise
- Version maximale autorisée du système d’exploitation
- Exiger que l’appareil soit au niveau ou sous le niveau de défense contre les menaces mobiles

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Comment dois-je utiliser les stratégies de conformité d’un appareil ?

### <a name="using-ems-conditional-access"></a>Utilisation de l’accès conditionnel EMS
Vous pouvez utiliser une stratégie de conformité avec accès conditionnel EMS pour permettre uniquement aux appareils conformes à une ou plusieurs règles de conformité des appareils d’accéder à des e-mails et à d’autres ressources de l’entreprise.

### <a name="not-using-ems-conditional-access"></a>Non-utilisation de l’accès conditionnel EMS
Vous pouvez également utiliser des stratégies de conformité d’appareils indépendamment de l’accès conditionnel EMS.
Quand vous utilisez des stratégies de conformité indépendamment, les appareils ciblés sont évalués et signalés avec leur état de conformité. Par exemple, vous pouvez obtenir un rapport sur le nombre d’appareils qui ne sont pas chiffrés, ou les appareils qui sont jailbreakés ou rootés. Mais quand vous utilisez des stratégies de conformité indépendamment, aucune restriction d’accès aux ressources de l’entreprise n’est appliquée.

Vous déployez les stratégies de conformité sur les utilisateurs. Quand une stratégie de conformité est déployée sur un utilisateur, la conformité de ses appareils est vérifiée. Si vous voulez en savoir plus sur le temps nécessaire pour que les appareils mobiles reçoivent une stratégie une fois celle-ci déployée, consultez Gérer des paramètres et des fonctionnalités sur vos appareils.

##  <a name="intune-classic-admin-console-vs-intune-azure-preview-portal"></a>Console d’administration Intune classique et portail en préversion Azure Intune

Si vous utilisiez la console d’administration Intune classique, notez les différences suivantes pour vous aider à effectuer la transition vers le nouveau processus de stratégie de conformité d’appareil dans le portail Azure :

-   Dans le portail Azure, les stratégies de conformité sont créées séparément pour chaque plateforme prise en charge. Dans la console d’administration d’Intune, une stratégie de conformité était commune à toutes les plateformes prises en charge.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Étapes suivantes

[Bien démarrer avec les stratégies de conformité d’appareils](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->

