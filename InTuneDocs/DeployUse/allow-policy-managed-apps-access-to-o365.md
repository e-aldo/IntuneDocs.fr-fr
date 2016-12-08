---
title: "Accès conditionnel à O365 en fonction de l’application | Microsoft Intune"
description: "Découvrez dans quelle mesure l’accès conditionnel pour la gestion des applications mobiles peut aider à contrôler les applications qui ont accès aux services O365."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5083cb49e7a98f19ff21c1972149b00aee4ec93e
ms.openlocfilehash: e57280821168ddb043d093485ec74f042bbebfef


---

# Autoriser uniquement les applications mobiles prenant en charge les stratégies GAM Intune à accéder aux services Office 365
Les [stratégies de gestion des applications mobiles Intune (GAM)](protect-apps-and-data-with-microsoft-intune.md) vous aident à protéger vos données d’entreprise sur les appareils qui sont inscrits pour la gestion dans Intune. Vous pouvez également utiliser des stratégies GAM sur les **appareils détenus par l’employé qui ne sont pas inscrits pour la gestion dans Intune**.  Dans ce cas, même si vous ne gérez pas l’appareil, vous devez toujours vous assurer que vos données et ressources d’entreprise sont protégées. À l’aide de l’accès conditionnel pour la gestion des applications mobiles, vous pouvez créer une stratégie qui autorise uniquement les applications mobiles prenant en charge les stratégies GAM Intune à accéder aux services O365 tels qu’Exchange Online.

Par exemple, en autorisant uniquement l’**application Microsoft Outlook** à accéder à Exchange Online, vous pouvez **bloquer les applications de messagerie intégrée sur iOS et Android**, qui ne bénéficient pas de la protection des données des stratégies GAM Intune pour récupérer des e-mails sur **Exchange Online**.

Le diagramme ci-dessous illustre le flux utilisé par les stratégies d’accès conditionnel pour la gestion des applications mobiles pour déterminer quand autoriser ou bloquer l’accès : ![Diagramme qui montre les différents critères inclus pour déterminer s’il faut autoriser ou bloquer l’accès](../media/mam-ca-decision-flow_simple.png).

Description des abréviations utilisées dans les diagrammes :
* **CP** : application Portail d’entreprise
* **AA** : application Azure Authenticator
* **AAD** : Azure Active Directory
* **EAS** : Exchange Active Sync

## Conditions préalables
**Avant** de pouvoir configurer une stratégie d’accès conditionnel pour la gestion des applications mobiles, vous devez avoir **un abonnement Enterprise Mobility + Security ou Azure Active Directory Premium**, et les utilisateurs doivent disposer d’une licence EMS ou Azure AD. Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/en-us/cloud-platform/enterprise-mobility-pricing) ou la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/en-us/pricing/details/active-directory/).


## Applications prises en charge
**Exchange Online** : **Microsoft Outlook** pour Android et iOS.

Pour en savoir plus sur l’expérience utilisateur avec une application qui a des stratégies d’accès conditionnel pour la gestion des applications mobiles, consultez [Ce qui se passe quand une application est utilisée dans le cadre de l’accès conditionnel pour la gestion des applications mobiles](use-apps-with-mam-ca.md).


## Étapes suivantes
[Créer une stratégie Exchange Online pour les applications GAM](mam-ca-for-exchange-online.md)

[Bloquer les applications dépourvues de l’authentification moderne](block-apps-with-no-modern-authentication.md)

### Voir aussi

[Protéger les données d’application avec des stratégies GAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO4-->


