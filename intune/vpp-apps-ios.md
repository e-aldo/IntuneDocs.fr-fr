---
title: "Gérer les applications iOS achetées en volume | Microsoft Docs"
titlesuffix: Azure portal
description: "Découvrez comment synchroniser les applications que vous avez achetées en volume à partir de l’App Store iOS dans Intune et ensuite gérer et suivre leur utilisation."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dc5ebd90483b0fa0e25461574085bd4160f012ea
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’App Store iOS vous permet d’acheter plusieurs licences pour une application que vous souhaitez exécuter dans votre entreprise. Le fait d’acheter plusieurs copies aide à gérer efficacement les applications de l’entreprise.

Microsoft Intune vous permet de gérer plusieurs copies des applications achetées par le biais de ce programme en :

- Signalant les informations de licence de l’App Store.
- Effectuant le suivi du nombre de licences utilisées.
- Vous empêchant d’installer davantage de copies de l’application que vous n’en possédez.

Vous pouvez utiliser deux méthodes pour affecter les applications achetées en volume :

### <a name="device-licensing"></a>Gestion des licences des appareils

Quand vous affectez une application à des appareils, une licence d’application est utilisée et reste associée à l’appareil auquel vous l’avez attribuée.

Quand vous affectez des applications achetées en volume à un appareil, l’utilisateur final de l’appareil n’a pas à fournir un ID Apple pour accéder à l’App Store.

### <a name="user-licensing"></a>Licences utilisateur

Quand vous affectez une application à un utilisateur, une licence d’application est utilisée et est associée à l’utilisateur. L’application peut être exécutée sur plusieurs appareils détenus par l’utilisateur (avec une limite contrôlée par Apple).

Quand vous affectez une application achetée en volume à des utilisateurs, chaque utilisateur final doit avoir un identifiant Apple valide pour accéder à l’App Store.

