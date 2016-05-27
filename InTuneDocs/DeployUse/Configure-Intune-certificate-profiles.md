---
# required metadata

title: Configurer les profils de certificat | Microsoft Intune
description:
keywords:
author: nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurer les profils de certificats Intune
Une fois l’infrastructure et les certificats configurés comme décrit dans [Configurer l’infrastructure de certificat](configure-certificate-infrastructure.md), vous pouvez configurer les profils de certificat :

**Tâche 1** : exporter le certificat d’autorité de certification racine approuvée
**Tâche 2** : créer des profils de certificat d’autorité de certification approuvée
**Tâche 3** : l’une ou l’autre des opérations suivantes :

Créer des profils de certificat SCEP

Créer des profils de certificat .PFX

### Tâche 1 : exporter le certificat racine approuvé
Exporter le certificat d'autorité de certification racine approuvée comme fichier **.cer** à partir de l'autorité de certification émettrice ou d'un appareil qui approuve votre autorité de certification émettrice. Vous n'exportez pas la clé privée.

Vous importerez ce certificat quand vous configurerez un profil de certificat approuvé.

### Tâche 2 : créer des profils de certificat approuvé
Vous devez créer un **profil de certificat approuvé** pour pouvoir créer un profil de certificat SCEP ou .PFX. Il faut un profil de certificat approuvé et un profil SCEP ou .PFS pour chaque plateforme d’appareil mobile.

##### Pour créer un profil de certificat approuvé

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com), puis cliquez sur **Stratégie** &gt; **Ajouter une stratégie**.

2.  Configurez l'un des types de stratégies suivants :

    **Android &gt; Profil de certificat approuvé (Android 4 et versions ultérieures)**

    **iOS &gt; Profil de certificat approuvé (iOS 7.1 et versions ultérieures)**

    **Mac OS X &gt; Profil de certificat approuvé (Mac OS X 10.9 et versions ultérieures)**

    **Windows &gt; Profil de certificat approuvé (Windows 8.1 et versions ultérieures)**

    **Windows &gt; Profil de certificat approuvé (Windows Phone 8.1 et versions ultérieures)**

    Pour en savoir plus : [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Fournissez les informations suivantes pour configurer les paramètres de profil de certificat approuvé pour Android, iOS, Mac OS X, Windows 8.1 ou Windows Phone 8.1. Dans le paramètre **Fichier de certificat**, importez le certificat d’autorité de certification racine approuvée (**.cer**) que vous avez exporté à partir de votre autorité de certification émettrice. Le paramètre **Banque d’informations de destination** s’applique uniquement aux appareils exécutant Windows 8.1 et versions ultérieures, et seulement si l’appareil a plusieurs magasins de certificats.


4.  Quand vous avez terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s'affiche dans l'espace de travail **Stratégie** et peut maintenant être déployée.

### Tâche 3 : créer des profils de certificat SCEP ou .PFX
Après avoir créé un profil de certificat d'autorité de certification approuvé, créez des profils de certificat SCEP ou .PFX pour chaque plateforme que vous souhaitez utiliser. Quand vous créez un profil de certificat SCEP, vous devez spécifier un profil de certificat approuvé pour cette même plateforme. Cette opération lie les deux profils de certificat, même si vous devez toujours déployer chaque profil séparément.

##### Pour créer un profil de certificat SCEP

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com), cliquez sur **Stratégie** &gt; **Ajouter une stratégie**.

2.  Configurez l'un des types de stratégies suivants :

    **Android &gt; Profil de certificat SCEP (Android 4 et versions ultérieures)**

    **iOS &gt; Profil de certificat SCEP (iOS 7.1 et versions ultérieures)**

    **Mac OS X &gt; Profil de certificat SCEP (Mac OS X 10.9 et versions ultérieures)**

    **Windows &gt; Profil de certificat SCEP (Windows 8.1 et versions ultérieures)**

    **Windows &gt; Profil de certificat SCEP (Windows Phone 8.1 et versions ultérieures)**

    Pour en savoir plus : [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Suivez les instructions de la page de configuration de profil pour configurer les paramètres de profil de certificat SCEP.

4.  Quand vous avez terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s'affiche dans l'espace de travail **Stratégie** et peut maintenant être déployée.

##### Pour créer un profil de certificat .PFX

1.  Ouvrez la [console d’administration Intune](https://manage.microsoft.com), cliquez sur **Stratégie** &gt; **Ajouter une stratégie**.

2.  Configurez l'un des types de stratégies suivants :



-   **Android &gt; Profil de certificat .PFX (Android 4 et versions ultérieures)**

    -   **Windows &gt; Profil de certificat PKCS #12 (.PFX) (Windows 10 et versions ultérieures)**

    -   **Windows &gt; Profil de certificat PKCS #12 (.PFX) (Windows Phone 10 et versions ultérieures)**

    -    **iOS > Profil de certificat PKCS #12 (.PFX) (iOS 7.1 et versions ultérieures)**    

    Pour en savoir plus : [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

3.  Entrez les informations demandées dans le formulaire de stratégie.

4.  Quand vous avez terminé, cliquez sur **Enregistrer la stratégie**.

La nouvelle stratégie s'affiche dans l'espace de travail **Stratégie** et peut maintenant être déployée.

## Déployer les profils de certificat
Quand vous déployez les profils de certificat, le fichier de certificat du profil de certificat d'autorité de certification approuvée est installé sur les appareils et le profil de certificat SCEP ou .PFX est utilisé par l'appareil pour créer une demande de certificat par l'appareil.

Les profils de certificat s'installent uniquement sur les appareils applicables, selon la plateforme utilisée lors de la création du profil.

-   Vous pouvez déployer les profils de certificat sur les regroupements d'utilisateurs ou d'appareils.

    > [!TIP]
    > Pour autoriser la publication des certificats sur des appareils rapidement après l'inscription de l'appareil, déployez le profil de certificat sur un groupe d'utilisateurs (pas un groupe d'appareils). Si vous déployez sur un groupe d'appareils, une inscription complète de l'appareil doit intervenir avant que l'appareil ne reçoive la stratégie.

-   Bien que chaque profil soit déployé séparément, le profil d'autorité de certification racine approuvé et le profil SCEP/.PFX doivent être déployés, sans quoi la stratégie de certificat SCEP/.PFX échoue.

Vous déployez des profils de certificat de la même façon que vous déployez une autre stratégie pour Intune :

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis cliquez sur **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes vers lesquels déployer la stratégie, puis cliquez sur **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer** : cliquez sur **Annuler**.

Quand vous sélectionnez une stratégie déployée, vous pouvez afficher d’autres informations sur le déploiement dans la partie inférieure de la liste de stratégies.
###  Étapes suivantes

Vous pouvez maintenant utiliser des certificats pour aider à sécuriser les profils de messagerie électronique, Wi-Fi et VPN :

-  [Configurer l’accès à la messagerie d’entreprise à l’aide de profils de messagerie](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [Connexions Wi-Fi dans Microsoft Intune](wi-fi-connections-in-microsoft-intune.md)
-  [Connexions VPN dans Microsoft Intune](vpn-connections-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


