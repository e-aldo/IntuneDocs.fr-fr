---
title: "Inscrire des appareils iOS - Programme d’inscription d’appareils | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment inscrire des appareils iOS d’entreprise à l’aide du programme d’inscription d’appareils (DEP)."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7981a9c0-168e-4c54-9afd-ac51e895042c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: adb2fd27d7f2b3f0ef4dce6b26fcb20d74b69a00
ms.openlocfilehash: 2986e659d384eaa67b64af1ce3ae48a1ac81a600


---

# <a name="enroll-ios-devices-using-device-enrollment-program"></a>Inscrire des appareils iOS à l’aide du programme d’inscription d’appareils

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune peut déployer un profil d’inscription qui inscrit les appareils iOS qui ont été achetés via le programme DEP « à distance ». Un profil contient les paramètres de gestion que vous souhaitez appliquer aux appareils. Le package d’inscription peut inclure des options d’Assistant Configuration pour l’appareil. Les appareils inscrits via le programme DEP ne peuvent pas être désinscrits par les utilisateurs.

>[!NOTE]
>Cette méthode d’inscription ne peut pas être utilisée avec celle du [gestionnaire d’inscription d’appareil](enroll-devices-using-device-enrollment-manager.md).

Pour gérer les appareils iOS d’entreprise avec le programme d’inscription des appareils (DEP) d’Apple, votre organisation doit participer au programme et obtenir des appareils par le biais de ce programme. Les détails de cette procédure sont disponibles à l'adresse suivante :  [https://deploy.apple.com](https://deploy.apple.com). Les avantages du programme incluent la configuration automatique des appareils sans utiliser de câble USB pour connecter chaque appareil à un ordinateur.

Avant de pouvoir inscrire des appareils iOS d’entreprise à l’aide du programme DEP, vous devez [obtenir un jeton approprié](get-apple-dep-token.md) auprès d’Apple. Ce jeton permet à Intune de synchroniser les informations sur les appareils participant à ce programme et appartenant à votre entreprise. Il permet également à Intune d'effectuer des téléchargements de profil d'inscription sur Apple et d'attribuer des appareils à ces profils.

Les autres méthodes d’inscription d’appareils iOS sont décrites dans [Choisir comment inscrire des appareils iOS dans Intune](choose-ios-enrollment-method.md).

## <a name="prerequisites"></a>Conditions préalables

Avant de configurer l’inscription des appareils iOS, effectuez les préparatifs suivants :

- [Configurer des domaines](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Configurer l’autorité MDM](set-mdm-authority.md)
- [Créer des groupes](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- Attribuer des licences utilisateur dans le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenir un certificat Push MDM Apple](get-an-apple-mdm-push-certificate.md)
- [Obtenir un jeton DEP Apple](get-apple-dep-token.md)

## <a name="create-an-apple-dep-profile-for-devices"></a>Créer un profil Apple DEP pour les appareils

Un profil d'inscription d'appareil définit les paramètres appliqués à un groupe d'appareils. Les étapes suivantes montrent comment créer un profil d’inscription d’appareil pour les appareils iOS inscrits à l’aide du programme DEP.

1. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Inscription Apple**.

3. Sous **Gérer les paramètres du programme Apple DEP**, sélectionnez **Profils DEP**.

4. Dans le panneau **Profils Apple DEP**, sélectionnez **Créer**.

5. Dans le panneau **Créer un profil d’inscription**, entrez un nom et une description pour le profil.

6. Pour **Affinité utilisateur**, choisissez si les appareils avec ce profil seront inscrits avec ou sans affinité utilisateur.

 - **Inscrire avec l’affinité utilisateur** : l’appareil doit être affilié à un utilisateur pendant l’installation initiale. Il peut ensuite être autorisé à accéder aux données et aux e-mails de l’entreprise. Choisissez l’affinité utilisateur pour les appareils gérés par DEP qui appartiennent à des utilisateurs et qui doivent utiliser le portail d’entreprise pour les services tels que l’installation d’applications. Notez que l’authentification multifacteur (MFA) ne fonctionne pas lors de l’inscription sur les appareils DEP avec l’affinité utilisateur. Après l’inscription, l’authentification multifacteur fonctionne comme prévu sur ces appareils.

    >[!NOTE]
    >Dans le cas de DEP avec affinité utilisateur, un point de terminaison WS-Trust 1.3 Username/Mixed doit être activé pour demander un jeton utilisateur.

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
        - **ID tactile** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Apple Pay** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Zoom** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Siri** : si cette option est activée, l’Assistant Installation vous invite à spécifier ce service pendant l’activation
        - **Données de diagnostic** : si cette option est activée, l’Assistant Configuration vous invite à spécifier ce service pendant l’activation

9. Pour enregistrer les paramètres de profil, sélectionnez **Créer** dans le panneau **Créer un profil d’inscription**.

## <a name="assign-apple-dep-serial-numbers-to-your-mdm-server"></a>Affecter des numéros de série Apple DEP à votre serveur MDM

