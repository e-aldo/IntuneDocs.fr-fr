---
title: "Scénarios de protection de la messagerie | Microsoft Docs"
description: "Cette rubrique présente quelques exemples de scénarios en expliquant comment les implémenter avec un accès conditionnel."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7d0b9cee72e8810b4f39bd81bd8f49d0818618c4
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a>Protéger l’accès à la messagerie avec Microsoft Intune : exemples de scénarios

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a>Scénario 1 : Empêcher les utilisateurs d’accéder à Exchange Online avec des appareils non conformes
### <a name="scenario-requirements"></a>Exigences du scénario
- Tous les utilisateurs du groupe de sécurité Azure Active Directory **Comptabilité** voient leur accès à Exchange Online bloqué si leur appareil n’est pas conforme à une stratégie de conformité que vous avez déployée.
- S’il existe des utilisateurs dans ce groupe dont les appareils ne sont pas pris en charge par Intune, leur accès à Exchange Online doit être bloqué sur cet appareil.
- Les utilisateurs qui figurent dans le groupe de sécurité Azure Active Directory **Finance** doivent être exemptés de la stratégie, même s’ils figurent également dans le groupe de sécurité **Comptabilité**.

Pour ce faire, configurez une stratégie d’accès conditionnel à Exchange Online avec les paramètres suivants :

- Choisissez **Activer la stratégie d’accès conditionnel**.

- Choisissez les plateformes auxquelles vous souhaitez autoriser l’accès à partir d’applications avec l’authentification moderne.
- Pour les applications Exchange ActiveSync, choisissez **Bloquer les appareils non conformes sur les plateformes prises en charge par Microsoft Intune** et **Bloquer tous les autres appareils sur les plateformes non prises en charge par Microsoft Intune**.
-   Dans la section **Groupe ciblé**, sous **Groupes de sécurité sélectionnés**, choisissez le groupe d’utilisateurs **Comptabilité**.

-   Dans la section **Groupe exempté**, sous **Groupes de sécurité sélectionnés**, choisissez le groupe d’utilisateurs **Finance**.


Le flux suivant est utilisé dans le scénario pour déterminer quels sont les appareils qui peuvent accéder à Exchange Online :

![Flux d’accès des appareils](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a>Scénario 2 : Tous les appareils iOS qui accèdent à Exchange sur site doivent être gérés par Intune
### <a name="scenario-requirements"></a>Exigences du scénario
- Seuls les appareils qui exécutent iOS doivent pouvoir accéder à Exchange sur site.
- Les appareils doivent également être inscrits dans Intune et respecter les règles de stratégie de conformité pour pouvoir être utilisés pour accéder à Exchange.

Pour ce faire, configurez la stratégie d’accès conditionnel à Exchange sur site ci-dessous avec les paramètres suivants :

-   Choisissez l’option **Bloquer l’accès des applications de messagerie à Exchange sur site si l’appareil n’est pas conforme ou n’est pas inscrit dans Microsoft Intune**. En choisissant cette option, vous activez la stratégie d’accès conditionnel, ce qui implique que tous les appareils doivent être inscrits dans Microsoft Intune et respecter les règles de stratégie de conformité pour pouvoir accéder à Exchange.

-   Pour les paramètres avancés Exchange ActiveSync, créez :

  -   Une exception de plateforme qui permet aux appareils exécutant iOS d'accéder à Exchange   

  -   Une règle par défaut qui spécifie que, si un appareil n’est pas couvert par la règle d’exception de la plateforme, il ne doit pas pouvoir accéder à Exchange. Cette règle permet de s’assurer que les appareils qui n’exécutent pas iOS ne peuvent pas accéder à Exchange.

Vous utilisez le flux suivant pour déterminer quels sont les appareils qui peuvent accéder à Exchange :

![Flux d’accès des appareils](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a>Scénario 3 : Aucun appareil Android ne peut accéder à Exchange sur site
### <a name="scenario-requirements"></a>Exigences du scénario
- L’accès à Exchange doit être bloqué pour tous les appareils Android.
- Tous les autres appareils pris en charge peuvent accéder à Exchange du moment qu’ils sont gérés par Intune.

Pour ce faire, configurez une stratégie d’accès conditionnel à Exchange sur site avec les paramètres suivants :

-   Choisissez l’option **Bloquer l’accès des applications de messagerie à Exchange sur site si l’appareil n’est pas conforme ou n’est pas inscrit dans Microsoft Intune**. En choisissant cette option, vous spécifiez que tous les appareils doivent être inscrits dans Intune et respecter les règles de stratégie de conformité.

- Pour les paramètres avancés Exchange ActiveSync, créez :
  -   exception de plateforme qui empêche les appareils exécutant Android d'accéder à Exchange ; Cette règle permet de s’assurer que les appareils Android ne peuvent pas être utilisés pour accéder à Exchange.

  -   Règle par défaut qui spécifie que tout appareil non couvert par d’autres règles doit être autorisé à accéder à Exchange. Cette règle par défaut garantit que les appareils exécutant des plateformes autres qu’Android mais prises en charge par Microsoft Intune peuvent être utilisés pour accéder à Exchange. Ils doivent toutefois être inscrits dans Intune et respecter les règles de stratégie de conformité.

Vous utilisez le flux suivant pour déterminer quels sont les appareils qui peuvent accéder à Exchange :

![Flux d’accès des appareils](./media/ConditionalAccess8-4.png)

