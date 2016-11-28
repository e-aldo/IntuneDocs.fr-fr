---
title: Choisir comment inscrire des appareils mobiles | Microsoft Intune
description: "Décider comment inscrire des appareils mobiles dans Intune en répondant à quelques questions simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: 02aed5f84340f7d64681e27f1e4312f7f927a6c1


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Choisir comment inscrire des appareils mobiles

L’inscription des appareils mobiles est le processus qui permet de gérer les smartphones, les tablettes et les ordinateurs portables dans Microsoft Intune. En tant qu’administrateur, vous devez déterminer la meilleure façon d’inscrire les appareils en fonction des éléments suivants :

 -  Propriété (appareil personnel ou d’entreprise)
 -  Utilisation (partagée ou personnelle)
 -  Plateforme (iOS, Android, Windows Phone, PC, Mac)

Vos réponses aux questions suivantes vous permettront de déterminer la méthode d’inscription qui convient le mieux pour les appareils que vous gérez.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Les employés apportent-ils leurs propres appareils ou ceux-ci sont-ils fournis par l’entreprise ?**

  - **Appareils personnels** : inscription de type « BYOD » (Apportez votre propre appareil). Les utilisateurs peuvent installer sur leur appareil l’application Portail d’entreprise Intune, puis inscrire leur appareil pour pouvoir accéder aux ressources d’entreprise telles que la messagerie, les applications d’entreprise, les données d’entreprise et le support.  

  - **Appareils d’entreprise** : les appareils d’entreprise peuvent être inscrits de différentes façons, selon les besoins de l’entreprise et les types d’appareils gérés.

> [!div class="button"]
[Inscription BYOD >](#what-byod-devices-can-your-users-enroll)   [Inscription d’un appareil d’entreprise >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Quels sont les appareils BYOD que vos utilisateurs peuvent inscrire ?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS et Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows 10 Mobile et Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [PC Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Vos appareils d’entreprise sont-ils partagés ou dédiés ?**

- **Partage des appareils d’entreprise** : ces appareils n’ont pas d’utilisateur attitré et ne sont généralement pas configurés pour accéder à la messagerie. Il peut s’agir d’appareils de type bornes ou autres appareils à visée utilitaire que les utilisateurs empruntent, puis rendent quand ils ont terminé. Les méthodes d’inscription recommandées dépendent de la plateforme de l’appareil.

- **Utilisateurs dédiés** : les appareils appartenant à l’entreprise qui sont attribués à des utilisateurs individuels doivent faire l’objet d’un suivi en tant que ressources d’entreprise, tout en permettant aux utilisateurs d’accéder à leur messagerie et à leurs données comme sur leurs appareils personnels. Les méthodes d’inscription recommandées dépendent de la plateforme de l’appareil.

> [!div class="button"]
[Partagé >](#what-operating-system-are-your-shared-devices-running)   [Dédié >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Quels systèmes d’exploitation sont exécutés sur vos appareils partagés ?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Comment allez-vous gérer vos appareils iOS partagés ?**

- **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Quand les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit avec ce profil.

- **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration. Si vous ne souhaitez pas réinitialiser les appareils, utilisez l’inscription directe.

- **Gestionnaire d’inscription d’appareil** : le Gestionnaire d’inscription d’appareil d’Intune permet à un responsable ou un administrateur d’inscrire plusieurs appareils mobiles avec un compte d’utilisateur unique. Ces appareils ne peuvent pas présenter une affinité utilisateur (c’est-à-dire des utilisateurs dédiés) et doivent s’inscrire en installant l’application Portail d’entreprise et en se connectant à cette dernière.

  > [!div class="button"]
  [Inscription DEP iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Inscription directe iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [Inscription à l’aide du logiciel de gestion d’inscription d’appareil >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Comment allez-vous gérer les appareils iOS dédiés ?**

Vous pouvez inscrire des appareils appartenant à l’entreprise avec des utilisateurs dédiés de différentes manières :

- **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Lorsque les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit auprès d’Intune.

- **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration.

- **Balisage avec le numéro IMEI** : en important les numéros IMEI (International Mobile Equipment Identity) des appareils d’entreprise, vous pouvez marquer ces derniers en tant qu’appareils appartenant à l’entreprise dans Intune. Les utilisateurs peuvent ensuite inscrire leurs appareils en tant qu’appareils personnels en installant l’application Portail d’entreprise. Ils pourront ainsi accéder aux ressources d’entreprise telles que la messagerie, les applications et les données.

  > [!div class="button"]
  [Marquer à l’aide de l’IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [DEP iOS](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistant Configuration d’iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marquer à l’aide de l’IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Nov16_HO3-->


