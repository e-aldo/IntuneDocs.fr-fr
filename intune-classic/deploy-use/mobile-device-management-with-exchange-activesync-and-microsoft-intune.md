---
title: Gestion des appareils mobiles avec Exchange ActiveSync
description: "Gérer les appareils mobiles avec la gestion de Microsoft Exchange ActiveSync (EAS) à l’aide du connecteur Exchange"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 02d6220a4c780eafb7afb01208e18e7df7684b68
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a>Gestion des appareils mobiles Microsoft Exchange ActiveSync avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour que Microsoft Intune gère directement des appareils mobiles, ces appareils doivent être [inscrits dans Intune](prerequisites-for-enrollment.md). Les administrateurs ont également la possibilité d’activer une solution de gestion plus limitée qui utilise la gestion de Microsoft Exchange ActiveSync (EAS) avec un connecteur Exchange. Les appareils peuvent être gérés avec des serveurs Exchange locaux ou avec Exchange Online, à l’aide de Microsoft Office 365. Microsoft Intune prend en charge une seule connexion du connecteur Exchange par abonnement, quel que soit le type de connecteur.

## <a name="exchange-access-rules-for-mobile-devices"></a>Règles d'accès Exchange pour les appareils mobiles ##

Exchange a besoin d’un ensemble de règles définissant ce qui se passe lorsque des appareils mobiles tentent de se connecter à EAS. Ces règles sont gérées dans la console d’administration Intune.

[Règles d’accès Exchange pour les appareils mobiles](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a>Installation du connecteur Exchange
Le connecteur Exchange vous permet de gérer votre déploiement Exchange dans la console Intune. Vous devez tout d’abord installer et configurer le connecteur Intune - Exchange approprié. Choisissez l’option appropriée en fonction de la configuration de votre serveur Exchange (en local ou hébergé en tant que service dans le cloud) :

-   [Configuration de Microsoft Intune pour Exchange Online ou les nouveaux environnements Microsoft Exchange Online Dedicated](intune-service-to-service-exchange-connector.md)
-   [Installation du connecteur Microsoft Intune pour les serveurs Exchange locaux et les environnements Microsoft Exchange Online Dedicated](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a>Mise en œuvre d’une stratégie pour des appareils mobiles gérés par Exchange
La console Intune peut être utilisée pour gérer [les paramètres de stratégie EAS](exchange-activesync-policy-settings-in-microsoft-intune.md) et pour [restreindre l’accès aux ressources de l’entreprise](restrict-access-to-email-and-o365-services-with-microsoft-intune.md). Pour obtenir une liste des paramètres de stratégie et des fonctionnalités Exchange ActiveSync prises en charge par des appareils mobiles spécifiques, consultez [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270) (Tableau de comparaison du client Exchange ActiveSync).

> [!NOTE]
> Lors de la connexion d’Intune à un environnement Microsoft Exchange, la stratégie EAS pour tous les utilisateurs gérés par Intune est réinitialisée sur la stratégie par défaut du serveur Microsoft Exchange, sauf si une stratégie plus spécifique a été définie dans Intune.

## <a name="wipe-company-data-from-mobile-devices"></a>Effacement de données d’entreprise d’appareils mobiles
Enfin, vous pouvez [effacer des données d’entreprise d’appareils mobiles gérés par EAS](wipe-for-exchange-managed-mobile-devices.md) lorsqu’ils ne sont plus en cours d’utilisation, ou si les appareils sont perdus ou volés.
