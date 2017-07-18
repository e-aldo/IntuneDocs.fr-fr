---
title: Inscrire des appareils iOS - Apple Configurator-Assistant Configuration
titleSuffix: Intune on Azure
description: "Découvrez comment utiliser Apple Configurator pour inscrire des appareils iOS d’entreprise à l’aide de l’Assistant Configuration."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d384cd0-b662-41e7-94f5-0c96790ab20a
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d74fbcebfe89bbafc545d11dd6316cb602db8ee
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-ios-devices-with-apple-configurator"></a>Inscrire des appareils iOS à l’aide de l’outil Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune prend en charge l’inscription d’appareils iOS d’entreprise à l’aide d’[Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) s’exécutant sur un ordinateur Mac. L’inscription avec Apple Configurator requiert que vous connectiez par USB chaque appareil iOS à un ordinateur Mac pour configurer l’inscription d’entreprise. Vous pouvez inscrire des appareils sur Intune avec Apple Configurator de deux manières :
- **Inscription Assistant de configuration** : Réinitialise l’appareil aux paramètres d’usine, le prépare à exécuter l’Assistant Configuration et installe les stratégies de l’entreprise pour le nouvel utilisateur de l’appareil. La plupart des scénarios nécessitent que la stratégie appliquée à l’appareil iOS comprenne l’affinité utilisateur pour activer l’application Portail d’entreprise Intune.
- **Inscription directe** : ne réinitialise pas l’appareil aux paramètres d’usine et l’inscrit avec une stratégie prédéfinie. Cette méthode est destinée aux appareils ne disposant **d’aucune affinité utilisateur**.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](enrollment-method-choose-ios.md).

## <a name="prerequisites"></a>Prérequis

Avant de configurer l’inscription des appareils iOS, effectuez les prérequis suivants :

