---
title: Inscrire des appareils | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
ms.sourcegitcommit: 928b79530ac278f78356f8d1ef9f267077634b5b
ms.openlocfilehash: e68e93fbf8bccceaf95e183a33049fdb35a9aae5


---

# Inscrire des appareils pour la gestion dans Intune
La gestion des appareils mobiles Microsoft Intune utilise l’inscription pour gérer les appareils et leur autoriser l’accès aux ressources. La façon dont vous inscrivez les appareils dépend du type d’appareil, de son propriétaire et du niveau de gestion souhaité. Les scénarios « Apportez votre propre appareil » (BYOD) et les scénarios d’appareils d’entreprise (COD) nécessitent un processus d’inscription. Les organisations qui utilisent Exchange ActiveSync (soit localement, soit hébergé dans le cloud) peuvent activer une gestion allégée sans conditions d’inscription. Vous pouvez également gérer des PC Windows à l’aide du logiciel client Intune.

###  Plateformes d’appareil prises en charge

Intune peut gérer les plateformes d’appareils suivantes :

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Activer l’inscription d’appareil  
 L’inscription permet aux utilisateurs d’accéder aux ressources de l’entreprise sur leurs appareils personnels et permet à l’administrateur de garantir que ces appareils sont conformes aux stratégies de protection des ressources d’entreprise. C’est le meilleur moyen d’activer des scénarios « Apportez votre propre appareil » avec Intune. L’administrateur doit activer l’inscription dans la console Intune, ce qui peut nécessiter la création d’une relation d’approbation avec l’appareil et l’attribution de licences aux utilisateurs. L’appareil est ensuite inscrit, généralement par les utilisateurs qui entrent leurs informations d’identification professionnelles ou scolaires. Ensuite, l’appareil reçoit une stratégie Intune et obtient l’accès aux ressources.

[Se préparer à inscrire des appareils dans Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Inscrire des appareils d’entreprise
Vous pouvez gérer les appareils d’entreprise (COD, Corporate-Owned Devices) avec la console Intune. Vous pouvez inscrire les appareils iOS directement par le biais d’outils fournis par Apple. Tous les types d’appareils peuvent être inscrits par un administrateur ou un gestionnaire à l’aide du Gestionnaire d’inscription d’appareil. Les appareils dotés d’un numéro IMEI peuvent également être identifiés et référencés comme appartenant à l’entreprise pour activer des scénarios COD.

[Inscrire des appareils d’entreprise](manage-corporate-owned-devices.md)

## Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud.



[Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Gérer des PC Windows avec Intune  
Vous pouvez également utiliser Microsoft Intune pour gérer des PC Windows à l’aide du logiciel client Intune pour PC Windows. Les PC gérés avec le client Intune peuvent :

 - Fournir un inventaire logiciel et matériel
 - Installer des applications de bureau (par exemple des fichiers .exe et .msi)
 - Paramètres du pare-feu

Les ordinateurs gérés avec le logiciel client Intune ne peuvent pas être réinitialisés ou mis hors service de manière sélective, et ne peuvent pas tirer parti de nombreuses fonctionnalités de gestion Intune telles que l’accès conditionnel, les paramètres VPN et Wi-Fi, ou le déploiement de certificats et de configurations de messagerie électronique.

[Gérer des PC Windows avec Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Jun16_HO2-->


