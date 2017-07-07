---
title: "Gestion DEP d’Apple pour les appareils iOS"
description: "Déployez un profil d’inscription qui inscrit les appareils iOS achetés via le programme DEP iOS « à distance », afin de gérer les appareils Apple."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8ff9d9e7-eed8-416c-8508-efc20fca8578
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1a02a8b092242df369b382b6cdcc2c2bbd10c10a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="enroll-corporate-owned-device-enrollment-program-ios-devices"></a>Inscrire des appareils iOS DEP d’entreprise

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune peut déployer un profil d’inscription qui inscrit les appareils iOS qui ont été achetés via le programme DEP « à distance ». Le package d’inscription peut inclure des options d’Assistant de configuration pour l’appareil.

>[!NOTE]
>L’inscription au programme DEP ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).
>En outre, si les utilisateurs inscrivent des appareils iOS (c’est-à-dire s’ils utilisent l’application de portail d’entreprise) et si les numéros de série de ces appareils sont ensuite importés et affectés à un profil DEP, les appareils seront désinscrits de Microsoft Intune.

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-dep-management"></a>Prérequis pour inscrire des appareils iOS à l’aide de la gestion Apple DEP

- [Installer un certificat APNs](set-up-ios-and-mac-management-with-microsoft-intune.md)

- Votre organisation doit participer au programme Apple DEP et obtenir des appareils par le biais de ce programme. Les détails de cette procédure sont disponibles à l'adresse suivante :  [https://deploy.apple.com](https://deploy.apple.com). Les avantages du programme incluent la configuration automatique des appareils sans utiliser de câble USB pour connecter chaque appareil à un ordinateur.

- Avant de pouvoir inscrire des appareils iOS d’entreprise à l’aide du programme DEP, vous devez obtenir un jeton approprié auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à ce programme et appartenant à votre entreprise. Il permet également à Intune d'effectuer des téléchargements de profil d'inscription sur Apple et d'attribuer des appareils à ces profils.

## <a name="steps-to-enroll-ios-devices-by-using-apple-dep-management"></a>Étapes d’inscription des appareils iOS à l’aide de la gestion Apple DEP

Les étapes suivantes décrivent la première inscription d’appareils iOS à l’aide de la gestion Apple DEP. Certaines de ces étapes pourront être répétées pour ajouter et supprimer des appareils dans votre organisation, par exemple, ajouter ou supprimer des numéros de série, comme décrit plus bas.

### <a name="get-an-encryption-key"></a>Obtenir une clé de chiffrement

1. En tant qu’administrateur, ouvrez la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **iOS** &gt; **Programme d’inscription d’appareils**, puis choisissez **Télécharger la clé de chiffrement**.

2. Enregistrez le fichier de clé de chiffrement (.pem) localement. Le fichier .pem est utilisé pour demander un certificat de relation d'approbation à partir du portail du programme d'inscription d'appareils d'Apple.

![Mettre à jour un jeton du programme d’inscription d’appareils](../media/dev-sa-ios-dep.png)

### <a name="get-a-device-enrollment-program-token"></a>Obtenir un jeton du programme d’inscription d’appareils