- [Un certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- Accès physique aux appareils iOS
- Numéros de série des appareils (consultez [How to get an iOS serial number](https://support.apple.com//HT204308) (Guide pratique pour obtenir un numéro de série iOS))
- Câbles de connexion USB
- Ordinateur Mac avec [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)
- [Ajouter des numéros de série Apple Configurator](apple-configurator-serial-numbers-add.md)

## <a name="setup-assistant-enrollment"></a>Inscription Assistant Configuration

### <a name="create-an-apple-configurator-profile-for-devices"></a>Créer un profil Apple Configurator pour les appareils

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils. Les étapes suivantes montrent comment créer un profil d’inscription d’appareil pour les appareils iOS inscrits à l’aide d’Apple Configurator.

1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
2. Sous **Gérer les paramètres d’inscription Apple Configurator**, sélectionnez **Profils AC**.
3. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez **Créer**.
4. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.
5. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil seront inscrits avec ou sans affinité utilisateur.

   - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur pendant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. L’affinité utilisateur doit être configurée pour les appareils gérés qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour les services tels que l’installation d’applications.
   - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

6. Sélectionnez **Créer** pour enregistrer le profil.

### <a name="add-apple-configurator-serial-numbers"></a>Ajouter des numéros de série Apple Configurator

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Suivez ces étapes pour ajouter des numéros de série à Intune quand vous souhaitez [inscrire des appareils d’entreprise iOS à l’aide d’Apple Configurator avec l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md). Vous pouvez ajouter les numéros de série un par un, ou charger un fichier de valeurs séparées par des virgules (CSV) de numéros de série. Après avoir ajouté des numéros de série, vous pouvez leur attribuer un profil. Le profil contient les paramètres de gestion spécifiques que vous souhaitez appliquer aux appareils.

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](enrollment-method-choose-ios.md).

**Ajouter des numéros de série Apple Configurator à Intune**

1. Créez une liste de valeurs, séparées par des virgules (.csv) avec deux colonnes, sans en-tête. Ajoutez l’identificateur IMEI dans la colonne de gauche et les détails dans la colonne de droite. Le maximum actuel de la liste est de 500 lignes. Dans un éditeur de texte, la liste .csv ressemble à ceci :

    F7TLWCLBX196,détails de l’appareil</br>
    DLXQPCWVGHMJ,détails de l’appareil

2. Dans le portail Azure, choisissez **Inscrire des appareils**, puis **Inscription Apple**.
3. Sous **Gérer les paramètres d’inscription d’Apple Configurator**, sélectionnez **Numéros de série d’Apple Configurator**.
4. Dans le panneau **Numéros de série d’Apple Configurator**, sélectionnez **Ajouter**.
5. Dans le panneau **Ajouter des numéros de série**, sélectionnez un profil à appliquer pour les numéros de série que vous importez. Si vous importez un fichier avec de nouvelles informations pour remplacer celles qui existent, sélectionnez Remplacer les informations pour les identificateurs existants afin que les nouvelles informations remplacent celles existantes.
6. Accédez au fichier .csv de numéros de série, puis sélectionnez **Ajouter**.

### <a name="assign-a-profile-to-specific-serial-numbers"></a>Affectation d’un profil à des numéros de série spécifiques

Intune vous permet d’affecter des profils à partir de deux emplacements différents dans le portail Azure. Vous pouvez affecter par profil Apple Configurator ou par appareil.

#### <a name="assign-by-devices"></a>Affecter par appareil
1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
3. Dans le panneau **Appareils Apple Configurator**, sélectionnez les numéros de série auxquels vous souhaitez affecter un profil, puis **Affecter un profil**.
4. Dans le panneau **Affecter un profil**, sélectionnez le profil que vous souhaitez affecter, puis **Affecter**.

#### <a name="assign-by-profiles"></a>Affecter par profil
1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
2. Choisissez **Profils AC** et sélectionnez le profil auquel vous souhaitez affecter des numéros de série.
3. Dans le panneau nommé correspondant au profil, sélectionnez **Numéros de série** > **Affecter**.
4. Sélectionnez les numéros de série que vous souhaitez affecter au profil, puis sélectionnez le bouton **Affecter**.

### <a name="export-the-profile-to-ios-devices"></a>Exporter le profil sur les appareils iOS
Après avoir créé le profil et affecté des numéros de série, vous devez exporter le profil à partir d’Intune, sous forme d’URL ou sous forme de fichier au format décrit ci-dessous. Ensuite, vous l’importez manuellement dans le programme Apple Configurator sur un Mac, après quoi le programme Apple Configurator le déploie sur les appareils.

1. Dans le portail Intune, choisissez le panneau **Profils d’inscription Apple Configurator**, puis le profil à exporter.
2. Dans le panneau du profil, sélectionnez **Exporter le profil**.
3. Copiez l’URL du profil dans [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) avec l’appareil iOS attaché. Vous la chargerez dans Apple Configurator plus tard pour définir le profil Intune utilisé par les appareils iOS.

  Vous allez télécharger l’URL de ce profil sur le service Apple avec Apple Configurator au cours de la procédure suivante pour définir le profil Intune utilisé par les appareils iOS.
4. Chargez l’URL de ce profil vers le service Apple avec Apple Configurator pour définir le profil Intune utilisé par les appareils iOS.
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

## <a name="direct-enrollment"></a>Inscription directe
Quand vous inscrivez directement des appareils iOS avec Apple Configurator, vous pouvez inscrire un appareil sans obtenir son numéro de série. Vous pouvez également nommer l’appareil à des fins d’identification avant qu’Intune capture son nom lors de l’inscription. L’application Portail d’entreprise n’est pas prise en charge pour les appareils inscrits directement. Cette aide suppose que vous utilisez Apple Configurator 2.0 sur un ordinateur Mac.

1. Dans le portail Intune, choisissez **Inscription d’appareils**, **Inscription Apple**, puis sélectionnez **Profils AC**.
2. Dans le panneau **Profils d’inscription Apple Configurator**, sélectionnez **Créer**.
3. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.
4. Pour **Affinité utilisateur** choisissez **Inscrire sans affinité utilisateur** pour vous assurer que l’appareil n’est pas associé à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.
5. Sélectionnez **Créer** pour enregistrer le profil.

### <a name="export-the-profile-as-mobileconfig-to-ios-devices"></a>Exporter le profil en tant que fichier .mobileconfig sur les appareils iOS

1. Dans le panneau **Exporter le profil**, téléchargez le profil d’inscription dans [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) pour l’envoyer directement comme profil de gestion sur un appareil iOS connecté. Cette méthode n’effectue pas une réinitialisation des paramètres d’usine de l’appareil.
2. Préparez l’appareil avec Apple Configurator à l’aide de la procédure suivante.
  1. Sur un ordinateur Mac, ouvrez Apple Configurator 2.0.
  2. Connectez l’appareil iOS à l’ordinateur Mac avec un câble USB. Fermez Photos, iTunes et toutes les autres applications qui s’ouvrent quand l’appareil est détecté.
  3. Dans Apple Configurator, choisissez l’appareil iOS connecté, puis cliquez sur le bouton **Ajouter**. Les options qui peuvent être ajoutées à l’appareil s’affichent dans la liste déroulante. Choisissez **Profils**.
  4. Utilisez le sélecteur de fichiers pour sélectionner le fichier .mobileconfig que vous avez exporté à partir d’Intune, puis choisissez **Ajouter**. Le profil est ajouté à l’appareil. Si l’appareil est Non supervisé, l’installation nécessite d’être acceptée sur l’appareil.
3. Utilisez la procédure suivante pour installer le profil sur l’appareil iOS. L’appareil doit avoir terminé l’Assistant Configuration et être prêt à l’emploi. Si l’inscription entraîne des déploiements d’applications, un ID Apple doit être configuré sur l’appareil, car les déploiements d’applications nécessitent de s’être connecté à l’APP Store avec un ID Apple.
   1. Déverrouillez l’appareil iOS.
   2. Dans la boîte de dialogue **Install profile** (Installer le profil) de **Management profile** (Gestion du profil), choisissez **Install** (Installer).
   3. Spécifiez le code d’accès d’appareil ou l’Apple ID, si nécessaire.
   4. Acceptez l’avertissement (**Warning**), puis choisissez **Install** (Installer).
   5. Acceptez l’avertissement distant (**Remote Warning**), puis choisissez **Trust** (Approuver).
   6. Quand la boîte de dialogue **Profile Installed** (Profil installé) confirme que le profil est installé, cliquez sur **Done** (Terminé).

    4. Sur l’appareil iOS, ouvrez **Settings** (Réglages) et accédez à **General (Général)** > **Device Management (Gestion des appareils)** > **Management Profile (Profil de gestion)**. Assurez-vous que l’installation du profil est répertoriée, puis vérifiez les restrictions de stratégie iOS et les applications installées. L’affichage des applications et des restrictions de stratégie sur l’appareil peut prendre jusqu’à dix minutes.

    5. Distribuez des appareils. L’appareil iOS est maintenant inscrit et géré dans Intune.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installation et utilisation du portail d’entreprise par les utilisateurs sur leurs appareils

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent effectuer les étapes supplémentaires décrites ci-dessous pour terminer l’exécution de l’Assistant Configuration et installer l’application Portail d’entreprise.
