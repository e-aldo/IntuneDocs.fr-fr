---
title: "Inscrire des appareils iOS - Programme d’inscription d’appareils"
titlesuffix: Azure portal
description: "Découvrez comment inscrire les appareils iOS d’entreprise à l’aide du programme d’inscription d’appareils."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f472c144e9bcda965486f8e88d38aa9d27df165
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Inscrire automatiquement des appareils iOS avec le Programme d’inscription des appareils d’Apple

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique vous aide à activer l’inscription d’appareils iOS pour les appareils achetés dans le cadre du [Programme d’inscription des appareils (DEP)](https://deploy.apple.com) d’Apple. Vous pouvez activer l’inscription DEP pour un grand nombre d’appareils sans jamais les toucher. Vous pouvez expédier des appareils tels que des iPhone et iPad directement aux utilisateurs. Quand l’utilisateur active l’appareil, l’Assistant Configuration s’exécute avec les paramètres préconfigurés et l’appareil s’inscrit à la gestion.

Pour activer l’inscription DEP, vous utilisez à la fois le portail Intune et le portail DEP Apple. Une liste de numéros de série ou un numéro de bon de commande est nécessaire pour que vous puissiez affecter des appareils à Intune à des fins de gestion. Vous créez des profils d’inscription DEP contenant les paramètres appliqués aux appareils lors de l’inscription.

Notez que l’inscription DEP ne fonctionne pas avec le [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

## <a name="what-is-supervised-mode"></a>Qu’est-ce que le mode supervisé ?
Apple a introduit le mode supervisé dans iOS 5. Un appareil iOS en mode supervisé peut être géré avec plus de contrôles. Il est donc particulièrement utile pour les appareils d’entreprise. Intune prend en charge la configuration des appareils pour le mode supervisé dans le cadre du Programme d’inscription des appareils Apple. 

<!--
**Steps to enable enrollment programs from Apple**
1. [Get an Apple DEP token and assign devices](#get-the-apple-dep-token)
2. [Create an enrollment profile](#create-an-apple-enrollment-profile)
3. [Synchronize DEP-managed devices](#sync-managed-device)
4. [Assign DEP profile to devices](#assign-an-enrollment-profile-to-devices)
5. [Distribute devices to users](#end-user-experience-with-managed-devices)
-->
## <a name="prerequisites"></a>Conditions préalables
- Appareils achetés dans le cadre du [Programme d’inscription des appareils d’Apple](http://deploy.apple.com)
- [Autorité MDM](mdm-authority-set.md)
- [Certificat Push MDM Apple](apple-mdm-push-certificate-get.md)

> [!NOTE]
> L’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription DEP configurée pour l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur les appareils. Les appareils ne peuvent pas inviter les utilisateurs à changer leur mot de passe lors de leur première connexion. De plus, les utilisateurs dont les mots de passe ont expiré ne sont pas invités à réinitialiser leur mot de passe lors de l’inscription. Ils doivent le faire à partir d’un autre appareil.

## <a name="get-the-apple-dep-token"></a>Obtenir le jeton DEP d’Apple

Avant de pouvoir inscrire des appareils iOS à l’aide du programme DEP, vous devez obtenir un fichier de jeton (.p7m) DEP auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils DEP appartenant à votre entreprise. Il permet également à Intune de charger des profils d’inscription sur Apple et d’attribuer des appareils à ces profils.

Vous utilisez le portail DEP Apple pour créer un jeton DEP. Vous utilisez également le portail DEP pour affecter des appareils à Intune à des fins de gestion.

> [!NOTE]
> Si vous supprimez le jeton du portail classique Intune avant de migrer vers Azure, Intune risque de restaurer le jeton Apple DEP supprimé. Vous pouvez supprimer à nouveau le jeton DEP du portail Azure. Vous pouvez supprimer à nouveau le jeton DEP du portail Azure.

**Étape 1. Téléchargez un certificat de clé publique Intune nécessaire à la création d’un jeton DEP Apple.**<br>

1. Dans le portail Azure d’Intune, choisissez **Inscription d’appareil** > **Inscription Apple** > **Jeton du programme d’inscription**.

  ![Capture d’écran du volet Jeton du programme d’inscription dans l’espace de travail Certificats Apple.](./media/enrollment-program-token-add.png)

2. Choisissez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) en local. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail du programme d'inscription d'appareils d'Apple.

  ![Capture d’écran du volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple pour télécharger une clé publique.](./media/enrollment-program-token-download.png)

**Étape 2. Créez et téléchargez un jeton DEP d’Apple.**<br>
1. Choisissez **Créer un jeton par le biais du Programme d’inscription des appareils Apple** pour ouvrir le portail du programme de déploiement d’Apple, et connectez-vous avec votre ID Apple d’entreprise. Vous pouvez utiliser cet ID Apple pour renouveler votre jeton DEP.
2.  Dans le portail des [programmes de déploiement](https://deploy.apple.com) d’Apple, choisissez **Get Started** (Prise en main) pour **Programme d’inscription des appareils**.

3. Dans la page **Gérer les serveurs** choisissez **Ajouter un serveur MDM**.
4. Entrez le **Nom du serveur MDM**, puis choisissez **Suivant**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.

   ![Capture d’écran de l’ajout d’un nom de serveur MDM pour le programme DEP et clic sur Suivant.](./media/enrollment-program-token-add-server.png)

5. La boîte de dialogue **Ajouter &lt;nom_serveur&gt;**  s’ouvre avec le message **Charger votre clé publique**. Choisissez **Choisir un fichier** pour charger le fichier .pem, puis choisissez **Suivant**.  


7. Accédez à **Programme de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Gérer les appareils**.
8. Sous **Choisir les appareils par**, spécifiez comment les appareils sont identifiés :
    - **Numéro de série**
    - **Numéro de commande**
    - **Télécharger un fichier CSV**

   ![Capture d’écran montrant le choix des appareils par numéro de série, la définition de Attribuer au serveur comme paramètre Choisir l’action, et la sélection du nom du serveur.](./media/enrollment-program-token-specify-serial.png)

9. Pour **Choisir une action**, choisissez **Affecter au serveur**, le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**. Le portail Apple affecte les appareils spécifiés au serveur Intune pour la gestion, puis affiche **Affectation terminée**.

   Dans le portail Apple, accédez à **Programmes de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Afficher l’historique d’affectation** pour afficher la liste des appareils et leur affectation aux serveurs MDM.

**Étape 3. Entrez l’ID Apple utilisé pour créer votre jeton du programme d’inscription.**<br>Dans le portail Azure d’Intune, fournissez l’ID Apple pour référence ultérieure. Utilisez cet ID pour renouveler votre jeton de programme d’inscription à l’avenir pour éviter d’avoir à réinscrire tous vos appareils.

![Capture d’écran : spécification de l’ID Apple utilisé pour créer le jeton du programme d’inscription et accès à ce jeton.](./media/enrollment-program-token-apple-id.png)

**Étape 4 :. Accédez à votre jeton du programme d’inscription à charger.**<br>
Accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Télécharger**. Avec le certificat Push, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits. Intune se synchronise automatiquement avec Apple pour afficher votre compte de programme d’inscription.

## <a name="create-an-apple-enrollment-profile"></a>Créer un profil d’inscription Apple

Maintenant que vous avez installé votre jeton, vous pouvez créer un profil d’inscription pour les appareils DEP. Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils lors de l’inscription.

1. Dans le portail Azure d’Intune, choisissez **Inscription d’appareil** > **Inscription Apple**.
2. Sous **Programme d’inscription pour Apple**, choisissez **Profils du programme d’inscription** > **Créer**.
3. Dans **Créer un profil d’inscription**, entrez un **Nom** et une **Description** pour le profil à des fins d’administration. Les utilisateurs ne voient pas ces détails. Vous pouvez utiliser ce champ **Nom** pour créer un groupe dynamique dans Azure Active Directory. Utilisez le nom du profil pour définir le paramètre enrollmentProfileName et attribuer des appareils avec ce profil d’inscription. En savoir plus sur les [groupes dynamiques Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

  Pour **Affinité utilisateur**, indiquez si les appareils avec ce profil sont inscrits avec ou sans utilisateur affecté.

 - Choisissez **Inscrire avec l’affinité utilisateur** pour les appareils qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour des services tels que l’installation d’applications. L’affinité utilisateur nécessite un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [En savoir plus](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - Choisissez **Inscrire sans l’affinité utilisateur** pour un appareil non affilié à un seul utilisateur. Utilisez cette option pour les appareils qui effectuent des tâches sans accéder aux données de l’utilisateur local. Les applications telles que l’application Portail d’entreprise ne fonctionnent pas.

4. Choisissez **Paramètres de gestion des appareils** pour configurer les paramètres de profil suivants :

  ![Capture d’écran : choix du mode d’administration. L’appareil a les paramètres suivants : Supervisé, Inscription verrouillée, Autoriser l’appairage défini sur Refuser tout. Apple Configurator Certificates est grisé pour un nouveau profil de programme d’inscription.](./media/enrollment-program-profile-mode.png)
    - **Supervisé** : mode de gestion qui active plusieurs options de gestion et désactive le verrou d’activation par défaut. Si vous laissez la case désactivée, vous disposez de fonctions de gestion limitées. Microsoft recommande l’utilisation du Programme d’inscription des appareils comme mécanisme d’activation du mode supervisé, en particulier pour les organisations qui déploient un grand nombre d’appareils iOS.

 > [!NOTE]
 > La configuration d’un appareil pour le mode supervisé ne peut pas être effectuée avec Intune après l’inscription de cet appareil. Après l’inscription, la seule façon d’activer le mode surveillé est de connecter l’appareil iOS à un Mac avec un câble USB et d’utiliser Apple Configurator. Cette opération réinitialise l’appareil et le configure en mode supervisé. Découvrez plus d’informations sur ceci dans la [documentation d’Apple Configurator](http://help.apple.com/configurator/mac/2.3). Un appareil supervisé indique que « Cet iPhone est géré par Contoso. » sur l’écran de verrouillage, et que « Cet iPhone est supervisé. Contoso peut surveiller votre trafic Internet et localiser cet appareil. » dans **Paramètres** > **Général** > **À propos de**.

    - **Inscription verrouillée** : (nécessite le Mode de gestion = supervisé) désactive les paramètres iOS qui pourraient autoriser la suppression du profil de gestion. Si vous laissez la case désactivée, cela permet de supprimer le profil de gestion du menu Paramètres. Après l’inscription de l’appareil, vous ne pourrez plus modifier ce paramètre sans réinitialiser l’appareil aux paramètres d’usine.

  - **Activer iPad partagé** : le Programme d’inscription des appareils d’Apple ne prend pas en charge iPad partagé.

    - **Autoriser l’appairage** : spécifie si les appareils iOS peuvent se synchroniser avec les ordinateurs. Si vous avez choisi **Autoriser Apple Configurator par certificat**, vous devez choisir un certificat sous **Certificats Apple Configurator**.

    - **Certificats Apple Configurator** : si vous avez choisi **Autoriser Apple Configurator par certificat** sous **Autoriser l’appairage**, choisissez un certificat Apple Configurator à importer.

  Choisissez **Enregistrer**.

5. Choisissez **Paramètres de l’Assistant Configuration** pour configurer les paramètres de profil suivants :

  ![Capture d’écran : choix des paramètres de configuration avec les paramètres disponibles pour un nouveau profil de programme d’inscription.](./media/enrollment-program-profile-settings.png)
    - **Nom du service** : s’affiche quand les utilisateurs appuient sur **À propos de la configuration** pendant l’activation.

    - **Numéro de téléphone du service** : s’affiche quand l’utilisateur clique sur le bouton **Besoin d’aide** pendant l’activation.
    - **Options de l’Assistant Installation** : ces paramètres facultatifs peuvent être configurés plus tard dans le menu **Paramètres** d’iOS.
        - **Code secret**
        - **Services d’emplacement**
        - **Restauration**
        - **ID Apple**
        - **Conditions générales**
        - **Touch ID**
        - **Apple Pay**
        - **Zoom**
        - **Siri**
        - **Données de diagnostic**

    Choisissez **Enregistrer**.

9. Pour enregistrer les paramètres de profil, choisissez **Créer** dans le panneau **Créer un profil d’inscription**. Le profil d’inscription s’affiche dans la liste des profils d’inscription du Programme d’inscription Apple.

## <a name="sync-managed-devices"></a>Synchroniser des appareils gérés
Maintenant qu’Intune est autorisé à gérer vos appareils, vous pouvez synchroniser Intune avec Apple pour voir vos appareils gérés dans le portail Azure d’Intune.

1. Dans le portail Azure d’Intune, choisissez **Inscription d’appareil** > **Inscription Apple** > **Appareils du programme d’inscription** > **Synchroniser**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

  ![Capture d’écran : sélection du nœud Appareils du programme d’inscription et choix du lien Synchroniser.](./media/enrollment-program-device-sync.png)
  
2. Dans le panneau **Synchroniser**, choisissez **Demander une synchronisation**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

  ![Capture d’écran du panneau de synchronisation : choix du lien Demander une synchronisation.](./media/enrollment-program-device-request-sync.png)

  Pour être conforme aux conditions d’Apple relatives à un trafic de programme d’inscription acceptable, Intune impose les restrictions suivantes :
     -  Une synchronisation complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise tous les numéros de série Apple affectés à Intune. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.
     -  Toute demande de synchronisation doit se terminer dans un délai de 15 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.
     - Intune synchronise les nouveaux appareils et les appareils supprimés auprès d’Apple toutes les 24 heures.

3. Dans l’espace de travail Appareils du programme d’inscription, choisissez **Actualiser** pour voir vos appareils.

## <a name="assign-an-enrollment-profile-to-devices"></a>Affecter un profil d’inscription à des appareils
Vous devez affecter un profil de programme d’inscription aux appareils pour pouvoir les inscrire.

>[!NOTE]
>Vous pouvez également affecter des numéros de série aux profils à partir du panneau **Numéros de série Apple**.

1. Dans le portail Azure d’Intune, choisissez **Inscription d’appareil** > **Inscription Apple**, puis **Profils du programme d’inscription**.
2. Dans la liste **Profils du programme d’inscription**, choisissez le profil que vous souhaitez affecter aux appareils, puis **Affecter des appareils**.

 ![Capture d’écran des affectations d’appareils avec l’option Affecter sélectionnée.](./media/enrollment-program-device-assign.png)

3. Choisissez **Affecter**, puis les appareils auxquels vous souhaitez affecter ce profil. Vous pouvez filtrer pour afficher les appareils disponibles :
  - **non affecté**
  - **indifférent**
  - **&lt;nom du profil&gt;**
4. Choisissez les appareils à affecter. La case à cocher au-dessus de la colonne sélectionne jusqu’à 1 000 appareils listés. Après sélection, cliquez sur **Affecter**. Pour inscrire plus de 1000 appareils, répétez les étapes d’affectation jusqu’à ce qu’un profil d’inscription ait été affecté à tous les appareils.

  ![Capture d’écran du bouton d’affectation de profil du programme d’inscription dans Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices"></a>Distribuer des appareils
Vous avez activé la gestion et la synchronisation entre Apple et Intune, et affecté un profil pour permettre d’inscrire vos appareils DEP. Vous pouvez désormais distribuer les appareils aux utilisateurs. Pour les appareils avec affinité utilisateur, chaque utilisateur doit se voir attribuer une licence Intune. Les appareils sans affinité utilisateur nécessitent une licence d’appareil. Un appareil activé ne peut pas appliquer de profil d’inscription tant que l’appareil n’est pas réinitialisé aux paramètres d’usine.

Consultez [Inscrire un appareil iOS dans Intune avec le Programme d’inscription des appareils](/intune-user-help/enroll-your-device-dep-ios). 
