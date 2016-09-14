---
title: Configurer les profils de certificat | Microsoft Intune
description: "Découvrez comment créer un profil de certificat Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8e3f7cac8eb3495aad3835ec4713d67a58383c66
ms.openlocfilehash: 8b08f8fde6136b8eca61f6ae7a8c21635f7d452e


---

# Configurer les profils de certificats Intune
Une fois que vous avez configuré l’infrastructure et les certificats comme décrit dans [Configurer l’infrastructure de certificat pour SCEP](configure-certificate-infrastructure-for-scep.md) ou [Configurer l’infrastructure de certificat pour PFX](configure-certificate-infrastructure-for-pfx.md), vous pouvez créer des profils de certificat. Voici le processus :

- **Tâche 1** : Exporter le certificat d’autorité de certification racine approuvée
- **Tâche 2** : Créer des profils de certificat approuvés
- **Tâche 3** : Créer l’un des deux types de profils de certificat :
  - Profils de certificat SCEP
  - Profils de certificat .PFX

## **Tâche 1** : Exporter le certificat d’autorité de certification racine approuvée
Exportez le certificat d’autorité de certification racine approuvée sous la forme d’un fichier **.cer** à partir de l’autorité de certification émettrice ou d’un appareil qui approuve votre autorité de certification émettrice. N’exportez pas la clé privée.

Vous importerez ce certificat quand vous configurerez un profil de certificat approuvé.

## **Tâche 2** : Créer des profils de certificat approuvés
Vous devez créer un profil de certificat approuvé avant de créer un profil de certificat SCEP (Protocole d’inscription de certificats simple) ou PKCS #12 (.PFX). Vous avez besoin d’un profil de certificat approuvé et d’un profil SCEP ou .PFX pour chaque plateforme d’appareil mobile.

### Pour créer un profil de certificat approuvé

