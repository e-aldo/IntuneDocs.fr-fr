---
title: "Choisir comment inscrire des appareils iOS dans Intune"
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment configurer l’inscription des appareils iOS dans Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: ee0ecf26a333ec441eb95e79473a9bf405e4120c
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="choose-how-to-enroll-ios-devices"></a>Choisir comment inscrire des appareils iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Cette rubrique décrit les méthodes que vous pouvez utiliser pour inscrire des appareils iOS, ainsi que la configuration requise pour l’inscription.

Utilisez les informations suivantes pour déterminer la méthode à utiliser pour l’inscription des appareils iOS. Toutes les méthodes suivantes, à l’exception des appareils BYOD, sont destinées à l’inscription d’appareils d’entreprise.

**Conditions préalables :** un [certificat des services de notification Push Apple](apple-mdm-push-certificate-get.md) est obligatoire.

## <a name="user-owned-ios-devices-byod"></a>Appareils iOS de l’utilisateur (BYOD)

Si les utilisateurs souhaitent inscrire leurs appareils BYOD (appareils personnels), la seule méthode d’inscription disponible pour les utilisateurs est de télécharger l’application de portail d’entreprise pour iOS depuis l’App Store et de suivre les instructions d’inscription de l’application. Une fois inscrits, les utilisateurs peuvent se connecter au réseau d’entreprise, rejoindre le domaine ou Azure Active Directory et obtenir l’accès aux ressources d’entreprise. Vous pouvez bloquer l’inscription d’appareils personnels iOS. Consultez la page [Définir des restrictions de type d’appareil](enrollment-restrictions-set.md#set-device-type-restrictions) pour obtenir des instructions.

## <a name="apple-configurator"></a>Apple Configurator

Vous pouvez inscrire des appareils iOS en exportant un profil d’inscription de l’entreprise, puis en connectant ces appareils mobiles à un Mac exécutant [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017). Apple Configurator prend en charge deux formes d’inscription :

- **Inscription Assistant Configuration** : rétablit les paramètres d’usine de l’appareil et le prépare à l’installation par le nouvel utilisateur. Cette méthode oblige l’administrateur à connecter l’appareil iOS par voie USB à un ordinateur Mac qui exécute l’outil Apple Configurator pour préconfigurer l’inscription. Les appareils sont alors remis à leurs utilisateurs, qui exécutent la procédure de l’Assistant Configuration. Cette procédure configure l’appareil avec les informations d’identification professionnelles ou scolaires de l’utilisateur et termine le processus d’inscription. Pour plus d’informations, consultez [Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md).

- **Inscription directe** : crée un fichier compatible avec Apple Configurator, à utiliser durant la préparation de l’appareil. Les paramètres d’usine de l’appareil inscrit ne sont pas rétablis et aucun utilisateur n’y est affilié. Pour inscrire des appareils, l’administrateur doit connecter l’appareil iOS par voie USB à un ordinateur Mac qui exécute l’outil Apple Configurator. Pour plus d’informations, consultez [Inscrire des appareils iOS en utilisant l’inscription directe Apple Configurator](apple-configurator-direct-enroll-ios.md).

## <a name="use-the-device-enrollment-program-dep"></a>Programme d’inscription des appareils (DEP)

Le programme DEP déploie un profil d’inscription selon le procédé OTA (Over The Air) sur les appareils achetés par son biais. Quand un utilisateur exécute l’Assistant Configuration sur l’appareil, celui-ci est inscrit dans Intune. Les appareils inscrits via le programme DEP ne peuvent pas être désinscrits par les utilisateurs. Pour plus d’informations, consultez [Inscrire des appareils iOS avec DEP](device-enrollment-program-enroll-ios.md).

## <a name="use-the-device-enrollment-manager-dem"></a>Utilisation du gestionnaire d’inscription d’appareil (DEM)
Le gestionnaire d’inscription est un type de compte d’utilisateur qui peut inscrire et gérer jusqu’à 1 000 appareils. Vous ajoutez des utilisateurs existants au compte de gestionnaire d’inscription d’appareil afin qu’ils puissent bénéficier de ces fonctionnalités. Chaque appareil que l’utilisateur DEM inscrit utilise une seule licence Intune. Pour plus d’informations, consultez [Inscrire des appareils avec le gestionnaire d’inscription d’appareils](device-enrollment-manager-enroll.md).

