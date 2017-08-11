---
title: "Configurer l’inscription au programme Apple School Manager pour les appareils iOS"
titleSuffix: Intune on Azure
description: "Découvrez comment configurer l’inscription au programme Apple School Manager pour les appareils iOS d’entreprise avec Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7079a22afc04b5674eb8f12a2833961e86939a28
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="enable-ios-device-enrollment-with-apple-school-manager"></a>Activer l’inscription des appareils iOS avec Apple School Manager

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Cette rubrique aide les administrateurs informatiques à activer l’inscription d’appareils iOS pour les appareils achetés dans le cadre du programme [Apple School Manager](https://school.apple.com/). Microsoft Intune peut déployer un profil d’inscription en direct qui inscrit les appareils Apple School Manager à la gestion. L’administrateur n’a jamais à accéder à chaque appareil géré. Le profil d’inscription contient des paramètres de gestion qui sont appliqués aux appareils lors de l’inscription, notamment des options de l’Assistant Configuration.

**Étapes de l’inscription au programme Apple School Manager**
1. [Obtenir un jeton Apple School Manager et affecter des appareils](#get-the-apple-token-and-assign-devices)
2. [Créer un profil d’inscription](#create-an-apple-enrollment-profile)
3. [Connexion School Data Sync](#connect-school-data-sync) (facultatif)
4. [Synchroniser les appareils gérés par Apple School Manager](#sync-managed-devices)
5. [Attribuer un profil Apple School Manager aux appareils](#assign-a-profile-to-devices)
6. [Distribuer des appareils aux utilisateurs](#distribute-devices-to-users)

>[!NOTE]
>L’inscription au programme Apple School Manager ne peut pas être utilisée avec le [programme DEP d’Apple](device-enrollment-program-enroll-ios.md) ni le [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

## <a name="get-the-apple-token-and-assign-devices"></a>Obtenir le jeton Apple et affecter des appareils

Avant de pouvoir inscrire des appareils iOS d’entreprise avec Apple School Manager, vous devez obtenir un fichier de jeton (.p7m) auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à Apple School Manager. Il permet également à Intune d'effectuer des chargements de profil d'inscription vers Apple et d'attribuer des appareils à ces profils. Lorsque vous vous trouvez dans le portail Apple, vous pouvez également affecter des numéros de série d’appareil à gérer.

**Conditions préalables**
- [Certificat Push MDM Apple](apple-mdm-push-certificate-get.md)
- Inscrit à [Apple School Management](http://school.apple.com)

**Étape 1. Téléchargez un certificat de clé publique Intune nécessaire à la création d’un jeton Apple.**<br>
1. Dans le [portail Intune](https://aka.ms/intuneportal) d’Azure, choisissez **Inscription de l’appareil**, puis **Jeton de programme d’inscription**.
2. Dans le panneau **Jeton du programme d’inscription**, sélectionnez **Télécharger votre clé publique** pour télécharger et enregistrer le fichier de clé de chiffrement (.pem) en local. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail Apple School Manager.

**Étape 2. Téléchargez un jeton et affectez des appareils.**<br>
Sélectionnez **Créer un jeton via Apple School Manager** et connectez-vous avec votre ID Apple d’entreprise. Vous pouvez utiliser cet ID Apple pour renouveler votre jeton Apple School Manager.

   1.  Dans le [portail Apple School Manager](https://school.apple.com), accédez à **Serveurs de gestion des appareils mobiles**, puis sélectionnez **Ajouter un serveur MDM** (coin supérieur droit).
   2.  Saisissez le **nom du serveur MDM**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.
   3.  Sélectionnez **Télécharger un fichier...**  dans le portail Apple, recherchez le fichier .pem, puis sélectionnez **Enregistrer un serveur MDM** (en bas à droite).
   4.  Sélectionnez **Obtenir un jeton** puis téléchargez le fichier de jeton de serveur (.p7m) sur votre ordinateur.
   5. Accédez à **Affectations d’appareil** et **Choisir appareil** par saisie manuelle des **numéros de série**, **numéro d’ordre**, ou **téléchargement de fichier CSV**.
   6.   Choisissez l’action **Affecter au serveur**, puis sélectionnez le **serveur MDM** que vous avez créé.
   7. Spécifiez comment **choisir des appareils**, puis fournissez des informations et détails sur les appareils.
   8. Choisissez **Attribuer au serveur** et le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**.

**Étape 3. Entrez l’ID Apple utilisé pour créer votre jeton Apple School Manager.**<br>Cet ID doit être utilisé pour renouveler votre jeton Apple School Manager et est stocké pour référence ultérieure.

**Étape 4 :. Localisez et téléchargez votre jeton.**<br>
Accédez au fichier du certificat (.p7m), choisissez **Ouvrir**, puis **Télécharger**. Intune synchronise automatiquement vos appareils Apple School Manager auprès d’Apple.

## <a name="create-an-apple-enrollment-profile"></a>Créer un profil d’inscription Apple
Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils lors de l’inscription.

1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
2. Sous **Programme d’inscription**, sélectionnez **Profils de programme d’inscription**.
3. Dans le panneau **Profils de programme d’inscription**, sélectionnez **Créer**.
4. Dans le panneau **Créer un profil d’inscription**, entrez un **nom** et une **description** pour le profil qui s’affiche dans le portail Intune.
5. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil sont inscrits avec ou sans affinité utilisateur.

 - **Inscrire avec l’affinité utilisateur** : affilie l’appareil à un utilisateur durant l’installation.

 >[!NOTE]
 >L’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription sur les appareils Apple School Manager avec l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur ces appareils.

  Le mode iPad partagé d’Apple School Manager nécessite l’inscription de l’utilisateur sans une affinité utilisateur.

 >[!NOTE]
    >Dans le cas d’Apple School Manager avec affinité utilisateur, un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/library/adfs2-help-endpoints) doit être activé pour demander un jeton utilisateur. [En savoir plus sur WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

 - **Inscrire sans affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l'utilisateur local. Les applications qui nécessitent une affinité utilisateur (dont l’application Portail d’entreprise utilisée pour l’installation des applications métier) ne fonctionnent pas.

6. Sélectionnez **Paramètres de gestion des appareils**. Ces éléments sont définis lors de l’activation et nécessitent une réinitialisation aux paramètres d’usine pour être modifiés. configurez les paramètres de profil suivants, puis sélectionnez **Enregistrer** :

    - **Supervisé** : mode de gestion qui active plusieurs options de gestion et désactive le verrou d’activation par défaut. Si vous laissez la case désactivée, vous disposez de fonctions de gestion limitées.

    - **Inscription verrouillée** : (nécessite le Mode de gestion = Supervisé) désactive les paramètres iOS qui pourraient autoriser la suppression du profil de gestion. Si vous laissez la case désactivée, cela permet de supprimer le profil de gestion du menu Paramètres.

  - **iPad partagé** : (nécessite une **inscription sans affinité utilisateur** et le mode **supervisé**.) Permet à plusieurs utilisateurs de se connecter à des iPad inscrits en utilisant un ID Apple géré. Les ID Apple gérés sont créés dans le portail Apple School Manager.

  >[!NOTE]
  >Si **Affinité utilisateur** a la valeur **With user affinity** (Avec affinité utilisateur) ou que le mode **Supervisé** a la valeur **Désactivé**, le mode iPad partagé est désactivé pour le profil d’inscription.

  - **Nombre maximal d’utilisateurs mis en cache** : (si **iPad partagé** = **Oui**) crée une partition sur l’appareil pour chaque utilisateur. La valeur recommandée est le nombre d’élèves susceptibles d’utiliser l’appareil sur une certaine période de temps. Par exemple, si six étudiants utilisent l’appareil régulièrement pendant la semaine, définissez ce nombre sur six.  

    - **Autoriser le jumelage** : spécifie si les appareils iOS peuvent se synchroniser avec les ordinateurs. Si vous choisissez **Autoriser Apple Configurator par certificat**, vous devez choisir un certificat sous **Certificats Apple Configurator**.

    - **Certificats Apple Configurator** : si vous avez choisi **Autoriser Apple Configurator par certificat** sous **Autoriser le jumelage**, sélectionnez un certificat Apple Configurator à importer.

7. Sélectionnez **Paramètres de l’Assistant Configuration**, configurez les paramètres de profil suivants, puis sélectionnez **Enregistrer** :

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

8. Pour enregistrer les paramètres de profil, sélectionnez **Créer** dans le panneau **Créer un profil d’inscription**.

## <a name="connect-school-data-sync"></a>Connexion School Data Sync
(Facultatif) Apple School Manager prend en charge la synchronisation des données de liste de classes avec Azure Active Directory (AD) à l’aide de Microsoft School Data Sync (SDS). Effectuez les étapes suivantes pour utiliser SDS pour synchroniser les données d’école.

1. Dans le panneau **Jeton du programme d’inscription**, sélectionnez la bannière d’informations bleue ou **Connexion SDS**.
2. Sélectionnez **Autoriser Microsoft School Data Sync à utiliser ce jeton**, et affectez la valeur **Autoriser**. Ce paramètre permet à Intune de se connecter avec SDS dans Office 365.
3. Pour activer une connexion entre Apple School Manager et Azure AD, sélectionnez **Configurer Microsoft School Data Sync**. Découvrez-en davantage sur [la configuration de School Data Sync](https://support.office.com/article/Install-the-School-Data-Sync-Toolkit-8e27426c-8c46-416e-b0df-c29b5f3f62e1).
4. Cliquez sur **OK** pour enregistrer et continuer.

## <a name="sync-managed-devices"></a>Synchroniser des appareils gérés
Maintenant qu’Intune a reçu l’autorisation de gérer vos appareils Apple School Manager, vous pouvez synchroniser Intune avec le service Apple pour voir vos appareils gérés dans le portail Intune.

1. Dans le portail Intune, choisissez **Inscription de l’appareil**, puis choisissez **Inscription Apple**.
2. Sous **Appareils du programme d’inscription**, sélectionnez **Synchronisation**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

    Pour être conforme aux conditions d’Apple pour un trafic acceptable, Intune impose les restrictions suivantes :
     -  Une synchronisation complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise chaque numéro de série attribué à Intune par Apple, que le numéro de série ait été ou non déjà synchronisé. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.
     -  Toute demande de synchronisation doit se terminer dans un délai de 15 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.

>[!NOTE]
>Vous pouvez également affecter des numéros de série Apple School Manager aux profils à partir du panneau **Appareils du programme d’inscription**.

## <a name="assign-a-profile-to-devices"></a>Attribuer un profil aux appareils
Un profil d’inscription doit être affecté aux appareils Apple School Manager gérés par Intune avant leur inscription.

1. Dans le portail Intune, choisissez **Inscription de l’appareil** > **Inscription Apple**, puis sélectionnez **Profils de programme d’inscription**.
2. Dans la liste des **Profils de programme d’inscription**, sélectionnez le profil que vous souhaitez affecter aux appareils, puis sélectionnez **Affectations d’appareils**
3. Sélectionnez **Affecter**, puis les appareils Apple School Manager auxquels vous souhaitez affecter ce profil. Vous pouvez filtrer pour afficher les appareils disponibles :
  - **non affecté**
  - **indifférent**
  - **&lt;Nom du profil Apple School Manager&gt;**
4. Sélectionnez les appareils que vous voulez affecter. La case à cocher au-dessus de la colonne sélectionne jusqu'à 1 000 appareils répertoriés. Cliquez sur **Affecter**. Pour inscrire plus de 1000 appareils, répétez les étapes d’affectation jusqu’à ce qu’un profil d’inscription ait été affecté à tous les appareils.

## <a name="distribute-devices-to-users"></a>Distribuer des appareils aux utilisateurs

Vous pouvez maintenant distribuer les appareils d’entreprise aux utilisateurs. Quand un appareil Apple School Manager iOS est activé, il est inscrit pour être géré par Intune. Si l’appareil a été activé et est en cours d’utilisation, le profil ne peut pas être appliqué jusqu'à ce que l’appareil soit réinitialisé aux paramètres d’usine.

### <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installation et utilisation du portail d’entreprise par les utilisateurs sur leurs appareils

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent exécuter l’Assistant Installation et installer l’application Portail d’entreprise.
