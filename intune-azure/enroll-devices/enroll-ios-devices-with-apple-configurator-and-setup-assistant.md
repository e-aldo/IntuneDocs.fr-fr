---
title: "Inscrire des appareils iOS - Apple Configurator - Assistant Configuration | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment utiliser Apple Configurator pour inscrire des appareils iOS d’entreprise à l’aide de l’Assistant Configuration."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: adb2fd27d7f2b3f0ef4dce6b26fcb20d74b69a00
ms.openlocfilehash: 8c6c92e6e7bd375063f2f19308fe19f6e44962ac


---

# <a name="enroll-ios-devices-with-apple-configurator-and-setup-assistant"></a>Inscrire des appareils iOS avec Apple Configurator et l’Assistant Configuration 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune prend en charge l’inscription d’appareils iOS d’entreprise à l’aide d’[Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s’exécutant sur un ordinateur Mac. Ce processus réinitialise l’appareil aux paramètres d’usine, le prépare à exécuter l’Assistant Configuration et installe les stratégies de l’entreprise pour le nouvel utilisateur de l’appareil.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](enroll-devices-using-device-enrollment-manager.md).

À l’aide d’Apple Configurator, vous pouvez réinitialiser un appareil iOS aux paramètres d’usine et le préparer à être configuré pour son nouvel utilisateur. Cette méthode implique de connecter l’appareil iOS à un ordinateur Mac via une connexion USB pour configurer l’inscription d’entreprise, et suppose que vous utilisez Apple Configurator 2.0. La plupart des scénarios nécessitent que la stratégie appliquée à l’appareil iOS comprenne l’affinité utilisateur pour activer l’application Portail d’entreprise Intune.

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](choose-ios-enrollment-method.md).

## <a name="prerequisites"></a>Conditions préalables

Avant de configurer l’inscription des appareils iOS, effectuez les préparatifs suivants :

