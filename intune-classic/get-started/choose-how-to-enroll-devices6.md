---
title: Choisir comment inscrire des appareils mobiles
description: "Décider comment inscrire des appareils mobiles dans Intune en répondant à quelques questions simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 6e996f7de29da6bb41c11d7f0686f1ead3f528bd
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a>Choisir comment inscrire des appareils mobiles

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vos réponses aux questions suivantes vous permettront de déterminer la méthode d’inscription qui convient le mieux pour les appareils que vous gérez.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Comment allez-vous gérer les appareils d’entreprise dédiés ?**

  > [!div class="button"]
[iOS DEP >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[Assistant Configuration d’iOS >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[Marquer à l’aide de l’IMEI >](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Vous pouvez inscrire des appareils appartenant à l’entreprise avec des utilisateurs dédiés de différentes manières :

  - **Programme d’inscription des appareils (DEP) d’Apple** : les appareils iOS achetés ou gérés à l’aide du programme d’inscription des appareils peuvent être ciblés avec un profil d’inscription. Lorsque les utilisateurs allument leur appareil pour la première fois, celui-ci télécharge le profil DEP et s’inscrit auprès d’Intune.

  - **Apple Configurator sur un Mac** : Apple Configurator est une application Apple qui s’exécute sur un ordinateur Mac. Pour installer un profil d’inscription sur un appareil iOS, connectez ce dernier au Mac à l’aide d’un câble USB. Si vous pouvez réinitialiser les appareils aux paramètres d’usine pour les inscrire, utilisez l’inscription à l’aide de l’Assistant Configuration.

  - **Identification avec le numéro IMEI** : en important les numéros IMEI (International Mobile Equipment Identity) des appareils d’entreprise, vous pouvez marquer ces derniers en tant qu’appareils appartenant à l’entreprise dans Intune. Il s’agit de la seule façon d’identifier les appareils Windows et Android (« mono-utilisateur ») dédiés comme appartenant à l’entreprise. Les appareils iOS qui ne sont pas inscrits auprès du programme d’inscription d’appareils d’Apple ou d’Apple Configurator peuvent également être référencés par un numéro IMEI. Après avoir pré-déclaré les appareils pour qu’ils soient marqués comme « d’entreprise », vous pouvez les distribuer aux utilisateurs. Les utilisateurs peuvent ensuite inscrire leurs appareils en tant qu’appareils dédiés en installant l’application Portail d’entreprise. Ils pourront ainsi accéder aux ressources d’entreprise telles que les e-mails, les applications et les données.

> [!div class="button"]
[< Retour](choose-how-to-enroll-devices3.md)
