---
title: Gestion des appareils mobiles avec Exchange ActiveSync | Microsoft Intune
description: "Gérez directement les appareils mobiles non inscrits que les utilisateurs n'ont pas inscrits auprès d’EAS (Exchange ActiveSync) à l'aide du connecteur Exchange"
keywords: 
author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: f545c7db4c29690a72c5a84dfcab6f179cbe72a2


---

# Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et de Microsoft Intune
Pour que Microsoft Intune gère directement des appareils mobiles, les utilisateurs doivent inscrire les appareils auprès d’Intune. Pour les appareils mobiles que les utilisateurs n'ont pas inscrits, vous pouvez activer la gestion EAS (Exchange ActiveSync) à l'aide du connecteur Exchange. Les appareils peuvent être gérés sur des serveurs Exchange locaux ou avec Exchange hébergé dans le cloud sur Microsoft Office 365.

## Règles d'accès Exchange pour les appareils mobiles ##

Exchange a besoin d’un ensemble de règles définissant ce qui se passe lorsque des appareils mobiles tentent de se connecter à EAS. Ces règles sont gérées dans la console d’administration Intune.

[Règles d'accès Exchange pour les appareils mobiles](exchange-access-rules-for-mobile-devices.md)

## Installation du connecteur Exchange
Le connecteur Exchange vous permet de gérer votre déploiement Exchange dans la console Intune. Vous devez tout d’abord installer et configurer le connecteur Intune - Exchange approprié. Choisissez l’option appropriée en fonction de la configuration de votre serveur Exchange (en local ou hébergé en tant que service dans le cloud) :

-   [Installation du connecteur Exchange local dans un environnement Exchange local](intune-on-premises-exchange-connector.md)
-   [Configuration du connecteur de service à service Microsoft Intune pour Exchange hébergé](intune-service-to-service-exchange-connector.md)

## Mise en œuvre d’une stratégie pour des appareils mobiles gérés par Exchange
Vous pouvez appliquer des paramètres de stratégie par le biais de la console Intune. Consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md). Pour obtenir une liste des paramètres de stratégie et des fonctionnalités Exchange ActiveSync prises en charge par des appareils mobiles spécifiques, consultez [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270) (Tableau de comparaison du client Exchange ActiveSync).

> [!NOTE]
> Lors de la connexion d’Intune à un environnement Microsoft Exchange, la stratégie EAS pour tous les utilisateurs gérés par Intune est réinitialisée sur la stratégie par défaut du serveur Microsoft Exchange, sauf si une stratégie plus spécifique a été définie dans Intune.

## Effacement de données d’entreprise d’appareils mobiles
Enfin, vous pouvez [effacer des données d’entreprise d’appareils mobiles gérés par EAS](wipe-for-exchange-managed-mobile-devices.md) lorsqu’ils ne sont plus en cours d’utilisation, ou si les appareils sont perdus ou volés.



<!--HONumber=Jul16_HO4-->


