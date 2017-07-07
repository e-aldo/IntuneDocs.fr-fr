---
title: "Vue d’ensemble du cycle de vie des applications"
description: "Obtenir des informations sur le cycle de vie des applications Intune gérées, depuis leur ajout jusqu’à leur retrait éventuel."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf505bec8a07923db78a870e4d7bfd64660e681c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Vue d’ensemble du cycle de vie des applications

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Le cycle de vie des applications Intune commence lorsqu’une application est ajoutée et évolue en différentes phases jusqu’à sa suppression.

![Le cycle de vie des applications](./media/app-lifecycle.png "le cycle de vie des applications Intune")

## <a name="add"></a>Ajouter

La première étape du déploiement d’applications consiste à ajouter celles que vous voulez gérer et affecter dans Intune. Il existe certes différents types d’applications avec lesquels vous pouvez travailler, mais les procédures de base sont les mêmes. Avec Intune, vous pouvez ajouter des applications pour des [appareils inscrits](apps-add.md) ([portail classique](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) et des [PC Windows que vous gérez avec le logiciel client Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Déploiement

Une fois que vous avez ajouté l’application à Intune, vous pouvez ensuite [l’affecter aux utilisateurs et appareils que vous gérez](apps-deploy.md) ([portail classique](/intune-classic/deploy-use/deploy-apps)). Intune facilite ce processus, et, une fois que l’application est déployée, vous pouvez [surveiller la réussite](apps-monitor.md) ([portail classique](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)) du déploiement depuis la console d’administration Intune. Certains magasins d’applications, tels que [l’Apple App Store](vpp-apps-ios.md) ([portail classique](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) et le [Windows Store](windows-store-for-business.md) ([portail classique](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), vous permettent également d’acheter des licences d’application en bloc pour votre société. Intune peut synchroniser des données grâce à ces magasins pour vous permettre de déployer des licences et d’effectuer leur suivi pour ces types d’applications directement à partir de la console d’administration Intune.

## <a name="configure"></a>Configurer

Dans le cadre du cycle de vie des applications, des nouvelles versions des applications sont publiées régulièrement. Intune propose des outils permettant de facilement [mettre à jour les applications](apps-add.md) ([portail classique](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) que vous avez déployées vers une version plus récente. En outre, vous pouvez configurer des fonctionnalités supplémentaires pour certaines applications, comme par exemple :
- [des stratégies de configuration des applications iOS](app-configuration-policies-use-ios.md) ([portail classique](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)), permettant de définir des paramètres pour des applications compatibles iOS utilisées lorsque l’application est exécutée. Par exemple, une application peut nécessiter des paramètres de marque spécifiques ou le nom d’un serveur auquel se connecter.
- Les [Stratégies Managed Browser](app-configuration-managed-browser.md) ([portail classique](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)), permettant de configurer les paramètres du navigateur Intune géré qui remplace le navigateur de l’appareil par défaut et vous permet de limiter les sites web auxquels vos utilisateurs peuvent accéder.

## <a name="protect"></a>Protection

Intune propose différentes manières de protéger les données dans vos applications. Les principales méthodes sont :
- [L’accès conditionnel](conditional-access.md) ([portail classique](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) qui contrôle l’accès à la messagerie et aux autres services en fonction des conditions que vous spécifiez. Les conditions incluent les types d’appareils ou la conformité à l’une des [stratégies de conformité des appareils](device-compliance.md) ([portail classique](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)) que vous avez déployées.
- [Les stratégies de protection des applications](app-protection-policy.md) ([portail classique](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) fonctionnent avec différentes applications pour protéger les données d’entreprise que ces dernières utilisent. Par exemple, vous pouvez limiter la copie de données entre des applications non gérées et des applications que vous gérez, ou vous pouvez empêcher les applications de s’exécuter sur des appareils jailbroken ou rootés.

## <a name="retire"></a>Mettre hors service

Enfin, il est probable que des applications que vous avez déployées deviennent obsolètes et doivent être supprimées. Intune facilite [la mise hors service d’applications](device-management.md) ([portail classique](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
