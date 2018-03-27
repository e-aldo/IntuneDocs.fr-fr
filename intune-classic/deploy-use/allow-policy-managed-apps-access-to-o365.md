---
title: Accès conditionnel à O365 en fonction de l’application
description: Découvrez dans quelle mesure l’accès conditionnel pour la gestion des applications mobiles peut aider à contrôler les applications qui ont accès aux services O365.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 12/05/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b0b0fbfce086729551b211dd4bc4b83348aa4787
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a>Autoriser uniquement les applications mobiles prenant en charge les stratégies de protection des applications Intune à accéder aux services Office 365

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les [stratégies de protection des applications Intune](protect-apps-and-data-with-microsoft-intune.md) vous aident à protéger vos données d’entreprise sur les appareils qui sont inscrits pour la gestion dans Intune. Vous pouvez également utiliser des stratégies de protection des applications sur les **appareils détenus par l’employé qui ne sont pas inscrits pour la gestion dans Intune**.  Dans ce cas, même si vous ne gérez pas l’appareil, vous devez toujours vous assurer que vos données et ressources d’entreprise sont protégées. En utilisant l’accès conditionnel en fonction des applications avec la gestion des applications mobiles, vous pouvez créer une stratégie qui autorise uniquement les applications mobiles prenant en charge les stratégies Intune App Protection à accéder aux services O365 tels qu’Exchange Online.

Par exemple, en autorisant uniquement l’**application Microsoft Outlook** à accéder à Exchange Online, vous pouvez **bloquer les applications de messagerie intégrée sur iOS et Android**, qui ne bénéficient pas de la protection des données des stratégies GAM Intune pour récupérer des e-mails sur **Exchange Online**. Vous pouvez aussi empêcher les applications mobiles qui ne prennent pas en charge la gestion des application mobiles Intune d’accéder à **SharePoint Online**.

Le diagramme ci-dessous illustre le flux utilisé par les stratégies d’accès conditionnel en fonction des applications pour déterminer quand autoriser ou bloquer l’accès : ![Diagramme qui montre les différents critères inclus pour déterminer s’il faut autoriser ou bloquer l’accès](../media/mam-ca-decision-flow_simple.png).

Description des abréviations utilisées dans les diagrammes :
* **CP** : application Portail d’entreprise
* **AA** : application Azure Authenticator
* **AAD** : Azure Active Directory
* **EAS** : Exchange Active Sync

## <a name="prerequisites"></a>Prérequis
**Pour pouvoir** créer une stratégie d’accès conditionnel en fonction des applications, vous devez avoir un **abonnement Enterprise Mobility + Security ou Azure Active Directory Premium**, et les utilisateurs doivent disposer d’une licence EMS ou Azure AD. Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).


## <a name="supported-apps"></a>Applications prises en charge
**Exchange Online** :
* **Microsoft Outlook** pour Android et iOS.

**SharePoint Online**
* Microsoft Word pour iOS et Android
* Microsoft Excel pour iOS et Android
* Microsoft PowerPoint pour iOS et Android
* Microsoft OneDrive Entreprise pour iOS et Android
* Microsoft OneNote pour iOS

>[!IMPORTANT]
>Pour les appareils Android, l’inscription initiale de l’appareil doit être effectuée en vous connectant à l’application OneDrive ou à l’application Outlook. L’application OneNote pour Android ne prend pas en charge MAM sans inscription.

Pour en savoir plus sur l’expérience utilisateur avec une application qui applique des stratégies d’accès conditionnel en fonction des applications, consultez la page [Ce qui se passe quand une application est utilisée dans le cadre de l’accès conditionnel pour la gestion des applications mobiles](use-apps-with-mam-ca.md).


## <a name="next-steps"></a>Étapes suivantes
[Créer une stratégie Exchange Online pour les applications GAM](mam-ca-for-exchange-online.md)

[Créer une stratégie SharePoint Online pour les applications GAM](mam-ca-for-sharepoint-online.md)

[Bloquer les applications sans authentification moderne](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Voir aussi

[Protéger les données d’application à l’aide de stratégies de protection des applications](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
