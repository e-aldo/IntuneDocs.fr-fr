---
title: "Profils de certificat pour l’accès aux ressources"
description: "Sécurisez l’accès à votre VPN, Wi-Fi et messagerie avec un certificat installé sur chaque appareil de l’utilisateur."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d20be5a701204fa3f41b051f21c967096f68d337
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Sécuriser l’accès aux ressources avec des profils de certificat dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Quand vous donnez un accès à des utilisateurs aux ressources d’entreprise par le biais de profils VPN, Wi-Fi ou de messagerie, vous pouvez sécuriser cet accès à l’aide d’un certificat installé sur chaque appareil de l’utilisateur. Le principe de fonctionnement est le suivant :

1. Assurez-vous de disposer d’une infrastructure de certificat appropriée, comme décrit dans [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md) et [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md).

2. Installez un certificat racine ou un certificat intermédiaire d’une autorité de certification sur chaque appareil pour qu’il reconnaisse la légitimité de votre autorité de certification. Pour ce faire, créez et déployez un **Profil de certificat approuvé**. Quand vous déployez ce profil, les appareils que vous gérez avec Intune demandent et reçoivent le certificat racine. Vous devez créer un profil distinct pour chaque plateforme. Le **Profil de certificat approuvé** est disponible pour ces plateformes :
 -  iOS 8.0 et versions ultérieures
 -  Mac OS X 10.9 et versions ultérieures
 -  Android 4.0 et versions ultérieures
 -  Android for Work
 -  Windows 8.1 et versions ultérieures
 -  Windows Phone 8.1 et versions ultérieures

3. Créez des profils de certificat pour que les appareils demandent l’utilisation d’un certificat pour l’authentification pour l’accès au VPN, au Wi-Fi et aux e-mails, comme décrit dans [Configurer les profils de certificats Intune](configure-intune-certificate-profiles.md). Vous pouvez créer et déployer un **profil de certificat PKCS #12 (.PFX)** *ou* un **profil de certificat SCEP** pour les appareils exécutant ces plateformes :

  -  iOS 8.0 et versions ultérieures
  -  Android 4.0 et versions ultérieures
  -  Android for Work
  -  Windows 10 (Desktop et Mobile) et versions ultérieures

  Utilisez un **profil de certificat SCEP** pour les appareils exécutant ces plateformes :
    -   Mac OS X 10.9 et versions ultérieures
    -   Windows Phone 8.1

Vous devez créer un profil distinct pour chaque plateforme. Quand vous créez le profil, associez-le au **profil de certificat racine approuvé** que vous avez déjà créé.

> [!NOTE]           
> - Si vous n’avez pas d’autorité de certification d’entreprise, vous devez en créer une.
>- Si vous décidez, en fonction de vos plateformes d’appareils, d’utiliser le profil SCEP (Simplified Certificate Enrollment Protocol), vous devez également configurer un serveur NDES (Network Device Enrollment Service).
>-  Si vous envisagez d’utiliser des profils SCEP ou .PFX, vous devez télécharger et configurer Microsoft Intune Certificate Connector.
>-  Découvrez comment configurer tous les services nécessaires dans [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md) ou [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md).

### <a name="next-steps"></a>Étapes suivantes
- [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md)
- [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md)
- [Configurer les profils de certificats Intune](configure-intune-certificate-profiles.md)
