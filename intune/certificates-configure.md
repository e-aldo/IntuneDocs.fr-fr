---
title: Créer un profil de certificat dans Microsoft Intune - Azure | Microsoft Docs
description: Pour vos appareils, ajouter ou créer un profil de certificat en configurant un environnement de certificat SCEP ou PKCS, exporter le certificat public, créer le profil dans le portail Azure, puis affecter SCEP ou PKCS aux profils de certificat dans Microsoft Intune dans le portail Azure
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 867a846b43edb3392db2be11e7ea544fa9317b6c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-a-certificate-profile-for-your-devices-in-microsoft-intune"></a>Configurer un profil de certificat pour vos appareils dans Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Quand vous donnez un accès à des utilisateurs aux ressources d’entreprise par le biais de profils VPN, Wi-Fi ou de messagerie, vous pouvez authentifier ces connexions à l’aide de certificats. Quand vous utilisez des certificats, vous n’avez pas besoin d’entrer vos nom d’utilisateur et mot de passe pour authentifier les connexions.

Vous pouvez utiliser Intune pour affecter ces certificats aux appareils que vous gérez. Intune prend en charge l’affectation et la gestion des types de certificats suivants :

- Protocole SCEP (Simple Certificate Enrollment Protocol)
- PKCS#12 (ou PFX)

Chacun de ces types de certificats a ses propres prérequis et exigences en matière d’infrastructure.

## <a name="overview"></a>Vue d’ensemble

1. Veillez à disposer d’une infrastructure de certificats appropriée. Vous pouvez utiliser des [certificats SCEP](certificates-scep-configure.md) et des [certificats PKCS](certficates-pfx-configure.md).

2. Installez un certificat racine ou un certificat intermédiaire d’une autorité de certification sur chaque appareil pour qu’il reconnaisse la légitimité de votre autorité de certification. Pour ce faire, créez et attribuez un **profil de certificat approuvé**. Quand vous affectez ce profil, les appareils que vous gérez avec Intune demandent et reçoivent le certificat racine. Vous devez créer un profil distinct pour chaque plateforme. Les profils de certificat approuvés sont disponibles pour les plateformes suivantes :

    - iOS 8.0 et versions ultérieures
    - macOS 10.9 et versions ultérieures
    - Android 4.0 et versions ultérieures
    - Android for Work
    - Windows 8.1 et versions ultérieures
    - Windows Phone 8.1 et versions ultérieures
    - Windows 10 et versions ultérieures

3. Créez des profils de certificat pour que les appareils demandent l’utilisation d’un certificat à des fins d’authentification pour l’accès au VPN, au Wi-Fi et aux e-mails. Vous pouvez créer et affecter un profil de certificat **PKCS** ou **SCEP** pour les appareils exécutant les plateformes suivantes :

   - iOS 8.0 et versions ultérieures
   - Android 4.0 et versions ultérieures
   - Android for Work
   - Windows 10 (Desktop et Mobile) et versions ultérieures

   Vous pouvez uniquement utiliser un profil de certificat **SCEP** pour les appareils exécutant les plateformes suivantes :

   - macOS 10.9 et versions ultérieures
   - Windows Phone 8.1 et versions ultérieures

Veillez à créer un profil distinct pour chaque plateforme d’appareil. Quand vous créez le profil, associez-le au profil de certificat racine approuvé que vous avez déjà créé.

### <a name="further-considerations"></a>Autres considérations

- Si vous n’avez pas d’autorité de certification d’entreprise, vous devez en créer une.
- Si vous utilisez des profils SCEP, configurez un serveur NDES (service d’inscription de périphérique réseau).
- Que vous envisagiez d’utiliser des profils SCEP ou PKCS, téléchargez et configurez Microsoft Intune Certificate Connector.


## <a name="step-1-configure-your-certificate-infrastructure"></a>Étape 1 : Configurer votre infrastructure de certificat

Consultez l’une des rubriques suivantes pour vous aider à configurer l’infrastructure pour chaque type de profil de certificat :

- [Configurer l’infrastructure de certificats pour SCEP dans Microsoft Intune](certificates-scep-configure.md)
- [Configurer et gérer les certificats PKCS avec Intune](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Étape 2 : Exporter votre certificat d’autorité de certification racine approuvée

Exportez le certificat d’autorité de certification racine approuvée sous la forme d’un certificat public (.cer) à partir de l’autorité de certification émettrice ou d’un appareil qui approuve votre autorité de certification émettrice. N’exportez pas la clé privée (.pfx).

Vous importez ce certificat quand vous configurez un profil de certificat approuvé.

## <a name="step-3-create-trusted-certificate-profiles"></a>Étape 3 : créer des profils de certificat approuvés
Vous devez créer un profil de certificat approuvé pour pouvoir créer un profil de certificat SCEP ou PKCS. Un profil de certificat approuvé et un profil SCEP ou PKCS sont nécessaires pour chaque plateforme d’appareil. Les étapes de création de certificats approuvés sont similaires pour chaque plateforme d’appareil.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le volet **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le volet Profils, choisissez **Créer un profil**.
4. Dans le volet **Créer un profil**, entrez un **Nom** et la **Description** du profil de certificat approuvé.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat approuvé. Actuellement, vous pouvez choisir une des plateformes suivantes pour les paramètres de certificat :

    - **Android**
    - **Android for Work**
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
8. Lorsque vous avez terminé, choisissez **OK**, revenez au volet **Créer un profil** et sélectionnez **Créer**.

Le profil est créé et apparaît dans la liste. Pour affecter ce profil à des groupes, consultez [Affecter des profils d’appareil](device-profile-assign.md).

Les appareils Android peuvent afficher un message indiquant qu’un tiers a installé un certificat approuvé.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Étape 4 : créer des profils de certificat SCEP ou PKCS

Consultez l’une des rubriques suivantes pour vous aider à configurer et affecter chaque type de profil de certificat :

- [Configurer et gérer les certificats SCEP avec Intune](certificates-scep-configure.md)
- [Configurer et gérer les certificats PKCS avec Intune](certficates-pfx-configure.md)

Après avoir créé un profil de certificat approuvé, créez des profils de certificat SCEP ou PKCS pour chaque plateforme que vous voulez utiliser. Quand vous créez un profil de certificat SCEP, entrez un profil de certificat approuvé pour cette même plateforme. Cette étape lie les deux profils de certificat, mais vous devez quand même affecter chaque profil séparément.

## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations générales sur la façon d’attribuer des profils d’appareils, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).