1. Accédez au [portail du Programme DEP](https://deploy.apple.com) (https://deploy.apple.com) et connectez-vous avec votre ID Apple d’entreprise. Cet ID Apple doit être utilisé par la suite pour renouveler votre jeton DEP.

2.  Dans le portail du Programme d’inscription d’appareils, accédez à **Programme d’inscription d’appareils** &gt; **Gérer les serveurs**, puis choisissez **Ajouter un serveur MDM**.

3.  Entrez le **Nom du serveur MDM**, puis choisissez **Suivant**. Le nom du serveur vous permet d’identifier le serveur de gestion des appareils mobiles (MDM) uniquement. Il ne s’agit pas du nom ou de l’URL du serveur Microsoft Intune.

4.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** s’ouvre. Choisissez **Choisir un fichier** pour charger le fichier .pem, puis choisissez **Suivant**.

5.  La boîte de dialogue **Ajouter&lt;nom_serveur&gt;** affiche un lien **Votre jeton de serveur**. Téléchargez le fichier de jeton de serveur (.p7m) sur votre ordinateur, puis choisissez **Terminé**.

   Ce fichier de certificat (.p7m) est utilisé pour établir une relation d'approbation entre le serveur Intune et le serveur du programme d'inscription d'appareils d'Apple.

### <a name="add-the-dep-token-to-intune"></a>Ajouter le jeton DEP à Intune

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Admin** &gt; **Gestion des appareils mobiles** &gt; **iOS** &gt; **Programme d’inscription d’appareils**.

2. Choisissez **Charger le jeton DEP**. **Accédez** au fichier de certificat (.p7m), entrez votre **ID Apple**, puis choisissez **Télécharger**.

### <a name="add-the-corporate-device-enrollment-policy"></a>Ajouter la stratégie Inscription d’appareil professionnel

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription d’appareil professionnel**, puis choisissez **Ajouter**.

2. Remplissez la section **Général**, notamment les champs **Nom** et **Description**, et spécifiez si les appareils attribués au profil ont une affinité utilisateur ou s’ils appartiennent à un groupe :

   - **Demander l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur durant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise pour le compte de cet utilisateur. L’**affinité utilisateur** doit être configurée pour les appareils gérés par DEP qui appartiennent à des utilisateurs et doivent utiliser le portail d’entreprise (c’est-à-dire, pour installer des applications). L’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription sur les appareils DEP avec l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur ces appareils. Les nouveaux utilisateurs qui doivent changer leur mot de passe lors de leur première connexion ne peuvent pas y être invités pendant l’inscription sur des appareils DEP. De plus, les utilisateurs dont les mots de passe ont expiré ne sont pas invités à réinitialiser leur mot de passe lors de l’inscription DEP et doivent le faire à partir d’un autre appareil.

    >[!NOTE]
    >Dans le cas de DEP avec affinité utilisateur, un [point de terminaison WS-Trust 1.3 Username/Mixed](https://technet.microsoft.com/en-us/library/adfs2-help-endpoints) doit être activé pour demander un jeton utilisateur. [En savoir plus sur WS-Trust 1.3](https://technet.microsoft.com/itpro/powershell/windows/adfs/get-adfsendpoint).

   - **Aucune affinité utilisateur** : l’appareil n’est pas affilié à un utilisateur. Utilisez cette affiliation pour les appareils qui effectuent des tâches sans accéder aux données de l’utilisateur local. Les applications qui nécessitent l’affiliation d’un utilisateur, y compris l’application Portail d’entreprise utilisée pour installer les applications métier, ne fonctionneront pas.

   Vous pouvez également **assigner les appareils au groupe suivant**. Choisissez **Sélectionner...** pour choisir un groupe.

   > [!Important]
   > L’attribution de groupes passe d’Intune à Azure Active Directory. Une fois que votre compte Intune reçoit la mise à jour applicable, l’option **Attribuer des appareils au groupe suivant** ne s’affiche pas. [En savoir plus](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).

3. Activez **Configurez les paramètres DEP (Device Enrollment Program) pour cette stratégie** pour prendre en charge le programme DEP.

      ![Volet de l’Assistant d’installation](../media/pol-sa-corp-enroll.png)

   Les paramètres suivants sont disponibles pour les appareils gérés par le programme DEP :

   - **Service** : s’affiche quand les utilisateurs appuient sur **À propos de la configuration** pendant l’activation
   - **Numéro de téléphone du support** : s’affiche quand l’utilisateur clique sur le bouton **Besoin d’aide** pendant l’activation
   - **Mode de préparation** : défini pendant l’activation et ne peut pas être modifié sans rétablir les paramètres d’usine de l’appareil :
       - **Non supervisé** : capacités de gestion limitées
       - **Supervisé** : active plusieurs options de gestion et désactive le verrou d’activation par défaut
   - **Verrouiller le profil d’inscription de l’appareil** : défini pendant l’activation et ne peut pas être modifié sans rétablir les paramètres d’usine
       - **Désactiver** : permet de supprimer le profil de gestion à partir du menu **Paramètres**
       - **Activer** : (nécessite le **Mode de préparation** = **Supervisé**) désactive l’option du menu Paramètres iOS permettant de supprimer le profil de gestion
   - **Options de l’Assistant Installation** : ces paramètres facultatifs peuvent être configurés plus tard dans le menu **Paramètres** d’iOS.
        - **Code secret** : demande un code secret pendant l’activation. Exige toujours un code secret, sauf si l’appareil doit être sécurisé ou si son accès doit être contrôlé d’une autre façon (c’est-à-dire, en mode plein écran qui limite l’appareil à une seule application)
       - **Services de localisation** : si activé, l’Assistant Installation vous invite à spécifier le service pendant l’activation
       - **Restaurer** : si activé, l’Assistant Installation invite à spécifier la sauvegarde iCloud pendant l’activation
       - **ID Apple** : si cette option est activée, iOS demande un ID Apple aux utilisateurs quand Intune tente d’installer une application sans ID. Un ID Apple est nécessaire pour télécharger des applications App Store iOS, y compris celles qui sont installées par Intune.
       - **Termes et conditions** : si cette option est activée, l’Assistant Installation invite l’utilisateur à accepter les conditions générales d’Apple pendant l’activation
       - **Touch ID** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
       - **Apple Pay** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
       - **Zoom** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
       - **Siri** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
       - **Envoyer les données de diagnostic à Apple** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
   -  **Activez la gestion supplémentaire via Apple Configurator** : spécifiez **Interdire** pour empêcher la synchronisation des fichiers avec iTunes ou la gestion via Apple Configurator. Il vaut mieux choisir **Interdire**, exporter les configurations supplémentaires d’Apple Configurator, puis déployer en tant que profil de configuration iOS personnalisé via Intune, au lieu d’utiliser ce paramètre pour permettre un déploiement manuel avec ou sans un certificat.
       - **Interdire** : empêche l’appareil de communiquer via USB (désactive l’appariement)
       - **Autoriser** : autorise un appareil à communiquer via une connexion USB pour n’importe quel PC ou Mac
       - **Demander un certificat** : permet un appariement avec un Mac avec un certificat importé dans le profil d’inscription

### <a name="assign-the-profile-to-devices"></a>Attribuer le profil aux appareils

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Stratégie** &gt; **Inscription des appareils de l’entreprise**, puis choisissez **Attribuer**.

2. Choisissez les appareils auxquels vous voulez attribuer le profil que vous avez créé. Vous pouvez choisir **Tous les appareils** ou sélectionner des appareils spécifiques, puis choisissez **Ajouter**.

> [!Important]
> Actuellement, Intune vous permet de désigner un profil d’inscription d’appareil « par défaut ». Dans ce cas, les nouveaux numéros de série sont automatiquement affectés à ce profil par défaut quand vous les synchronisez avec le service Apple DEP. Dès que votre client aura migré vers le nouveau portail Azure, vous ne pourrez plus définir de profil par défaut et les numéros de série ne seront plus automatiquement attribués à ce profil. Vous devrez affecter les numéros de série à un profil spécifique. [En savoir plus](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="assign-dep-devices-for-management"></a>Attribuer des appareils DEP pour la gestion

1. Accédez au [portail du Programme DEP](https://deploy.apple.com) (https://deploy.apple.com) et connectez-vous avec votre ID Apple d’entreprise.

2. Accédez à **Programme de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Gérer les appareils**.

3. Spécifiez la façon dont vous allez **Choisir des appareils**, fournissez les informations relatives aux appareils et spécifiez les détails par appareil : **Numéro de série**, **Numéro de commande**ou **Télécharger un fichier CSV**.

4. Choisissez **Attribuer au serveur** et le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**.

### <a name="synchronize-dep-managed-devices"></a>Synchroniser les appareils gérés par le programme DEP

Cette étape synchronise les appareils avec le service Apple DEP et les affiche dans la console Intune.

1. En tant qu’administrateur, ouvrez la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Admin** &gt; **Gestion des appareils mobiles** &gt; **iOS** &gt; **Programme d’inscription d’appareils**, puis choisissez **Synchroniser maintenant**. Une demande de synchronisation est envoyée à Apple.

2. Pour afficher les appareils gérés par DEP après la synchronisation, dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Groupes** &gt; **Tous les appareils** &gt; **Appareils d’entreprise préinscrits** &gt; **Par numéro de série iOS**. Dans l’espace de travail **Par numéro de série iOS**, l’**État** des appareils gérés est « Non contacté » tant que l’appareil n’est pas démarré et n’exécute pas l’Assistant d’installation pour inscrire l’appareil.

   Pour être conforme aux conditions d’Apple pour un trafic DEP acceptable, Intune impose les restrictions suivantes :

   - Une synchronisation DEP complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise chaque numéro de série attribué à Intune par Apple, que le numéro de série ait été ou non déjà synchronisé. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.

   - Toute demande de synchronisation doit se terminer dans un délai de 10 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.

### <a name="distribute-devices-to-users"></a>Distribuer des appareils aux utilisateurs

Vous pouvez maintenant distribuer vos appareils d’entreprise aux utilisateurs. Quand un appareil iOS est activé, il est inscrit pour être géré par Intune. Le nombre limite d’appareils de l’utilisateur s’applique aux appareils gérés par DEP.

>[!NOTE]
>Si un utilisateur tente d’inscrire un appareil DEP, mais a dépassé le nombre limite d’appareils pouvant être inscrits, l’inscription échoue en mode silencieux, sans qu’il en soit averti.

## <a name="changes-to-intune-group-assignments"></a>Modifications apportées aux affectations de groupe Intune

Depuis avril 2017, la gestion des groupes d’appareils est transmise à Azure Active Directory. Après la transition vers des groupes Azure Active Directory, l’affectation de groupe n’apparaîtra pas dans les options de profil d’inscription de l’entreprise. Plusieurs mois pourront s’écouler avant que vous ne constatiez les effets de cette modification. Après le déplacement vers le nouveau portail, les attributions de groupes d’appareils dynamiques peuvent être définies en fonction des noms des profils d’inscription de l’entreprise.

Lors de la migration, pour chaque groupe d’appareils Intune préattribué par un profil d’inscription des appareils de l’entreprise, un groupe d’appareils dynamique correspondant est créé dans Azure AD à partir du nom du profil d’inscription des appareils de l’entreprise. Les nouveaux noms de profil ont le format *EnrollmentProfile : &lt;nom du profil associé&gt;*. Ce processus garantit que les appareils déjà affectés à un groupe d’appareils sont inscrits automatiquement dans le groupe avec une stratégie et des applications déployées.

Cette création automatique d’un groupe se produit une seule fois, lors de la migration des groupes. Après la migration, les administrateurs Intune doivent créer des groupes à l’aide du portail Azure. Pour connaître l’impact que cela implique sur l’inscription des appareils iOS d’entreprise, consultez [Changes to Automatic Grouping for Corporate Pre-enrolled iOS Devices](https://blogs.technet.microsoft.com/intunesupport/2017/04/19/changes-to-automatic-grouping-for-corporate-pre-enrolled-ios-devices/) (Modifications du regroupement automatique pour les appareils iOS d’entreprise préinscrits).

Vous pouvez également chercher à [en savoir plus sur les groupes Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).

### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription des appareils](prerequisites-for-enrollment.md)
