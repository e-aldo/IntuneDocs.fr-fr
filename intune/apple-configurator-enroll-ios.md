---
title: Inscrire des appareils iOS - Apple Configurator-Assistant Configuration
titleSuffix: Intune on Azure
description: "Découvrez comment utiliser Apple Configurator pour inscrire des appareils iOS d’entreprise à l’aide de l’Assistant Configuration."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb3ea2fbd8d710bcb8eccac9b4512ce8ba941fc2
ms.sourcegitcommit: 7674efb7de5ad54390801165364f5d9c58ccaf84
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Inscrire des appareils iOS à l’aide de l’outil Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune prend en charge l’inscription d’appareils iOS à l’aide d’[Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s’exécutant sur un ordinateur Mac. L’inscription avec Apple Configurator requiert que vous connectiez par USB chaque appareil iOS à un ordinateur Mac pour configurer l’inscription d’entreprise. Vous pouvez inscrire des appareils sur Intune avec Apple Configurator de deux manières :
- **Inscription Assistant Configuration** : réinitialise l’appareil aux paramètres d’usine et le prépare à l’inscription durant l’Assistant Configuration.
- **Inscription directe** : ne réinitialise pas l’appareil aux paramètres d’usine et l’inscrit avec les paramètres iOS. Cette méthode prend seulement en charge les appareils **sans affinité utilisateur**.

Vous ne pouvez pas utiliser les méthodes d’inscription Apple Configurator avec le [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

## <a name="prerequisites"></a>Prérequis

- Accès physique aux appareils iOS
- [Définir l’autorité MDM](mdm-authority-set.md)
- [Un certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- Numéros de série des appareils (inscription Assistant Configuration uniquement)
- Câbles de connexion USB
- Ordinateur Mac exécutant [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)

## <a name="create-an-apple-configurator-profile-for-devices"></a>Créer un profil Apple Configurator pour les appareils

Un profil d’inscription d’appareil définit les paramètres appliqués durant l’inscription. Ces paramètres ne sont appliqués qu’une seule fois. Suivez ces étapes pour créer un profil d’inscription en vue d’inscrire des appareils iOS avec Apple Configurator.

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Choisissez **Inscription de l’appareil** > **Inscription Apple**.
4. Dans **Gérer les paramètres d’inscription Apple Configurator**, sélectionnez **Profils AC**.
5. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez **Créer**.
6. Tapez un **Nom** et une **Description** pour le profil à des fins d’administration. Les utilisateurs ne voient pas ces détails. Vous pouvez utiliser ce champ Nom pour créer un groupe dynamique dans Azure Active Directory. Utilisez le nom du profil pour définir le paramètre enrollmentProfileName et affecter des appareils avec ce profil d’inscription. Découvrez plus en détail les groupes dynamiques Azure Active Directory.

  ![Capture d’écran de l’écran de création d’un profil avec l’option Inscrire avec l’affinité utilisateur sélectionnée](./media/apple-configurator-profile-create.png)

7. Spécifiez l’**affinité utilisateur** :
   - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur durant l’Assistant Configuration. Il peut ensuite accéder aux données et aux e-mails de l’entreprise. L’affinité utilisateur est obligatoire pour les appareils gérés qui appartiennent à des utilisateurs et qui doivent utiliser le Portail d’entreprise pour les services tels que l’installation d’applications.
   - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas. Obligatoire pour l’inscription directe.

6. Sélectionnez **Créer** pour enregistrer le profil.

## <a name="setup-assistant-enrollment"></a>Inscription Assistant Configuration

### <a name="add-apple-configurator-serial-numbers"></a>Ajouter des numéros de série Apple Configurator

**Ajouter des numéros de série Apple Configurator à Intune**

1. Créez une liste de valeurs, séparées par des virgules (.csv) avec deux colonnes, sans en-tête. Ajoutez le numéro de série dans la colonne de gauche, et les détails dans celle de droite. Le maximum actuel de la liste est de 500 lignes. Dans un éditeur de texte, la liste .csv ressemble à ceci :

    F7TLWCLBX196,détails de l’appareil</br>
    DLXQPCWVGHMJ,détails de l’appareil

   Découvrez [comment trouver le numéro de série d’un appareil iOS](https://support.apple.com/HT204073).
2. Dans le portail Azure d’Intune, choisissez **Inscription de l’appareil**, puis **Inscription Apple**.
3. Sous **Gérer les paramètres d’inscription d’Apple Configurator**, sélectionnez **Appareils Apple Configurator**.
4. Sélectionnez **Ajouter**.
5. Sélectionnez un **Profil d’inscription** à appliquer aux numéros de série que vous importez. Si vous importez un fichier qui remplace les détails existants par des nouveaux, sélectionnez **Remplacer les détails des identificateurs existants**.
6. Accédez au fichier csv de numéros de série, puis sélectionnez **Ajouter**.

### <a name="reassign-a-profile-to-device-serial-numbers"></a>Réaffecter un profil à des numéros de série d’appareils

Vous affectez un profil d’inscription quand vous importez des numéros de série iOS dans le cadre de l’inscription Apple Configurator. Intune vous permet d’affecter des profils à partir de deux endroits différents dans le portail Azure :
- **Appareils Apple Configurator**
- **Profils AC**

#### <a name="assign-from-apple-configurator-devices"></a>Affecter un profil à partir d’appareils Apple Configurator
1. Dans le portail Azure d’Intune, choisissez **Inscription de l’appareil**, puis **Inscription Apple**.
3. Dans le panneau **Appareils Apple Configurator**, sélectionnez les numéros de série auxquels vous souhaitez affecter un profil, puis **Affecter un profil**.
4. Dans le panneau **Affecter un profil**, sélectionnez le **Nouveau profil** à affecter, puis sélectionnez **Affecter**.

#### <a name="assign-from-profiles"></a>Affecter à partir de profils
1. Dans le portail Azure d’Intune, choisissez **Inscription de l’appareil**, puis **Inscription Apple**.
2. Choisissez **Profils AC** et sélectionnez le profil à affecter à des numéros de série.
3. Dans le panneau du profil, choisissez **Appareils affectés**, puis **Affecter**.
4. Appliquez un filtre pour trouver les numéros de série des appareils à affecter au profil, sélectionnez les appareils, puis choisissez **Affecter**.

### <a name="export-the-profile"></a>Exporter le profil
Une fois que vous avez créé le profil et affecté des numéros de série, vous devez exporter le profil d’Intune comme URL. Ensuite, importez-le dans Apple Configurator sur un Mac pour le déployer sur des appareils.

1. Dans le portail Azure d’Intune, choisissez **Inscription de l’appareil** > Inscription Apple** > **Profils AC**, puis choisissez le profil à exporter.
2. Dans le panneau du profil, sélectionnez **Exporter le profil**.
3. Copiez l’URL du profil. Vous pouvez l’ajouter plus tard dans Apple Configurator pour définir le profil Intune utilisé par les appareils iOS.

  Ensuite, importez ce profil dans Apple Configurator au cours de la procédure suivante pour définir le profil Intune utilisé par les appareils iOS.

### <a name="enroll-devices-with-setup-assistant"></a>Inscrire des appareils avec l’Assistant Configuration

1.  Sur un ordinateur Mac, ouvrez **Apple Configurator 2**. Dans la barre de menus, choisissez **Apple Configurator 2**, puis cliquez sur **Préférences**.
  > [!WARNING]
  > Les appareils sont réinitialisés aux paramètres d’usine durant le processus d’inscription. En guise de bonne pratique, vous devez réinitialiser l’appareil et l’allumer. Les appareils doivent afficher l’écran **Hello** quand vous les connectez.

2. Dans le volet **Préférences**, sélectionnez **Serveurs** et cliquez sur le symbole plus (« + ») pour lancer l’Assistant de serveur MDM. Choisissez **Suivant**.
3. Entrez le **Nom d’hôte ou l’URL** et l’**URL d’inscription** du serveur MDM sous Inscription Assistant Configuration pour les appareils iOS avec Microsoft Intune. Pour l’URL d’inscription, entrez l’URL du profil d’inscription exporté depuis Intune. Choisissez **Suivant**.  

  Vous pouvez ignorer sans risque un avertissement indiquant « L’URL du serveur n’est pas vérifiée ». Pour continuer, cliquez sur **Suivant** jusqu’à ce que l’Assistant soit terminé.
4.  Connectez les appareils mobiles iOS à l’ordinateur Mac à l’aide d’un adaptateur USB.
5.  Choisissez **Préparer**. Dans le volet **Prepare iOS Device** (Préparer l’appareil iOS), sélectionnez **Manual** (Manuel), puis **Next** (Suivant).
6. Dans le panneau **Enroll in MDM Server** (Inscription dans un serveur MDM), sélectionnez le nom du serveur que vous avez créé, puis cliquez sur **Next** (Suivant).
7. Dans le volet **Supervise Devices** (Surveiller les appareils), sélectionnez le niveau de surveillance, puis cliquez sur **Next** (Suivant).
8. Dans le panneau **Create an Organization** (Créer une organisation), choisissez **l’organisation** ou créez-en une, puis cliquez sur **Next** (Suivant).
9. Dans le panneau **Configure iOS Setup Assistant** (Configurer l’Assistant Configuration iOS), choisissez les étapes à présenter à l’utilisateur, puis sélectionnez **Prepare** (Préparer). Si vous y êtes invité, authentifiez-vous pour mettre à jour les paramètres d’approbation.  
10. Une fois la préparation de l’appareil iOS terminée, déconnectez le câble USB.  

### <a name="distribute-devices"></a>Distribuer des appareils
Les appareils sont désormais prêts pour l'inscription d'entreprise. Éteignez les appareils et distribuez-les aux utilisateurs. Quand les utilisateurs allument leur appareil, l’Assistant Configuration démarre.

Après avoir reçu leur appareil, les utilisateurs doivent exécuter l’Assistant Configuration. Des appareils configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils.

## <a name="direct-enrollment"></a>Inscription directe
Quand vous inscrivez directement des appareils iOS avec Apple Configurator, vous pouvez inscrire un appareil sans obtenir son numéro de série. Vous pouvez également nommer l’appareil à des fins d’identification avant qu’Intune capture son nom lors de l’inscription. L’application Portail d’entreprise n’est pas prise en charge pour les appareils inscrits directement. Cette méthode n’effectue pas une réinitialisation des paramètres d’usine de l’appareil.

Vous ne pouvez pas installer d’applications nécessitant l’affiliation de l’utilisateur (notamment l’application Portail d’entreprise utilisée pour installer des applications métier).

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exporter le profil en tant que fichier .mobileconfig sur les appareils iOS
1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Exporter le profil**, téléchargez le profil d’inscription dans [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) pour l’envoyer (push) directement comme profil de gestion sur les appareils iOS.
4. Préparez l’appareil avec Apple Configurator à l’aide de la procédure suivante.
  1. Sur un ordinateur Mac, ouvrez Apple Configurator 2.0.
  2. Connectez l’appareil iOS à l’ordinateur Mac avec un câble USB. Fermez Photos, iTunes et toutes les autres applications qui s’ouvrent quand l’appareil est détecté.
  3. Dans Apple Configurator, choisissez l’appareil iOS connecté, puis cliquez sur le bouton **Ajouter**. Les options qui peuvent être ajoutées à l’appareil s’affichent dans la liste déroulante. Choisissez **Profils**.
  4. Utilisez le sélecteur de fichiers pour sélectionner le fichier .mobileconfig que vous avez exporté à partir d’Intune, puis choisissez **Ajouter**. Le profil est ajouté à l’appareil. Si l’appareil est Non supervisé, l’installation doit être acceptée sur l’appareil.
5. Utilisez la procédure suivante pour installer le profil sur l’appareil iOS. L’appareil doit avoir terminé l’Assistant Configuration et être prêt à l’emploi. Si l’inscription entraîne des déploiements d’applications, un ID Apple doit être configuré sur l’appareil, car les déploiements d’applications exigent que vous soyez connecté à l’App Store avec un ID Apple.
   1. Déverrouillez l’appareil iOS.
   2. Dans la boîte de dialogue **Install profile** (Installer le profil) de **Management profile** (Gestion du profil), choisissez **Install** (Installer).
   3. Spécifiez le code secret de l’appareil ou l’Apple ID, si nécessaire.
   4. Acceptez l’avertissement (**Warning**), puis choisissez **Install** (Installer).
   5. Acceptez l’avertissement distant (**Remote Warning**), puis choisissez **Trust** (Approuver).
   6. Quand la boîte de dialogue **Profile Installed** (Profil installé) confirme que le profil est installé, cliquez sur **Done** (Terminé).

6. Sur l’appareil iOS, ouvrez **Settings** (Réglages) et accédez à **General (Général)** > **Device Management (Gestion des appareils)** > **Management Profile (Profil de gestion)**. Assurez-vous que l’installation du profil est répertoriée, puis vérifiez les restrictions de stratégie iOS et les applications installées. L’affichage des applications et des restrictions de stratégie sur l’appareil peut prendre jusqu’à dix minutes.

7. Distribuez des appareils. L’appareil iOS est maintenant inscrit et géré dans Intune.
