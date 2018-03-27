---
title: Déployer des stratégies et des applications
description: Vous pouvez activer des paramètres de stratégie et déployer des applications qui seront appliquées dès que les appareils sont inscrits dans la gestion.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3da91a23a3aaa7da4f914bb04eda9a2f640db733
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="create-policies-and-publish-apps"></a>Créer des stratégies et publier des applications

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique explique aux administrateurs Intune comment créer des stratégies et comment publier des applications qu’ils peuvent ensuite déployer sur des appareils gérés.

Avant de commencer l’inscription des applications dans Intune, vous pouvez activer les paramètres de stratégie et les applications qui seront déployées dès que ces appareils passent en gestion. Les stratégies Intune fournissent des paramètres qui vous permettent de contrôler les paramètres de sécurité des appareils mobiles, de gérer les paramètres du Pare-feu Windows et d’Endpoint Protection pour les ordinateurs, et de déployer des applications. Vous pouvez configurer la stratégie, ajouter des applications et déployer ces applications afin que les appareils reçoivent les paramètres et les applications dès leur inscription dans Intune.

Les stratégies et les applications sont spécifiques à la plateforme.

## <a name="manage-device-settings"></a>Gérer les paramètres de l’appareil

 Les paramètres de stratégie de l’appareil sont configurés et gérés sur une base par plateforme. Les liens suivants fournissent les listes des paramètres disponibles pour chaque plateforme :

- [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android et Samsung KNOX Standard](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (PC et mobile)](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Équipe Windows](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [PC Windows exécutant le client logiciel Intune](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Découvrez comment [gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Ajouter et déployer des applications

Vous pouvez ajouter des applications à Intune et les déployer sur des appareils gérés de deux façons :
- **Installation requise** : les applications installent automatiquement l’application sur les appareils gérés
- **Installation disponible** : les applications apparaissent dans le portail d’entreprise Intune afin que les utilisateurs puissent choisir de les installer sur leurs appareils

### <a name="add-apps"></a>Ajouter des applications

Vous devez tout d’abord rendre les applications disponibles dans Intune à l’aide de l’une des méthodes suivantes :
- [Ajouter des applications pour les appareils inscrits](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Ajouter des applications pour les PC exécutant le client logiciel Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Déployer des applications

Maintenant que l’application est disponible dans Intune, vous pouvez la déployer sur des appareils gérés :
- [Déployer des applications sur des appareils](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Déployer des applications achetées en volume :
    - [iOS - Programme d’achat en volume](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Microsoft Store pour Entreprises](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](/intune-classic/deploy-use/android-for-work-apps)

    Une fois que vous avez configuré des applications pour le déploiement, vous pouvez [configurer des applications](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr;**Organiser les utilisateurs et les appareils**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personnaliser le portail d’entreprise** &rarr;](/intune/company-portal-customize)  
