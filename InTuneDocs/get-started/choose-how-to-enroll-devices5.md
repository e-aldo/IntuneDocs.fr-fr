---
title: Choisir comment inscrire des appareils mobiles | Microsoft Intune
description: "Décider comment inscrire des appareils mobiles dans Intune en répondant à quelques questions simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 53c22143b5b367ed5732ed14fb06937d66489afa


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Choisir comment inscrire des appareils mobiles

Vos réponses aux questions suivantes vous permettront de déterminer la méthode d’inscription qui convient le mieux pour les appareils que vous gérez.


## <a name="how-will-you-manage-shared-ios-devices"></a>**Comment allez-vous gérer vos appareils iOS partagés ?**

> [!div class="button"]
[Inscription DEP iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
[Inscription directe iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
[Inscription à l’aide du gestionnaire d’inscription d’appareil >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Lorsque les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit avec ce profil.

  - **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration. Si vous ne souhaitez pas réinitialiser les appareils, utilisez l’inscription directe.

  - **Gestionnaire d’inscription d’appareil** : le Gestionnaire d’inscription d’appareil d’Intune permet à un responsable ou un administrateur d’inscrire plusieurs appareils mobiles avec un compte d’utilisateur unique. Ces appareils ne peuvent pas présenter une affinité utilisateur (c’est-à-dire des utilisateurs dédiés) et doivent s’inscrire en installant l’application Portail d’entreprise et en se connectant à cette dernière.

  > [!div class="button"]
  [< Retour](choose-how-to-enroll-devices3.md)



<!--HONumber=Dec16_HO2-->


