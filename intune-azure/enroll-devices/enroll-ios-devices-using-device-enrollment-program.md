---
title: "Inscrire des appareils iOS - Programme d’inscription d’appareils"
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment inscrire des appareils iOS d’entreprise à l’aide du programme d’inscription d’appareils (DEP)."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 53f1c688aad2f810d8a887435dd8d122d4f471ae
ms.openlocfilehash: d8fa3a19915076f1a603449dd426172fbc5a613a
ms.lasthandoff: 04/27/2017


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Inscrire des appareils iOS à l’aide du programme d’inscription d’appareils

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Cette rubrique aide les administrateurs informatiques à inscrire des appareils d’entreprise iOS achetés dans le cadre du [Programme d’inscription des appareils (DEP) Apple](https://deploy.apple.com). Microsoft Intune peut déployer un profil d’inscription qui inscrit les appareils DEP « à distance » afin que l’administrateur n’ait jamais à toucher aucun des appareils gérés. Un profil DEP contient les paramètres de gestion que vous souhaitez appliquer aux appareils durant l’inscription. Le package d’inscription peut inclure des options d’Assistant Configuration pour l’appareil.

>[!NOTE]
>L’inscription au programme DEP ne peut pas être utilisée avec le [gestionnaire d’inscription d’appareil](enroll-devices-using-device-enrollment-manager.md).
>De plus, si les utilisateurs inscrivent leurs appareils iOS à l’aide de l’application Portail d’entreprise et que les numéros de série de ces appareils sont ensuite importés et affectés à un profil DEP, les appareils seront désinscrits de Microsoft Intune.

**Étapes d’inscription DEP**
1. [Obtenir un jeton DEP Apple](#get-the-apple-dep-certificate)
2. [Créer un profil DEP](#create-anapple-dep-profile)
3. [Affecter des numéros de série Apple DEP à votre serveur Intune](#assign-apple-dep-serial-numbers-to-your-mdm-server)
4. [Synchroniser les appareils gérés par le programme DEP](#synchronize-dep-managed-devices)
5. [Attribuer un profil DEP aux appareils](#assign-a-dep-profile-to-devices)
6. [Distribuer des appareils aux utilisateurs](#distribute-devices-to-users)

## <a name="get-the-apple-dep-certificate"></a>Obtenir le certificat DEP Apple
Avant de pouvoir inscrire des appareils d’entreprise iOS à l’aide du programme DEP d’Apple, vous devez obtenir un fichier de certificat DEP (.p7m) auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à ce programme et appartenant à votre entreprise. Il permet également à Intune d'effectuer des chargements de profil d'inscription vers Apple et d'attribuer des appareils à ces profils.

Pour gérer les appareils iOS d’entreprise avec le programme DEP, votre organisation doit participer au programme et obtenir des appareils par le biais de ce programme. Les détails de cette procédure sont disponibles à l’adresse suivante : https://deploy.apple.com. Les avantages du programme incluent la configuration automatique des appareils sans utiliser de câble USB pour connecter chaque appareil à un ordinateur.

> [!NOTE]
> Si votre client Intune a été migré de la console classique Intune vers le portail Azure et que vous avez supprimé un jeton DEP Apple de la console d’administration Intune pendant la période de migration, ce jeton DEP peut avoir été restauré dans votre compte Intune. Vous pouvez supprimer à nouveau le jeton DEP du portail Azure.

**Étape 1. Téléchargez un certificat de clé publique Intune nécessaire à la création d’un jeton DEP Apple.**<br>
1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**. Dans le panneau Intune, choisissez **Inscription de l’appareil** > **Jeton Apple DEP**.
2. Sélectionnez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) en local. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail du programme d'inscription d'appareils d'Apple.

**Étape 2 : Téléchargez un jeton DEP Apple à partir du site web Apple approprié.**<br>
Sélectionnez [Créer un jeton DEP via les programmes de déploiement Apple](https://deploy.apple.com) (https://deploy.apple.com) et connectez-vous avec votre ID Apple d’entreprise. Vous pouvez utiliser cet ID Apple pour renouveler votre jeton DEP.

   1.  Dans le [Portail Programme d’inscription des appareils Apple](https://deploy.apple.com), accédez à **Programme d’inscription d’appareils** &gt; **Gérer les serveurs**, puis choisissez **Ajouter un serveur MDM**.
   2.  Entrez le **Nom du serveur MDM**, puis choisissez **Suivant**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.
   3.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** s’ouvre. Choisissez **Choisir un fichier** pour charger le fichier .pem, puis choisissez **Suivant**.
   4.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** affiche un lien **Votre jeton de serveur**. Téléchargez le fichier de jeton de serveur (.p7m) sur votre ordinateur, puis choisissez **Terminé**.

**Étape 3 : Entrez l’ID Apple utilisé pour créer votre jeton DEP Apple. Cet ID peut être utilisé pour renouveler votre jeton DEP Apple.**

**Étape 4 :. Accédez à votre jeton DEP Apple à télécharger. Intune se synchronise automatiquement avec votre compte DEP.**<br>
Accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Télécharger**. Avec le certificat Push, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits.

## <a name="create-an-apple-dep-profile"></a>Créer un profil DEP Apple

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils. Les étapes suivantes montrent comment créer un profil d’inscription d’appareil pour les appareils iOS inscrits à l’aide du programme DEP.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.
2. Dans le panneau Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
3. Sous **Gérer les paramètres du programme Apple DEP**, sélectionnez **Profils DEP**.
4. Dans le panneau **Profils Apple DEP**, sélectionnez **Créer**.
5. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.
6. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil seront inscrits avec ou sans affinité utilisateur.

 - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur pendant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. Choisissez l’affinité utilisateur pour les appareils gérés par DEP qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour les services tels que l’installation d’applications. Notez que l’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription sur les appareils DEP avec l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur ces appareils. Les nouveaux utilisateurs qui doivent changer leur mot de passe lors de leur première connexion ne peuvent pas y être invités pendant l’inscription sur des appareils DEP. De plus, les utilisateurs dont les mots de passe ont expiré ne sont pas invités à réinitialiser leur mot de passe lors de l’inscription DEP et doivent le faire à partir d’un autre appareil.

    >[!NOTE]
    >Dans le cas de DEP avec affinité utilisateur, un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) doit être activé pour demander un jeton utilisateur. [En savoir plus sur WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur (y compris l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionneront pas.

7. Sélectionnez **Paramètres de gestion des appareils**, configurez les paramètres de profil suivants, puis sélectionnez **Enregistrer** :

    - **Supervisé** : mode de gestion qui active plusieurs options de gestion et désactive le verrou d’activation par défaut. Si vous laissez la case désactivée, vous disposez de fonctions de gestion limitées.

    - **Inscription verrouillée** : (nécessite le Mode de gestion = Supervisé) désactive les paramètres iOS qui pourraient autoriser la suppression du profil de gestion. Si vous laissez la case désactivée, cela permet de supprimer le profil de gestion du menu Paramètres. Cet élément est défini pendant l’activation et ne peut pas être modifié sans rétablir les paramètres d’usine.

    - **Autoriser le jumelage** : spécifie si les appareils iOS peuvent se synchroniser avec les ordinateurs. Si vous choisissez **Autoriser Apple Configurator par certificat**, vous devez choisir un certificat sous **Certificats Apple Configurator**.

    - **Certificats Apple Configurator** : si vous avez choisi **Autoriser Apple Configurator par certificat** sous **Autoriser le jumelage**, sélectionnez un certificat Apple Configurator à importer.

8. Sélectionnez **Paramètres de l’Assistant Configuration**, configurez les paramètres de profil suivants, puis sélectionnez **Enregistrer** :

    - **Nom du service** : s’affiche quand les utilisateurs appuient sur **À propos de la configuration** pendant l’activation.

    - **Numéro de téléphone du service** : s’affiche quand l’utilisateur clique sur le bouton Besoin d’aide pendant l’activation.
    - **Options de l’Assistant Installation** : ces paramètres facultatifs peuvent être configurés plus tard dans le menu **Paramètres** d’iOS.
        - **Code secret** : demande un code secret pendant l’activation. Exige toujours un code secret, sauf si l’appareil doit être sécurisé ou si son accès doit être contrôlé d’une autre façon (c’est-à-dire, en mode plein écran qui limite l’appareil à une seule application).
        - **Services de localisation** : si activé, l’Assistant Installation vous invite à spécifier le service pendant l’activation
        - **Restaurer** : si activé, l’Assistant Installation invite à spécifier la sauvegarde iCloud pendant l’activation
        - **ID Apple** : si cette option est activée, iOS demande un ID Apple aux utilisateurs quand Intune tente d’installer une application sans ID. Un ID Apple est nécessaire pour télécharger des applications App Store iOS, y compris celles qui sont installées par Intune.
        - **Termes et conditions** : si cette option est activée, l’Assistant Installation invite l’utilisateur à accepter les conditions générales d’Apple pendant l’activation
        - **Touch ID** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Apple Pay** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Zoom** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Siri** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Données de diagnostic** : si cette option est activée, l’Assistant Configuration vous invite à spécifier ce service pendant l’activation

9. Pour enregistrer les paramètres de profil, sélectionnez **Créer** dans le panneau **Créer un profil d’inscription**.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Affecter des numéros de série Apple DEP à votre serveur MDM
Les numéros de série d’appareil doivent être affectés à votre serveur Intune MDM dans le portail web Apple DEP pour autoriser Intune à gérer ces appareils.

1. Accédez au [portail du Programme DEP](https://deploy.apple.com) (https://deploy.apple.com) et connectez-vous avec votre ID Apple d’entreprise.

2. Accédez à **Programme de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Gérer les appareils**.

3. Spécifiez la façon dont vous allez **Choisir des appareils**, puis fournissez les informations relatives aux appareils et spécifiez les détails par appareil : **Numéro de série**, **Numéro de commande** ou **Télécharger un fichier CSV**.

4. Choisissez **Attribuer au serveur** et le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**.

## <a name="synchronize-dep-managed-devices"></a>Synchroniser les appareils gérés par le programme DEP
Maintenant qu’Intune a reçu l’autorisation de gérer vos appareils DEP, vous pouvez synchroniser Intune avec le service DEP pour voir vos appareils gérés dans le portail Intune.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune du portail Azure, choisissez **Inscription de l’appareil**, puis **Inscription Apple**.

3. Sous **Gérer les paramètres du programme Apple DEP**, sélectionnez **Numéros de série DEP**.

4. Dans le panneau **Numéros de série Apple DEP**, sélectionnez **Synchroniser**.

5. Dans le panneau **Synchroniser**, sélectionnez **Demander une synchronisation**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

    Pour être conforme aux conditions d’Apple pour un trafic DEP acceptable, Intune impose les restrictions suivantes :
     -    Une synchronisation DEP complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise chaque numéro de série attribué à Intune par Apple, que le numéro de série ait été ou non déjà synchronisé. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.
     -    Toute demande de synchronisation doit se terminer dans un délai de 10 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.

>[!NOTE]
>Vous pouvez également affecter des numéros de série DEP aux profils à partir du panneau **Numéros de série Apple DEP**.

## <a name="assign-a-dep-profile-to-devices"></a>Attribuer un profil DEP aux appareils
Les appareils DEP gérés par Intune doivent avoir un profil DEP affecté avant inscription.

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune du portail Azure, choisissez **Inscription de l’appareil** > **Inscription Apple**, puis sélectionnez **Profils DEP**.

3. Dans la liste des **Profils d’inscription Apple DEP**, sélectionnez le profil que vous souhaitez affecter aux appareils, puis sélectionnez **Affectations d’appareils**

4. Sélectionnez **Affecter**, puis sélectionnez les appareils DEP auxquels vous souhaitez affecter ce profil. Vous pouvez filtrer pour afficher les appareils DEP disponibles :
  - **non affecté**
  - **indifférent**
  - **&lt;Nom du profil DEP&gt;**

  ![Capture d’écran du bouton d’affectation du profil DEP dans le portail Intune](media/dep-profile-assignment.png)

5. Sélectionnez les périphériques que vous voulez affecter. La case à cocher au-dessus de la colonne sélectionne jusqu'à 1 000 appareils répertoriés. Après sélection, cliquez sur **Affecter**. Pour inscrire plus de 1 000 appareils, répétez les étapes d’affectation jusqu'à ce que tous les appareils disposent d’un profil DEP.

## <a name="distribute-devices-to-users"></a>Distribuer des appareils aux utilisateurs

Vous pouvez maintenant distribuer les appareils d’entreprise aux utilisateurs. Quand un appareil DEP iOS est activé, il est inscrit pour être géré par Intune. Si l’appareil a été activé et est en cours d’utilisation, le profil ne peut pas être appliqué jusqu'à ce que l’appareil soit réinitialisé aux paramètres d’usine.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installation et utilisation du portail d’entreprise par les utilisateurs sur leurs appareils

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent effectuer les étapes supplémentaires décrites ci-dessous pour terminer l’exécution de l’Assistant Configuration et installer l’application Portail d’entreprise.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Comment les utilisateurs inscrivent des appareils iOS d’entreprise avec l’affinité utilisateur

1. Quand les utilisateurs allument leur appareil, ils sont invités à terminer l’exécution de l’Assistant Installation. Pendant l’installation, les utilisateurs sont invités à fournir leurs informations d’identification. Ils doivent utiliser les informations d’identification (c’est-à-dire, le nom d’utilisateur principal ou UPN) associées à leur abonnement dans Intune.

2. Pendant l’installation, les utilisateurs sont invités à fournir un ID Apple. Ils doivent fournir un identifiant Apple pour permettre à l’appareil d’installer le portail d’entreprise. Ils peuvent également fournir l’identifiant Apple à partir du menu des paramètres iOS après l’installation.

3. Une fois l’installation terminée, les utilisateurs doivent installer l’application Portail d’entreprise à partir de l’App Store.

4. Les utilisateurs se connectent désormais au Portail d’entreprise à l’aide de l’UPN utilisé pendant la configuration de l’appareil.

5. Une fois connectés, les utilisateurs sont invités à inscrire leurs appareils. La première étape consiste à identifier l’appareil. L’application présente la liste des appareils iOS déjà inscrits par l’entreprise et affectés au compte Intune de l’utilisateur. Il doit choisir l’appareil approprié. Si cet appareil n’est pas encore inscrit par l’entreprise, ils doivent choisir « nouvel appareil » pour poursuivre la procédure d’inscription standard.

6. Dans l’écran suivant, les utilisateurs confirment le numéro de série du nouvel appareil. Pour ce faire, les utilisateurs sélectionnent un lien qui s’affiche. Le lien lance l’application Paramètres, ce qui permet aux utilisateurs de vérifier leur numéro de série. Les utilisateurs doivent ensuite entrer les quatre derniers caractères du numéro de série dans l’application Portail d’entreprise.

   Cette étape vérifie que l’appareil est l’appareil d’entreprise inscrit dans Intune. Si le numéro de série de l’appareil ne correspond pas, l’utilisateur a sélectionné un appareil incorrect. L’utilisateur doit revenir à l’écran précédent et sélectionner un autre appareil.

7. Une fois le numéro de série vérifié, l’application Portail d’entreprise redirige l’utilisateur vers le site web Portail d’entreprise pour finaliser l’inscription. Ensuite, le site web invite les utilisateurs à retourner à l’application.

L’inscription est terminée et les utilisateurs peuvent désormais utiliser cet appareil avec l’ensemble complet de fonctionnalités.

