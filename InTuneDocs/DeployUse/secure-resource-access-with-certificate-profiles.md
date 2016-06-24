---
# required metadata

title: Activer l’accès aux ressources d’entreprise à l’aide de profils de certificat | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: kmyrup
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Sécuriser l’accès aux ressources avec des profils de certificat dans Microsoft Intune
Quand vous activez l’accès aux ressources d’entreprise par le biais de profils VPN, Wi-Fi ou de messagerie, vous pouvez sécuriser cet accès avec un certificat installé sur chaque appareil de l’utilisateur. Le principe de fonctionnement est le suivant :

1. Assurez-vous de disposer d’une infrastructure de certificat appropriée, comme décrit dans [Configurer l’infrastructure de certificat](configure-certificate-infrastructure.md).

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
> La configuration de tous ces éléments est décrite dans la rubrique [Configurer l’infrastructure de certificat](configure-certificate-infrastructure.md).

### Étapes suivantes
- [Configurer l’infrastructure de certificat](configure-certificate-infrastructure.md)
- [Configurer les profils de certificats Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Jun16_HO1-->


