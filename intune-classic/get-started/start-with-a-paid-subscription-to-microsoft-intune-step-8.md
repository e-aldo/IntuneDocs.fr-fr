---
title: Activer l’inscription d’appareil
description: Définissez l’autorité MDM et activez l’inscription des appareils iOS, Windows, Android et Mac.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e9572181fb15ec97e7ae4c11a8ab2e4fe4cc9b30
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="enable-enrollment-for-mobile-devices"></a>Activer l’inscription des appareils mobiles

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique explique aux administrateurs Intune comment activer l’inscription des appareils mobiles. Pour obtenir de l’aide sur l’utilisation d’Intune sur votre téléphone, consultez [Utilisation d’appareils gérés pour votre travail](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).

Pour configurer la gestion des appareils mobiles avec Intune, vous devez d’abord définir *l’autorité de gestion des appareils mobiles*, qui identifie le service permettant de gérer les appareils associés à votre compte. Cette aide suppose que vous allez utiliser le service Intune plutôt que System Center Configuration Manager. Une fois l’autorité MDM définie, vous pouvez activer la gestion des plateformes d’appareil et inscrire vos appareils auprès de l’application Portail d’entreprise.

## <a name="enable-device-enrollment"></a>Activer l’inscription d’appareil

1. **Utiliser Intune comme autorité de gestion des appareils mobiles** Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Administration**>**Gestion des appareils mobiles**, puis choisissez **Définir l’autorité MDM** sous **Tâches**.  

2. Dans la boîte de dialogue Autorité de gestion des appareils mobiles, cliquez sur **Oui**.

    ![Console d’administration. Définir l’autorité de gestion des appareils mobiles sur Intune](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a>Choisir comment inscrire des appareils

Intune peut gérer les appareils de différentes manières selon les besoins de votre entreprise. Les appareils BYOD (Apportez votre propre appareil), CYOD (Choisissez votre propre appareil), appartenant à l’entreprise et en mode plein écran font partie des scénarios d’inscription disponibles.

Suivez ces étapes pour [Choisir comment inscrire des appareils](choose-how-to-enroll-devices1.md).

## <a name="enable-mdm-for-your-device-platform"></a>Activer la gestion des appareils mobiles pour votre plateforme d'appareils
L’inscription doit être activée pour les appareils iOS, Mac et Android for Work établissant une relation entre le fournisseur de plateforme et votre client Intune. Les appareils Windows et Android ne nécessitent pas d’étapes supplémentaires, mais pour les appareils Windows, vous pouvez simplifier l’inscription d’appareils pour vos utilisateurs en créant une entrée de Registre DNS spéciale.

Activez l’inscription d’appareils pour la plateforme d’appareils que vous souhaitez gérer. La configuration requise varie en fonction de la plateforme :

- [iOS et macOS](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [Windows 10 et Windows Phone](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [PC Windows](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (client de logiciel Intune)
- [Android for Work](/intune-classic/deploy-use/set-up-android-for-work)

Une fois l’inscription activée, les utilisateurs peuvent télécharger l’application Portail d’entreprise sur leur appareil et terminer le processus d’inscription d’appareil.

### <a name="enable-company-owned-device-enrollment"></a>Activer l’inscription d’un appareil d’entreprise
Vous pouvez également activer plusieurs scénarios [d’inscription d’un appareil appartenant à l’entreprise](/intune-classic/deploy-use/manage-corporate-owned-devices), notamment :
- [Programme d’inscription d’appareils d’Apple](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Inscription par le biais de l’Assistant Configuration Apple Configurator](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Inscription directe Apple Configurator](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Gestionnaire d’inscription d’appareil](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a>Étapes suivantes
Félicitations ! Vous venez d’effectuer la dernière étape du *guide de démarrage rapide Intune*. Maintenant que votre configuration initiale est terminée, vous pouvez envisager d’activer des fonctionnalités supplémentaires de gestion des appareils mobiles.

>[!div class="step-by-step"]
>[&larr; **Inscrire des appareils**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tâches après la configuration** &rarr;](.\post-configuration-tasks.md)  
