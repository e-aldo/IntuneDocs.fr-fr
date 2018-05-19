---
title: Inscrire des appareils iOS - Programme d’inscription d’appareils
titleSuffix: Microsoft Intune
description: Découvrez comment inscrire des appareils iOS d’entreprise à l’aide du programme d’inscription des appareils.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7ddbf360-0c61-11e8-ba89-0ed5f89f718b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f6f16bfd148e3c386aaf0ced78381e1eed8ae47
ms.sourcegitcommit: b0ad42fe5b5627e5555b2f9e5bb81bb44dbff078
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2018
---
# <a name="automatically-enroll-ios-devices-with-apples-device-enrollment-program"></a>Inscrire automatiquement des appareils iOS avec le Programme d’inscription des appareils d’Apple

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
## <a name="prerequisites"></a>Prérequis
- Appareils achetés dans le cadre du [Programme d’inscription des appareils d’Apple](http://deploy.apple.com)
- [Autorité MDM](mdm-authority-set.md)
- [Certificat Push MDM Apple](apple-mdm-push-certificate-get.md)

## <a name="get-an-apple-dep-token"></a>Obtenir un jeton DEP Apple

Avant de pouvoir inscrire des appareils iOS à l’aide du programme DEP, vous devez obtenir un fichier de jeton (.p7m) DEP auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils DEP appartenant à votre entreprise. Il permet également à Intune de charger des profils d’inscription sur Apple et d’attribuer des appareils à ces profils.

Vous utilisez le portail DEP Apple pour créer un jeton DEP. Vous utilisez également le portail DEP pour affecter des appareils à Intune à des fins de gestion.

> [!NOTE]
> Si vous supprimez le jeton du portail classique Intune avant de migrer vers Azure, Intune risque de restaurer le jeton Apple DEP supprimé. Vous pouvez supprimer à nouveau le jeton DEP du portail Azure. Vous pouvez supprimer à nouveau le jeton DEP du portail Azure.

### <a name="step-1-download-the-intune-public-key-certificate-required-to-create-the-token"></a>Étape 1. Téléchargez le certificat de clé publique Intune nécessaire à la création du jeton.

1. Dans [Intune sur le portail Azure](https://aka.ms/intuneportal), choisissez **Inscription des appareils** > **Inscription Apple** > **Jetons du programme d’inscription** > **Ajouter**.

    ![Récupérez un jeton du programme d’inscription.](./media/device-enrollment-program-enroll-ios/image01.png)

2. Autorisez Microsoft à envoyer des informations d’utilisateur et d’appareil à Apple en sélectionnant **J’accepte**.

   ![Capture d’écran du volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple pour télécharger une clé publique.](./media/device-enrollment-program-enroll-ios-newui/add-enrollment-program-token-pane.png)

3. Choisissez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) en local. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail du programme d'inscription d'appareils d'Apple.


### <a name="step-2-use-your-key-to-download-a-token-from-apple"></a>Étape 2. Utilisez votre clé pour télécharger un jeton auprès d’Apple.

1. Choisissez **Créer un jeton pour le Programme d’inscription des appareils d’Apple** pour ouvrir le portail du programme de déploiement d’Apple, et connectez-vous avec votre ID Apple d’entreprise. Vous pouvez utiliser cet ID Apple pour renouveler votre jeton DEP.
2.  Dans le portail des [programmes de déploiement](https://deploy.apple.com) d’Apple, choisissez **Get Started** (Prise en main) pour **Programme d’inscription des appareils**.

3. Dans la page **Gérer les serveurs** choisissez **Ajouter un serveur MDM**.
4. Entrez le **Nom du serveur MDM**, puis choisissez **Suivant**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.

5. La boîte de dialogue **Ajouter &lt;nom_serveur&gt;**  s’ouvre avec le message **Charger votre clé publique**. Choisissez **Choisir un fichier** pour charger le fichier .pem, puis choisissez **Suivant**.

6. Accédez à **Programme de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Gérer les appareils**.
7. Sous **Choisir les appareils par**, spécifiez comment les appareils sont identifiés :
    - **Numéro de série**
    - **Numéro de commande**
    - **Télécharger un fichier CSV**

   ![Capture d’écran montrant le choix des appareils par numéro de série, la définition de Attribuer au serveur comme paramètre Choisir l’action, et la sélection du nom du serveur.](./media/enrollment-program-token-specify-serial.png)

8. Pour **Choisir une action**, choisissez **Affecter au serveur**, le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**. Le portail Apple affecte les appareils spécifiés au serveur Intune pour la gestion, puis affiche **Affectation terminée**.

   Dans le portail Apple, accédez à **Programmes de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Afficher l’historique d’affectation** pour afficher la liste des appareils et leur affectation aux serveurs MDM.

### <a name="step-3-save-the-apple-id-used-to-create-this-token"></a>Étape 3. Enregistrez l’ID Apple utilisé pour créer le jeton.

Dans le portail Azure d’Intune, fournissez l’ID Apple pour référence ultérieure.

![Capture d’écran : spécification de l’ID Apple utilisé pour créer le jeton du programme d’inscription et accès à ce jeton.](./media/device-enrollment-program-enroll-ios/image03.png)

### <a name="step-4-upload-your-token"></a>Étape 4. Chargez votre jeton.
Dans la zone **Jeton Apple**, accédez au fichier du certificat (.pem), choisissez **Ouvrir**, puis **Créer**. Avec le certificat Push, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits. Intune se synchronise automatiquement avec Apple pour afficher votre compte de programme d’inscription.

## <a name="create-an-apple-enrollment-profile"></a>Créer un profil d’inscription Apple

Maintenant que vous avez installé votre jeton, vous pouvez créer un profil d’inscription pour les appareils DEP. Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils lors de l’inscription.

1. Dans Intune, sur le Portail Azure, choisissez **Inscription des appareil** > **Inscription Apple** > **Jetons du programme d’inscription**.
2. Sélectionnez un jeton et choisissez **Profils**, puis **Créer un profil**.

    ![Capture d’écran Créer un profil.](./media/device-enrollment-program-enroll-ios/image04.png)

3. Dans **Créer un profil**, entrez le **Nom** et la **Description** du profil qui serviront à des fins d’administration. Les utilisateurs ne voient pas ces détails. Vous pouvez utiliser ce champ **Nom** pour créer un groupe dynamique dans Azure Active Directory. Utilisez le nom du profil pour définir le paramètre enrollmentProfileName et attribuer des appareils avec ce profil d’inscription. En savoir plus sur les [groupes dynamiques Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal#using-attributes-to-create-rules-for-device-objects).

    ![Nom et description du profil.](./media/device-enrollment-program-enroll-ios/image05.png)

4. Pour **Affinité utilisateur**, indiquez si les appareils possédant ce profil doivent être inscrits avec ou sans utilisateur attribué.
    - **Inscrire avec affinité utilisateur** : choisissez cette option pour les appareils qui appartiennent à des utilisateurs et qui veulent utiliser le Portail d’entreprise pour des services comme l’installation d’applications. Cette option permet également aux utilisateurs d’authentifier leurs appareils avec le Portail d’entreprise. L’affinité utilisateur nécessite un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [En savoir plus](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

    - **Inscrire sans affinité utilisateur** : choisissez cette option pour les appareils non affiliés à un seul utilisateur, qui effectuent des tâches sans accéder aux données de l’utilisateur local. Les applications telles que l’application Portail d’entreprise ne fonctionnent pas.

5. Si vous avez choisi **Inscrire avec affinité utilisateur**, vous avez la possibilité d’autoriser les utilisateurs à s’authentifier avec le Portail d’entreprise au lieu de l’Assistant Configuration Apple.

    ![Authentification avec le Portail d’entreprise.](./media/device-enrollment-program-enroll-ios/authenticatewithcompanyportal.png)

    > [!NOTE]
    > L’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription DEP si les propriétés de profil sont définies sur **Inscrire avec l’affinité utilisateur**. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur les appareils. Les appareils ne peuvent pas inviter les utilisateurs à changer leur mot de passe lors de leur première connexion. De plus, les utilisateurs dont les mots de passe ont expiré ne sont pas invités à réinitialiser leur mot de passe lors de l’inscription. Ils doivent le faire à partir d’un autre appareil.

6. Choisissez **Paramètres de gestion des appareils** et indiquez si vous souhaitez que les appareils possédant ce profil soient supervisés ou non.

    ![Capture d’écran Paramètres de gestion des appareils.](./media/device-enrollment-program-enroll-ios/devicemanagementsettingsblade.png)

    Les appareils **supervisés** offrent plus d’options de gestion ; le Verrouillage d’activation est par défaut désactivé. Microsoft recommande l’utilisation du Programme d’inscription des appareils comme mécanisme d’activation du mode supervisé, en particulier pour les organisations qui déploient un grand nombre d’appareils iOS.

    Les utilisateurs sont informés du fait que leurs appareils sont supervisés de deux manières :

   - L’écran de verrouillage indique : « Cet iPhone est géré par Contoso. »
   - L’écran **Paramètres** > **Général** > **À propos de** indique : « Cet iPhone est supervisé. Contoso peut surveiller votre trafic Internet et localiser cet appareil. »

     > [!NOTE]
     > Seul Apple Configurator permet de rétablir la supervision sur un appareil inscrit sans supervision. Pour cela, l’appareil iOS doit être relié à un Mac par câble USB. Découvrez plus d’informations sur ceci dans la [documentation d’Apple Configurator](http://help.apple.com/configurator/mac/2.3).

7. Choisissez si vous souhaitez ou non que l’inscription soit verrouillée pour les appareils possédant ce profil. **L’inscription verrouillée** désactive les paramètres iOS qui permettent de supprimer le profil de gestion du menu **Paramètres**. Après l’inscription de l’appareil, vous ne pourrez plus modifier ce paramètre sans réinitialiser l’appareil aux paramètres d’usine. Pour ces appareils, le Mode d’administration **Supervisé** doit avoir la valeur *Oui*. 

8. Choisissez si vous souhaitez ou non que les appareils possédant ce profil puissent **Se synchroniser avec des ordinateurs**. Si vous choisissez **Autoriser Apple Configurator par certificat**, vous devez choisir un certificat sous **Certificats Apple Configurator**.

9. Si vous avez sélectionné **Autoriser Apple Configurator par certificat** à l’étape précédente, choisissez un certificat Apple Configurator à importer.

10. Choisissez **OK**.

11. Choisissez **Paramètres de l’Assistant Configuration** pour configurer les paramètres de profil suivants : ![Personnalisation de l’Assistant Configuration.](./media/device-enrollment-program-enroll-ios/setupassistantcustom.png)


    |                 Paramètre                  |                                                                                               Description                                                                                               |
    |------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    |     <strong>Nom du service</strong>     |                                                             S’affiche quand l’utilisateur appuie sur <strong>À propos de la configuration</strong> pendant l’activation.                                                              |
    |    <strong>Numéro de téléphone du service</strong>     |                                                          S’affiche quand l’utilisateur clique sur le bouton <strong>Besoin d’aide</strong> pendant l’activation.                                                          |
    | <strong>Options de l’Assistant Configuration</strong> |                                                     Les paramètres facultatifs suivants pourront être configurés plus tard dans le menu <strong>Paramètres</strong> d’iOS.                                                      |
    |        <strong>Code secret</strong>         | Invite à saisir un code secret pendant l’activation. Exige toujours un code secret, sauf si l’appareil doit être sécurisé ou si son accès doit être contrôlé d’une autre façon (c’est-à-dire, en mode plein écran qui limite l’appareil à une seule application). |
    |    <strong>Services d’emplacement</strong>    |                                                                 Si cette option est activée, l’Assistant Configuration invite à spécifier le service pendant l’activation.                                                                  |
    |         <strong>Restauration</strong>         |                                                                Si cette option est activée, l’Assistant Configuration invite à spécifier la sauvegarde iCloud pendant l’activation.                                                                 |
    |   <strong>ID Apple et iCloud</strong>   |                         Si cette option est activée, l’Assistant Configuration invite l’utilisateur à se connecter avec un ID Apple, et l’écran Applications et données autorisera la restauration de l’appareil à partir de la sauvegarde iCloud.                         |
    |  <strong>Conditions générales</strong>   |                                                   Si cette option est activée, l’Assistant Configuration invite l’utilisateur à accepter les conditions générales d’Apple pendant l’activation.                                                   |
    |        <strong>Touch ID</strong>         |                                                                 Si cette option est activée, l’Assistant Configuration invite à spécifier ce service pendant l’activation.                                                                 |
    |        <strong>Apple Pay</strong>        |                                                                 Si cette option est activée, l’Assistant Configuration invite à spécifier ce service pendant l’activation.                                                                 |
    |          <strong>Zoom</strong>           |                                                                 Si cette option est activée, l’Assistant Configuration invite à spécifier ce service pendant l’activation.                                                                 |
    |          <strong>Siri</strong>           |                                                                 Si cette option est activée, l’Assistant Configuration invite à spécifier ce service pendant l’activation.                                                                 |
    |     <strong>Données de diagnostic</strong>     |                                                                 Si cette option est activée, l’Assistant Configuration invite à spécifier ce service pendant l’activation.                                                                 |


12. Choisissez **OK**.

13. Pour enregistrer le profil, choisissez **Créer**.

## <a name="sync-managed-devices"></a>Synchroniser des appareils gérés
Maintenant qu’Intune est autorisé à gérer vos appareils, vous pouvez synchroniser Intune avec Apple pour voir vos appareils gérés dans le portail Azure d’Intune.

1. Dans Intune, sur le Portail Azure, sélectionnez **Inscription des appareils** > **Inscription Apple** > **Jetons du programme d’inscription** > choisissez un jeton dans la liste > **Appareils** > **Synchroniser**. ![Capture d’écran du nœud Appareils du programme d’inscription sélectionné, avec choix du lien Synchroniser.](./media/device-enrollment-program-enroll-ios/image06.png)

   Pour être conforme aux conditions d’Apple relatives à un trafic de programme d’inscription acceptable, Intune impose les restrictions suivantes :
   - Une synchronisation complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune extrait toute la liste actualisée des numéros de série attribués au serveur MDM Apple connecté à Intune. Une fois qu’un appareil de programme d’inscription est supprimé du portail Intune, il ne peut pas être réimporté tant que la synchronisation complète n’a pas été exécutée.   
   - Une synchronisation est exécutée automatiquement toutes les 24 heures. Vous pouvez également synchroniser en cliquant sur le bouton **Synchroniser** (pas plus d’une fois toutes les 15 minutes). Toutes les demandes de synchronisation doivent se terminer en 15 minutes. Le bouton **Synchroniser** est désactivé tant que la synchronisation n’est pas terminée. Cette synchronisation actualise l’état existant de l’appareil et importe les nouveaux appareils affectés au serveur MDM Apple.   


## <a name="assign-an-enrollment-profile-to-devices"></a>Affecter un profil d’inscription à des appareils
Vous devez affecter un profil de programme d’inscription aux appareils pour pouvoir les inscrire.

>[!NOTE]
>Vous pouvez également affecter des numéros de série aux profils à partir du panneau **Numéros de série Apple**.

1. Dans Intune, sur le Portail Azure, sélectionnez **Inscription des appareils** > **Inscription Apple** > **Jetons du programme d’inscription** > choisissez un jeton dans la liste.
2. Sélectionnez **Appareils** > choisissez des appareils dans la liste > **Attribuer un profil**.
3. Sous **Attribuer un profil**, choisissez un profil pour les appareils, puis sélectionnez **Attribuer**.

### <a name="assign-a-default-profile"></a>Attribuer un profil par défaut

Vous pouvez choisir un profil à appliquer par défaut à tous les appareils qui s’inscrivent avec un jeton spécifique.

1. Dans Intune, sur le Portail Azure, sélectionnez **Inscription des appareils** > **Inscription Apple** > **Jetons du programme d’inscription** > choisissez un jeton dans la liste.
2. Sélectionnez **Définir un profil par défaut**, choisissez un profil dans la liste déroulante, puis sélectionnez **Enregistrer**. Ce profil s’appliquera à tous les appareils qui s’inscriront avec ce jeton.

## <a name="distribute-devices"></a>Distribuer des appareils
Vous avez activé la gestion et la synchronisation entre Apple et Intune, et affecté un profil pour permettre d’inscrire vos appareils DEP. Vous pouvez désormais distribuer les appareils aux utilisateurs. Pour les appareils avec affinité utilisateur, chaque utilisateur doit se voir attribuer une licence Intune. Les appareils sans affinité utilisateur nécessitent une licence d’appareil. Un appareil activé ne peut pas appliquer de profil d’inscription tant que l’appareil n’est pas réinitialisé aux paramètres d’usine.

Consultez [Inscrire un appareil iOS dans Intune avec le Programme d’inscription des appareils](/intune-user-help/enroll-your-device-dep-ios).

## <a name="renew-a-dep-token"></a>Renouveler un jeton DEP  
1. Accédez à deploy.apple.com.  
2. Sous **Gérer les serveurs**, choisissez votre serveur MDM associé au fichier de jeton que vous voulez renouveler.
3. Choisissez **Générer un nouveau jeton**.  
4. Choisissez **Votre jeton de serveur**.  
5. Dans [Intune, sur le Portail Azure](https://aka.ms/intuneportal), choisissez **Inscription des appareils** > **Inscription Apple** > **Jetons du programme d’inscription**.  
6. Choisissez le jeton, puis **Renouveler le jeton**.  
7. Entrez l’identifiant Apple utilisé pour créer le jeton original.  
8. Chargez le jeton qui vient d’être téléchargé.  
9. Choisissez **Renouveler le jeton**. Vous verrez la confirmation que le jeton a été renouvelé.   



