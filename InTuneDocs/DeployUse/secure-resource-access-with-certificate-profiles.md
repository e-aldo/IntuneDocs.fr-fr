---
title: "Profils de certificat pour l’accès aux ressources | Microsoft Intune"
description: "Sécurisez l’accès à votre VPN, Wi-Fi et messagerie avec un certificat installé sur chaque appareil de l’utilisateur."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 98c32f924b60734d9a592ebdd7e00429dc32af26


---

# Sécuriser l’accès aux ressources avec des profils de certificat dans Microsoft Intune
Quand vous activez l’accès aux ressources d’entreprise par le biais de profils VPN, Wi-Fi ou de messagerie, vous pouvez sécuriser cet accès avec un certificat installé sur chaque appareil de l’utilisateur. Le principe de fonctionnement est le suivant :

1. Assurez-vous de disposer d’une infrastructure de certificat appropriée, comme décrit dans [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md) ou [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md).

2. Installez un certificat racine (ou certificat d’autorité de certification intermédiaire) sur chaque appareil pour qu’il reconnaisse la légitimité de votre autorité de certification. Pour cela, vous devez créer et déployer un **profil de certificat approuvé**. Quand vous déployez ce profil, les appareils que vous gérez avec Intune demandent et reçoivent le certificat racine. Vous devez créer un profil distinct pour chaque plateforme. Le **Profil de certificat approuvé** est disponible pour ces plateformes :
 -  iOS 7.1 et versions ultérieures
 -  Mac OS X 10.9 et versions ultérieures
 -  Android 4.0 et versions ultérieures
 -  Windows 8.1 et versions ultérieures
 -  Windows Phone 8.1 et versions ultérieures

3. Faites en sorte que chaque appareil demande un certificat à utiliser pour l’authentification de l’accès au VPN, au Wi-Fi et à la messagerie, comme décrit dans [Configurer les profils de certificat Intune](configure-intune-certificate-profiles.md). Vous pouvez créer et déployer un **profil de certificat PKCS #12 (.PFX)** ou un **profil de certificat SCEP** pour les appareils sur ces plateformes :

-  Android 4.0 et versions ultérieures
-  iOS 7.1 et versions ultérieures
-  Windows 10 (Desktop et Mobile) et versions ultérieures

Utilisez le **profil de certificat SCEP** pour :
-   Mac OS X 10.9 et versions ultérieures
-   Windows Phone 8.1 et versions ultérieures

Vous devez créer un profil distinct pour chaque plateforme. Quand vous créez le profil, vous l’associez au **profil de certificat racine approuvé** que vous avez déjà créé.

> [!NOTE]           
> -    Si vous n’avez pas d’autorité de certification d’entreprise, vous devez en créer une.
>- Si vous décidez, en fonction de vos plateformes d’appareils, d’utiliser le profil SCEP (Simplified Certificate Enrollment Protocol), vous devez également configurer un serveur NDES (Network Device Enrollment Service).
>-  Si vous envisagez d’utiliser des profils SCEP ou .PFX, vous devez télécharger et configurer Microsoft Intune Certificate Connector.
> Cette configuration est décrite dans [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md) et [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md).

### Étapes suivantes
- [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md)
- [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md)
- [Configurer les profils de certificats Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO4-->


