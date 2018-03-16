---
title: "Configurer l’inscription au programme Apple School Manager pour les appareils iOS"
titlesuffix: Microsoft Intune
description: "Découvrez comment configurer l’inscription au programme Apple School Manager pour les appareils iOS d’entreprise avec Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f639a61c4d481a891156383c3a23e0e1511a5fbe
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="set-up-ios-device-enrollment-with-apple-school-manager"></a>Configurer l’inscription des appareils iOS avec Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

> [!NOTE]
> ### <a name="temporary-user-interface-differences"></a>Différences temporaires d’interface utilisateur
>
>L’interface utilisateur des fonctionnalités décrites sur cette page est en cours de mise à jour. Le déploiement de ces mises à jour sur tous les comptes d’utilisateurs se déroulera jusqu’à la fin du mois d’avril.
>
>Si votre page **Inscription des appareils** ressemble à l’image ci-dessous, c’est le signe que votre compte n’est pas encore passé à la nouvelle interface utilisateur ; vous pouvez utiliser cette page d’aide.
>
>![Ancienne interface utilisateur d’Intune](./media/appleenroll-oldui.png)
>
>Si votre page **Inscription des appareils** ressemble à l’image ci-dessous, c’est le signe que vos interfaces utilisateur ont été mises à jour.  Accédez à [cette page d’aide](apple-school-manager-set-up-ios-newui.md).
>
>![Nouvelle interface utilisateur d’Intune](./media/appleenroll-newui.png)

