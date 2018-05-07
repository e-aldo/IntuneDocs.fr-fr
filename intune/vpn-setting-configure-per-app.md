---
title: Configurer un VPN par application dans Microsoft Intune pour les appareils iOS
titleSuffix: ''
description: Spécifiez les applications gérées qui peuvent utiliser votre réseau privé virtuel (VPN, Virtual Private Network) sur les appareils iOS gérés par Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67e2630fc2a7ccd75ac86c797e36c389757d908a
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="set-up-per-app-virtual-private-network-vpn-in-intune-for-ios-devices"></a>Configurer un VPN par application dans Intune pour les appareils iOS

Vous pouvez spécifier les applications gérées qui peuvent utiliser votre VPN sur les appareils iOS gérés par Intune. Quand vous créez un VPN par application dans Intune, l’utilisateur final se connecte automatiquement à votre VPN pour accéder aux documents de l’entreprise.

Un VPN par application est actuellement disponible pour les fournisseurs suivants : 

 - Pulse Connect Secure
 - Checkpoint Remote Access VPN
 - F5
 - SonicWall


## <a name="prerequisites-for-the-per-app-vpn"></a>Prérequis du réseau VPN par application

Pour prouver son identité, le serveur VPN présente le certificat qui doit être accepté sans invite par l’appareil. Pour garantir l’approbation automatique du certificat, créez un profil de certificat approuvé qui contient le certificat racine du serveur VPN émis par l’Autorité de certification. 

Exportez le certificat et ajoutez l’Autorité de certification.

1. Ouvrez la console d’administration sur votre serveur VPN.
2. Vérifiez que votre serveur VPN utilise l’authentification basée sur les certificats. 
3. Exportez le fichier du certificat racine approuvé. Il a une extension .cer et vous l’ajoutez quand vous créez un profil de certificat approuvé.
4. Ajoutez le nom de l’Autorité de certification qui a émis le certificat pour l’authentification auprès du serveur VPN.
    Si l’Autorité de certification présentée par l’appareil correspond à l’une des Autorités de certification de la liste des Autorités de certification approuvées sur le serveur VPN, celui-ci authentifie l’appareil.

## <a name="create-a-group-for-your-vpn-users"></a>Créer un groupe pour vos utilisateurs VPN

Créez ou choisissez un groupe existant dans Azure Active Directory (Azure AD) pour contenir les membres qui ont accès au VPN par application.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
2. Choisissez **Groupes** et cliquez sur **Nouveau groupe**.
3. Sélectionnez un **Type de groupe** pour le groupe. 
3. Entrez le **Nom de groupe** du groupe. 
4. Entrez la **Description de groupe** du groupe. 
5. Sélectionnez **Affecté** comme **Type d’appartenance**.
7. Recherchez les utilisateurs VPN par nom ou adresse e-mail dans le volet **Membres**.
8. Sélectionnez chaque utilisateur et cliquez sur **Sélectionner**.
9. Cliquez sur **Créer**

## <a name="create-a-trusted-certificate-profile"></a>Créer un profil de certificat approuvé

Importez le certificat racine du serveur VPN émis par l’Autorité de certification dans un profil créé dans Intune. Le profil de certificat approuvé permet à l’appareil iOS d’approuver automatiquement l’Autorité de certification que présente le serveur VPN.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
2. Choisissez **Configuration de l’appareil** et cliquez sur **Profils**.
3. Cliquez sur **Créer un profil**. Dans **Créer un profil** :
    1. Tapez le **Nom**.
    2. Tapez la **Description**.
    3. Sélectionnez **iOS** pour la **Plateforme**.
    4. Sélectionnez **Certificat approuvé** pour le **Type de profil**.
