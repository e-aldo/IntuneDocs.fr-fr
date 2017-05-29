---
title: Inscrire des appareils iOS - Apple Configurator-Assistant Configuration
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment utiliser Apple Configurator pour inscrire des appareils iOS d’entreprise à l’aide de l’Assistant Configuration."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e6b0bc51515a2b72c7574a7ca7e29c094f3bdbdb
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Intune prend en charge l’inscription d’appareils iOS d’entreprise à l’aide d’[Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s’exécutant sur un ordinateur Mac. Ce processus réinitialise l’appareil aux paramètres d’usine, le prépare à exécuter l’Assistant Configuration et installe les stratégies de l’entreprise pour le nouvel utilisateur de l’appareil.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

À l’aide d’Apple Configurator, vous pouvez réinitialiser un appareil iOS aux paramètres d’usine et le préparer à être configuré pour son nouvel utilisateur. Cette méthode implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise, et suppose que vous utilisez Apple Configurator 2.0. La plupart des scénarios nécessitent que la stratégie appliquée à l’appareil iOS comprenne l’affinité utilisateur pour activer l’application Portail d’entreprise Intune.

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](enrollment-method-choose-ios.md).

## <a name="prerequisites"></a>Prérequis

Avant de configurer l’inscription des appareils iOS, effectuez les prérequis suivants :

