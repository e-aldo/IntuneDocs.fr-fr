---
title: Utiliser des certificats PKCS avec Microsoft Intune - Azure | Micrososft Docs
description: Découvrez comment ajouter ou créer des certificats PKCS (Public Key Cryptography Standards) avec Microsoft Intune, notamment comment exporter un certificat racine, configurer le modèle de certificat, télécharger et installer Microsoft Intune Certificate Connector, créer un profil de configuration d’appareil, créer un profil de certificat PKCS dans Azure et votre autorité de certification.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61a190be2b4685030438988dab0d0134a8fa9f9b
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
ms.locfileid: "31836185"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configurer et utiliser des certificats PKCS avec Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Les certificats servent à authentifier et à sécuriser l’accès à vos ressources d’entreprise, par exemple un réseau privé virtuel ou votre réseau Wi-Fi. Cet article explique comment exporter un certificat PKCS, puis l’ajouter à un profil Intune. 

## <a name="requirements"></a>Configuration requise

Pour utiliser des certificats PKCS avec Intune, veillez à disposer de l’infrastructure suivante :

* Un domaine Active Directory Domain Services (AD DS) déjà configuré.
 
  Pour plus d’informations sur l’installation et la configuration des services AD DS, consultez [Planification et conception des services AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Une autorité de certification (AC) d’entreprise déjà configurée.

  Pour plus d’informations sur l’installation et la configuration des services de certificats Active Directory (AD CS), consultez [Guide pas à pas des services de certificats Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Intune impose d’exécuter AD CS avec une autorité de certification (AC) d’entreprise, et non avec une AC autonome.

* Un client connecté à l’AC d’entreprise.
* Une copie exportée de votre certificat racine provenant de votre AC d’entreprise.
* Microsoft Intune Certificate Connector (NDESConnectorSetup.exe), téléchargé à partir de votre portail Intune.
* Un serveur Windows Server pour héberger Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exporter le certificat racine à partir de l’AC d’entreprise

Pour l’authentification avec un VPN, un réseau Wi-Fi et d’autres ressources, un certificat d’autorité de certification intermédiaire ou racine est nécessaire sur chaque appareil. Les étapes suivantes expliquent comment récupérer le certificat requis auprès de l’AC d’entreprise concernée.

1. Connectez-vous à votre AC d’entreprise avec un compte disposant de privilèges administratifs.
2. Ouvrez une invite de commandes en tant qu’administrateur.
3. Exportez le certificat d’AC racine (.cer) vers un emplacement où vous pourrez y accéder ultérieurement.

   Par exemple :

4. Une fois l'Assistant terminé, mais avant de fermer l'Assistant, cliquez sur **Lancer l'interface utilisateur de Certificate Connector**.

   `certutil -ca.cert certnew.cer`

   Pour plus d’informations, consultez la page [Tâches CertUtil pour la gestion des certificats](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Configurer les modèles de certificats sur l’autorité de certification

1. Connectez-vous à votre AC d’entreprise avec un compte disposant de privilèges administratifs.
2. Ouvrez la console **Autorité de certification**, cliquez avec le bouton droit sur **Modèles de certificats** et sélectionnez **Gérer**.
3. Recherchez le modèle de certificat **Utilisateur**, cliquez dessus avec le bouton droit et sélectionnez **Dupliquer le modèle**. La fenêtre **Propriétés du nouveau modèle** s’ouvre.
4. Sous l’onglet **Compatibilité** : 
   * **Autorité de certification** : **Windows Server 2008 R2**
   * **Destinataire du certificat** : **Windows 7 / Server 2008 R2**
5. Sous l'onglet **Général** :
   * Dans **Nom complet du modèle**, choisissez un nom qui a du sens pour vous.

   > [!WARNING]
   > Par défaut, **Nom du modèle** est identique à **Nom complet du modèle**, *sans les espaces*. Notez le nom du modèle, vous en aurez besoin plus tard.

6. Dans **Traitement de la demande**, sélectionnez **Autoriser l’exportation de la clé privée**.
7. Dans **Chiffrement**, vérifiez que **Taille de clé minimale** a la valeur 2048.
8. Dans **Nom du sujet**, choisissez **Fournir dans la requête**.
9. Dans **Extensions**, vérifiez que vous voyez bien Système de fichiers EFS, Messagerie sécurisée et Authentification client sous **Stratégies d’application**.
    
      > [!IMPORTANT]
      > Pour les modèles de certificats iOS, accédez à l’onglet **Extensions**, mettez à jour **Utilisation de la clé** et vérifiez que l’option **Signature faisant preuve de l’origine** n’est pas sélectionnée.

10. Dans **Sécurité**, ajoutez le compte d’ordinateur du serveur sur lequel vous avez installé Microsoft Intune Certificate Connector.
    * Accordez les autorisations **Lecture** et **Inscription** à ce compte.
11. Sélectionnez **Appliquer**, puis **OK** pour enregistrer le modèle de certificat.
12. Fermez la **Console Modèles de certificat**.
13. Dans la console **Autorité de certification**, cliquez avec le bouton droit sur **Modèles de certificats**, **Nouveau** et **Modèle de certificat à délivrer**.
    * Choisissez le modèle que vous avez créé lors des étapes précédentes et sélectionnez **OK**.
14. Pour que le serveur gère les certificats pour le compte des utilisateurs et appareils inscrits auprès d’Intune, suivez ces étapes :

    a. Cliquez avec le bouton droit sur l’autorité de certification et sélectionnez **Propriétés**.

    b. Dans l’onglet Sécurité, ajoutez le compte d’ordinateur du serveur sur lequel vous exécutez Microsoft Intune Certificate Connector.
      * Accordez les autorisations **Émettre et gérer des certificats** et **Demander des certificats** au compte d’ordinateur.
15. Déconnectez-vous de l’AC d’entreprise.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Télécharger, installer et configurer Microsoft Intune Certificate Connector

![Téléchargement de Connector][ConnectorDownload]

1. Dans le [portail Azure](https://portal.azure.com), sélectionnez **Tous les services** et filtrez sur **Intune**. Sélectionnez **Microsoft Intune**, puis **Configuration de l’appareil**. 
2. Sélectionnez **Autorité de certification**, **Ajouter**, puis **Télécharger le fichier du connecteur**. Enregistrez le fichier téléchargé à un emplacement accessible à partir du serveur où il sera installé. 
3. Connectez-vous à ce serveur, puis exécutez le programme d’installation : 

    1. Acceptez l’emplacement par défaut. Le connecteur est installé dans `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`.
    2. Dans Options du programme d’installation, sélectionnez **Distribution PFX**, puis **Suivant**.
    3. Cliquez sur **Installer** et attendez que l’installation se termine.
    4. Après cela, cochez **Lancer le connecteur Intune**, puis sélectionnez **Terminer**.

4. La fenêtre NDES Connector doit s’ouvrir et afficher l’onglet **Inscription**. Pour activer la connexion à Intune, sélectionnez **Connexion** et spécifiez un compte disposant d’autorisations administratives globales.
5. Sous l’onglet **Avancé**, laissez l’option **Utiliser le compte SYSTÈME de cet ordinateur (par défaut)** sélectionnée.
6. Cliquez sur **Appliquer**, puis sur **Fermer**.
7. Revenez au portail Azure (**Intune** > **Configuration de l’appareil** > **Autorité de certification**). Après quelques minutes, une coche verte s’affiche et l’**État de la connexion** est **Active**. Votre serveur de connecteur peut désormais communiquer avec Intune.

## <a name="create-a-device-configuration-profile"></a>Créer un profil de configuration d’appareils

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Accédez à **Intune**, **Configuration de l’appareil**, **Profils**, puis sélectionnez **Créer un profil**.

   ![Accès à Intune][NavigateIntune]

3. Entrez les propriétés suivantes :
   * le **Nom** du profil ;
   * une description (facultatif) ;
   * la **Plateforme** sur laquelle le profil sera déployé ;
   * **Type de profil** : **Certificat approuvé**.

4. Accédez à **Paramètres** et entrez le fichier .cer du certificat d’AC racine exporté précédemment.

   > [!NOTE]
   > En fonction de la plateforme que vous avez choisie à l’**Étape 3**, vous n’aurez pas forcément la possibilité de choisir le **Magasin de destination** du certificat.

   ![Paramètres du profil][ProfileSettings]

5. Sélectionnez **OK**, puis **Créer** pour enregistrer votre profil.
6. Pour affecter le nouveau profil à un ou plusieurs appareils, consultez [Affecter des profils d’appareils Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Créer un profil de certificat PKCS

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Accédez à **Intune**, **Configuration de l’appareil**, **Profils**, puis sélectionnez **Créer un profil**.
3. Entrez les propriétés suivantes :
   * le **Nom** du profil ;
   * une description (facultatif) ;
   * la **Plateforme** sur laquelle le profil sera déployé ;
   * **Type de profil** : **Certificat PKCS**.
4. Accédez à **Paramètres** et entrez les propriétés suivantes :
   * **Seuil de renouvellement (%)** : la valeur recommandée est de 20 %.
   * **Période de validité du certificat** : si vous n’avez pas changé le modèle de certificat, cette option peut être réglée sur un an.
   * **Autorité de certification** : nom de domaine complet (FQDN) interne de l’AC d’entreprise.
   * **Nom de l’autorité de certification** : indique le nom de l’AC d’entreprise, qui peut être différent de l’élément précédent.
   * **Nom du modèle de certificat** : nom du modèle créé précédemment. Rappel : Par défaut, **Nom du modèle** est identique à **Nom complet du modèle**, *sans les espaces*.
   * **Format du nom de l’objet** : réglez cette option sur **Nom commun**, sauf indication contraire.
   * **Autre nom de l’objet** : réglez cette option sur **Nom d’utilisateur principal (UPN)**, sauf indication contraire.
   * **Utilisation améliorée de la clé** : à condition que vous ayez utilisé les paramètres par défaut à l’étape 10 de la section [Configurer les modèles de certificats sur l’autorité de certification](#configure-certificate-templates-on-the-certification-authority) (dans et article), ajoutez les **Valeurs prédéfinies** suivantes de la sélection :
      * **Tout objet**
      * **Authentification client**
      * **Messagerie sécurisée**
   * **Certificat racine** (pour les profils Android) : indique le fichier .cer exporté à l’Étape 3 de la section [Exporter le certificat racine à partir de l’AC d’entreprise](#export-the-root-certificate-from-the-enterprise-ca) (dans cet article).

5. Sélectionnez **OK**, puis **Créer** pour enregistrer votre profil.
6. Pour affecter le nouveau profil à un ou plusieurs appareils, consultez l’article [Affecter des profils d’appareils Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Accéder à Intune sur le Portail Azure et créer un nouveau profil pour un certificat approuvé"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Créer un profil et charger un certificat approuvé"
[ConnectorDownload]: ./media/certificates-download-connector.png "Télécharger Certificate Connector sur le Portail Azure"  
