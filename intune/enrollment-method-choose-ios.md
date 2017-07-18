---
title: "Choisir comment inscrire des appareils iOS dans Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment configurer l’inscription des appareils iOS dans Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Choisir comment inscrire des appareils iOS et macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique décrit les méthodes qu'un administrateur informatique peut utiliser pour activer l’inscription d’appareils iOS dans Intune.

Utilisez les informations suivantes pour déterminer la méthode à utiliser pour l’inscription des appareils iOS. Toutes les méthodes suivantes, à l’exception des appareils BYOD, sont destinées à l’inscription d’appareils d’entreprise.

**Conditions préalables :** un [certificat des services de notification Push Apple](apple-mdm-push-certificate-get.md) est obligatoire.

## <a name="user-owned-ios-devices-byod"></a>Appareils iOS de l’utilisateur (BYOD)

Si les utilisateurs souhaitent inscrire leurs appareils BYOD (appareils personnels), ils peuvent télécharger l’application Portail d’entreprise pour iOS depuis l’App Store et de suivre les instructions d’inscription de l’application. Une fois inscrits, les utilisateurs peuvent se connecter au réseau d’entreprise, rejoindre le domaine ou Azure Active Directory et obtenir l’accès aux ressources d’entreprise. Pour activer BYOD, la seule exigence est un [certificat de service de notification push Apple](apple-mdm-push-certificate-get.md). Vous pouvez également bloquer l’inscription d’appareils personnels iOS. Consultez la page [Définir des restrictions de type d’appareil](enrollment-restrictions-set.md) pour obtenir des instructions.

## <a name="user-owned-macos-devices-byod"></a>Appareils macOS de l’utilisateur (BYOD)

Vous pouvez activer l’inscription d’appareils macOS. Pour activer l’inscription macOS, la seule exigence est un [certificat de service de notification push Apple](apple-mdm-push-certificate-get.md). Pour plus d’informations, consultez [Inscrire des appareils macOS](./macos-enroll.md)

## <a name="enrollment-program-with-apple"></a>Programme d’inscription auprès d’Apple
Apple offre des programmes d’achat d’appareils qui incluent l’inscription et d’infrastructure de gestion des appareils. Les appareils achetés par le biais d’un de ces programmes peuvent être inscrits par lots et « à distance » en affectant des numéros de série d’appareil pour la gestion Intune.

- **Programme d’inscription des appareils (DEM)** : le programme d’inscription des appareils d’Apple pour les organisations et les entreprises. Pour plus d’informations, consultez [Inscrire des appareils iOS avec DEP](device-enrollment-program-enroll-ios.md).
- **Apple School Manager** : le programme d’inscription des appareils d’Apple pour les écoles. Pour plus d’informations, consultez [Activer l’inscription des appareils iOS avec Apple School Manager](apple-school-manager-set-up-ios.md)

## <a name="apple-configurator"></a>Apple Configurator

Vous pouvez inscrire des appareils iOS en exportant un profil d’inscription de l’entreprise, puis en connectant ces appareils mobiles à un Mac exécutant Apple Configurator. Apple Configurator prend en charge deux formes d’inscription :

- **Inscription Assistant Configuration** : rétablit les paramètres d’usine de l’appareil et le prépare à l’installation par le nouvel utilisateur. Cette méthode oblige l’administrateur à connecter l’appareil iOS par voie USB à un ordinateur Mac qui exécute l’outil Apple Configurator pour préconfigurer l’inscription. Les appareils sont alors remis à leurs utilisateurs, qui exécutent l’Assistant Configuration lors du premier démarrage de l’appareil. Cette procédure configure l’appareil avec les informations d’identification professionnelles ou scolaires de l’utilisateur et termine le processus d’inscription. Pour plus d’informations, consultez [Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md).

- **Inscription directe** : crée un fichier compatible avec Apple Configurator, à utiliser durant la préparation de l’appareil. Les paramètres d’usine de l’appareil inscrit ne sont pas rétablis et aucun utilisateur n’y est affilié. Pour inscrire des appareils, l’administrateur doit connecter l’appareil iOS par voie USB à un ordinateur Mac qui exécute l’outil Apple Configurator. Pour plus d’informations, consultez [Inscrire des appareils iOS en utilisant l’inscription directe Apple Configurator](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Programme d’inscription des appareils (DEP)

Le programme DEP déploie un profil d’inscription selon le procédé OTA (Over The Air) sur les appareils achetés par son biais. Quand un utilisateur exécute l’Assistant Configuration sur l’appareil lors de son premier démarrage, celui-ci est inscrit dans Intune. Pour plus d’informations, consultez [Inscrire des appareils iOS avec DEP](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Utilisation du gestionnaire d’inscription d’appareil (DEM)
Le gestionnaire d’inscription est un compte d’utilisateur générique qui peut inscrire et gérer jusqu’à 1 000 appareils sans. Les appareils gérés par DEM ne peuvent pas avoir d’affinité utilisateur, l’appareil n’a donc jamais de propriétaire. Vous donnez aux utilisateurs Intune des autorisations DEM pour leur proposer ces fonctionnalités. Chaque appareil que l’utilisateur DEM inscrit utilise une licence Intune. Pour plus d’informations, consultez [Inscrire des appareils avec le gestionnaire d’inscription d’appareils](device-enrollment-manager-enroll.md).