Vous pouvez également synchroniser, gérer et affecter des livres que vous avez achetés dans le Store VPP (Programme d’achat en volume) d’Apple avec Intune. Pour plus d’informations, consultez [Guide pratique pour gérer les livres électroniques iOS que vous avez achetés par le biais d’un programme d’achat en volume](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gérer les applications pour appareils iOS achetées en volume

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>Prend en charge les applications achetées via le programme d’achat en volume (VPP) Apple pour les appareils iOS

Achetez plusieurs licences pour des applications iOS via le [Programme d’achat en volume Apple pour les entreprises](http://www.apple.com/business/vpp/) ou [Programme d’achat en volume Apple pour les organismes éducatifs](http://volume.itunes.apple.com/us/store). Cela implique la configuration d’un compte Apple VPP à partir du site web Apple et l’importation du jeton Apple VPP dans Intune.  Vous pouvez ensuite synchroniser vos informations d’achat en volume avec Intune et suivre votre utilisation des applications achetées en volume.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>Prend en charge les applications achetées en volume B2B pour les appareils iOS

En outre, les développeurs tiers peuvent également distribuer des applications en privé aux membres autorisés du programme d’achat en volume pour les entreprises. Ces membres du programme d’achat en volume pour les entreprises peuvent se connecter à l’App Store du programme d’achat en volume et acheter leurs applications. Les applications du programme d’achat en volume pour les entreprises achetées par l’utilisateur final se synchronisent avec leurs locataires Intune.

## <a name="before-you-start"></a>Avant de commencer
Avant de commencer, vous devez obtenir un jeton VPP auprès d’Apple et l’importer dans votre compte Intune. En outre, vous devez comprendre les critères suivants :

* Vous pouvez associer plusieurs jetons VPP à votre compte Intune.
* Si vous avez déjà utilisé un jeton VPP avec un autre produit, vous devez en générer un nouveau à utiliser avec Intune.
* Chaque jeton est valide pendant un an.
* Par défaut, Intune se synchronise avec le service Apple VPP deux fois par jour. Vous pouvez lancer une synchronisation manuelle à tout moment.
* Avant de commencer à utiliser Apple VPP avec Intune, supprimez les comptes d’utilisateur VPP existants créés avec d’autres fournisseurs de gestion des appareils mobiles (MDM). Par mesure de sécurité, ces comptes d’utilisateur ne sont pas synchronisés dans Intune. Intune synchronise uniquement les données du service Apple VPP qui ont été créées par Intune.
* Avec Intune, vous pouvez ajouter jusqu’à 256 jetons VPP.
* Le programme Profil d’inscription des appareils d’Apple automatise l’inscription auprès de la gestion des appareils mobiles (MDM). Avec le Profil d’inscription des appareils, vous pouvez configurer des appareils d’entreprise sans les avoir en main. Vous pouvez inscrire avec le programme Profil d’inscription des appareils en utilisant le même compte d’agent du programme que celui que vous avez utilisé avec le programme d’achat en volume d’Apple. L’ID de programme de déploiement Apple est unique pour les programmes répertoriés dans le site web [Programmes de déploiement Apple](https://deploy.apple.com) et il ne peut pas être utilisé pour se connecter aux services Apple, comme iTunes Store.
* Quand vous affectez des applications VPP à l’aide du modèle de licence utilisateur à des utilisateurs ou des appareils (avec une affinité d’utilisateur), chaque utilisateur Intune doit être associé à un e-mail ou un ID Apple unique quand il accepte les conditions générales Apple sur son appareil. Vérifiez que, quand vous configurez un appareil pour un nouvel utilisateur Intune, vous le faites avec l’ID Apple unique ou l’adresse e-mail de cet utilisateur. L’ID Apple ou l’adresse e-mail et l’utilisateur Intune forment une paire unique. Ils peuvent être utilisés sur cinq appareils au maximum.
* Un jeton VPP est pris en charge pour une utilisation sur un seul compte Intune à la fois. Ne réutilisez pas le même jeton VPP pour plusieurs clients Intune.
* Quand vous affectez des applications VPP à l’aide du modèle de licence utilisateur à des utilisateurs ou des appareils (avec une affinité d’utilisateur), chaque utilisateur Intune doit être associé à un e-mail ou un ID Apple unique quand il accepte les conditions générales Apple sur son appareil.
Vérifiez que quand vous configurez un appareil pour un nouvel utilisateur Intune, vous le configurez avec l’e-mail ou l’ID Apple unique de cet utilisateur. L’identifiant Apple ou l’adresse e-mail et l’utilisateur Intune forment une paire unique. Ils peuvent être utilisés sur cinq appareils au maximum.

>[!IMPORTANT]
>Après avoir importé le jeton VPP dans Intune, n’importez pas le même jeton dans une autre solution de gestion d’appareils, car cela peut entraîner la perte des enregistrements utilisateur et de l’attribution de licence.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Pour obtenir et charger un jeton Apple VPP

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
1.  Dans le panneau **Intune**, choisissez **Applications mobiles** > **Jetons VPP iOS** sous **Configurer**.
2.  Dans le panneau qui présente la liste des jetons VPP, sélectionnez **Créer**.
4. Dans le panneau **Créer un jeton VPP**, spécifiez les informations suivantes :
    - **Fichier de jeton VPP** : si vous ne l’avez pas encore fait, inscrivez-vous au Programme d’achat en volume Apple pour les entreprises ou au programme pour les organismes éducatifs. Après inscription, téléchargez le jeton VPP Apple de votre compte et sélectionnez-le ici.
    - **ID Apple** : saisissez l’ID Apple du compte associé au programme d’achats en volume.
    - **Pays/région** : sélectionnez le Store du pays VPP.  Intune synchronise les applications VPP pour tous les paramètres régionaux à partir du magasin du pays VPP spécifié.
        > [!WARNING]  
        > Si vous changez de pays, les métadonnées des applications et l’URL du Store sont mises à jour lors de la prochaine synchronisation avec le service Apple pour les applications créées avec ce jeton. L’application n’est pas mise à jour si elle n’existe pas dans le Store du nouveau pays.

    - **Type de compte VPP** : choisissez **Entreprise** ou **Éducation**.
    - **Application automatique des mises à jour** : choisissez **Activé** ou **Désactivé** pour activer les mises à jour automatiques. Quand elle est activée, Intune met à jour toutes les applications achetées pour le jeton spécifié via le service Intune quand l’appareil s’enregistre.
détecte les mises à jour des applications VPP dans l’App Store et les envoie (push) automatiquement à l’appareil quand celui-ci s’enregistre.
4. Une fois ces opérations effectuées, sélectionnez **Charger**.

Le jeton est affiché dans le panneau de liste de jetons.

Vous pouvez synchroniser les données détenues par Apple avec Intune à tout moment en sélectionnant **Synchroniser maintenant**.

## <a name="to-assign-a-volume-purchased-app"></a>Pour affecter une application achetée en volume

1.  Dans le panneau **Intune**, choisissez **Applications mobiles** > **Applications** sous **Gérer**.
2.  Dans le panneau avec la liste d’applications, choisissez l’application que vous voulez affecter, puis choisissez **Affectations**.
3.  Dans le panneau ***Nom de l’application*** - **Affectations**, choisissez **Sélectionner des groupes** puis, dans le panneau **Sélectionner des groupes**, choisissez les groupes d’utilisateurs ou d’appareils Azure AD auxquels vous voulez affecter l’application.
5.  Pour chaque groupe que vous avez sélectionné, choisissez les paramètres suivants :
    - **Type** : indiquez si l’application sera **Disponible** (les utilisateurs finaux peuvent installer l’application à partir du portail d’entreprise) ou **Obligatoire** (l’application sera automatiquement installée sur les appareils des utilisateurs finaux).
    - **Type de licence** : choisissez entre **Gestion des licences des utilisateurs** et **Gestion des licences des appareils**.
6.  Une fois que vous avez terminé, choisissez **Enregistrer**.


>[!NOTE]
>La liste des applications affichées est associée à un jeton. Si vous avez une application qui est associée à plusieurs jetons VPP, la même application est affichée plusieurs fois (une fois pour chaque jeton).

## <a name="end-user-prompts-for-vpp"></a>Invites de l’utilisateur final concernant le programme VPP

L’utilisateur final reçoit des invites concernant l’installation d’applications VPP dans plusieurs scénarios. Le tableau suivant explique chaque condition :

| # | Scénario                                | Invite au programme Apple VPP                              | Invite d’installation d’application | Invite de saisie de l’identifiant Apple |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | BYOD – Licence associée à un utilisateur                             | Y                                                                                               | Y                                           | Y                                 |
| 2 | Corp – Licence associée à un utilisateur (appareil non supervisé)     | Y                                                                                               | Y                                           | Y                                 |
| 3 | Corp – Licence associée à un utilisateur (appareil supervisé)         | Y                                                                                               | N                                           | Y                                 |
| 4 | BYOD – Licence associée à un appareil                           | N                                                                                               | Y                                           | N                                 |
| 5 | Corp – Licence associée à un appareil (appareil non supervisé)                           | N                                                                                               | Y                                           | N                                 |
| 6 | Corp – Licence associée à un appareil (appareil supervisé)                           | N                                                                                               | N                                           | N                                 |
| 7 | Mode plein écran (appareil supervisé) – Licence associée à un appareil | N                                                                                               | N                                           | N                                 |
| 8 | Mode plein écran (appareil supervisé) – Licence associée à un utilisateur   | --- | ---                                          | ---                                |

> [!Note]  
> Il n’est pas recommandé d’affecter des applications VPP à des appareils en mode plein écran à l’aide de la gestion des licences utilisateur VPP.

## <a name="revoking-app-licenses-and-deleting-tokens"></a>Révocation des licences d’application et suppression des jetons 

<!-- 820863 -->For a given device that has one or more iOS volume-purchase program (VPP) apps, you revoke all associated device-based app licenses for the device. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app and reclaim a license, you must change the assignment type of the VPP app to **Uninstall**. If you remove an app that was assigned to a user, Intune reclaims the user or device license and uninstallS the app from the device.

>[!NOTE]
>Intune récupère toutes les licences utilisateur d’applications VPP iOS quand un employé quitte l’entreprise et ne fait plus partie des groupes AAD.

<!-- 820879 -->You can delete a iOS Volume Purchasing Program (VPP) token using the console. This may be necessary when you have duplicate instances of a VPP token. Deleting a token will also delete any associated apps and assignment. However, deleting a token does not revoke app licenses or uninstall apps. 

>[!NOTE]
>Intune ne peut pas révoquer de licences d’application après la suppression d’un jeton. 

<!-- 820870 -->To revoke the license of all VPP apps for a given VPP token, you must first revoke all app licenses associated with the token, then delete the token.

## <a name="further-information"></a>Informations supplémentaires

Quand un utilisateur avec un appareil éligible essaie pour la première fois d’installer une application VPP sur un appareil, il est invité à participer au programme VPP d’Apple. Il doit accepter pour que l’installation de l’application se poursuive. L’invitation à participer au Programme d’achat en volume (VPP) Apple nécessite que l’utilisateur puisse utiliser l’application iTunes sur l’appareil iOS. Si vous avez défini une stratégie pour désactiver l’application iTunes Store, la gestion des licences par utilisateur pour le programme VPP ne fonctionne pas. La solution consiste à autoriser l’application iTunes en supprimant la stratégie ou à utiliser la gestion des licences par appareil.

## <a name="next-steps"></a>Étapes suivantes

Consultez la page [Guide pratique pour surveiller des applications](apps-monitor.md) pour plus d’informations pour vous aider à contrôler les affectations de l’application.
