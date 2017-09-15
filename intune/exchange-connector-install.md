---
title: Configurer le connecteur Exchange pour EAS local avec Intune
titleSuffix: Azure portal
description: "Utiliser l’outil Connector pour permettre la communication entre Intune et le serveur Exchange Server local"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0376ea1-eb13-4f13-84da-7fd92d8cd63c
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9dc93cf0a24032eba051f770af1b35f9932acc9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="set-up-the-intune-on-premises-exchange-connector-in-microsoft-intune-azure"></a>Configurer le connecteur Exchange local de Microsoft Intune dans Microsoft Intune Azure

Les environnements Exchange Server locaux peuvent utiliser le connecteur Exchange local pour gérer l’accès des appareils aux boîtes de messagerie Exchange locales en fonction de l’inscription ou non des appareils dans Intune et de leur conformité aux stratégies de conformité Intune. Le connecteur Exchange local est également responsable de la détection des appareils mobiles qui se connectent à des serveurs Exchange locaux en synchronisant l’enregistrement Exchange Active Sync (EAS) existant avec Intune.

> [!IMPORTANT]
> Microsoft Intune prend en charge une seule connexion du connecteur Exchange local par abonnement, quel que soit le type de connecteur.

Pour configurer une connexion qui permet à Microsoft Intune de communiquer avec l’instance Exchange Server locale, vous devez suivre les étapes ci-dessous :

1.  Téléchargez le connecteur Exchange local Intune à partir du portail Azure.
2.  Installer et configurer le connecteur Exchange local d’Intune.
3.  Validez la connexion Exchange.

## <a name="on-premises-exchange-connector-requirements"></a>Configuration requise pour le connecteur Exchange local
Le tableau suivant indique la configuration requise pour l’ordinateur sur lequel vous installez le connecteur Exchange local.