1. Accédez au [portail du Programme DEP](https://deploy.apple.com) (https://deploy.apple.com) et connectez-vous avec votre ID Apple d’entreprise. 

2. Accédez à **Programme de déploiement** &gt; **Programme d’inscription d’appareils** &gt; **Gérer les appareils**. 

3. Spécifiez la façon dont vous allez **Choisir des appareils**, puis fournissez les informations relatives aux appareils et spécifiez les détails par appareil : **Numéro de série**, **Numéro de commande** ou **Télécharger un fichier CSV**. 

4. Choisissez **Attribuer au serveur** et le &lt;nom_serveur&gt; spécifié pour Microsoft Intune, puis **OK**.

## <a name="synchronize-dep-managed-devices"></a>Synchroniser des appareils gérés par le programme DEP

1. Dans le panneau Intune du portail Azure, choisissez **Inscrire des appareils**, puis **Inscription Apple**.

2. Sous **Gérer les paramètres du programme Apple DEP**, sélectionnez **Numéros de série DEP**.

4. Dans le panneau **Numéros de série Apple DEP**, sélectionnez **Synchroniser**.

5. Dans le panneau **Synchroniser**, sélectionnez **Demander une synchronisation**. La barre de progression indique la durée pendant laquelle vous devez patienter avant de redemander la synchronisation.

    Pour être conforme aux conditions d’Apple pour un trafic DEP acceptable, Intune impose les restrictions suivantes :
     -  Une synchronisation DEP complète ne peut pas s’exécuter plus d’une fois tous les sept jours. Pendant une synchronisation complète, Intune actualise chaque numéro de série attribué à Intune par Apple, que le numéro de série ait été ou non déjà synchronisé. Si une synchronisation complète est tentée dans les sept jours de la synchronisation complète précédente, Intune actualise seulement les numéros de série qui ne figurent pas déjà dans Intune.
     -  Toute demande de synchronisation doit se terminer dans un délai de 10 minutes. Pendant ce temps ou jusqu’au succès de la demande, le bouton **Synchroniser** est désactivé.

>[!NOTE]
>Vous pouvez également affecter des numéros de série DEP aux profils à partir du panneau **Numéros de série Apple DEP**.

## <a name="distribute-devices-to-users"></a>Distribuer des appareils aux utilisateurs

Vous pouvez maintenant distribuer les appareils d’entreprise aux utilisateurs. Quand un appareil iOS est activé, il est inscrit pour être géré par Intune.


## <a name="how-users-install-and-use-the-company-portal-on-their-devices"></a>Installation et utilisation du portail d’entreprise par les utilisateurs sur leurs appareils

Les appareils qui sont configurés avec une affinité utilisateur peuvent installer et exécuter l’application Portail d’entreprise pour télécharger des applications et gérer des appareils. Une fois que les utilisateurs reçoivent leurs appareils, ils doivent effectuer les étapes supplémentaires décrites ci-dessous pour terminer l’exécution de l’Assistant Configuration et installer l’application Portail d’entreprise.

### <a name="how-users-enroll-corporate-owned-ios-devices-with-user-affinity"></a>Comment les utilisateurs inscrivent des appareils iOS d’entreprise avec l’affinité utilisateur 

1. Quand les utilisateurs allument leur appareil, ils sont invités à terminer l’exécution de l’Assistant Installation. Pendant l’installation, les utilisateurs sont invités à fournir leurs informations d’identification. Ils doivent utiliser les informations d’identification (c’est-à-dire, le nom d’utilisateur principal ou UPN) associées à leur abonnement dans Intune.

2. Pendant l’installation, les utilisateurs sont invités à fournir un ID Apple. Ils doivent fournir un identifiant Apple pour permettre à l’appareil d’installer le portail d’entreprise. Ils peuvent également fournir l’identifiant à partir du menu des paramètres iOS après l’installation.

3. Une fois l’installation terminée, les utilisateurs doivent installer l’application Portail d’entreprise à partir de l’App Store.

4. Les utilisateurs se connectent désormais au Portail d’entreprise à l’aide de l’UPN utilisé pendant la configuration de l’appareil.

5. Une fois connectés, les utilisateurs sont invités à inscrire leurs appareils. La première étape consiste à identifier l’appareil. L’application présente la liste des appareils iOS déjà inscrits par l’entreprise et affectés au compte Intune de l’utilisateur. Il doit choisir l’appareil approprié. Si cet appareil n’est pas encore inscrit par l’entreprise, ils doivent choisir « nouvel appareil » pour poursuivre la procédure d’inscription standard.

6. Dans l’écran suivant, les utilisateurs confirment le numéro de série du nouvel appareil. Pour ce faire, les utilisateurs sélectionnent un lien qui s’affiche. Le lien lance l’application Paramètres, ce qui permet aux utilisateurs de vérifier leur numéro de série. Les utilisateurs doivent ensuite entrer les quatre derniers caractères du numéro de série dans l’application Portail d’entreprise.

   Cette étape vérifie que l’appareil est l’appareil d’entreprise inscrit dans Intune. Si le numéro de série de l’appareil ne correspond pas, l’utilisateur a sélectionné un appareil incorrect. L’utilisateur doit revenir à l’écran précédent et sélectionner un autre appareil.

7. Une fois le numéro de série vérifié, l’application Portail d’entreprise redirige l’utilisateur vers le site web Portail d’entreprise pour finaliser l’inscription. Ensuite, le site web invite les utilisateurs à retourner à l’application.

L’inscription est terminée et les utilisateurs peuvent désormais utiliser cet appareil avec l’ensemble complet de fonctionnalités.



<!--HONumber=Feb17_HO1-->


