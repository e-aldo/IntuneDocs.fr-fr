---
title: Choisir comment inscrire des appareils mobiles | Microsoft Intune
description: "Décider comment inscrire des appareils mobiles dans Intune en répondant à quelques questions simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a563105aafb447c6e009cca09645e630709ff72d
ms.openlocfilehash: 143f77bde09648a233ff09e9740668191a50cb1e


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Choisir comment inscrire des appareils mobiles

Vos réponses aux questions suivantes vous permettent de déterminer la méthode d’inscription qui convient le mieux pour les appareils que vous gérez.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Les employés apportent-ils leurs propres appareils ou ceux-ci sont-ils fournis par l’entreprise ?**

  - **Appareils d’utilisateurs** : inscription « Apportez votre propre appareil » (BYOD, Bring Your Own Device)
  - **Appareils d’entreprise** : inscription d’un appareil d’entreprise

> [!div class="button"]
[Inscription BYOD >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[Inscription d’un appareil d’entreprise >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Quels sont les appareils BYOD que vos utilisateurs peuvent inscrire ?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS et Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile et Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [PC Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Vos appareils d’entreprise sont-ils partagés ou dédiés ?**

> [!div class="button"]
[Partagé >](#what-operating-system-are-your-shared-devices-running)   [Dédié >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Quels systèmes d’exploitation sont exécutés sur vos appareils partagés ?**

> [!div class="button"]
[Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Comment allez-vous gérer vos appareils iOS partagés ?**

> [!div class="button"]
[Inscription DEP iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Inscription directe iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Inscription à l’aide du logiciel de gestion d’inscription d’appareil >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être associés à un profil d’inscription. Quand les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit avec ce profil.

  - **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’option Inscription de l’Assistant Configuration. Si vous ne souhaitez pas réinitialiser les appareils, utilisez l’option Inscription directe.

  - **Gestionnaire d’inscription d’appareil (Intune)** : le Gestionnaire d’inscription d’appareil d’Intune permet à un responsable ou un administrateur d’inscrire plusieurs appareils mobiles avec un compte d’utilisateur unique. Ces appareils ne peuvent pas présenter des utilisateurs dédiés (une affinité utilisateur) et doivent s’inscrire en installant l’application Portail d’entreprise et en se connectant à cette dernière.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Comment allez-vous gérer les appareils iOS dédiés ?**

> [!div class="button"]
[DEP iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistant Configuration d’iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marquer à l’aide de l’IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Vous pouvez inscrire des appareils appartenant à l’entreprise avec des utilisateurs dédiés de différentes manières :

  - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être associés à un profil d’inscription. Quand les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit auprès d’Intune.

  - **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’option Inscription de l’Assistant Configuration.

  - **Balisage avec le numéro IMEI** : en important les numéros IMEI (International Mobile Equipment Identity) des appareils d’entreprise, vous pouvez marquer ces derniers en tant qu’appareils appartenant à l’entreprise dans Intune. Les utilisateurs peuvent ensuite inscrire leurs appareils en tant qu’appareils personnels en installant l’application Portail d’entreprise. Ils pourront ainsi accéder aux ressources d’entreprise, telles que la messagerie, les applications et les données.



<!--HONumber=Nov16_HO4-->


