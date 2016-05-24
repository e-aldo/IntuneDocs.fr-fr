---
# required metadata

title: Vue d’ensemble du cycle de vie des applications | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vue d’ensemble du cycle de vie des applications

Le cycle de vie des applications Intune commence lorsqu’une application est ajoutée et évolue en différentes phases jusqu’à sa suppression.

![Le cycle de vie des applications](./media/applifecycle_nobg.png "the Intune app lifecycle")

## Ajouter

La première étape du déploiement d’applications consiste à ajouter celles que vous souhaitez gérer et déployer dans Intune. Il existe certes différents types d’applications avec lesquels vous pouvez travailler, mais les procédures de base sont les mêmes. Avec Intune, vous pouvez ajouter des applications pour des [appareils inscrits](add-apps-for-mobile-devices-in-microsoft-intune.md) et des [PC Windows que vous gérez avec le logiciel client Intune](add-apps-for-windows-pcs-in-microsoft-intune.md)..

## Déployer

Une fois que vous avez ajouté l’application à Intune, vous pouvez ensuite [la déployer sur les appareils que vous gérez](deploy-apps.md). Intune facilite ce processus, et, une fois que l’application est déployée, vous pouvez [surveiller le succès](monitor-apps-in-microsoft-intune.md) du déploiement depuis la console d’administration Intune. Certains magasins d’applications, tels que l’[Apple App Store](manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune.md) et le [Windows Store](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md), vous permettent également d’acheter des licences d’application en bloc pour votre société. Intune peut synchroniser des données grâce à ces magasins pour vous permettre de déployer des licences et d’effectuer leur suivi pour ces types d’applications directement à partir de la console d’administration Intune.

## La configuration de

Dans le cadre du cycle de vie des applications, des nouvelles versions des applications sont publiées régulièrement. Intune propose des outils permettant de facilement [mettre à jour des applications](update-apps-using-microsoft-intune.md) que vous avez déployées à une version plus récente. En outre, certaines applications vous permettent de configurer des fonctionnalités supplémentaires, comme par exemple :
- [des stratégies de configuration des applications iOS](configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune.md), qui vous permettent de définir des paramètres pour des applications compatibles iOS utilisées lorsque l’application est exécutée. Par exemple, une application peut nécessiter des paramètres de marque spécifiques ou le nom d’un serveur auquel se connecter.
- [des stratégies de navigateur gérées](manage-internet-access-using-managed-browser-policies.md), qui vous permettent de configurer les paramètres du navigateur Intune géré qui remplace le navigateur de l’appareil par défaut et vous permet de limiter les sites Web auxquels vos utilisateurs peuvent accéder.

## Protection

Intune propose différentes manières de protéger les données dans vos applications. Les principales méthodes sont :
- [l’accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), qui permet de contrôler l’accès à la messagerie et à d’autres services en fonction de conditions que vous spécifiez (comme des types d’appareil ou la conformité à une [stratégie de conformité des appareils](introduction-to-device-compliance-policies-in-microsoft-intune.md) que vous avez déployée).
- [la gestion des applications mobiles (MAM)](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md), qui fonctionne avec différentes applications pour protéger les données d’entreprise que ces dernières utilisent. Par exemple, vous pouvez limiter la copie de données entre des applications non gérées et des applications que vous gérez, ou vous pouvez empêcher les applications de s’exécuter sur des appareils jailbroken ou rootés.

## Mettre hors service

Enfin, il est probable que des applications que vous avez déployées deviennent obsolètes et doivent être supprimées. Intune facilite [la mise hors service d’applications](retire-apps-using-microsoft-intune.md)..


<!--HONumber=May16_HO1-->


