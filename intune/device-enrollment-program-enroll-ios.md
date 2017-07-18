---
title: "Inscrire des appareils iOS - Programme d’inscription d’appareils"
titleSuffix: Intune on Azure
description: "Découvrez comment inscrire les appareils iOS d’entreprise à l’aide du programme d’inscription d’appareils."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f509f5332b2f8b5f6745816f8795a9a54c10ce2d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2017
---
# <a name="set-up-ios-device-enrollment-with-device-enrollment-program"></a>Configurer l’inscription des appareils iOS avec le programme d’inscription des appareils

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique aide les administrateurs informatiques à activer l’inscription d’appareils iOS pour les appareils achetés dans le cadre du [Programme d’inscription d’appareils (DEP) Apple](https://deploy.apple.com). Microsoft Intune peut également déployer un profil d’inscription « par liaison radio » sur les appareils achetés par le biais du programme DEP. L’administrateur n’a jamais à accéder à chaque appareil géré. Un profil DEP contient des paramètres de gestion qui sont appliqués aux appareils lors de l’inscription, notamment des options de l’Assistant d’installation.

Pour activer l’inscription DEP, vous utilisez à la fois le portail Intune et le portail DEP Apple. Un numéro de commande ou liste de vos appareils DEP est également nécessaire pour que vous puissiez les affecter à Intune pour la gestion dans le portail Apple.

>[!NOTE]
>L’inscription au programme DEP ne peut pas être utilisée avec le [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

**Étapes pour activer les programmes d’inscription d’Apple**
1. [Obtenir un jeton DEP Apple et affecter des appareils](#get-the-apple-dep-certificate)
2. [Créer un profil d’inscription](#create-anapple-enrollment-profile)
3. [Synchroniser les appareils gérés par le programme DEP](#sync-dep-managed-devices)
4. [Attribuer un profil DEP aux appareils](#assign-a-dep-profile-to-devices)
5. [Distribuer des appareils aux utilisateurs](#distribute-devices-to-users)

## <a name="get-the-apple-dep-token"></a>Obtenir le jeton DEP d’Apple

Avant de pouvoir inscrire des appareils iOS d’entreprise à l’aide du programme DEP (Device Enrollment Program) d’Apple, vous devez obtenir un fichier de jeton (.p7m) approprié auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à ce programme et appartenant à votre entreprise. Il permet également à Intune d'effectuer des chargements de profil d'inscription vers Apple et d'attribuer des appareils à ces profils.

> [!NOTE]
> Si votre client Intune a été migré de la console classique Intune vers le portail Azure et que vous avez supprimé un jeton DEP Apple de la console d’administration Intune pendant la période de migration, ce jeton DEP peut avoir été restauré dans votre compte Intune. Vous pouvez supprimer à nouveau le jeton DEP du portail Azure.

**Conditions préalables**
- [Certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- Inscrit pour le [programme d’inscription des appareils d’Apple](http://deploy.apple.com)

**Étape 1. Téléchargez un certificat de clé publique Intune nécessaire à la création d’un jeton DEP Apple.**<br>
1. Dans le portail Intune, choisissez **Inscription de l’appareil**, **Inscription Apple**, puis **Jeton de programme d’inscription**.
![Capture d’écran du volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple.](./media/enrollment-program-token-add.png)
2. Sélectionnez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) en local. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail du programme d'inscription d'appareils d'Apple.
![Capture d’écran du volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple pour télécharger une clé publique.](./media/enrollment-program-token-download.png)

**Étape 2. Créez et téléchargez un jeton DEP d’Apple.**<br>
Sélectionnez **Créer un jeton par le biais du programme d’inscription d’appareils d’Apple** pour ouvrir le portail du programme de déploiement d’Apple et connectez-vous avec votre ID Apple d’entreprise. Vous pouvez utiliser cet ID Apple pour renouveler votre jeton DEP.
  ![Capture d’écran du volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple.](./media/enrollment-program-token-create.png)

  ![Capture d’écran du volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple pour télécharger une clé publique.](./media/enrollment-program-token-sign.png)
   1.  Dans le [portail Programmes de déploiement](https://deploy.apple.com) d’Apple, sélectionnez **Mise en route** pour **Programme d’inscription d’appareils**.
   ![Capture d’écran du programme d’inscription avec clic sur Get Started pour le programme d’inscription d’appareils.](./media/enrollment-program-token-started.png)
   2. Dans la page **Gérer les serveurs** choisissez **Ajouter un serveur MDM**.
   3. Entrez le **Nom du serveur MDM**, puis choisissez **Suivant**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.

   ![Capture d’écran de l’ajout d’un nom de serveur MDM pour le programme DEP et clic sur Suivant.](./media/enrollment-program-token-add-server.png)
   4.  La boîte de dialogue **Ajouter &lt;nom_serveur&gt;**  s’ouvre avec le message **Charger votre clé publique**. Choisissez **Choisir un fichier** pour charger le fichier .pem, puis choisissez **Suivant**.
   ![Capture d’écran du choix du bouton de fichier de clé publique et clic sur Suivant.](./media/enrollment-program-token-choose-file.png)
   4.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** affiche un lien **Votre jeton de serveur**. Téléchargez le fichier de jeton de serveur (.p7m) sur votre ordinateur, puis choisissez **Terminé**.
   ![Capture d’écran du choix du bouton de fichier de clé publique et clic sur Suivant.](./media/enrollment-program-token-your-token.png)
   5. Accédez à **Programme de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Gérer les appareils**.
   6. Sous **Choisir les appareils par**, spécifiez comment les appareils sont identifiés :
    - **Numéro de série**
    - **Numéro de commande**
    - **Télécharger un fichier CSV**

   ![Capture d’écran montrant le choix des appareils par numéro de série, la définition de Attribuer au serveur comme paramètre Choisir l’action, et la sélection du nom du serveur.](./media/enrollment-program-token-specify-serial.png)

   7. Dans **Choisir l’action**, sélectionnez **Attribuer au serveur**, sélectionnez le &lt;nom_du_serveur&gt; spécifié pour Microsoft Intune, puis cliquez sur **OK**. Le portail Apple affecte les appareils spécifiés au serveur Intune pour la gestion, puis affiche **Affectation terminée**.

   Dans le portail Apple, accédez à **Programmes de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Afficher l’historique d’affectation** pour afficher la liste des appareils et leur affectation aux serveurs MDM.

**Étape 3. Entrez l’ID Apple utilisé pour créer votre jeton du programme d’inscription.**<br>Dans le portail Intune, fournissez l’ID Apple pour référence ultérieure. Utilisez cet ID pour renouveler votre jeton de programme d’inscription pour éviter d’avoir à réinscrire tous vos appareils.
![Capture d’écran montrant la spécification de l’ID Apple utilisé pour créer le jeton du programme d’inscription et l’accès au jeton du programme d’inscription. ](./media/enrollment-program-token-apple-id.png)
**Étape 4. Accédez à votre jeton du programme d’inscription à charger.**<br>
Accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Télécharger**. Avec le certificat Push, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits. Intune se synchronise automatiquement avec Apple pour afficher votre compte de programme d’inscription.

## <a name="create-an-apple-enrollment-profile"></a>Créer un profil d’inscription Apple

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils lors de l’inscription.

1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
2. Sous **Programme d’inscription pour Apple**, sélectionnez **Profils du programme d’inscription**, puis sélectionnez **Créer** dans le panneau **Profils du programme d’inscription**.
![Capture d’écran montrant la sélection du lien de création pour créer un profil du programme d’inscription.](./media/enrollment-program-profile-create.png)
3. Dans le panneau **Créer un profil d’inscription**, entrez un **Nom** et une **Description** pour le profil à des fins d’administration. Les utilisateurs ne voient pas ces détails.
![Capture d’écran montrant la spécification du nom et de la description, puis la sélection de l’option Inscrire avec l’affinité utilisateur pour un nouveau profil du programme d’inscription.](./media/enrollment-program-profile-name.png)
Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil sont inscrits avec ou sans affinité utilisateur.

 - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur durant l’installation. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. Choisissez l’**affinité utilisateur** pour les appareils qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour des services tels que l’installation d’applications.

<<<<<<< HEAD
 > [!NOTE]
 > L’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription sur les appareils gérés par le programme d’inscription avec l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur ces appareils. Les nouveaux utilisateurs qui doivent changer leur mot de passe lors de leur première connexion ne peuvent pas y être invités pendant l’inscription sur des appareils. De plus, les utilisateurs dont les mots de passe ont expiré ne sont pas invités à réinitialiser leur mot de passe lors de l’inscription et doivent le faire à partir d’un autre appareil.

 >[!NOTE]
 >La gestion du programme d’inscription avec affinité utilisateur nécessite l’activation d’un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints) pour demander un jeton utilisateur. [En savoir plus sur WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
=======
    >[!NOTE]
    >Dans le cas de DEP avec affinité utilisateur, un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints) doit être activé pour demander un jeton utilisateur. [En savoir plus sur WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
>>>>>>> 0c3fe0dee88e8ef4d8ad8ad28c0f8957831dd5b3

 - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

4. Sélectionnez **Paramètres de gestion des appareils** pour configurer les paramètres de profil suivants : ![Capture d’écran montrant le choix du mode de gestion avec Supervisé, inscription verrouillée, Autoriser l’appairage défini sur Refuser tout, et les certificats Apple Configurator grisés pour un nouveau profil du programme d’inscription.](./media/enrollment-program-profile-mode.png)
    - **Supervisé** : mode de gestion qui active plusieurs options de gestion et désactive le verrou d’activation par défaut. Si vous laissez la case désactivée, vous disposez de fonctions de gestion limitées.

    - **Inscription verrouillée** : (nécessite le Mode de gestion = Supervisé) désactive les paramètres iOS qui pourraient autoriser la suppression du profil de gestion. Si vous laissez la case désactivée, cela permet de supprimer le profil de gestion du menu Paramètres. Cet élément est défini pendant l’activation et ne peut pas être modifié sans rétablir les paramètres d’usine.

    - **Autoriser l’appairage** : spécifie si les appareils iOS peuvent se synchroniser avec les ordinateurs. Si vous choisissez **Autoriser Apple Configurator par certificat**, vous devez choisir un certificat sous **Certificats Apple Configurator**.

    - **Certificats Apple Configurator** : si vous avez choisi **Autoriser Apple Configurator par certificat** sous **Autoriser le jumelage**, sélectionnez un certificat Apple Configurator à importer.

  Choisissez **Enregistrer**.

5. Sélectionnez **Paramètres de l’Assistant Configuration** pour configurer les paramètres de profil suivants : ![Capture d’écran montrant le choix des paramètres de configuration avec les paramètres disponibles pour un nouveau profil du programme d’inscription.](./media/enrollment-program-profile-settings.png)
    - **Nom du service** : s’affiche quand les utilisateurs appuient sur **À propos de la configuration** pendant l’activation.

    - **Numéro de téléphone du service** : s’affiche quand l’utilisateur clique sur le bouton Besoin d’aide pendant l’activation.
    - **Options de l’Assistant Installation** : ces paramètres facultatifs peuvent être configurés plus tard dans le menu **Paramètres** d’iOS.
        - **Code secret** : demande un code secret pendant l’activation. Exige toujours un code secret, sauf si l’appareil doit être sécurisé ou si son accès doit être contrôlé d’une autre façon (c’est-à-dire, en mode plein écran qui limite l’appareil à une seule application).
        - **Services de localisation** : si activé, l’Assistant Installation vous invite à spécifier le service pendant l’activation
        - **Restaurer** : si activé, l’Assistant Installation invite à spécifier la sauvegarde iCloud pendant l’activation
        - **ID Apple** : si cette option est activée, iOS demande un ID Apple aux utilisateurs quand Intune tente d’installer une application sans ID. Un ID Apple est nécessaire pour télécharger des applications App Store iOS, notamment celles installées par Intune.
        - **Termes et conditions** : si cette option est activée, l’Assistant Installation invite l’utilisateur à accepter les conditions générales d’Apple pendant l’activation
        - **Touch ID** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Apple Pay** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Zoom** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Siri** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Données de diagnostic** : si cette option est activée, l’Assistant Configuration vous invite à spécifier ce service pendant l’activation

    Choisissez **Enregistrer**.
9. Pour enregistrer les paramètres de profil, sélectionnez **Créer** dans le panneau **Créer un profil d’inscription**. Le profil d’inscription s’affiche dans la liste des profils d’inscription du Programme d’inscription Apple.

## <a name="sync-managed-devices"></a>Synchroniser des appareils gérés
Maintenant qu’Intune est autorisé à gérer vos appareils, vous pouvez synchroniser Intune avec Apple pour voir vos appareils gérés dans le portail Intune.

1. Dans le portail Intune, choisissez **Inscription d’appareils** &gt; **Inscription Apple** &gt; **Appareils du programme d’inscription**.
2. Sous **Appareils du programme d’inscription**, sélectionnez **Synchronisation**. Le panneau **Synchronisation** s’affiche.
![Capture d’écran du nœud Appareils du programme d’inscription sélectionné, avec choix du lien Synchroniser.](./media/enrollment-program-device-sync.png)
3. Dans le panneau **Synchroniser**, sélectionnez **Demander une synchronisation**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.
![Capture d’écran du panneau de synchronisation, avec choix du lien Demander une synchronisation.](./media/enrollment-program-device-request-sync.png)
    Pour être conforme aux conditions d’Apple relatives à un trafic de programme d’inscription acceptable, Intune impose les restrictions suivantes :
     -  Une synchronisation complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise chaque numéro de série attribué à Intune par Apple, que le numéro de série ait été ou non déjà synchronisé. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.
     -  Toute demande de synchronisation doit se terminer dans un délai de 15 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.
4. Dans l’espace de travail Appareils du programme d’inscription, choisissez **Actualiser** pour voir vos appareils.

## <a name="assign-an-enrollment-profile-to-devices"></a>Affecter un profil d’inscription à des appareils
Un profil du programme d’inscription doit être affecté aux appareils gérés par Intune avant leur inscription.

>[!NOTE]
>Vous pouvez également affecter des numéros de série aux profils à partir du panneau **Numéros de série Apple**.

1. Dans le portail Intune, choisissez **Inscription de l’appareil** > **Inscription Apple**, puis sélectionnez **Profils de programme d’inscription**.
2. Dans la liste des **Profils du programme d’inscription**, sélectionnez le profil que vous souhaitez affecter aux appareils, puis sélectionnez **Affecter des appareils**.
![Capture d’écran du panneau de synchronisation, avec choix du lien Demander une synchronisation.](./media/enrollment-program-device-assign.png)
3. Sélectionnez **Affecter**, puis sélectionnez les appareils auxquels vous souhaitez affecter ce profil. Vous pouvez filtrer pour afficher les appareils disponibles :
  - **non affecté**
  - **indifférent**
  - **&lt;nom du profil&gt;**
4. Sélectionnez les appareils que vous voulez affecter. La case à cocher au-dessus de la colonne sélectionne jusqu'à 1 000 appareils répertoriés. Après sélection, cliquez sur **Affecter**. Pour inscrire plus de 1000 appareils, répétez les étapes d’affectation jusqu’à ce qu’un profil d’inscription ait été affecté à tous les appareils.

  ![Capture d’écran du bouton d’affectation de profil du programme d’inscription dans le portail Intune](media/dep-profile-assignment.png)

## <a name="end-user-experience-with-managed-devices"></a>Expérience de l’utilisateur final avec les appareils gérés

Vous pouvez désormais distribuer les appareils aux utilisateurs. Pour les appareils avec affinité utilisateur, chaque utilisateur doit se voir attribuer une licence Intune. Si l’appareil a été activé et est en cours d’utilisation, le profil ne peut pas être appliqué jusqu'à ce que l’appareil soit réinitialisé aux paramètres d’usine. Quand l’appareil iOS gérés par le programme d’inscription est activé, l’utilisateur voit ce qui suit :  

1. **Configurer l’appareil iOS** : les utilisateurs peuvent choisir parmi les options suivantes :
  - **Configurer en tant que nouvel appareil**
  - **Restaurer à partir d’une sauvegarde iCloud**
  - **Restaurer à partir d’une sauvegarde iTunes**
2. Les utilisateurs sont informés du fait que **Microsoft va configurer automatiquement leur appareil.** Les informations de configuration supplémentaires suivantes sont également disponibles :

  **La configuration permet à Microsoft de gérer cet appareil à distance.**

  **Un administrateur peut vous aider à configurer des comptes e-mail et réseau, à installer et configurer des applications, et à gérer les paramètres à distance.**

  **Un administrateur peut désactiver des fonctionnalités, installer et supprimer des applications, surveiller et limiter le trafic Internet, et effacer à distance cet appareil.**

  **La configuration est fournie par :<br> Équipe iOS MicrosoftIntune<br> One Microsoft Way, Redmond, WA 98052 (États-Unis)**

3. Les utilisateurs sont invités à fournir le nom d’utilisateur et le mot de passe de leur compte professionnel ou scolaire.
4. Les utilisateurs sont invités à fournir leur ID Apple. Un ID Apple est nécessaire pour installer l’application Portail d’entreprise Intune et d’autres applications. Une fois les informations d’identification fournies, l’appareil installe un profil de gestion qui ne peut pas être supprimé. Le profil de gestion Intune est affiché dans **Paramètres** > **Général** > **Gestion des appareils** sur l’appareil.

Les utilisateurs peuvent maintenant finir de configurer leur appareil d’entreprise par l’intermédiaire du portail d’entreprise Intune ou de l’Assistant Configuration Apple.