|Condition requise|Plus d'informations|
|---------------|--------------------|
|Systèmes d'exploitation|Intune prend en charge le connecteur Exchange local sur un ordinateur qui exécute toutes les éditions de Windows Server 2008 SP2 64 bits, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2.<br /><br />Le connecteur n’est pas pris en charge sur une installation Server Core.|
|Microsoft Exchange|Les connecteurs locaux nécessitent Microsoft Exchange 2010 SP1 ou une version ultérieure ou la version de Microsoft Exchange Online Dedicated héritée. Pour déterminer si votre environnement Exchange Online Dedicated présente la **nouvelle** configuration ou une configuration **héritée**, contactez votre responsable de comptes.|
|Autorité de gestion des appareils mobiles| [Définit Intune comme autorité de gestion des appareils mobiles](https://docs.microsoft.com/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-mdm-authority-set).|
|Matériel|L’ordinateur sur lequel vous installez le connecteur nécessite un processeur 1,6 GHz avec 2 Go de mémoire RAM et 10 Go d’espace disque libre.|users-add.md
|Synchronisation Active Directory|Avant de pouvoir utiliser le connecteur pour connecter Intune à votre serveur Exchange Server, vous devez [configurer la synchronisation Active Directory](users-add.md) pour que vos utilisateurs et groupes de sécurité locaux soient synchronisés avec votre instance d’Azure Active Directory.|
|Logiciels supplémentaires|Une installation complète de Microsoft .NET Framework 4.5 et Windows PowerShell 2.0 doit exister sur l’ordinateur qui héberge le connecteur.|
|Réseau|L’ordinateur sur lequel vous installez le connecteur doit être dans un domaine qui entretient une relation d’approbation avec le domaine qui héberge votre instance d’Exchange Server.<br /><br />L’ordinateur nécessite des configurations qui lui permettent d’accéder au service Intune à travers les pare-feu et les serveurs proxy sur les ports 80 et 443. Les domaines utilisés par Intune comprennent manage.microsoft.com, &#42;manage.microsoft.com et &#42;.manage.microsoft.com.|


### <a name="exchange-cmdlet-requirements"></a>Spécifications des applets de commande Exchange

Vous devez créer un compte d’utilisateur Active Directory utilisé par le connecteur Exchange d’Intune. Le compte doit être autorisé à exécuter les applets de commande Windows PowerShell Exchange nécessaires suivantes :


 -   Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 -   Get-CasMailbox, Set-CasMailbox
 -   Get-ActiveSyncMailboxPolicy, Set-ActiveSyncMailboxPolicy, New-ActiveSyncMailboxPolicy, Remove-ActiveSyncMailboxPolicy
 -   Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 -   Get-ActiveSyncDeviceStatistics
 -   Get-ActiveSyncDevice
 -   Get-ExchangeServer
 -   Get-ActiveSyncDeviceClass
 -   Get-Recipient
 -   Clear-ActiveSyncDevice, Remove-ActiveSyncDevice
 -   Set-ADServerSettings
 -   Get-Command

## <a name="download-the-on-premises-exchange-connector-software-installation-package"></a>Télécharger le package d’installation du logiciel Connecteur Exchange local

1. Sur un système d’exploitation Windows Server pris en charge pour le connecteur Exchange local, ouvrez le [portail Azure](http://portal.azure.com) et connectez-vous avec un compte d’utilisateur administrateur dans le serveur Exchange local et disposant d’une licence d’utilisation d’Exchange Server.

2. Choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

3. Choisissez **Intune**, le tableau de bord Intune s’affiche, sélectionnez alors **Accès local**.

4. À partir de la section **Installation**, choisissez **Accès local - Connecteur Exchange ActiveSync**, puis **Télécharger le connecteur local**.

5.  Le connecteur Exchange local se trouve dans un dossier compressé (.zip) que vous pouvez ouvrir ou enregistrer. Dans la boîte de dialogue **Téléchargement de fichier**, choisissez **Enregistrer** pour stocker le dossier compressé dans un emplacement sécurisé.

    > [!IMPORTANT]
    > Ne renommez pas et ne déplacez pas les fichiers du dossier du connecteur Exchange local. Déplacer ou renommer le contenu du dossier entraîne l’échec de l’installation d’Exchange Connector.

## <a name="install-and-configure-the-intune-on-premises-exchange-connector"></a>Installer et configurer le connecteur Exchange local d’Intune
Procédez comme suit pour installer le connecteur Exchange local d’Intune. Le connecteur Exchange local ne peut être installé qu’une seule fois par abonnement Intune, et sur un ordinateur seulement. Si vous essayez de configurer un connecteur Exchange local supplémentaire, la connexion initiale est remplacée par la nouvelle.

1.  Sur un système d’exploitation pris en charge pour le connecteur local, extrayez les fichiers de **Exchange_Connector_Setup.zip** à un emplacement sécurisé.

2.  Une fois les fichiers extraits, ouvrez le dossier extrait et double-cliquez sur **Exchange_Connector_Setup.exe** pour installer le connecteur Exchange local.

    > [!IMPORTANT]
    > Si le dossier de destination n’est pas un emplacement sécurisé, vous devez supprimer le fichier de certificat **WindowsIntune.accountcert** après l’installation d’On-Premises Connector.

3.  Dans la boîte de dialogue **Microsoft Intune Exchange Connector**, sélectionnez **Serveur Microsoft Exchange sur site** ou **Serveur Microsoft Exchange hébergé**.

  ![Choisir le type de votre serveur Exchange](./media/intune-sa-exchange-connector-config.png)

  Pour un serveur Exchange local, spécifiez le nom du serveur ou le nom de domaine complet du serveur Exchange qui héberge le rôle **Serveur d’accès au client**.

  Pour un serveur Exchange hébergé, spécifiez l’adresse du serveur Exchange. Pour trouver l'URL du serveur Exchange hébergé :

    1. Ouvrez Outlook Web App pour Office 365.

    2. Choisissez l’icône **?** dans l’angle supérieur gauche et sélectionnez **À propos de**.

    3. Recherchez la valeur **Serveur externe POP**.

    4. Choisissez **Serveur proxy** pour spécifier les paramètres du serveur proxy pour votre serveur Exchange hébergé.
        1. Sélectionnez **Utiliser un serveur proxy lors de la synchronisation des informations de l'appareil mobile**.

        2. Entrez le **nom du serveur proxy** et le **numéro de port** à utiliser pour accéder au serveur.

        3. S’il est nécessaire de fournir des informations d’identification d’utilisateur pour accéder au serveur proxy, sélectionnez **Utiliser les informations d’identification pour la connexion au serveur proxy**. Ensuite, entrez le **domaine\utilisateur** et le **mot de passe**.

        4. Choisissez **OK**.

    5. Dans les champs **Utilisateur (Domaine\utilisateur)** et **Mot de passe**, entrez les informations d’identification nécessaires pour la connexion à votre serveur Exchange.

    6.  Fournissez les informations d’identification administratives nécessaires pour envoyer des notifications à la boîte aux lettres Exchange Server de l’utilisateur. Vous pouvez configurer ces notifications avec des stratégies d’accès conditionnel dans Intune.

        Vérifiez que le service de découverte automatique et les services web Exchange sont configurés sur le serveur d'accès au client Exchange. Pour plus d’informations, consultez [Serveur d’accès au client](https://technet.microsoft.com/library/dd298114.aspx).

    7.  Dans le champ **Mot de passe** , entrez le mot de passe de ce compte pour permettre à Intune d’accéder au serveur Exchange Server.

    8. Choisissez **Se connecter**.

    > [!NOTE]
    > La configuration de la connexion peut prendre quelques minutes.

Lors de la configuration, le connecteur Exchange stocke vos paramètres de proxy pour permettre l’accès à Internet. Si vos paramètres de proxy changent, vous devez reconfigurer le connecteur Exchange pour lui appliquer les paramètres de proxy mis à jour.

Une fois la connexion configurée par le connecteur Exchange, les appareils mobiles qui sont associés à des utilisateurs gérés dans le connecteur Exchange sont automatiquement synchronisés et ajoutés au connecteur Exchange. Cette synchronisation peut prendre un certain temps.

> [!NOTE]
> Si vous avez installé le connecteur Exchange local et qu’à un moment donné, vous supprimez la connexion Exchange, vous devez désinstaller le connecteur Exchange local de l’ordinateur où il a été installé.

## <a name="validate-the-exchange-connection"></a>Valider la connexion Exchange

Une fois que vous avez correctement configuré le connecteur Exchange, vous pouvez afficher l’état de la connexion et la dernière tentative de synchronisation réussie. Pour valider la connexion du connecteur Exchange :

- Dans le tableau de bord Intune, choisissez **Accès local**. Sous **Gérer**, sélectionnez **Accès à Exchange sur site** pour vérifier l’état de connexion.

Vous pouvez également vérifier la date et l'heure de la dernière tentative de synchronisation réussie.

## <a name="next-steps"></a>Étapes suivantes
[Création d’une stratégie d’accès conditionnel pour Exchange sur site](conditional-access-exchange-create.md)