- [Configurer des domaines](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Configurer l’autorité MDM](set-mdm-authority.md)
- [Créer des groupes](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurer le portail d’entreprise](/intune-azure/manage-apps/company-portal-app.md)
- Attribuer des licences utilisateur dans le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenir un certificat Push MDM Apple](get-an-apple-mdm-push-certificate.md)
- Assurez-vous d’avoir un accès physique aux appareils iOS
- Obtenez les numéros de série des appareils (consultez [Comment obtenir un numéro de série iOS](https://support.apple.com//HT204308))
- Disposer de câbles de connexion USB
- Vérifiez que vous disposez d’un ordinateur Mac avec [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) installé
- [Ajouter des numéros de série Apple Configurator](add-apple-configurator-serial-numbers.md)


## <a name="create-an-apple-configurator-profile-for-devices"></a>Créer un profil Apple Configurator pour les appareils

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils. Les étapes suivantes montrent comment créer un profil d’inscription d’appareil pour les appareils iOS inscrits à l’aide d’Apple Configurator.

1. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Inscription Apple**.

3. Sous **Gérer les paramètres d’inscription Apple Configurator**, sélectionnez **Profils AC**.

4. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez **Créer**.

5. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.

6. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil seront inscrits avec ou sans affinité utilisateur.

   - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur pendant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. L’affinité utilisateur doit être configurée pour les appareils gérés par DEP qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour les services tels que l’installation d’applications.

   - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

7. Sélectionnez **Créer** pour enregistrer le profil.

## <a name="assign-serial-numbers-to-an-apple-configurator-profile"></a>Affecter des numéros de série à un profil Apple Configurator

Après avoir créé les profils Apple Configurator, vous pouvez affecter des numéros de série d’appareils aux profils. Pour être en mesure d’affecter des numéros de série, vous devez d’abord les ajouter à Intune en suivant la procédure décrite dans [Ajouter des numéros de série Apple Configurator](add-apple-configurator-serial-numbers.md).

### <a name="assign-serial-numbers-to-apple-configurator-profiles"></a>Affecter des numéros de série aux profils Apple Configurator

1. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez le profil auquel vous souhaitez affecter des numéros de série.

2. Dans le panneau nommé correspondant au profil, sélectionnez **Numéros de série** > **Affecter**.

3. Sélectionnez les numéros de série que vous souhaitez affecter au profil, puis sélectionnez le bouton **Affecter**.

## <a name="export-the-profile-to-ios-devices"></a>Exporter le profil sur les appareils iOS

Après avoir créé le profil et affecté des numéros de série, vous devez exporter le profil à partir d’Intune, sous forme d’URL ou sous forme de fichier au format décrit ci-dessous. Ensuite, vous l’importez manuellement dans le programme Apple Configurator sur un Mac, après quoi le programme Apple Configurator le déploie sur les appareils.

### <a name="export-a-profile-using-setup-assistant-enrollment"></a>Exporter un profil à l’aide de l’inscription Assistant Configuration

1. Dans le panneau **Profils d’inscription Apple Configurator**, choisissez le profil à exporter.

2. Dans le panneau du profil, sélectionnez **Exporter le profil**.

3. Copiez l’URL du profil dans [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) avec l’appareil iOS attaché. Vous la chargerez dans Apple Configurator plus tard pour définir le profil Intune utilisé par les appareils iOS.

  Vous devez modifier l’URL du profil 2.0 pour prendre en charge Apple Configurator 2. Pour cela, remplacez ce code :
    ```
    https://manage.microsoft.com/EnrollmentServer/Discovery.svc/iOS/ESProxy?id=
    ```
    Par celui-ci :

    ```
    https://appleconfigurator2.manage.microsoft.com/MDMServiceConfig?id=
    ```

   Vous allez télécharger l’URL de ce profil sur le service Apple DEP avec Apple Configurator au cours de la procédure suivante pour définir le profil Intune utilisé par les appareils iOS.

4. Téléchargez l’URL de ce profil sur le service Apple DEP avec Apple Configurator pour définir le profil Intune utilisé par les appareils iOS.


    1.  Sur un ordinateur Mac, ouvrez **Apple Configurator 2**. Dans la barre de menus, choisissez **Apple Configurator 2**, puis cliquez sur **Préférences**.

         > [!WARNING]
         > Les paramètres d'usine des appareils sont rétablis pendant le processus d'inscription. En guise de bonne pratique, vous devez réinitialiser l’appareil et l’allumer. Les appareils doivent afficher l’écran **Hello** quand vous les connectez.

    2. Dans le panneau **Préférences**, sélectionnez **Serveurs** et cliquez sur le symbole plus (« + ») pour lancer l’assistant de serveur MDM. Choisissez **Suivant**.

    3. Entrez le **Nom** et l’**URL d’inscription** pour le serveur MDM issus de l’étape 6 de la section Inscription Assistant Configuration pour les appareils iOS avec Microsoft Intune. Pour l’URL d’inscription, entrez l’URL du profil d’inscription exporté depuis Intune. Choisissez **Suivant**.  

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

8.  **Distribuer des appareils**.
    Les appareils sont désormais prêts pour l'inscription d'entreprise. Éteignez les appareils et distribuez-les aux utilisateurs. Quand les utilisateurs allument leur appareil, l’Assistant Configuration démarre.

## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installation et utilisation du portail d’entreprise par les utilisateurs sur leurs appareils

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent effectuer les étapes supplémentaires décrites ci-dessous pour terminer l’exécution de l’Assistant Configuration et installer l’application Portail d’entreprise.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Comment les utilisateurs inscrivent des appareils iOS d’entreprise avec l’affinité utilisateur

1. Quand les utilisateurs allument leur appareil, ils sont invités à terminer l’exécution de l’Assistant Installation. Pendant l’installation, les utilisateurs sont invités à fournir leurs informations d’identification. Ils doivent utiliser les informations d’identification (c’est-à-dire, le nom d’utilisateur principal ou UPN) associées à leur abonnement dans Intune.

2. Pendant l’installation, les utilisateurs sont invités à fournir un ID Apple. Ils doivent fournir un identifiant Apple pour permettre à l’appareil d’installer le portail d’entreprise. Ils peuvent également fournir l’identifiant à partir du menu des paramètres iOS après l’installation.

3. Une fois l’installation terminée, l’appareil iOS doit installer l’application Portail d’entreprise à partir de l’App Store.

4. L’utilisateur peut désormais se connecter au portail d’entreprise à l’aide de l’UPN qu’il a utilisé pendant la configuration de l’appareil.

5. Une fois connectés, les utilisateurs sont invités à inscrire leurs appareils. La première étape consiste à identifier l’appareil. L’application présente la liste des appareils iOS déjà inscrits par l’entreprise et affectés au compte Intune de l’utilisateur. Il doit choisir l’appareil approprié. Si cet appareil n’est pas encore inscrit par l’entreprise, ils doivent choisir « nouvel appareil » pour poursuivre la procédure d’inscription standard.

6. Dans l’écran suivant, les utilisateurs doivent confirmer le numéro de série du nouvel appareil. Les utilisateurs peuvent appuyer sur le lien « Confirmez le numéro de série » pour lancer l’application Paramètres afin de vérifier le numéro de série. Les utilisateurs doivent ensuite entrer les quatre derniers caractères du numéro de série dans l’application Portail d’entreprise.

    Cette étape vérifie que l’appareil est l’appareil d’entreprise inscrit dans Intune. Si le numéro de série de l’appareil ne correspond pas, l’appareil sélectionné est incorrect. L’utilisateur doit revenir à l’écran précédent et sélectionner un autre appareil.

7. Une fois le numéro de série vérifié, l’application Portail d’entreprise redirige l’utilisateur vers le site web Portail d’entreprise pour finaliser l’inscription. Ensuite, le site web invite les utilisateurs à retourner à l’application.

L’inscription est terminée et les utilisateurs peuvent désormais utiliser cet appareil avec l’ensemble complet de fonctionnalités.



<!--HONumber=Feb17_HO1-->