Cette rubrique vous aide à configurer l’inscription d’appareils iOS pour les appareils achetés dans le cadre du programme [Apple School Manager](https://school.apple.com/). En utilisant Intune avec Apple School Manager, vous pouvez inscrire de grandes quantités d’appareils iOS sans jamais les avoir en main. Quand un étudiant ou un enseignant active l’appareil, l’Assistant Configuration s’exécute avec les paramètres préconfigurés et l’appareil s’inscrit à la gestion.

Pour activer l’inscription Apple School Manager, vous utilisez à la fois les portails Intune et Apple School Manager. Une liste de numéros de série ou un numéro de bon de commande est nécessaire pour que vous puissiez affecter des appareils à Intune à des fins de gestion. Vous créez des profils d’inscription DEP contenant les paramètres appliqués aux appareils lors de l’inscription.

Notez que l’inscription au programme Apple School Manager ne peut pas être utilisée avec le [Programme d’inscription des appareils d’Apple](device-enrollment-program-enroll-ios.md) ni avec le [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

**Prérequis**
- [Certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- [Autorité MDM](mdm-authority-set.md)
- [Certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- L’affinité utilisateur nécessite un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints). [En savoir plus](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).
- Appareils achetés via le programme [Apple School Management](http://school.apple.com)

>[!NOTE]
>L’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription sur les appareils Apple School Manager avec l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur ces appareils. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur les appareils. Les appareils ne peuvent pas inviter les utilisateurs à changer leur mot de passe lors de leur première connexion. De plus, les utilisateurs dont les mots de passe ont expiré ne sont pas invités à réinitialiser leur mot de passe lors de l’inscription. Ils doivent le faire à partir d’un autre appareil.

## <a name="get-the-apple-token-and-assign-devices"></a>Obtenir le jeton Apple et affecter des appareils

Avant de pouvoir inscrire des appareils iOS d’entreprise avec Apple School Manager, vous devez obtenir un fichier de jeton (.p7m) auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à Apple School Manager. Il permet également à Intune d'effectuer des chargements de profil d'inscription vers Apple et d'attribuer des appareils à ces profils. Lorsque vous vous trouvez dans le portail Apple, vous pouvez également affecter des numéros de série d’appareil à gérer.

**Étape 1. Téléchargez un certificat de clé publique Intune nécessaire à la création d’un jeton Apple.**<br>
1. Dans le [portail Azure d’Intune](https://aka.ms/intuneportal), choisissez **Inscription de l’appareil**, puis **Jeton du programme d’inscription**.

  ![Volet Jeton de programme d’inscription dans l’espace de travail Certificats Apple pour télécharger une clé publique](./media/enrollment-program-token-download.png)

2. Dans le panneau **Jeton du programme d’inscription**, choisissez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) localement. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail Apple School Manager.

**Étape 2. Téléchargez un jeton et affectez des appareils.**<br>
1. Choisissez **Créer un jeton via Apple School Manager** et connectez-vous avec votre ID Apple d’entreprise. Vous pouvez utiliser cet ID Apple pour renouveler votre jeton Apple School Manager.
2.  Dans le [portail Apple School Manager](https://school.apple.com), accédez à **Serveurs de gestion des appareils mobiles**, puis choisissez **Ajouter un serveur MDM** (en haut à droite).
3.  Saisissez le **nom du serveur MDM**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.
   ![Portail Apple School Manager avec l’option Numéro de série sélectionnée](./media/asm-server-assignment.png)

4.  Choisissez **Télécharger un fichier...**  dans le portail Apple, recherchez le fichier .pem, puis choisissez **Enregistrer un serveur MDM** (en bas à droite).
5.  Choisissez **Obtenir un jeton** puis téléchargez le fichier de jeton de serveur (.p7m) sur votre ordinateur.
6. Accédez à **Affectations d’appareil** et **Choisir appareil** par saisie manuelle des **numéros de série**, **numéro d’ordre**, ou **téléchargement de fichier CSV**.
     ![Portail Apple School Manager avec l’option Numéro de série sélectionnée](./media/asm-device-assignment.png)
7.  Choisissez l’action **Affecter au serveur**, puis choisissez le **serveur MDM** que vous avez créé.
8. Spécifiez comment **choisir des appareils**, puis fournissez des informations et détails sur les appareils.
9. Choisissez **Attribuer au serveur** et le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**.

**Étape 3. Entrez l’ID Apple utilisé pour créer votre jeton Apple School Manager.**<br>Cet ID doit être utilisé pour renouveler votre jeton Apple School Manager et est stocké pour référence ultérieure.

![Spécification de l’ID Apple utilisé pour créer le jeton du programme d’inscription et accès à ce jeton](./media/enrollment-program-token-apple-id.png)

**Étape 4 :. Localisez et téléchargez votre jeton.**<br>
Accédez au fichier du certificat (.p7m), choisissez **Ouvrir**, puis **Télécharger**. Intune synchronise automatiquement vos appareils Apple School Manager auprès d’Apple.

## <a name="create-an-apple-enrollment-profile"></a>Créer un profil d’inscription Apple
Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils lors de l’inscription.

1. Dans le portail Azure d’Intune, choisissez **Inscription de l’appareil**, puis **Inscription Apple**.
2. Sous **Programme d’inscription**, choisissez **Profils de programme d’inscription**.
3. Dans le panneau **Profils de programme d’inscription**, choisissez **Créer**.
4. Dans le panneau **Créer un profil d’inscription**, entrez un **nom** et une **description** pour le profil qui s’affiche dans Intune.
5. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil sont inscrits avec ou sans affinité utilisateur.

 - **Inscrire avec l’affinité utilisateur** : affilie l’appareil à un utilisateur durant l’installation.

  Le mode iPad partagé d’Apple School Manager nécessite l’inscription de l’utilisateur sans une affinité utilisateur.

 - Choisissez **Inscrire sans l’affinité utilisateur** pour un appareil non affilié à un seul utilisateur, par exemple un appareil partagé. Utilisez cette option pour les appareils qui effectuent des tâches sans accéder aux données de l’utilisateur local. Les applications telles que l’application Portail d’entreprise ne fonctionnent pas.

6. Choisissez **Paramètres de gestion des appareils**. Ces éléments sont définis lors de l’activation et nécessitent une réinitialisation aux paramètres d’usine pour être modifiés. Configurez les paramètres de profil suivants, puis choisissez **Enregistrer** :

  ![Choix du mode de gestion](./media/enrollment-program-profile-mode.png)

    - **Supervisé** : mode de gestion qui active plusieurs options de gestion et désactive le verrou d’activation par défaut. Si vous laissez la case désactivée, vous disposez de fonctions de gestion limitées.

     - **Inscription verrouillée** : (nécessite le Mode de gestion = supervisé) désactive les paramètres iOS qui pourraient autoriser la suppression du profil de gestion. Si vous laissez la case désactivée, cela permet de supprimer le profil de gestion du menu Paramètres.
   - **iPad partagé** : (nécessite une **inscription sans affinité utilisateur** et le mode supervisé.) Permet à plusieurs utilisateurs de se connecter à des iPad inscrits en utilisant un ID Apple géré. Les ID Apple gérés sont créés dans le portail Apple School Manager. Découvrez plus d’informations sur [l’iPad partagé](education-settings-configure-ios-shared.md). Examinez également les [spécifications pour iPad partagé d’Apple](https://help.apple.com/classroom/ipad/2.0/#/cad7e2e0cf56).

   >[!NOTE]
   >Si **Affinité utilisateur** a la valeur **With user affinity** (Avec affinité utilisateur) ou que le mode **Supervisé** a la valeur **Désactivé**, le mode iPad partagé est désactivé pour le profil d’inscription.

        - **Maximum Cached Users** - (Requires **Shared iPad** = **Yes**) Creates a partition on the device for each user. The recommended value is the number of students likely to use the device over a period of time. For example, if six students use the device regularly during the week, set this number to six.  

    - **Autoriser le jumelage** : spécifie si les appareils iOS peuvent se synchroniser avec les ordinateurs. Si vous choisissez **Autoriser Apple Configurator par certificat**, vous devez choisir un certificat sous **Certificats Apple Configurator**.

      - **Certificats Apple Configurator** : si vous avez choisi **Autoriser Apple Configurator par certificat** sous **Autoriser l’appairage**, choisissez un certificat Apple Configurator à importer.

7. Choisissez **Paramètres de l’Assistant Configuration**, configurez les paramètres de profil suivants, puis choisissez **Enregistrer** :

    - **Nom du service** : s’affiche quand les utilisateurs appuient sur **À propos de la configuration** pendant l’activation.

    - **Numéro de téléphone du service** : s’affiche quand l’utilisateur clique sur le bouton Besoin d’aide pendant l’activation.
    - **Options de l’Assistant Installation** : s’ils sont exclus des options de l’assistant de configuration, ces paramètres facultatifs peuvent être configurés plus tard dans le menu **Paramètres** d’iOS.
        - **Code secret** : demande un code secret pendant l’activation. Exige toujours un code secret, sauf si l’appareil doit être sécurisé ou si son accès doit être contrôlé d’une autre façon (c’est-à-dire, en mode plein écran qui limite l’appareil à une seule application).
        - **Services de localisation** : si activé, l’Assistant Installation vous invite à spécifier le service pendant l’activation
        - **Restaurer** : si activé, l’Assistant Installation invite à spécifier la sauvegarde iCloud pendant l’activation
        - **ID Apple** : si cette option est activée, iOS demande un ID Apple aux utilisateurs quand Intune tente d’installer une application sans ID. Un ID Apple est nécessaire pour télécharger des applications App Store iOS, y compris les applications qui sont installées par Intune.
        - **Termes et conditions** : si cette option est activée, l’Assistant Installation invite l’utilisateur à accepter les conditions générales d’Apple pendant l’activation
        - **Touch ID** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Apple Pay** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Zoom** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Siri** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Données de diagnostic** : si cette option est activée, l’Assistant Configuration vous invite à spécifier ce service pendant l’activation

8. Pour enregistrer les paramètres de profil, choisissez **Créer** dans le panneau **Créer un profil d’inscription**.

## <a name="connect-school-data-sync"></a>Connexion School Data Sync
(Facultatif) Apple School Manager prend en charge la synchronisation des données de liste de classes avec Azure Active Directory (AD) à l’aide de Microsoft School Data Sync (SDS). Effectuez les étapes suivantes pour utiliser SDS pour synchroniser les données d’école.

1. Dans le panneau **Jeton du programme d’inscription**, choisissez la bannière d’informations bleue ou **Connexion SDS**.
2. Choisissez **Autoriser Microsoft School Data Sync à utiliser ce jeton**, et affectez la valeur **Autoriser**. Ce paramètre permet à Intune de se connecter avec SDS dans Office 365.
3. Pour activer une connexion entre Apple School Manager et Azure AD, choisissez **Configurer Microsoft School Data Sync**. Découvrez-en davantage sur [la configuration de School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Cliquez sur **OK** pour enregistrer et continuer.

## <a name="sync-managed-devices"></a>Synchroniser des appareils gérés
Maintenant qu’Intune a reçu l’autorisation de gérer vos appareils Apple School Manager, vous pouvez synchroniser Intune avec le service Apple pour voir vos appareils gérés dans Intune.

1. Dans le portail Azure d’Intune, choisissez **Inscription d’appareil** > **Inscription Apple** > **Appareils du programme d’inscription** > **Synchroniser**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

  ![Sélection du nœud Appareils du programme d’inscription et choix du lien Synchroniser](./media/enrollment-program-device-sync.png)
2. Dans le panneau **Synchroniser**, choisissez **Demander une synchronisation**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

  ![Panneau de synchronisation avec choix du lien Demander une synchronisation](./media/enrollment-program-device-request-sync.png)

  Pour être conforme aux conditions d’Apple pour un trafic acceptable, Intune impose les restrictions suivantes :
   -    Une synchronisation complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise chaque numéro de série attribué à Intune par Apple, que le numéro de série ait été ou non déjà synchronisé. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.
   -    Toute demande de synchronisation doit se terminer dans un délai de 15 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.

>[!NOTE]
>Vous pouvez également affecter des numéros de série Apple School Manager aux profils à partir du panneau **Appareils du programme d’inscription**.

## <a name="assign-a-profile-to-devices"></a>Attribuer un profil aux appareils
Un profil d’inscription doit être affecté aux appareils Apple School Manager gérés par Intune avant leur inscription.

1. Dans le portail Azure d’Intune, choisissez **Inscription d’appareil** > **Inscription Apple**, puis **Profils du programme d’inscription**.
2. Dans la liste **Profils du programme d’inscription**, choisissez le profil que vous voulez affecter aux appareils, puis **Affectations d’appareils**.

 ![Affectations des appareils avec Affecter sélectionné](./media/enrollment-program-device-assign.png)

3. Choisissez **Affecter**, puis les appareils Apple School Manager auxquels vous voulez affecter ce profil. Vous pouvez filtrer pour afficher les appareils disponibles :
  - **non affecté**
  - **indifférent**
  - **&lt;nom du profil&gt;**
4. Choisissez les appareils à affecter. La case à cocher au-dessus de la colonne sélectionne jusqu'à 1 000 appareils répertoriés. Cliquez sur **Affecter**. Pour inscrire plus de 1000 appareils, répétez les étapes d’affectation jusqu’à ce qu’un profil d’inscription ait été affecté à tous les appareils.

  ![Bouton d’affectation de profil du programme d’inscription dans Intune](media/dep-profile-assignment.png)

## <a name="distribute-devices-to-users"></a>Distribuer des appareils aux utilisateurs

Vous pouvez maintenant distribuer les appareils d’entreprise aux utilisateurs. Quand un appareil Apple School Manager iOS est activé, il est inscrit pour être géré par Intune. Si l’appareil a été activé et est en cours d’utilisation, le profil ne peut pas être appliqué jusqu'à ce que l’appareil soit réinitialisé aux paramètres d’usine.
