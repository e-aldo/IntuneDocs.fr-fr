---
title: "Gérer les applications achetées en volume"
titleSuffix: Intune on Azure
description: "Découvrez comment synchroniser les applications que vous avez achetées en volume à partir de l’App Store iOS dans Intune et ensuite gérer et suivre leur utilisation."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 433cec8e0bc2012090e680e0a28a9a77d7b13a38
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Guide pratique pour gérer les applications iOS que vous avez achetées par le biais d’un programme d’achat en volume avec Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’App Store iOS vous permet d’acheter plusieurs licences pour une application que vous souhaitez exécuter dans votre entreprise. L’achat de plusieurs licences d’une application aide à réduire les coûts d’administration liés au suivi de plusieurs copies d’application achetées.

Microsoft Intune vous permet de gérer les applications que vous avez achetées par le biais de ce programme en :

- Important les informations de licence à partir de l’App Store
- Effectuant le suivi du nombre de licences que vous avez utilisées
- Vous empêchant d’installer davantage de copies de l’application que vous n’en possédez

Vous pouvez utiliser deux méthodes pour affecter les applications achetées en volume :

### <a name="device-licensing"></a>Gestion des licences des appareils

Quand vous affectez une application à des appareils, une licence d’application est utilisée et reste associée à l’appareil auquel vous l’avez attribuée.
Quand vous affectez des applications achetées en volume à un appareil, l’utilisateur final de l’appareil n’a pas à fournir un ID Apple pour accéder à l’App Store. 

### <a name="user-licensing"></a>Licences utilisateur

Quand vous affectez une application à des utilisateurs, une licence d’application est utilisée et est associée à l’utilisateur. L’application peut être exécutée sur plusieurs appareils détenus par l’utilisateur.
Quand vous affectez une application achetée en volume à des utilisateurs, chaque utilisateur final doit avoir un ID Apple valide pour accéder à l’App Store.


