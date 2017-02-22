---
title: "Guide de configuration des paramètres Wi-Fi d’Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : apprenez à utiliser Intune pour configurer des connexions Wi-Fi sur les appareils que vous gérez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: f91d919a72b7d14353250d2de532ab083a62c210


---

# <a name="how-to-configure-wi-fi-settings"></a>Configuration des paramètres Wi-Fi 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez les profils Wi-Fi de Microsoft Intune pour déployer les paramètres de réseau sans fil des utilisateurs et des appareils de votre organisation. Lorsque vous déployez un profil Wi-Fi, vos utilisateurs ont accès à votre réseau Wi-Fi d’entreprise sans avoir à le configurer eux-mêmes.

Par exemple, vous installez un nouveau réseau Wi-Fi nommé Contoso Wi-Fi et souhaitez configurer tous les appareils iOS pour qu’ils se connectent à ce réseau. Voici le processus :

1. Créez un profil Wi-Fi contenant les paramètres nécessaires pour se connecter au réseau sans fil Contoso Wi-Fi.
2. Affectez le profil à un groupe contenant tous les utilisateurs d’appareils iOS.
3. Les utilisateurs recherchent le nouveau réseau Wi-Fi Contoso dans la liste des réseaux sans fil sur leur appareil et peuvent facilement se connecter à celui-ci.

Les profils Wi-Fi prennent en charge les plateformes suivantes :

- Android 4 et versions ultérieures
- iOS 8.0 et versions ultérieures
- Mac OS (Mac OS X 10.9 et versions ultérieures)

Pour les appareils exécutant Windows 8.1, Windows 10 et Windows 10 Mobile, vous pouvez importer une configuration Wi-Fi précédemment exportée à partir d’un autre appareil.

Utilisez les informations de cette rubrique pour apprendre les notions de base sur la configuration d’un profil Wi-Fi et lisez autres rubriques pour chaque plateforme pour en savoir plus sur les caractéristiques des appareils.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Création d’un profil d'appareil contenant des paramètres Wi-Fi

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil** , saisissez un **Nom** et une **Description** pour votre profil Wi-Fi.
5. À partir de la liste déroulante **Plateforme**, sélectionnez la plateforme de l’appareil auquel vous souhaitez appliquer les paramètres Wi-Fi. Actuellement, vous pouvez choisir une des plateformes suivantes pour les paramètres Wi-Fi :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows 8.1 et versions ultérieures (importer un profil)**
6. À partir de la liste déroulante **Profil**, choisissez **Wi-Fi de base** ou **Wi-Fi d’entreprise**.
    >[!TIP]
    >Utilisez **Wi-Fi de base** pour fournir des fonctionnalités de base telles que le nom et le SSID du réseau. **Wi-Fi d’entreprise** vous permet de fournir des informations supplémentaires telles que le protocole d’authentification extensible (EAP) si votre réseau Wi-Fi l’utilise. **Importation Wi-Fi** (pour Windows 8.1 et Windows 10) vous permet d’importer des paramètres Wi-Fi dans un fichier XML que vous avez précédemment exporté à partir d’un autre appareil.
7. Selon la plateforme que vous choisissez, les paramètres que vous pouvez configurer diffèrent. Accédez à une des rubriques suivantes pour les paramètres détaillés pour chaque plateforme :
    - [Paramètres Android](wi-fi-for-android.md)
    - [Paramètres iOS](wi-fi-for-ios.md)
    - [Paramètres Mac OS](wi-fi-for-macos.md)
    - [Paramètres Windows Phone 8.1](wi-fi-import-for-windows-8-1.md)
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le volet de la liste des profils.
Si vous souhaitez continuer et affecter ce profil à des groupes, consultez [Guide pratique d’affectation des profils d'appareil](how-to-assign-device-profiles.md).




<!--HONumber=Feb17_HO1-->