1.  Dans la [console d’administration Intune](https://manage.microsoft.com), choisissez **Stratégie** &gt; **Ajouter une stratégie**.
2.  Ajoutez l’un de ces types de stratégie :
    - **Android &gt; Profil de certificat approuvé (Android 4 et versions ultérieures)**
    - **iOS &gt; Profil de certificat approuvé (iOS 7.1 et versions ultérieures)**
    - **Mac OS X &gt; Profil de certificat approuvé (Mac OS X 10.9 et versions ultérieures)**
    - **Windows &gt; Profil de certificat approuvé (Windows 8.1 et versions ultérieures)**
    - **Windows &gt; Profil de certificat approuvé (Windows Phone 8.1 et versions ultérieures)**

    Pour en savoir plus : [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Entrez les informations suivantes pour configurer les paramètres de profil de certificat approuvé pour Android, iOS, Mac OS X, Windows 8.1 ou Windows Phone 8.1.

    - Dans le paramètre **Fichier de certificat**, importez le certificat d’autorité de certification racine approuvée (fichier .cer) que vous avez exporté à partir de votre autorité de certification émettrice. Le paramètre **Banque d’informations de destination** s’applique uniquement aux appareils exécutant Windows 8.1 et versions ultérieures, et seulement si l’appareil a plusieurs magasins de certificats.
    -  Sous **Format du nom de l’objet**, sélectionnez **Personnalisé** pour entrer un format de nom d’objet personnalisé.  
        Les deux variables actuellement prises en charge pour le format personnalisé sont `Common Name (CN)` et `Email (E)`. En combinant ces variables avec des chaînes statiques, vous pouvez créer un format de nom d’objet personnalisé tel que celui-ci :  

        `CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US`  

        Dans cet exemple, l’administrateur a créé un format de nom d’objet qui, en plus des variables `CN` et `E`, utilise des chaînes pour les valeurs de l’unité d’organisation, de l’organisation, de l’emplacement, de la région et du pays. La [fonction CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) répertorie les chaînes prises en charge.  
4.  Choisissez **Enregistrer la stratégie**.

La nouvelle stratégie apparaît dans l’espace de travail **Stratégie**. À présent, vous pouvez la déployer.

## **Tâche 3** : Créer des profils de certificat SCEP ou .PFX
Après avoir créé un profil de certificat d’autorité de certification approuvée, créez des profils de certificat SCEP ou .PFX pour chaque plateforme que vous voulez utiliser. Quand vous créez un profil de certificat SCEP, vous devez spécifier un profil de certificat approuvé pour cette même plateforme. Cette opération lie les deux profils de certificat, mais vous devez quand même déployer chaque profil séparément.

### Pour créer un profil de certificat SCEP

1.  Dans la [console d’administration Intune](https://manage.microsoft.com), choisissez **Stratégie** &gt; **Ajouter une stratégie**.
2.  Ajoutez l’un de ces types de stratégie :
    - **Android &gt; Profil de certificat SCEP (Android 4 et versions ultérieures)**
    - **iOS &gt; Profil de certificat SCEP (iOS 7.1 et versions ultérieures)**
    - **Mac OS X &gt; Profil de certificat SCEP (Mac OS X 10.9 et versions ultérieures)**
    - **Windows &gt; Profil de certificat SCEP (Windows 8.1 et versions ultérieures)**
    - **Windows &gt; Profil de certificat SCEP (Windows Phone 8.1 et versions ultérieures)**

    Pour en savoir plus : [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Suivez les instructions de la page de configuration de profil pour configurer les paramètres de profil de certificat SCEP.
    > [!NOTE]
    >
    > Sous **Format du nom de l’objet**, sélectionnez **Personnalisé** pour entrer un format de nom d’objet personnalisé.
    >
    > Les deux variables actuellement prises en charge pour le format personnalisé sont `Common Name (CN)` et `Email (E)`. En combinant ces variables avec des chaînes statiques, vous pouvez créer un format de nom d’objet personnalisé tel que celui-ci :

    >     CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US

    > Dans cet exemple, l’administrateur a créé un format de nom d’objet qui, en plus des variables `CN` et `E`, utilise des chaînes pour les valeurs de l’unité d’organisation, de l’organisation, de l’emplacement, de la région et du pays. La [fonction CertStrToName](https://msdn.microsoft.com/en-us/library/windows/desktop/aa377160.aspx) répertorie les chaînes prises en charge.

4.  Choisissez **Enregistrer la stratégie**.

La nouvelle stratégie apparaît dans l’espace de travail **Stratégie**. À présent, vous pouvez la déployer.

### Pour créer un profil de certificat .PFX

1.  Dans la [console d’administration Intune](https://manage.microsoft.com), choisissez **Stratégie** &gt; **Ajouter une stratégie**.
2.  Ajoutez l’un de ces types de stratégie :
  - **Android &gt; Profil de certificat .PFX (Android 4 et versions ultérieures)**
  - **Windows &gt; Profil de certificat PKCS #12 (.PFX) (Windows 10 et versions ultérieures)**
  - **Windows &gt; Profil de certificat PKCS #12 (.PFX) (Windows Phone 10 et versions ultérieures)**
  - **iOS > Profil de certificat PKCS #12 (.PFX) (iOS 7.1 et versions ultérieures)**    
    Pour en savoir plus : [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).
3.  Entrez les informations demandées dans le formulaire de stratégie.
4.  Choisissez **Enregistrer la stratégie**.

La nouvelle stratégie apparaît dans l’espace de travail **Stratégie**. À présent, vous pouvez la déployer.

## Déployer les profils de certificat
Quand vous déployez des profils de certificat, le fichier de certificat issu du profil de certificat d’autorité de certification approuvée est installé sur l’appareil. L’appareil utilise le profil de certificat SCEP ou .PFX pour créer une demande de certificat par l’appareil.

Les profils de certificat s’installent uniquement sur les appareils exécutant la plateforme que vous utilisez quand vous créez le profil.

-   Vous pouvez déployer des profils de certificat sur des regroupements d’utilisateurs ou d’appareils.

    > [!TIP]
    > Pour publier un certificat sur un appareil rapidement après l’inscription de l’appareil, déployez le profil de certificat sur un groupe d’utilisateurs plutôt que sur un groupe d’appareils. Si vous déployez sur un groupe d’appareils, une inscription complète des appareils est préalablement nécessaire pour qu’ils puissent recevoir des stratégies.

-   Même si vous déployez chaque profil séparément, vous devez également déployer l’autorité de certification racine approuvée et le profil SCEP ou .PFX. Dans le cas contraire, la stratégie de certificat SCEP ou .PFX échoue.

Déployez les profils de certificat de la même façon que vous déployez d’autres stratégies pour Intune :

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.
2.  Dans la boîte de dialogue **Gérer le déploiement** :
    -   **Pour déployer la stratégie**, sélectionnez un ou plusieurs groupes sur lesquels la déployer, puis choisissez **Ajouter** &gt; **OK**.
    -   **Pour fermer la boîte de dialogue sans la déployer**, choisissez **Annuler**.

Quand vous sélectionnez une stratégie déployée, vous pouvez afficher d’autres informations sur le déploiement dans la partie inférieure de la liste de stratégies.

### Étapes suivantes

Ensuite, découvrez comment utiliser des certificats pour sécuriser les profils de messagerie, Wi-Fi et VPN.

-  [Configurer l’accès à la messagerie d’entreprise à l’aide de profils de messagerie](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Connexions Wi-Fi dans Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Connexions VPN dans Microsoft Intune](vpn-connections-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


