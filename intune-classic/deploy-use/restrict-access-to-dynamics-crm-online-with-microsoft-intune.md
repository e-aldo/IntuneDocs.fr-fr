---
title: "Protéger l’accès à Dynamics CRM Online | Microsoft Docs"
description: "Utilisez l’accès conditionnel pour protéger et contrôler l’accès à Dynamics CRM Online."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6740e6f5894f6dfd7788d90cc8f445e0a63821a9
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="protect-access-to-dynamics-crm-online-with-intune"></a>Protéger l’accès à Dynamics CRM Online avec Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez contrôler l’accès à Microsoft Dynamics CRM Online à partir des appareils iOS et Android avec l’accès conditionnel Microsoft Intune.  L’accès conditionnel Intune comprend deux composants :
* Une [stratégie de conformité des appareils](introduction-to-device-compliance-policies-in-microsoft-intune.md) que l’appareil doit respecter pour être considéré comme conforme.
* Une [stratégie d’accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) dans laquelle vous spécifiez les conditions que l’appareil doit remplir pour accéder au service.

Pour en savoir plus sur le fonctionnement de l’accès conditionnel, lisez l’article [Protéger l’accès à la messagerie, à Office 365 et à d’autres services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

> [!IMPORTANT]
> Pour déployer l’accès conditionnel, vous devez avoir des abonnements à Intune et Azure Active Directory Premium, et les utilisateurs doivent avoir une licence pour chacun des deux produits. L’**abonnement Enterprise Mobility + Security (EMS)** comprend un abonnement à Intune et un abonnement à Azure Active Directory Premium. Pour plus d’informations, consultez la [page de tarification d’Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing). Si vous n’avez pas d’abonnement EMS, vous pouvez obtenir un abonnement à Azure Active Directory Premium. Consultez la [page de tarification d’Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

Quand un utilisateur ciblé tente d’utiliser l’application Dynamics CRM sur son appareil, l’évaluation suivante se produit :

![Diagramme qui montre les points de décision utilisés pour déterminer si un appareil est autorisé ou non à accéder à un service](../media/mdm-ca-dynamics-crm-flow-diagram.png)

Pour accéder à Dynamics CRM Online, l’appareil doit être :
* Un appareil **Android** ou **iOS**.
* **Inscrit** auprès d’Intune.
* **Conforme** à toutes les stratégies de conformité Intune déployées.

L’état de l’appareil est stocké dans Azure Active Directory, qui autorise ou bloque l’accès en fonction des conditions que vous spécifiez.

Si une condition n’est pas remplie, l’utilisateur reçoit l’un des messages suivants quand il tente de se connecter :
* Si l’appareil n’est pas inscrit auprès d’Intune ou dans Azure Active Directory, l’utilisateur reçoit un message contenant des instructions pour installer l’application Portail d’entreprise et inscrire l’appareil.
* Si l’appareil n’est pas conforme, l’utilisateur reçoit un message le dirigeant vers le site web ou l’application Portail d’entreprise Microsoft Intune, où il peut trouver des informations sur le problème et des solutions pour y remédier.

## <a name="configure-conditional-access-for-dynamics-crm-online"></a>Configurer l’accès conditionnel à Dynamics CRM Online  
### <a name="step-1-configure-active-directory-security-groups"></a>Étape 1 : configurer les groupes de sécurité Active Directory

Avant de commencer, configurez les groupes de sécurité Azure Active Directory pour la stratégie d'accès conditionnel. Vous pouvez configurer ces groupes dans le **Centre d’administration Office 365**. Vous utilisez ces groupes pour cibler les utilisateurs avec la stratégie ou les exempter de la stratégie. Quand un utilisateur est ciblé par une stratégie, chaque appareil qu'il utilise doit être conforme à cette stratégie pour qu'il puisse accéder aux ressources.

Vous pouvez spécifier deux types de groupes que la stratégie Dynamics CRM pourra utiliser :
* **Groupes ciblés**. Contient des groupes d’utilisateurs auxquels la stratégie s’applique.
* **Groupes exemptés**. Contient des groupes d’utilisateurs exempts de la stratégie.

Si un utilisateur se trouve dans les deux groupes, il est exempt de la stratégie.

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a>Étape 2 : configurer et déployer une stratégie de conformité
[Créez](create-a-device-compliance-policy-in-microsoft-intune.md) une stratégie de conformité et [déployez](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)-la sur tous les appareils qui seront affectés par la stratégie. Il s’agit de tous les appareils utilisés par les utilisateurs des groupes ciblés.

> [!NOTE]
> Tandis que les stratégies de conformité sont déployées sur les groupes Intune, les stratégies d’accès conditionnel sont destinées aux groupes de sécurité Azure Active Directory.

> [!IMPORTANT]
> Si vous n’avez pas déployé de stratégie de conformité, les appareils seront traités comme étant conformes.

Quand vous êtes prêt, passez à l’Étape 3.
### <a name="step-3-configure-the-dynamics-crm-policy"></a>Étape 3 : Configurer la stratégie Dynamics CRM
Ensuite, configurez la stratégie de manière à restreindre l’accès à Dynamics CRM aux appareils gérés et conformes. Cette stratégie sera stockée dans Azure Active Directory.

1.  Dans la console d’administration Intune, choisissez **Stratégie > Accès conditionnel > Stratégie Dynamics CRM Online**.

  ![Capture d’écran de la page de stratégie d’accès conditionnel Dynamics CRM Online](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  Choisissez **Activer la stratégie d’accès conditionnel**.
3.  Sous **Accès aux applications**, vous pouvez choisir d’appliquer la stratégie d’accès conditionnel à :
  * **iOS**
  * **Android**
4.  Sous **Groupes ciblés**, choisissez **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory auxquels la stratégie sera appliquée. Vous pouvez cibler cette stratégie sur tous les utilisateurs ou seulement sur un groupe d’utilisateurs donné.
5.    Sous **Groupes exemptés**, vous pouvez éventuellement choisir **Modifier** pour sélectionner les groupes de sécurité Azure Active Directory exempts de cette stratégie.
6.    Une fois terminé, choisissez **Enregistrer**.

Vous avez maintenant configuré l’accès conditionnel à Dynamics CRM. La stratégie d’accès conditionnel prend effet immédiatement. Il est donc inutile de la déployer.
##  <a name="monitor-the-compliance-and-conditional-access-policies"></a>analyser la conformité et les stratégies d'accès conditionnel

Dans l'espace de travail **Groupes** , vous pouvez afficher l'état de l'accès conditionnel de vos appareils.

Choisissez un groupe d’appareils mobiles puis, sous l’onglet **Appareils**, l’un des **Filtres**suivants :
* **Appareils non enregistrés avec AAD**. Ces appareils ne peuvent pas accéder à Dynamics CRM.
* **Appareils non conformes**. Ces appareils ne peuvent pas accéder à Dynamics CRM.
* **Appareils enregistrés avec AAD et conformes**. Ces appareils peuvent accéder à Dynamics CRM.

##  <a name="next-steps"></a>Étapes suivantes
* [Protéger l’accès à Exchange Online](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [Protéger l’accès à Exchange sur site](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [Protéger l’accès à SharePoint Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [Protéger l’accès à Skype Entreprise Online](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)

