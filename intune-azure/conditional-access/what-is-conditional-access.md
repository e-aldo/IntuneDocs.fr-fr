---
title: "Qu’est-ce que l’accès conditionnel ? | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : apprenez à définir les conditions que les utilisateurs et appareils doivent respecter pour accéder aux ressources d’entreprise dans la version préliminaire de Microsoft Intune Azure."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 41931f64db969c82f79e007c4be9e68b7caf4ce9
ms.openlocfilehash: 20696fb2dc0126aa224e779738cedb4f95f666e8


---

# <a name="what-is-conditional-access"></a>Qu’est-ce que l’accès conditionnel ?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Dans cette rubrique, nous décrivons l’accès conditionnel tel qu’il s’applique à Enterprise Mobility + Security, ainsi que les fonctionnalités d’accès conditionnel dans Intune.

L’accès conditionnel d’Enterprise Mobility + Security (EMS) exploite la puissance d’Azure Active Directory Premium et Microsoft Intune pour vous fournir le contrôle dont vous avez besoin pour protéger vos données d’entreprise, tout en offrant à vos utilisateurs une expérience qui leur permettra d’effectuer leurs tâches efficacement à partir de n’importe quel appareil.

Avec un accès conditionnel, vous pouvez définir des conditions qui limitent l’accès à vos données d’entreprise en fonction de l’emplacement, l’état de l'appareil et de l’utilisateur, et la sensibilité de l’application.

Du point de vue de l’appareil, Intune et Azure Active Directory fonctionnent ensemble pour s’assurer que seuls les appareils gérés et compatibles sont autorisés à accéder à la messagerie et aux services Office 365. Par exemple, vous pouvez définir une stratégie dans Azure Active Directory pour autoriser uniquement les ordinateurs qui sont joints au domaine, ou les appareils mobiles qui sont inscrits dans une application de gestion d'appareils mobiles comme Intune, à pouvoir accéder aux services Office 365. Vous pouvez utiliser Intune pour définir un profil de conformité d'appareil qui évalue l’état de conformité de l’appareil. L’état de conformité est signalé à Azure Active Directory, qui l’utilise pour l’application de la stratégie lorsque l’utilisateur tente d’accéder aux ressources de votre entreprise. Pour en savoir plus sur la conformité des appareils dans Intune, consultez [Qu’est-ce que la compatibilité des appareils ?](/intune-azure/set-device-compliance/what-is-device-compliance)

L’accès conditionnel pour les applications de cloud telles qu’Exchange Online peut être configuré via Azure Active Directory. Pour plus d'informations, consultez cet [article](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal).

## <a name="on-premises-conditional-access-in-intune"></a>Accès conditionnel local dans Intune

L’accès conditionnel dans Intune peut servir à autoriser ou bloquer l’accès à **Exchange en local** en fonction de la gestion et de l’inscription des appareils.

Les paramètres de profil de conformité d’appareil sont utilisés pour évaluer la conformité de l’appareil. L’accès conditionnel utilise une formule d’évaluation pour autoriser ou bloquer l’accès à Exchange en local. Quand vous utilisez un accès conditionnel avec un profil de conformité d'appareil, seuls les appareils conformes peuvent accéder à Exchange en local. Vous pouvez configurer des paramètres avancés dans l’accès conditionnel pour un contrôle plus granulaire, par exemple : autoriser ou bloquer certaines plateformes ou bloquer immédiatement les appareils qui ne sont pas gérés par Intune.

Le profil de conformité d'appareil et l’accès conditionnel sont affectés à l’utilisateur. La conformité de chaque appareil que l’utilisateur utilise pour accéder à Exchange en local est contrôlée. N’oubliez pas que l’utilisateur de l’appareil doit déployer un profil de conformité sur l’appareil afin que sa conformité soit évaluée. Si aucune stratégie de conformité n’est déployée sur l’utilisateur, l’appareil est considéré comme conforme et aucune restriction d’accès ne s’applique.

Quand un appareil ne remplit pas les conditions définies, l'utilisateur final est guidé tout au long du processus d'inscription de cet appareil et du processus de résolution du problème qui empêche l'appareil d'être conforme.

## <a name="next-steps"></a>Étapes suivantes

[Guide de création d’une stratégie d’accès conditionnel à Exchange sur site](create-conditional-access-policy-for-exchange-on-premises.md)

[Guide pratique de configuration de l’accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-conditional-access-azure-portal)



<!--HONumber=Feb17_HO1-->


