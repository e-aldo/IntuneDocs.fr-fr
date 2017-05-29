---
title: Configuration de la gestion Android | Microsoft Docs
description: Activez la gestion des appareils mobiles pour les appareils Android et KNOX Standard avec Microsoft Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4042a22ecfbab7970ea4b3dab8ee6a82b0da5f78
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="set-up-android-device-management"></a>Configuration de la gestion des appareils Android

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

En tant qu’administrateur Intune, vous pouvez activer la gestion des appareils Android, notamment les appareils Samsung Knox Standard, à partir du portail d’entreprise. Les utilisateurs peuvent alors inscrire leurs appareils à l’aide de l’application Portail d’entreprise disponible sur Google Play.

Par défaut, les appareils Android peuvent être inscrits dans Intune. Pour bloquer l’inscription des appareils Android, connectez-vous au [portail d’administration Microsoft Intune](https://manage.microsoft.com) avec vos informations d’identification d’administrateur. Choisissez **Admin** > **Gestion des appareils mobiles** > **Règles d’inscription**, puis décochez la case **Autoriser les appareils Android**.

1.  **Configurer Intune**<br>
    Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](prerequisites-for-enrollment.md#step-2-set-mdm-authority) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2.  **Inscription sur Android activée**<br>
    Aucune configuration supplémentaire dans la console Intune n’est nécessaire pour activer l’inscription d’appareils mobiles Android.

3.  **Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise.**

    Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Android dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android). Le processus d’inscription indique aux utilisateurs ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent voir ou ne peuvent pas voir sur leurs appareils.

    Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :
  - [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](how-to-educate-your-end-users-about-microsoft-intune.md)
  - [Conseils destinés aux utilisateurs relatifs aux appareils Android](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

En l’absence de Google Play Store en Chine, les appareils Android doivent obtenir l’application Portail d’entreprise dans les places de marché des applications chinoises. L’application Portail d’entreprise pour Android sera disponible en téléchargement dans les boutiques suivantes :
* [Baidu](https://go.microsoft.com/fwlink/?linkid=836946)
* [Huawei](https://go.microsoft.com/fwlink/?linkid=836948)
* [Tencent](https://go.microsoft.com/fwlink/?linkid=836949)
* [Wandoujia](https://go.microsoft.com/fwlink/?linkid=836950)
* [Xiaomi](https://go.microsoft.com/fwlink/?linkid=836947)

L’application Portail d’entreprise pour Android utilise Google Play Services pour communiquer avec le service Microsoft Intune. Étant donné que les services Google Play ne sont pas encore disponibles en Chine, le traitement des tâches suivantes peut prendre jusqu’à 8 heures. 

|Console d’administration Intune| Application Portail d’entreprise Intune pour Android |Site web du portail d’entreprise Intune|   
|---|---|---|
|réinitialisation complète| Supprimer un appareil distant| Supprimer l’appareil (local et distant)|
|réinitialisation sélective| Réinitialiser l’appareil| Réinitialiser un appareil|
|Déploiements d’applications nouvelles ou mises à jour| Installer des applications métier disponibles| Réinitialisation du code secret d’un appareil|
|Verrouillage à distance|||
|Réinitialiser le code secret|||

### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription d’appareils dans Microsoft Intune](prerequisites-for-enrollment.md)

