---
title: "Déployer des stratégies et des applications | Microsoft Intune"
description: "Vous pouvez activer des paramètres de stratégie et déployer des applications qui seront appliquées dès que les appareils sont inscrits dans la gestion."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 56f7d1578ba6b193c6547686675e0fd4fde5f378


---

# <a name="create-policies-and-publish-apps"></a>Créer des stratégies et publier des applications
Avant de commencer l’inscription des applications dans Intune, vous pouvez activer les paramètres de stratégie et les applications qui seront déployées dès que ces appareils passent en gestion. Les stratégies Intune fournissent des paramètres qui vous permettent de contrôler les paramètres de sécurité des appareils mobiles, de gérer les paramètres du Pare-feu Windows et d’Endpoint Protection pour les ordinateurs, et de déployer des applications. Vous pouvez configurer la stratégie, ajouter des applications et déployer ces applications afin que les appareils reçoivent les paramètres et les applications dès leur inscription dans Intune.

Les stratégies et les applications sont spécifiques à la plateforme.

## <a name="manage-device-settings"></a>Gérer les paramètres de l’appareil

 Les paramètres de stratégie de l’appareil sont configurés et gérés sur une base par plateforme. Vous pouvez configurer la stratégie pour les plateformes suivantes :

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android et Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (PC et mobile)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Équipe Windows](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [PC Windows exécutant le client logiciel Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Découvrez comment [gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Ajouter et déployer des applications

Vous pouvez ajouter des applications à Intune et les déployer sur des appareils gérés de deux façons :
- **Installation requise** : les applications installent automatiquement l’application sur les appareils gérés
- **Installation disponible** : les applications apparaissent dans le portail d’entreprise Intune afin que les utilisateurs puissent choisir de les installer sur leurs appareils

### <a name="add-apps"></a>Ajouter des applications

Vous devez tout d’abord rendre les applications disponibles dans Intune à l’aide de l’une des méthodes suivantes :
- [Ajouter des applications pour les appareils inscrits](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Ajouter des applications pour les PC exécutant le client logiciel Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Déployer des applications

Maintenant que l’application est disponible dans Intune, vous pouvez la déployer sur des appareils gérés :
- [Déployer des applications sur des appareils](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Déployer des applications achetées en volume :
    - [iOS - Programme d’achat en volume](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Windows Store pour Entreprises](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    Une fois que vous avez configuré des applications pour le déploiement, vous pouvez [configurer des applications](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) et [surveiller des applications](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr;**Organiser les utilisateurs et les appareils**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personnaliser le portail d’entreprise** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Dec16_HO2-->


