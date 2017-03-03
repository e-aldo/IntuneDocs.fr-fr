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
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b245dac28f88e7eab70dfa9d759b15e155f8a7df


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>Quelle est la conformité des appareils dans la version préliminaire d'Intune Azure ?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Pour protéger les données de l’entreprise, vous devez vérifier que les appareils utilisés pour accéder aux données et applications d’entreprise respectent certaines règles. Ces règles peuvent inclure l’utilisation d’un code confidentiel pour accéder aux appareils et le chiffrement des données stockées sur les appareils. Un ensemble de règles de ce type est appelé une **stratégie de conformité**.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Comment dois-je utiliser les stratégies de conformité d’un appareil ?
Vous pouvez utiliser une stratégie de conformité avec accès conditionnel pour permettre uniquement à des appareils qui sont conformes aux règles de stratégie de conformité d’accéder à des e-mails et à d’autres services.

Vous pouvez également utiliser des stratégies de conformité indépendamment de l’accès conditionnel.
Quand vous utilisez des stratégies de conformité indépendamment, les appareils ciblés sont évalués et signalés avec leur état de conformité. Par exemple, vous pouvez obtenir un rapport sur le nombre d’appareils qui ne sont pas chiffrés, ou les appareils qui sont jailbreakés ou rootés. Mais quand vous utilisez des stratégies de conformité indépendamment, aucune restriction d’accès aux ressources de l’entreprise n’est appliquée.

Vous déployez les stratégies de conformité sur les utilisateurs. Quand une stratégie de conformité est déployée sur un utilisateur, la conformité de ses appareils est vérifiée. Si vous voulez en savoir plus sur le temps nécessaire pour que les appareils mobiles reçoivent une stratégie une fois celle-ci déployée, consultez Gérer des paramètres et des fonctionnalités sur vos appareils.

##  <a name="concepts"></a>Concepts
Voici quelques termes et les concepts qui sont utiles pour comprendre comment utiliser les stratégies de conformité.

### <a name="compliance-requirements"></a>Exigences de conformité
Les exigences de conformité sont, pour simplifier, des règles comme l’exigence d’un code PIN ou d’un chiffrement que vous pouvez spécifier comme requises ou non requises pour une stratégie de conformité.

<!---### Actions for noncompliance

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

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Différences entre la console d’administration Intune classique et Intune dans le portail Azure


Si vous utilisiez la console d’administration Intune classique précédemment, notez les différences suivantes pour vous aider à effectuer la transition vers le nouveau processus de conformité d’appareil dans le portail Azure :


-   Dans le portail Azure, les stratégies de conformité sont créées séparément pour chaque plateforme prise en charge. Dans la console d’administration d’Intune, une stratégie de conformité était commune à toutes les plateformes prises en charge.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Étapes suivantes

[Prise en main des stratégies de conformité](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO3-->