- [Obtenir un certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- Assurez-vous d’avoir un accès physique aux appareils iOS
- Obtenez les numéros de série des appareils (consultez [Comment obtenir un numéro de série iOS](https://support.apple.com//HT204308))
- Disposer de câbles de connexion USB
- Vérifiez que vous disposez d’un ordinateur Mac avec [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) installé
- [Ajouter des numéros de série Apple Configurator](apple-configurator-serial-numbers-add.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Créer un profil Apple Configurator pour les appareils

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils. Les étapes suivantes montrent comment créer un profil d’inscription d’appareil pour les appareils iOS inscrits à l’aide d’Apple Configurator.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Inscription Apple**.

3. Sous **Gérer les paramètres d’inscription Apple Configurator**, sélectionnez **Profils AC**.

4. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez **Créer**.

5. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.

6. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil seront inscrits avec ou sans affinité utilisateur.

   - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur pendant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. L’affinité utilisateur doit être configurée pour les appareils gérés qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour les services tels que l’installation d’applications.

   - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

7. Sélectionnez **Créer** pour enregistrer le profil.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Affecter des numéros de série à un profil Apple Configurator

Après avoir créé les profils Apple Configurator, vous pouvez affecter des numéros de série d’appareils aux profils. Pour être en mesure d’affecter des numéros de série, vous devez d’abord les ajouter à Intune en suivant la procédure décrite dans [Ajouter des numéros de série Apple Configurator](apple-configurator-serial-numbers-add.md).

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Affecter des numéros de série aux profils Apple Configurator

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez le profil auquel vous souhaitez affecter des numéros de série.

3. Dans le panneau nommé correspondant au profil, sélectionnez **Numéros de série** > **Affecter**.

4. Sélectionnez les numéros de série que vous souhaitez affecter au profil, puis sélectionnez le bouton **Affecter**.

## <a name="export-the-profile-to-ios-devices"></a>Exporter le profil sur les appareils iOS

Après avoir créé le profil et affecté des numéros de série, vous devez exporter le profil à partir d’Intune, sous forme d’URL ou sous forme de fichier au format décrit ci-dessous. Ensuite, vous l’importez manuellement dans le programme Apple Configurator sur un Mac, après quoi le programme Apple Configurator le déploie sur les appareils.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Exporter un profil à l’aide de l’inscription Assistant Configuration

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau **Profils d’inscription Apple Configurator**, choisissez le profil à exporter.

3. Dans le panneau du profil, sélectionnez **Exporter le profil**.

4. Copiez l’URL du profil dans [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) avec l’appareil iOS attaché. Vous la chargerez dans Apple Configurator plus tard pour définir le profil Intune utilisé par les appareils iOS.

  Vous allez télécharger l’URL de ce profil sur le service Apple avec Apple Configurator au cours de la procédure suivante pour définir le profil Intune utilisé par les appareils iOS.

5. Chargez l’URL de ce profil vers le service Apple avec Apple Configurator pour définir le profil Intune utilisé par les appareils iOS.
 1.  Sur un ordinateur Mac, ouvrez **Apple Configurator 2**. Dans la barre de menus, choisissez **Apple Configurator 2**, puis cliquez sur **Préférences**.
  > [!WARNING]
  > Les paramètres d'usine des appareils sont rétablis pendant le processus d'inscription. En guise de bonne pratique, vous devez réinitialiser l’appareil et l’allumer. Les appareils doivent afficher l’écran **Hello** quand vous les connectez.

  2. Dans le volet **Préférences**, sélectionnez **Serveurs** et cliquez sur le symbole plus (« + ») pour lancer l’Assistant de serveur MDM. Choisissez **Suivant**.

  3. Entrez le **Nom d’hôte ou l’URL** et l’**URL d’inscription** du serveur MDM sous Inscription Assistant Configuration pour les appareils iOS avec Microsoft Intune. Pour l’URL d’inscription, entrez l’URL du profil d’inscription exporté depuis Intune. Choisissez **Suivant**.  

    Vous pouvez ignorer sans risque un avertissement indiquant « L’URL du serveur n’est pas vérifiée ». Pour continuer, cliquez sur **Suivant** jusqu’à ce que l’Assistant soit terminé.

  4.  Connectez les appareils mobiles iOS à l’ordinateur Mac à l’aide d’un adaptateur USB.
  > [!WARNING]
  > Les paramètres d'usine des appareils sont rétablis pendant le processus d'inscription. En guise de bonne pratique, vous devez réinitialiser l’appareil et l’allumer. Les appareils doivent afficher l’écran **Hello** quand vous lancez l’Assistant de configuration.

  5.  Choisissez **Préparer**. Dans le volet **Prepare iOS Device** (Préparer l’appareil iOS), sélectionnez **Manual** (Manuel), puis **Next** (Suivant).
  6. Dans le panneau **Enroll in MDM Server** (Inscription dans un serveur MDM), sélectionnez le nom du serveur que vous avez créé, puis cliquez sur **Next** (Suivant).
  7. Dans le volet **Supervise Devices** (Surveiller les appareils), sélectionnez le niveau de surveillance, puis cliquez sur **Next** (Suivant).
  8. Dans le panneau **Create an Organization** (Créer une organisation), choisissez **l’organisation** ou créez-en une, puis cliquez sur **Next** (Suivant).
  9. Dans le panneau **Configure iOS Setup Assistant** (Configurer l’Assistant Configuration iOS), choisissez les étapes à présenter à l’utilisateur, puis sélectionnez **Prepare** (Préparer). Si vous y êtes invité, authentifiez-vous pour mettre à jour les paramètres d’approbation.  
  10. Une fois la préparation de l’appareil iOS terminée, déconnectez le câble USB.  
6.  **Distribuer des appareils**.
    Les appareils sont désormais prêts pour l'inscription d'entreprise. Éteignez les appareils et distribuez-les aux utilisateurs. Quand les utilisateurs allument leur appareil, l’Assistant Configuration démarre.

    Voir [Guide pratique pour former vos utilisateurs finaux à Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune). Vous pouvez également diriger les utilisateurs vers [Utilisation de votre appareil iOS ou macOS avec Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installation et utilisation du portail d’entreprise par les utilisateurs sur leurs appareils

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent effectuer les étapes supplémentaires décrites ci-dessous pour terminer l’exécution de l’Assistant Configuration et installer l’application Portail d’entreprise.

