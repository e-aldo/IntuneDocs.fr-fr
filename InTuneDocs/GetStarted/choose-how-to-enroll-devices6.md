---
title: Choisir comment inscrire des appareils mobiles | Microsoft Intune
description: "Décider comment inscrire des appareils mobiles dans Intune en répondant à quelques questions simples"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: f65bdbc7aa708b37a766275494e080436d9a5485
ms.openlocfilehash: 3e5c9ed2ba374172ea27b61a34f0746f582f0ebc


---
# Choisir comment inscrire des appareils mobiles

Vos réponses aux questions suivantes vous permettront de déterminer la méthode d’inscription qui convient le mieux pour les appareils que vous gérez.

## **Comment allez-vous gérer les appareils iOS dédiés ?**

  > [!div class="button"]
[DEP iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistant Configuration d’iOS >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marquer à l’aide de l’IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Vous pouvez inscrire des appareils appartenant à l’entreprise avec des utilisateurs dédiés de différentes manières :

  - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Lorsque les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit auprès d’Intune.

  - **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration.

  - **Balisage avec le numéro IMEI** : en important les numéros IMEI (International Mobile Equipment Identity) des appareils d’entreprise, vous pouvez marquer ces derniers en tant qu’appareils appartenant à l’entreprise dans Intune. Les utilisateurs peuvent ensuite inscrire leurs appareils en tant qu’appareils personnels en installant l’application Portail d’entreprise. Ils pourront ainsi accéder aux ressources d’entreprise telles que la messagerie, les applications et les données.

  > [!div class="button"]
  [< Retour](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO3-->


