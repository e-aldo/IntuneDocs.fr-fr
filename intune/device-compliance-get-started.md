---
title: "Stratégies de conformité des appareils Intune"
titleSuffix: Intune on Azure
description: "Utilisez cette rubrique pour en savoir plus sur la conformité dans Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9723e5a8b001068e8b7c9994723e6c7111e7a80d
ms.sourcegitcommit: abd8f9f62751e098f3f16b5b7de7eb006b7510e4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/20/2017
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Bien démarrer avec les stratégies de conformité des appareils Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Quelle est la conformité des appareils dans Intune ?

Les stratégies de conformité des appareils Intune définissent les règles et les paramètres auxquels doit se conformer un appareil pour qu’il soit considéré comme conforme par Intune.

Ces règles sont les suivantes :

- Utiliser un mot de passe pour accéder aux appareils

- Chiffrement

- Si l’appareil est jailbroken ou rooté

- Version minimale du système d’exploitation requise

- Version maximale autorisée du système d’exploitation

- Exiger que l’appareil soit au niveau ou sous le niveau de défense contre les menaces mobiles

Vous pouvez également utiliser des stratégies de conformité des appareils pour surveiller l’état de conformité dans vos appareils.

### <a name="device-compliance-requirements"></a>Exigences de conformité des appareils

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

##  <a name="pre-requisites"></a>Conditions préalables

Vous devez souscrire aux abonnements suivants pour utiliser des stratégies de conformité des appareils avec Intune :

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Plateformes prises en charge :

-   Android

-   iOS

-   macOS (préversion)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Les appareils doivent être inscrits dans Intune pour signaler leur état de conformité.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Fonctionnement des stratégies de conformité des appareils Intune avec Azure AD

Quand un appareil est inscrit dans Intune, le processus d’inscription Azure AD ajoute des informations aux attributs de l’appareil dans Azure AD. Parmi les informations clés de l’appareil figure son état de conformité, qui est utilisé par les stratégies d’accès conditionnel pour bloquer ou autoriser l’accès à la messagerie et à d’autres ressources d’entreprise.

- Découvrez plus en détail le [processus d’inscription Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Utilisations des stratégies de conformité des appareils

### <a name="with-conditional-access"></a>Avec accès conditionnel
Vous pouvez utiliser une stratégie de conformité avec accès conditionnel pour permettre uniquement aux appareils conformes à une ou plusieurs règles de conformité des appareils d’accéder aux e-mails et à d’autres ressources de l’entreprise.

### <a name="without-conditional-access"></a>Sans accès conditionnel
Vous pouvez également utiliser des stratégies de conformité d’appareils indépendamment de l’accès conditionnel. Quand vous utilisez des stratégies de conformité indépendamment, les appareils ciblés sont évalués et signalés avec leur état de conformité. Par exemple, vous pouvez obtenir un rapport sur le nombre d’appareils qui ne sont pas chiffrés, ou les appareils qui sont jailbreakés ou rootés. Mais quand vous utilisez des stratégies de conformité indépendamment, aucune restriction d’accès aux ressources de l’entreprise n’est appliquée.

Vous déployez les stratégies de conformité sur les utilisateurs. Quand une stratégie de conformité est déployée sur un utilisateur, la conformité de ses appareils est vérifiée. Si vous voulez en savoir plus sur le temps nécessaire pour que les appareils mobiles reçoivent une stratégie une fois celle-ci déployée, consultez Gérer des paramètres et des fonctionnalités sur vos appareils.

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Utilisation des stratégies de conformité des appareils dans le portail classique Intune et dans le Portail Azure

Passez en revue les principales différences pour faciliter la transition vers le nouveau flux de travail de la stratégie de conformité des appareils dans le portail Azure.

- Dans le portail Azure, les stratégies de conformité sont créées séparément pour chaque plateforme prise en charge.
- Dans le portail classique Intune, une stratégie de conformité des appareils était commune à toutes les plateformes prises en charge.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Migrer les stratégies de conformité des appareils du portail classique Intune vers le portail Azure

Les stratégies de conformité des appareils créées dans le [portail classique Intune](https://manage.microsoft.com) n’apparaissent pas dans le nouveau [portail Intune Azure](https://portal.azure.com). Toutefois, elles continuent de cibler des utilisateurs et peuvent être gérées par le biais du portail classique Intune.

Si vous souhaitez tirer parti des nouvelles fonctionnalités liées à la conformité des appareils dans le portail Azure, vous devez créer des stratégies de conformité des appareils dans le portail Azure lui-même. Si, dans le portail Azure, vous affectez une nouvelle stratégie de conformité des appareils à un utilisateur déjà associé à une stratégie de ce type dans le portail Intune classique, les stratégies du portail Intune Azure sont prioritaires par rapport à celles qui sont créées à partir du portail classique Intune.

##  <a name="next-steps"></a>Étapes suivantes

Créez une stratégie de conformité des appareils pour les plateformes suivantes :

- [Android](compliance-policy-create-android.md)
- [Android for Work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [MacOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
