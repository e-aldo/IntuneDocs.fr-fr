---
title: "Votre appareil Android semble être chiffré"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ba593c08-1a78-4013-8525-b45a948772ec
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 269ad7968242f8f5ce7095c9c73347987675e846
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="your-android-device-seems-to-be-encrypted-but-company-portal-says-otherwise"></a>Votre appareil Android semble être chiffré, mais le portail d’entreprise dit que non

Quand vous chiffrez un appareil, vous encodez les informations qu’il contient à l’aide d’une clé secrète connue de vous seul et, par conséquent, vous empêchez les personnes non autorisées d’y accéder. Dans le cadre de la protection de vos informations, votre organisation vous demande de chiffrer votre appareil Android pour pouvoir accéder aux fichiers, à la messagerie et aux données de l’entreprise.

## <a name="common-issues"></a>Problèmes courants

Les versions plus récentes d’Android, en particulier à partir de la v7.0, requièrent un code secret de démarrage pour garantir que votre appareil est entièrement chiffré. Les fabricants d’appareils ont des différentes descriptions et différents emplacements pour le code secret de démarrage. La plupart du temps, le terme utilisé est « Démarrage sécurisé ». 

## <a name="solutions"></a>Solutions

### <a name="add-a-startup-pin"></a>Ajouter un code confidentiel de démarrage

Certains appareils Android nécessitent de créer un code de démarrage pour vous assurer que votre appareil est sécurisé. Il existe de nombreuses versions d’Android, proposées par de nombreux fabricants différents. Vous pouvez essayer de résoudre ce problème en recherchant un emplacement dans votre application de paramètres pour activer cette option. Par exemple, sur le Galaxy S7 de Samsung, vous activez le démarrage sécurisé en accédant à **Paramètres** > **Écran de verrouillage et sécurité** > **Démarrage sécurisé**.  

### <a name="downgrade-your-version-of-android"></a>Rétrograder votre version d’Android
Si votre appareil vous offre la possibilité de passer à la version antérieure Android 6.0+, faites-le. Si vous essayez de passer votre appareil à une version antérieure, vous risquez de perdre des données. Si cette option n’existe pas, nous vous conseillons de contacter votre administrateur informatique pour résoudre ce problème. Vous pouvez obtenir les informations de contact de votre administrateur informatique sur le [site web Portail d’entreprise](http://portal.manage.microsoft.com).

## <a name="specific-manufacturer-issues"></a>Problèmes propres à certains fabricants

Certains appareils Android sur la version 7.0+ chiffrent les données de manière non conforme à certains standards de la plateforme Android. Ces appareils peuvent sembler être chiffrés par défaut, mais Intune reconnaît les méthodes utilisées quand les informations de l’appareil sont menacées par des utilisateurs malveillants ayant un accès physique à l’appareil.

> [!Note]
> Microsoft travaille avec les fabricants pour résoudre les problèmes que nous identifions lors des tests ou que les utilisateurs nous signalent. Cet article sera mis à jour chaque fois que de nouvelles informations seront disponibles. 

## <a name="known-devices"></a>Appareils connus

### <a name="known-devices-that-can-be-updated-to-fix-this-issue"></a>Appareils connus pouvant être mis à jour pour résoudre ce problème

Si vous avez un des appareils suivants, vous pouvez rencontrer ce problème si vous n'avez pas mis à jour votre appareil vers la version la plus récente d’Android. Vous pouvez installer des mises à jour pour ces appareils en accédant à **Paramètres** > **Mise à jour**. 

- [Huawei Honor 8](http://consumer.huawei.com/en/support/mobile-phones/honor8_en-sup.htm)
- [Huawei P9](http://consumer.huawei.com/mobile-phones/p9/index.html)

### <a name="known-devices-that-currently-cannot-be-updated-to-fix-this-issue"></a>Appareils connus ne pouvant actuellement pas être mis à jour pour résoudre ce problème

- [Huawei Mate 8](http://consumer.huawei.com/en/mobile-phones/mate8/index.htm)
- [Smartphones Xiaomi Mi](https://xiaomi-mi.com/mi-smartphones/)
