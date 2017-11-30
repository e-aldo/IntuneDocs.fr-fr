---
title: "Configurer et gérer les certificats PKCS avec Intune"
titleSuffix: Intune on Azure
description: "Créez et affectez des certificats PKCS avec Intune."
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 11/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 105b5fc73bc537eaca67a0e6943701ba25a53972
ms.sourcegitcommit: 2b35c99ca7d3dbafe2dfe1e0b9de29573db403b9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/16/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Configurer et gérer les certificats PKCS avec Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Configuration requise

Pour utiliser des certificats PKCS avec Intune, vous devez disposer de l’infrastructure suivante :

* Un domaine Active Directory Domain Services (AD DS) déjà configuré.
 
  Si vous avez besoin de plus d’informations sur l’installation et la configuration d’AD DS, consultez l’article [Conception et planification AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Une autorité de certification (AC) d’entreprise déjà configurée.

  Si vous avez besoin de plus d’informations sur l’installation et la configuration des services de certificats Active Directory (AD CS), consultez l’article [Guide pas à pas des services de certificats Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune impose d’exécuter AD CS avec une autorité de certification (AC) d’entreprise, et non avec une AC autonome.

* Un client connecté à l’AC d’entreprise.
* Une copie exportée de votre certificat racine provenant de votre AC d’entreprise.
* Microsoft Intune Certificate Connector (NDESConnectorSetup.exe), téléchargé sur votre portail Intune.
* Un serveur Windows Server disponible pour héberger Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exporter le certificat racine à partir de l’AC d’entreprise

Un certificat d’AC intermédiaire ou racine est nécessaire sur chaque appareil pour l’authentification avec un VPN, un réseau Wi-Fi et d’autres ressources. Les étapes suivantes expliquent comment récupérer le certificat requis auprès de l’AC d’entreprise concernée.

1. Ouvrez une session auprès de votre AC d’entreprise, sous un compte bénéficiant de privilèges administratifs.
2. Ouvrez une invite de commandes en tant qu’administrateur.
3. Exportez le certificat d’AC racine à un emplacement où vous pourrez accéder ultérieurement.

   Exemple :

   `certutil -ca.cert certnew.cer`

   Pour plus d’informations, consultez la page [Tâches CertUtil pour la gestion des certificats](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).


## <a name="configure-certificate-templates-on-the-certification-authority"></a>Configurer les modèles de certificats sur l’autorité de certification

1. Ouvrez une session auprès de votre AC d’entreprise, sous un compte bénéficiant de privilèges administratifs.
2. Ouvrez la console **Autorité de certification**.
3. Cliquez avec le bouton droit sur **Modèles de certificats** et sélectionnez **Gérer**.
4. Recherchez le modèle de certificat **Utilisateur**, cliquez avec le bouton droit et sélectionnez **Dupliquer le modèle**. La fenêtre **Propriétés du nouveau modèle** s’ouvre.
5. Dans l’onglet **Compatibilité** :
   * **Autorité de certification** : **Windows Server 2008 R2**
   * **Destinataire du certificat** : **Windows 7 / Server 2008 R2**
6. Sous l'onglet **Général** :
   * Dans **Nom complet du modèle**, choisissez un nom qui a du sens pour vous.

   > [!WARNING]
   > Par défaut, **Nom du modèle** est identique à **Nom complet du modèle**, *sans les espaces*. Notez le nom du modèle ; vous l’utiliserez plus tard.

7. Dans l’onglet **Traitement des demandes**, cochez la case **Autoriser l’exportation de la clé privée**.
8. Dans l’onglet **Chiffrement**, vérifiez que **Taille de clé minimale** a la valeur 2048.
9. Dans l’onglet **Nom de l’objet**, sélectionnez la case d’option **Fournir dans la demande**.
10. Dans l’onglet **Extensions**, vérifiez que vous voyez bien Système de fichiers EFS, Messagerie sécurisée et Authentification client sous **Stratégies d’application**.
    
      > [!IMPORTANT]
      > Pour les modèles de certificats iOS et macOS, sous l’onglet **Extensions**, modifiez **Utilisation de la clé** et vérifiez que l’option **Signature faisant preuve de l’origine** n’est pas sélectionnée.

11. Dans l’onglet **Sécurité**, ajoutez le compte d’ordinateur du serveur sur lequel vous avez installé Microsoft Intune Certificate Connector.
    * Accordez les autorisations **Lecture** et **Inscription** à ce compte.
12. Cliquez sur **Appliquer**, puis sur **OK** pour enregistrer le modèle de certificat.
13. Fermez la **Console Modèles de certificat**.
14. Dans la console **Autorité de certification**, cliquez avec le bouton droit sur **Modèles de certificats**, **Nouveau** et **Modèle de certificat à délivrer**.
    * Choisissez le modèle que vous avez créé lors des étapes précédentes et cliquez sur **OK**.
15. Pour que le serveur gère les certificats pour le compte des utilisateurs et appareils inscrits auprès d’Intune, suivez ces étapes :

    a. Cliquez avec le bouton droit sur l’autorité de certification et sélectionnez **Propriétés**.

    b. Dans l’onglet Sécurité, ajoutez le compte d’ordinateur du serveur sur lequel vous exécutez Microsoft Intune Certificate Connector.
      * Accordez les autorisations **Émettre et gérer des certificats** et **Demander des certificats** au compte d’ordinateur.
16. Fermez votre session auprès de l’AC d’entreprise.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Télécharger, installer et configurer Microsoft Intune Certificate Connector

![Téléchargement de Connector][ConnectorDownload]

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Accédez à **Intune**, **Configuration de l’appareil**, **Autorité de certification**, puis cliquez sur **Télécharger Certificate Connector**.
   * Enregistrez le fichier téléchargé à un emplacement où vous pouvez accéder, sur le serveur où vous effectuerez l’installation.
3. Ouvrez une session sur le serveur où vous installerez Microsoft Intune Certificate Connector.
4. Exécutez le programme d’installation et acceptez l’emplacement par défaut. Il installe le connecteur à cet endroit : C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.

      a. Sur la page Options du programme d’installation, sélectionnez **Distribution PFX** et cliquez sur **Suivant**.

   b. Cliquez sur **Installer** et attendez que l’installation se termine.

   c. Sur la page de fin, cochez la case intitulée **Lancer Intune Connector** et cliquez sur **Terminer**.

5. La fenêtre NDES Connector s’ouvre sur l’onglet **Inscription**. Pour activer la connexion à Intune, vous devez cliquer sur **Connexion** et spécifier un compte disposant d’autorisations administratives.
6. Sur l’onglet **Avancé**, vous pouvez laisser la case d’option **Utiliser le compte SYSTÈME de cet ordinateur (par défaut)** sélectionné.
7. Cliquez sur **Appliquer**, puis sur **Fermer**.
8. Revenez à présent sur le Portail Azure. Sous **Intune**, **Configuration de l’appareil**, **Autorité de certification**, vous devez voir apparaître une coche verte et le mot **Active** sous **État de la connexion** au bout de quelques minutes. Cette confirmation vous indique que votre serveur de connecteur peut communiquer avec Intune.

## <a name="create-a-device-configuration-profile"></a>Créer un profil de configuration d’appareils

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Accédez à **Intune**, **Configuration de l’appareil**, **Profils**, puis cliquez sur **Créer un profil**.

   ![Accès à Intune][NavigateIntune]

3. Remplissez les informations suivantes :
   * le **Nom** du profil ;
   * une description (facultatif) ;
   * la **Plateforme** sur laquelle le profil sera déployé ;
   * **Type de profil** : **Certificat approuvé**.
4. Accédez à **Paramètres** et fournissez le fichier .cer du certificat d’AC racine exporté précédemment.

   > [!NOTE]
   > Selon la plateforme que vous avez choisie à **l’Étape 3**, vous n’aurez pas forcément la possibilité de choisir la **Banque d’informations de destination** du certificat.

   ![Paramètres du profil][ProfileSettings]

5. Cliquez sur **OK**, puis sur **Créer** pour enregistrer votre profil.
6. Pour affecter le nouveau profil à un ou plusieurs appareils, consultez la page [Affecter des profils d’appareils Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Créer un profil de certificat PKCS

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Accédez à **Intune**, **Configuration de l’appareil**, **Profils**, puis cliquez sur **Créer un profil**.
3. Remplissez les informations suivantes :
   * le **Nom** du profil ;
   * une description (facultatif) ;
   * la **Plateforme** sur laquelle le profil sera déployé ;
   * **Type de profil** : **Certificat PKCS**.
4. Accédez à **Paramètres** et indiquez les informations suivantes :
   * **Seuil de renouvellement (%)** : la valeur recommandée est de 20 %.
   * **Période de validité du certificat** : si vous n’avez pas modifié le modèle de certificat, cette option devrait être réglée sur un an.
   * **Autorité de certification** : cette option correspond au nom de domaine complet (FQDN) interne de l’AC d’entreprise.
   * **Nom de l’autorité de certification** : cette option fait référence au nom de l’AC d’entreprise, qui peut être différent de l’élément précédent.
   * **Nom du modèle de certificat** : cette option correspond au nom du modèle créé précédemment. Rappel : Par défaut, **Nom du modèle** est identique à **Nom complet du modèle**, *sans les espaces*.
   * **Format du nom de l’objet** : réglez cette option sur **Nom commun**, sauf indication contraire.
   * **Autre nom de l’objet** : réglez cette option sur **Nom d’utilisateur principal (UPN)**, sauf indication contraire.
   * **Utilisation améliorée de la clé** : à condition que vous ayez utilisé les paramètres par défaut à l’étape 10 de la section précédente **Configurer les modèles de certificats sur l’autorité de certification**, ajoutez les **Valeurs prédéfinies**  suivantes dans la zone de sélection :
      * **Tout objet**
      * **Authentification client**
      * **Messagerie sécurisée**
   * **Certificat racine** (pour les profils Android) : cette option fait référence au fichier .cer exporté à l’étape 3 de la section précédente [Exporter le certificat racine à partir de l’AC d’entreprise](#export-the-root-certificate-from-the-enterprise-ca).

5. Cliquez sur **OK**, puis sur **Créer** pour enregistrer votre profil.
6. Pour affecter le nouveau profil à un ou plusieurs appareils, consultez l’article [Affecter des profils d’appareils Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Accéder à Intune sur le Portail Azure et créer un nouveau profil pour un certificat approuvé"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Créer un profil et charger un certificat approuvé"
[ConnectorDownload]: ./media/certificates-pfx-configure-connector-download.png "Télécharger Certificate Connector sur le Portail Azure"