4. Cliquez sur l’icône de dossier et accédez à votre certificat VPN (fichier .cer) que vous avez exporté à partir de votre console d’administration VPN. Cliquez sur **OK**.
5. Cliquez sur **Create (Créer)**.

    ![Créer un profil de certificat approuvé](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Créer un profil de certificat SCEP

Le profil de certificat racine approuvé permet à iOS d’approuver automatiquement le serveur VPN. Le certificat SCEP fournit les informations d’identification du client VPN iOS au serveur VPN. Il permet à l’appareil d’authentifier en mode silencieux sans demander à l’utilisateur de l’appareil iOS un nom d’utilisateur et un mot de passe. 

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
2. Choisissez **Configuration de l’appareil** et cliquez sur **Profils**.
3. Cliquez sur **Créer un profil**. Dans **Créer un profil** :
    1. Tapez le **Nom**.
    2. Tapez la **Description**.
    3. Sélectionnez **iOS** pour la **Plateforme**.
    4. Sélectionnez **Certificat SCEP** pour le **Type de profil**.
4. Sélectionnez **Années** et tapez `2` pour la **Période de validité du certificat**.
5. Sélectionnez **Nom commun** pour **Format du nom de l’objet**.
6. Sélectionnez **Nom principal de l’utilisateur (UPN)** pour **Autre nom de l’objet**.
7. Sélectionnez **Signature numérique** et **Chiffrage de clés** pour **Utilisation de la clé**.
8. Sélectionnez **2048** pour **Taille de la clé (bits)**.
9. Cliquez sur le certificat racine et sélectionnez un certificat SCEP. Cliquez sur **OK**.
10. Tapez `Client Authentication` dans **Nom** pour **Utilisation améliorée de la clé**.
11. Tapez `1.3.6.1.5.5.7.3.2` dans **Identificateur d’objet**.
12. Cliquez sur **Ajouter**.
13. Tapez l’***URL du serveur*** et cliquez sur **Ajouter**.
14. Cliquez sur **OK**.
15. Cliquez sur **Create (Créer)**.

    ![Créer un profil de certificat SCEP](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Créer un profil VPN par application

Le profil VPN contient le certificat SCEP qui inclut les informations d’identification du client, les informations de connexion au VPN et l’indicateur VPN par application permettant d’activer la fonctionnalité VPN par application pour que l’application iOS l’utilise.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
2. Choisissez **Configuration de l’appareil** et cliquez sur **Profils**.
3. Cliquez sur **Créer un profil**. Dans **Créer un profil** :
    1. Tapez le **Nom**.
    2. Tapez la **Description**.
    3. Sélectionnez **iOS** pour la **Plateforme**.
    4. Sélectionnez **VPN** pour le **Type de profil**.
4. Sélectionnez **VPN de base**. Dans **VPN de base** :
    1. Tapez le **Nom de la connexion**.
    2. Tapez l’**Adresse IP ou FQDN**.
    3. Sélectionnez **Certificats** pour la **Méthode d’authentification**.
    4. Sélectionnez le certificat SCEP sous **Certificat d’authentification** et cliquez sur **OK**.
    5. Sélectionnez votre VPN pour le **Type de connexion**.
    6. Si nécessaire, configurez les attributs pour votre réseau VPN.
    7. Sélectionnez **Désactiver le fractionnement pour le tunneling**.
5. Cliquez sur **VPN automatique**. Dans **VPN automatique** :
    1. Sélectionnez **VPN par application** pour le **Type de VPN automatique**.
    2. Tapez l’URL du VPN et cliquez sur **Ajouter**.
    3. Cliquez sur **OK**.
6. Cliquez sur **OK**.
7. Cliquez sur **Create (Créer)**.

    ![Créer un profil VPN par application](./media/vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Associer une application au profil VPN

Après avoir ajouté votre profil VPN, associez l’application et le groupe Azure AD au profil.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
2. Choisissez **Applications mobiles**.
3. Cliquez sur **Applications**.
4. Sélectionnez l’application dans la liste des applications.
5. Cliquez sur **Affectations**.
6. Cliquez sur **Ajouter un groupe**.
7. Sélectionnez **Obligatoire** pour le **Type affectation** dans le volet**Ajouter un groupe**.
6. Sélectionnez le groupe que vous avez défini précédemment et sélectionnez **Rendre cette application obligatoire**.
8. Sélectionnez votre définition de VPN pour le **VPN**.
 
    > [!NOTE]  
    > La définition de VPN peut prendre jusqu’à une minute pour récupérer la valeur. Attendez 3 à 5 minutes avant de cliquer sur **Enregistrer**.

9. Cliquez sur **OK**, puis sur **Enregistrer**.

    ![Associer une application au VPN](./media/vpn-per-app-app-to-vpn.png)

## <a name="verify-the-connection-on-the-ios-device"></a>Vérifier la connexion sur l’appareil iOS

Une fois votre VPN par application défini et associé à votre application, vérifiez que la connexion fonctionne sur l’appareil.

### <a name="before-you-attempt-to-connect"></a>Avant d’essayer de se connecter

 - Veillez à exécuter iOS 7 ou ultérieur.
 - Veillez à déployer *toutes* les stratégies mentionnées ci-dessus sur le même groupe d’utilisateurs. Si vous ne le faites pas, vous ne pourrez pas profiter de l’expérience de VPN par application.  
 - Vérifiez que l’application VPN tierce prise en charge est installée. Les applications VPN prises en charge sont les suivantes :
    - Pulse Secure
    - Point de contrôle
    - F5
    - SonicWall

### <a name="connect-using-the-per-app-vpn"></a>Se connecter avec le VPN par application

Vérifiez l’expérience sans contact en vous connectant sans devoir sélectionner le VPN ni taper vos informations d’identification. L’expérience sans contact signifie que :

 - L’appareil ne vous demande pas d’approuver le serveur VPN. Autrement dit, vous voyez la boîte de dialogue **Approbation dynamique**.
 - Vous n’avez pas à entrer d’informations d’identification.
 - Vous êtes connecté au VPN après avoir appuyé sur le bouton de connexion.

Vérifiez la connexion sur un appareil iOS.

1. Appuyez sur l’application VPN.
2. Appuyez sur **Se connecter**.  
Le VPN se connecte sans aucune autre invite.

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Étapes suivantes

- Pour examiner les paramètres iOS, consultez [Paramètres VPN pour les appareils iOS dans Microsoft Intune](vpn-settings-ios.md).
-  Pour plus d’informations sur les paramètres VPN et Intune, consultez [Guide pratique pour configurer des paramètres VPN dans Microsoft Intune](vpn-settings-configure.md).
