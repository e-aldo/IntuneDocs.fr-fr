---
title: Guide pratique pour configurer des certificats avec Intune
titleSuffix: Intune on Azure
description: "Découvrez comment utiliser Intune pour créer et attribuer des certificats qui vous aident à sécuriser les connexions Wi-Fi, VPN et autres."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da23a0c79c5e0e178e52e956561e2764268d09df
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Guide pratique pour configurer des certificats dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Quand vous donnez un accès à des utilisateurs aux ressources d’entreprise par le biais de profils VPN, Wi-Fi ou de messagerie, vous pouvez authentifier ces connexions à l’aide de certificats. L’utilisation de certificats évite à l’utilisateur d’avoir à saisir ses nom d’utilisateur et mot de passe pour authentifier les connexions.

Vous pouvez utiliser Intune pour affecter ces certificats aux appareils que vous gérez. Intune prend en charge l’affectation et la gestion des types de certificats suivants :

- Protocole SCEP (Simple Certificate Enrollment Protocol)
- PKCS#12 (ou PFX)

Chacun de ces types de certificats est associé à sa propre configuration requise et à des exigences d’infrastructure spécifiques.

## <a name="general-workflow"></a>Flux de travail général

1. Assurez-vous de disposer d’une infrastructure de certificat appropriée. Vous pouvez utiliser des [certificats SCEP](certificates-scep-configure.md) et des [certificats PKCS](certficates-pfx-configure.md).
2. Installez un certificat racine ou un certificat intermédiaire d’une autorité de certification sur chaque appareil pour qu’il reconnaisse la légitimité de votre autorité de certification. Pour ce faire, créez et attribuez un **profil de certificat approuvé**. Quand vous attribuez ce profil, les appareils que vous gérez avec Intune demandent et reçoivent le certificat racine. Vous devez créer un profil distinct pour chaque plateforme. Les profils de certificat approuvés sont disponibles pour ces plateformes :
    - iOS 8.0 et versions ultérieures
    - macOS 10.9 et versions ultérieures
    - Android 4.0 et versions ultérieures
    - Android for Work
    - Windows 8.1 et versions ultérieures
    - Windows Phone 8.1 et versions ultérieures
    - Windows 10 et versions ultérieures
3. Créez des profils de certificat pour que les appareils demandent l’utilisation d’un certificat à des fins d’authentification pour l’accès au VPN, au Wi-Fi et aux e-mails. Vous pouvez créer et affecter un profil de certificat **PKCS** ou **SCEP** pour les appareils exécutant ces plateformes :
    - iOS 8.0 et versions ultérieures
    - Android 4.0 et versions ultérieures
    - Android for Work
    - Windows 10 (Desktop et Mobile) et versions ultérieures

    Vous pouvez seulement utiliser un profil de certificat SCEP avec ces plateformes :

-   macOS 10.9 et versions ultérieures
-   Windows Phone 8.1 et versions ultérieures

Vous devez créer un profil distinct pour chaque plateforme d’appareil. Quand vous créez le profil, associez-le au profil de certificat racine approuvé que vous avez déjà créé.

### <a name="further-considerations"></a>Autres considérations

- Si vous n’avez pas d’autorité de certification d’entreprise, vous devez en créer une.
- Si vous décidez, en fonction de vos plateformes d’appareils, d’utiliser le profil SCEP (Simplified Certificate Enrollment Protocol), vous devez également configurer un serveur NDES (Network Device Enrollment Service).
- Si vous envisagez d’utiliser des profils SCEP ou PKCS, vous devez télécharger et configurer Microsoft Intune Certificate Connector.


## <a name="step-1--configure-your-certificate-infrastructure"></a>Étape 1 : configurer votre infrastructure de certificat

Consultez l’une des rubriques suivantes pour vous aider à configurer l’infrastructure pour chaque type de profil de certificat :

- [Configurer l’infrastructure de certificats pour SCEP dans Microsoft Intune](certificates-scep-configure.md)
- [Configurer votre infrastructure de certificats Microsoft Intune pour PKCS](certficates-pfx-configure.md)


## <a name="step-2---export-your-trusted-root-ca-certificate"></a>Étape 2 : exporter votre certificat d’autorité de certification racine approuvée

Exportez le certificat d’autorité de certification racine approuvée sous la forme d’un fichier **.cer** à partir de l’autorité de certification émettrice ou d’un appareil qui approuve votre autorité de certification émettrice. N’exportez pas la clé privée.

Vous importerez ce certificat quand vous configurerez un profil de certificat approuvé.

## <a name="step-3-create-trusted-certificate-profiles"></a>Étape 3 : créer des profils de certificat approuvés
Vous devez créer un profil de certificat approuvé pour pouvoir créer un profil de certificat SCEP ou PKCS. Il faut un profil de certificat approuvé et un profil SCEP ou PKCS pour chaque plateforme d’appareil. Le processus de création de certificats approuvés est identique pour chaque plate-forme d’appareil.

### <a name="to-create-a-trusted-certificate-profile"></a>Pour créer un profil de certificat approuvé

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de certificat approuvé.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat approuvé. Actuellement, vous pouvez choisir une des plateformes suivantes pour les paramètres de certificat :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Certificat approuvé**.
7. Accédez au certificat que vous avez enregistré dans la Tâche 1, puis cliquez sur **OK**.
8. Pour les appareils Windows 8.1 et Windows 10 uniquement, sélectionnez le **Magasin de destination** pour le certificat approuvé à partir de :
    - **Boutique de certificats de l’ordinateur - Racine**
    - **Boutique de certificats de l’ordinateur - Intermédiaire**
    - **Boutique de certificats de l’utilisateur - Intermédiaire**
8. Lorsque vous avez terminé, cliquez sur **OK**, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).


> [!Note]
> Les appareils Android affichent une notification indiquant qu’un tiers a installé un certificat approuvé.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Étape 4 : créer des profils de certificat SCEP ou PKCS

Consultez l’une des rubriques suivantes pour vous aider à configurer et affecter chaque type de profil de certificat :

- [Configurer et gérer les certificats SCEP avec Intune](certificates-scep-configure.md)
- [Configurer et gérer les certificats PKCS avec Intune](certficates-pfx-configure.md)

Après avoir créé un profil de certificat approuvé, créez des profils de certificat SCEP ou PKCS pour chaque plateforme que vous voulez utiliser. Quand vous créez un profil de certificat SCEP, vous devez spécifier un profil de certificat approuvé pour cette même plateforme. Cette opération lie les deux profils de certificat, mais vous devez quand même attribuer chaque profil séparément.


## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations générales sur la façon d’attribuer des profils d’appareils, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).