Vous pouvez également synchroniser, gérer et affecter des livres que vous avez achetés dans le Store VPP (Programme d’achat en volume) d’Apple avec Intune. Utilisez la charge de travail **Documentation** dans le portail Intune pour gérer la documentation. Les procédures de gestion de la documentation sont identiques à celles que vous utilisez pour gérer des applications.
Vous devez avoir chargé un jeton Apple VPP avant de commencer. Vous ne pouvez actuellement affecter de la documentation qu’en tant qu’installation **Requise**.
Lorsque vous affectez un livre à un appareil, celui-ci doit disposer de l’application iBook intégrée. Dans le cas contraire, l’utilisateur doit réinstaller l’application pour pouvoir lire le livre. Vous ne pouvez pas actuellement utiliser Intune pour restaurer les applications intégrées qui ont été supprimées.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Gérer les applications pour appareils iOS achetées en volume
Achetez plusieurs licences pour des applications iOS via le [Programme d’achat en volume Apple pour les entreprises](http://www.apple.com/business/vpp/) ou [Programme d’achat en volume Apple pour les organismes éducatifs](http://volume.itunes.apple.com/us/store). Cela implique la configuration d’un compte Apple VPP à partir du site web Apple et l’importation du jeton Apple VPP dans Intune.  Vous pouvez ensuite synchroniser vos informations d’achat en volume avec Intune et suivre votre utilisation des applications achetées en volume.

## <a name="before-you-start"></a>Avant de commencer
Avant de commencer, vous devez obtenir un jeton VPP auprès d’Apple et l’importer dans votre compte Intune. En outre, vous devez comprendre les critères suivants :

* Vous pouvez associer plusieurs jetons de programme d’achat de volume à votre compte Intune.
* Si vous avez déjà utilisé un jeton VPP avec un autre produit, vous devez en générer un nouveau à utiliser avec Intune.
* Chaque jeton est valide pendant un an.
* Par défaut, Intune se synchronise avec le service Apple VPP deux fois par jour. Vous pouvez lancer une synchronisation manuelle à tout moment.
* Après avoir importé le jeton VPP dans Intune, n’importez pas le même jeton dans une autre solution de gestion d’appareils, car cela peut entraîner la perte des enregistrements utilisateur et de l’attribution de licence.
* Avant de commencer à utiliser iOS VPP avec Intune, supprimez les comptes d’utilisateur VPP existants créés avec d’autres fournisseurs de gestion des appareils mobiles. Par mesure de sécurité, ces comptes d’utilisateur ne sont pas synchronisés dans Intune. Intune synchronise uniquement les données du service Apple VPP qui ont été créées par Intune.
* Avec Intune, vous pouvez ajouter jusqu’à 256 jetons VPP.
* Si vous affectez une application achetée en volume pour un appareil inscrit via un profil DEP ou Apple Configurator, seules les applications qui ciblent les appareils fonctionnent. Vous ne pouvez pas cibler des applications achetées en volume sur les utilisateurs d’un appareil DEP qui n’a pas d’affinité d’utilisateur.
* Un jeton VPP est pris en charge pour une utilisation sur un seul compte Intune à la fois. Ne réutilisez pas le même jeton VPP pour plusieurs clients Intune.
* Quand vous affectez des applications VPP à l’aide du modèle de licence utilisateur à des utilisateurs ou des appareils (avec une affinité d’utilisateur), chaque utilisateur Intune doit être associé à un e-mail ou un ID Apple unique quand il accepte les conditions générales Apple sur son appareil.
Vérifiez que quand vous configurez un appareil pour un nouvel utilisateur Intune, vous le configurez avec l’e-mail ou l’ID Apple unique de cet utilisateur. L’ID Apple ou e-mail et l’utilisateur Intune forment une paire unique et peuvent être utilisés sur cinq appareils maximum.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Pour obtenir et charger un jeton Apple VPP

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
1.  Dans la charge de travail **Mobile apps**, choisissez **Installation** > **jetons VPP iOS**.
2.  Dans la liste du panneau des jetons VPP, cliquez sur **Ajouter**.
3.  Dans le panneau **Nouveau jeton VPP**, spécifiez les informations suivantes :
    - **Fichier de jeton VPP** : si vous ne l’avez pas encore fait, inscrivez-vous au Programme d’achat en volume Apple pour les entreprises ou au programme pour les organismes éducatifs. Après inscription, téléchargez le jeton VPP Apple de votre compte et sélectionnez-le ici.
    - **ID Apple** : saisissez l’ID Apple du compte associé au programme d’achats en volume.
    - **Type de compte VPP** : choisissez **Entreprise** ou **Éducation**.
4. Une fois ces opérations effectuées, cliquez sur **Télécharger**.

Le jeton est affiché dans le panneau de liste de jetons.


Vous pouvez synchroniser les données détenues par Apple avec Intune à tout moment en sélectionnant **Synchroniser maintenant**.

> [!NOTE]
> Microsoft Intune synchronise uniquement les informations des applications qui disponibles de manière publique par l’intermédiaire de l’iTunes Store. **Les applications B2B personnalisées pour iOS** ne sont pas encore prises en charge. Si votre scénario cible ce type d’application, les informations de l’application ne sont pas synchronisées.

## <a name="to-assign-a-volume-purchased-app"></a>Pour affecter une application achetée en volume

1.  Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **App Licenses** (Licences d’applications).
2.  Dans le panneau de liste d’applications, choisissez l’application que vous souhaitez affecter, puis choisissez «**...**  » > **Affecter des groupes**.
3.  Dans le panneau *<app name>* - **Affectations**, choisissez **Gérer** > **Affectations**.
4.  Choisissez **Sélectionner des groupes** puis, dans le panneau **Sélectionner des groupes**, choisissez les groupes d’utilisateurs ou d’appareils Azure AD auxquels vous souhaitez affecter l’application.
5.  Pour chaque groupe que vous avez sélectionné, choisissez les paramètres suivants :
    - **Type** : indiquez si l’application sera **Disponible** (les utilisateurs finaux peuvent installer l’application à partir du portail d’entreprise) ou **Obligatoire** (l’application sera automatiquement installée sur les appareils des utilisateurs finaux).
Quand vous attribuez une application VPP en tant que **Disponible**, le contenu et la licence de l’application sont attribués directement à partir de l’App Store.
    - **Type de licence** : choisissez entre **Gestion des licences des utilisateurs** et **Gestion des licences des appareils**.
6.  Une fois que vous avez terminé, choisissez **Enregistrer**.


>[!NOTE]
>La liste des applications affichées est associée à un jeton. Si vous avez une application qui est associée à plusieurs jetons VPP, la même application est affichée plusieurs fois (une fois pour chaque jeton).

## <a name="further-information"></a>Informations supplémentaires

Pour récupérer une licence, vous devez remplacer l’action d’attribution par Désinstaller. La licence est récupérée une fois l’application désinstallée.

Quand un utilisateur avec un appareil éligible essaie pour la première fois d’installer une application VPP, il est invité à participer au programme VPP d’Apple. Il doit accepter pour que l’installation de l’application se poursuive. L’invitation à participer au Programme d’achat en volume (VPP) Apple nécessite que l’utilisateur puisse utiliser l’application iTunes sur l’appareil iOS. Si vous avez défini une stratégie pour désactiver l’application iTunes Store, la gestion des licences par utilisateur pour le programme VPP ne fonctionne pas. La solution consiste à autoriser l’application iTunes en supprimant la stratégie ou à utiliser la gestion des licences par appareil.



## <a name="next-steps"></a>Étapes suivantes

Consultez la page [Guide pratique pour surveiller des applications](apps-monitor.md) pour plus d’informations pour vous aider à contrôler les affectations de l’application.