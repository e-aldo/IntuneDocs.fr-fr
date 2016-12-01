---
title: "Archive des nouveautés | Microsoft Intune"
description: "Nouveautés archivées de Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1
ROBOTS: noindex,nofollow
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: aa8fe81b6a9f6b11bba9c15ede36d9df9cd2e0da
ms.openlocfilehash: 72a2f8026d1a67a3a49111daa9a7b8380b0cb088


---
# <a name="whats-new---archive"></a>Nouveautés - Archive

Cette page est une archive des annonces récentes dévoilées dans [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md).

## <a name="october-2016"></a>Octobre 2016

### <a name="conditional-access-for-mobile-application-management"></a>Accès conditionnel à la gestion des applications mobiles
Vous pourrez restreindre l’accès à Exchange Online en autorisant uniquement l’accès à partir d’applications qui prennent en charge les stratégies Intune de gestion des applications mobiles, comme Outlook. [Cette nouvelle fonctionnalité](/intune/deploy-use/allow-policy-managed-apps-access-to-o365) est complémentaire des stratégies Intune de gestion des applications mobiles (GAM), car vous pouvez bloquer l’accès aux clients de messagerie intégrés ou autres applications qui n’ont pas été configurés avec les stratégies Intune GAM. Cela permet de vous assurer que tous les utilisateurs accèdent aux données de votre organisation à l’aide d’applications qui peuvent être protégées avec la gestion des applications mobiles Intune. Vous pouvez démarrer la gestion des applications mobiles Intune via le Portail Azure, dans la nouvelle section Accès conditionnel du panneau « Paramètres ».

### <a name="conditional-access-for-windows-pcs"></a>Accès conditionnel pour les PC Windows
Vous pouvez maintenant créer des stratégies d’accès conditionnel via la console d’administration Intune pour bloquer l’accès des PC Windows à [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) et à [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune). Vous pouvez également créer des stratégies d’accès conditionnel pour bloquer l’accès à des applications de bureau Office et à des applications universelles.

### <a name="android-for-work-support"></a>Support d’Android for Work

> [!IMPORTANT]

> Alors que vous pouvez déployer des applications Android for Work avec l’action __Obligatoire__, vous pouvez uniquement déployer les applications __disponibles__ si vos groupes Intune ont migré vers la nouvelle expérience Azure AD pour les groupes.

Intune fait maintenant partie du programme Android for Work (AfW). Nous allons déployer la prise en charge des fonctionnalités AfW dès ce mois-ci et pendant plusieurs mois. Notez que le déploiement d’AfW disponible tire parti de la nouvelle expérience de regroupement et de ciblage. Les comptes de service Intune récemment approvisionnés pourront utiliser cette fonctionnalité dès qu’ils auront accès à AfW.

<!--Existing Intune customers can use this feature in production once their tenant has been migrated. Existing customers are welcome to create a trial Intune account to plan for and test this feature until their tenant has been migrated. Any questions on grouping and targeting timelines, please contact our [migration team](mailto:intunegrps@microsoft.com).-->

[Lisez l’annonce de Microsoft concernant la prise en charge d’Intune dans Android for Work](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/12/microsoft-intune-support-for-android-for-work/).

Les rubriques Intune suivantes sont nouvelles ou sont mises à jour avec des informations relatives à Android for Work :

Pour les informaticiens :
- [Configurer Android for Work](/intune/deploy-use/set-up-android-for-work)
<!--- [Nathan Bigman's resource access topics]()-->
- [Restreindre l’accès à la messagerie Exchange Online et Exchange Online Dedicated (nouvel environnement) avec Intune](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
- [Restreindre l’accès à la messagerie Exchange localement et Exchange Online Dedicated (environnement hérité) avec Intune](/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
- [Paramètres de stratégie de conformité Android for Work](/intune/deploy-use/afw-compliance-policy-settings-in-microsoft-intune)
- [Comment déployer des applications Android for Work](/intune/deploy-use/android-for-work-apps)
- [Configurer des applications Android for Work avec des stratégies de configuration des applications mobiles](/intune/deploy-use/afw-app-configuration-policy)
- [Paramètres de stratégie Android for Work](/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)

Pour les utilisateurs finaux :
- [Ce qui se passe quand vous créez un profil professionnel](/intune/enduser/what-happens-when-you-create-a-work-profile-android)
- [Créer un profil professionnel et inscrire votre appareil dans Intune](/intune/enduser/create-a-work-profile-and-enroll-your-device-in-intune-android)

### <a name="lookout-integration-to-protect-ios-devices"></a>Intégration de la protection Lookout pour les appareils Android
En octobre, Microsoft intègre la solution de Lockout qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et d’autres menaces. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur leurs appareils, l’activer et corriger les menaces signalées par celles-ci pour accéder aux données d’entreprise. Découvrez comment [configurer et déployer l’application Lookout for Work](/intune/deploy-use/configure-and-deploy-lookout-for-work-apps).
<!--TFS 1319493-->

<!--### New Microsoft Intune Company Portal available for Windows 10 devices
Microsoft is releasing a new [Microsoft Intune Company Portal for Windows 10 devices](https://go.microsoft.com/fwlink/?linkid=830663). This app, which leverages the new Windows 10 Universal format, will provide the user with an updated user experience within the app and identical experiences across all Windows 10 devices, PC and Mobile alike, while still enabling all the same functionality that they are using today.

The new app will also allow users to leverage additional platform features like single sign-on (SSO) and certificate-based authentication on Windows 10 devices. The app will be made available as an upgrade to the existing Windows 8.1 Company Portal and Windows Phone 8.1 Company Portal installs from the Windows Store.-->

### <a name="intune-app-wrapping-tool-for-android"></a>Outil de création de package de restrictions d’application Intune pour Android
Vous pouvez configurer vos applications pour utiliser des stratégies de gestion des applications mobiles (GAM) à l’aide de l’outil de création de package de restrictions d’application Intune. La prise en charge des stratégies GAM d’Intune sans nécessiter l’inscription d’appareils est désormais disponible.

### <a name="manage-printing-from-apps-managed-using-mam-policies"></a>Gestion de l’impression à partir d’applications gérées à l’aide de stratégies MAM
Vous pouvez maintenant empêcher l’impression de données d’entreprise à partir d’applications dotées de stratégies MAM. Ce paramètre est disponible sur le [portail Azure](/Intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) et pris en charge sur les appareils [iOS](/Intune/deploy-use/ios-mam-policy-settings) et [Android](/Intune/deploy-use/android-mam-policy-settings).
<!--TFS 1014328-->

### <a name="support-for-fingerprints-on-android-devices"></a>Prise en charge des empreintes sur les appareils Android
Les stratégies de gestion des applications mobiles (GAM) Android permettent à présent aux utilisateurs d’accéder à une application avec leur empreinte au lieu de taper leur code confidentiel. Cliquez [ici](/Intune/deploy-use/android-mam-policy-settings) pour en savoir plus sur les paramètres de stratégie de gestion des applications mobiles pour Android.

### <a name="notices"></a>Remarques

__Compatibilité entre Android Samsung KNOX et Intune__ Certains modèles de téléphone Samsung Galaxy Ace ne peuvent pas être gérés par Intune en tant qu’appareils Samsung KNOX. Lorsque vous inscrivez ces appareils à Intune, ils sont gérés comme des appareils Android standard.

Les références de modèle concernées sont :

* SM-G313HU
* SM-G313HY
* SM-G313M
* SM-G313MY
* SM-G313U

Aucune autre action n’est requise de votre part ou de celle de vos utilisateurs. Pour plus d’informations, consultez le site web [Samsung KNOX](https://www.samsungknox.com).

__L’application Portail d’entreprise pour Windows 8 est dépréciée ; la prise en charge des plateformes Windows Phone 8 et Windows RT est dépréciée__ Depuis octobre 2016, la prise en charge du portail d’entreprise Windows 8 par Microsoft Intune est dépréciée. Microsoft Intune ne prendra également plus en charge les plateformes Windows Phone 8 et Windows RT. Ainsi, vous ne pourrez plus inscrire ni mettre à jour des appareils Windows Phone 8 ou Windows RT.

Néanmoins, vous pourrez continuer à gérer les appareils Windows Phone 8, Windows RT et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.

Dès novembre 2016, la prise en charge du portail d’entreprise Windows Phone 8 ne sera plus assurée.
<!--TFS 1255391-->

### <a name="whats-coming"></a>Nouveautés à venir

__Nouveau portail d’entreprise Microsoft Intune disponible pour les appareils Windows 10__ Microsoft lance un nouveau portail d’entreprise Microsoft Intune pour les appareils Windows 10. Cette application, au nouveau format Windows 10 universel, fournira à l’utilisateur une expérience inédite de l’application et une expérience identique sur tous les appareils Windows 10, PC et mobiles, tout en offrant les mêmes fonctionnalités qu’aujourd’hui.

La nouvelle application permettra également aux utilisateurs de tirer parti de fonctionnalités de plateforme supplémentaires telles que l’authentification unique (SSO) et par certificat sur les appareils Windows 10. Elle sera disponible en tant que mise à niveau du portail d’entreprise Windows 8.1 actuel et du portail d’entreprise Windows Phone 8.1 installés à partir du Windows Store. Pour plus d’informations, consultez [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).
<!--TFS 1016502-->

## <a name="september-2016"></a>Septembre 2016
### <a name="new-features-announcements-and-information"></a>Nouvelles fonctionnalités, annonces et informations
* [Accès conditionnel Windows](#windows-conditional-access)
* [Prise en charge d’iOS 10](#ios-10-support)
* [L’outil de création de package de restrictions d’application prend en charge la gestion des applications mobiles (GAM) sans inscription d’appareils pour Android et iOS](#app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios)
* [Début de la transition des groupes Intune vers les groupes Azure Active Directory en septembre](#intune-groups-begin-transitioning-to-azure-active-directory-in-september)
* [Intégration de la protection Lookout pour les appareils Android](#lookout-integration-to-protect-android-devices)
* [Mises à jour du portail d’entreprise pour Android, iOS et Windows](#company-portal-updates)
* [Glossaire Intune](#intune-glossary)
* [Nouveautés à venir](#whats-coming)

### <a name="windows-conditional-access"></a>Accès conditionnel Windows
Vous pouvez maintenant créer des stratégies d’accès conditionnel via la console d’administration Intune pour bloquer l’accès des PC Windows à Exchange Online et à SharePoint Online. Vous pouvez également créer des stratégies d’accès conditionnel pour bloquer l’accès à des applications de bureau Office et à des applications universelles.

### <a name="ios-10-support"></a>Prise en charge d’iOS 10
Les scénarios existants pour la gestion Intune MDM et GAM sont compatibles avec iOS 10. Pour obtenir des conseils, consultez le [blog de l’équipe de support technique Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

### <a name="app-wrapping-tool-supports-mam-without-device-enrollment-for-android-and-ios"></a>L’outil de création de package de restrictions d’application prend en charge la gestion des applications mobiles (GAM) sans inscription d’appareils pour Android et iOS
Cet outil de ligne de commande permet d’activer la fonctionnalité GAM d’Intune dans les applications métier pour iOS et Android. C’est la façon la plus simple d’incorporer le SDK Intune MAM dans votre application, pour que celle-ci applique les stratégies de gestion des appareils mobiles déployées via Intune. Avec les stratégies de gestion des appareils mobiles, vous pouvez :

1. Chiffrer les données de l’application.
2. Exiger que l’utilisateur entre un code confidentiel au démarrage de l’application.
3. Autoriser l’application à transférer des données uniquement vers d’autres applications gérées.
4. Interdire à l’application de sauvegarder des données sur Android, iTunes et iCloud.
5. Autoriser uniquement les opérations couper, copier et coller vers et depuis d’autres applications gérées.

La préversion publique du dernier outil de création de package de restrictions d’application Intune prend désormais en charge la gestion des applications mobiles (GAM) sans inscription des appareils dans des applications métier internes pour iOS et Android. Cela signifie que vos utilisateurs finaux n’ont pas besoin d’inscrire leurs appareils dans Intune pour utiliser des applications métier avec la fonctionnalité GAM.

Toute personne peut tester la préversion publique du logiciel et lire la documentation d’aide, disponible dans msintuneappsdk sur GitHub :

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

<p style="margin-left: 40px">http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Avant d’installer et d’utiliser la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android et iOS, effectuez les opérations suivantes :

* Lisez les termes du contrat de licence Microsoft applicables à la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android et iOS.
* Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android, vous reconnaissez accepter ces termes du contrat de licence. Si vous ne les acceptez pas, n'utilisez pas le logiciel.
<!---TFS 1235607--->

### <a name="intune-groups-begin-transitioning-to-azure-active-directory-in-september"></a>Début de la transition des groupes Intune vers les groupes Azure Active Directory en septembre
Certains nouveaux comptes Intune utiliseront les groupes de sécurité Active Directory Azure au lieu des groupes d’utilisateurs Intune. Vous serez averti que vous utilisez des groupes de sécurité par l’ajout d’un lien vers le Portail de gestion Azure dans la page Groupes du Portail Intune.

### <a name="lookout-integration-to-protect-android-devices"></a>Intégration de la protection Lookout pour les appareils Android
Microsoft intègre la solution de protection contre les menaces mobiles de Lookout, qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et autres menaces présents sur les appareils. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur les appareils Android, activer l’application et corriger les menaces signalées dans l’application Lookout for Work pour pouvoir accéder aux ressources. Pour plus d’informations, consultez [Restrict access based on device, network, and application risk](restrict-access-based-on-device-network-app-risk.md) (Restreindre l’accès en fonction du risque évalué pour l’appareil, le réseau et l’application).


### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise

__Android__

<p style="margin-left: 40px">**Ajout de « Notifications » dans le portail d’entreprise pour Android**<br/>
<p style="margin-left: 40px">Une nouvelle icône Notifications a été ajoutée dans la page d’accueil du Portail d’entreprise pour Android. En appuyant sur cette icône, vous accédez directement à la page Notifications. Cette page affiche aux utilisateurs finaux tous les éléments importants à examiner dans l’application Portail d’entreprise, par exemple, la non-conformité d’un appareil, une mise à jour de l’inscription ou l’activation d’une inscription. L’application Portail d’entreprise iOS offre déjà cette fonctionnalité de notifications. Avec la nouvelle page Notifications, si l’appareil est déjà inscrit, l’utilisateur ne verra pas la page Configuration de l’accès à l’entreprise s’afficher chaque fois qu’il accède ou revient au Portail d’entreprise. Si vous rédigez votre propre guide de l’utilisateur final, mettez à jour votre documentation pour refléter cette modification. Vous trouverez des captures d’écran mises à jour [ici](https://aka.ms/androidcpupdate).  

__iOS__
<p style="margin-left: 40px">**Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
<p style="margin-left: 40px">Tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS doivent maintenant utiliser la version la plus récente. Les nouveaux utilisateurs peuvent uniquement télécharger la dernière version, et les utilisateurs actuels doivent effectuer une mise à jour vers cette version. La nouvelle version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent des versions antérieures d’iOS ne pourront pas accéder au Portail d’entreprise ni être inscrits si les utilisateurs ne mettent pas à jour ces appareils vers iOS 8.0 ou une version ultérieure, et ne mettent pas à jour l’application Portail d’entreprise vers la nouvelle version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.
<!---TFS 1283165--->

<p style="margin-left: 40px">**Améliorations apportées à l’accès des utilisateurs finaux iOS à leurs applications**<br/>
<p style="margin-left: 40px">Les modifications suivantes ont été apportées aux vignettes d’applications dans l’application Portail d’entreprise pour iOS. Ces vignettes dirigent les utilisateurs vers différentes vues dans un emplacement unique, à savoir le site web du Portail d’entreprise, pour toutes leurs applications. Les restrictions d’Apple n’autorisent pas l’affichage des applications métier et gérées de l’App Store dans l’application Portail d’entreprise, ce qui oblige les utilisateurs à consulter plusieurs vues pour trouver leurs différentes applications.

<p style="margin-left: 40px">La vignette **Applications d’entreprise** pointait auparavant vers une liste de toutes les applications dans l’onglet TOUT du site web du Portail d’entreprise. Elle a toujours le même comportement, mais son nom a été remplacé par **Toutes les applications**.

<p style="margin-left: 40px">La vignette **Autres applications** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les applications dont l’affichage dans le Portail d’entreprise était autorisé par Apple. Cette vignette s’appelle maintenant **Applications proposées**. Quand l’utilisateur appuie dessus, il accède à l’onglet SÉLECTION du site web du Portail d’entreprise.

<p style="margin-left: 40px">La vignette **Catégories** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les catégories d’applications. Son nom n’a pas changé, mais la vignette pointe maintenant vers l’onglet CATÉGORIES du site web du Portail d’entreprise. Vous trouverez des captures d’écran mises à jour [ici](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
  <!---TFS 1317133--->

<p style="margin-left: 40px">**Invitation à l’installation de l’application Managed Browser iOS si un professionnel de l’informatique définit cette obligation pour une application**<br/>
<p style="margin-left: 40px">Si vous avez configuré un clip web pour qu’il s’ouvre uniquement dans le navigateur géré, et que ce navigateur n’est pas installé sur l’appareil, l’application Portail d’entreprise sur l’appareil invitera l’utilisateur à installer le navigateur géré pour permettre l’ouverture du clip web.
  <!---TFS 1228570--->

__Windows__
<p style="margin-left: 40px">**Bouton Commentaires ajouté à l’application Portail d’entreprise Windows Phone 8.1**<br/>
<p style="margin-left: 40px">L’application Portail d’entreprise Windows Phone 8.1 comporte un nouveau bouton « Envoyer des commentaires » qui permet aux utilisateurs d’envoyer des commentaires sur l’application. Pour afficher le bouton, les utilisateurs appuient sur le menu « points de suspension » en bas à droite de l’écran de l’application Portail d’entreprise, puis sur **Envoyer des commentaires**. Les commentaires, après avoir été regroupés et rendus anonymes, sont utilisés par Microsoft pour améliorer l’expérience utilisateur dans l’application Portail d’entreprise.
<!---TFS 1317806--->

### <a name="intune-glossarybr"></a>Glossaire Intune</br>
Nous avons ajouté une nouvelle rubrique [Glossaire](https://docs.microsoft.com/intune/understand-explore/intune-glossary) à la bibliothèque pour vous aider à comprendre certains des termes utilisés dans le produit Intune.

## <a name="august-2016"></a>Août 2016
### <a name="app-management"></a>Gestion d'applications
<!---@Barry, I created the buckets of App management, Device management, etc but am not tied to them. Just wanted to break up and organize the feature list. If you're going to take over the Company Portal section, please talk to Stacie about how she's been organizing it. --->

__Applications masquées et affichées pour iOS 9.3__ Pour les appareils exécutant iOS 9.3 ou une version ultérieure, vous pouvez utiliser la liste des applications affichées et masquées dans la stratégie de configuration générale d’iOS pour :
- Spécifier une liste d’applications à masquer aux utilisateurs. Les utilisateurs ne peuvent pas afficher ou lancer ces applications.
- Spécifier une liste d’applications que les utilisateurs peuvent afficher et lancer. Aucune autre application ne peut être affichée ou lancée.

Les applications que vous pouvez spécifier incluent celles que vous avez déployées, ainsi que les applications iOS intégrées telles que Messages et Notes. Pour plus d’informations, consultez [Paramètres de la stratégie iOS dans Microsoft Intune]( https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune).
<!---TFS 1279009 checked--->
__Stratégie des applications autorisées et bloquées pour les appareils dotés de Samsung KNOX__ Vous pouvez désormais configurer une stratégie personnalisée pour les appareils dotés de Samsung KNOX, qui vous permet de créer l’un des éléments suivants :
- Une liste d’applications qui sont bloquées sur l’appareil. Même si elle est installée, une application incluse dans la liste d’applications bloquées ne peut pas être activée sur l’appareil.
- Une liste d’applications que les utilisateurs de l’appareil sont autorisés à installer à partir du magasin Google Play. Aucune autre application ne peut être installée à partir de ce magasin.

Ces paramètres peuvent uniquement être utilisés par les appareils qui exécutent Samsung KNOX.
Pour plus d’informations, consultez [Utiliser des stratégies personnalisées pour autoriser et bloquer des applications pour les appareils Samsung KNOX]( custom-policy-to-allow-and-block-samsung-knox-apps.md).
<!---TFS 1311629 checked --->
__Nouvelles applications compatibles avec les stratégies de gestion des applications mobiles (MAM)__ L’application Yammer pour [iOS](https://itunes.apple.com/app/yammer/id289559439?mt=8) et [Android](https://play.google.com/store/apps/details?id=com.yammer.v1) est désormais compatible avec les [stratégies de gestion des applications mobiles (MAM) Intune](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), que l’appareil soit inscrit ou non.

Pour obtenir la liste complète des applications MAM compatibles, consultez le site des [partenaires des applications Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners).
<!--- TFS 1252335 & 1252336 checked--->


<!--- I started putting TFS numbers in the What's Coming topic and found it helpful when updating the What's New. Up to you if you want to continue. --->

__Applications de visionneuse Intune__ Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
- Intune AV Viewer
- Intune PDF Viewer
- Intune Image Viewer pour Android depuis Google Play

Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle [application Rights Management (partage RMS) pour Android](https://docs.microsoft.com/en-us/intune/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune#viewing-media-files-with-the-rights-management-sharing-app), qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. Quand l’application de visionneuse Intune ne sera plus prise en charge, elle sera supprimée du Google Store et ne sera plus disponible pour une utilisation ultérieure.

### <a name="device-management"></a>Gestion des appareils
__Prise en charge d’Android 7.0__ Intune assure la prise en charge dès le premier jour du système d’exploitation Android 7.0 pour les appareils mobiles, bientôt disponible.
<!---TFS 1262053--->
### <a name="google-removal-of-remote-passcode-reset-capability-on-android-70-devices"></a>Suppression par Google de la fonctionnalité de réinitialisation à distance du code secret sur les appareils Android 7.0
Google supprime la fonctionnalité permettant aux utilisateurs finaux et aux administrateurs informatiques de réinitialiser à distance le code secret de leurs appareils Android 7.0. Auparavant, les administrateurs informatiques pouvaient réinitialiser à distance le code secret d’un utilisateur, et les utilisateurs finaux pouvaient réinitialiser leur code secret depuis le site web du Portail d’entreprise.



### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise
__Site web Portail d’entreprise__
- **Lien des commentaires sur le Portail d’entreprise à l’attention de Microsoft** <br/>
Le site web du Portail d’entreprise permet aux utilisateurs finaux de sélectionner un nouveau lien « Commentaires », en bas de la page, pour envoyer des commentaires à Microsoft concernant leur expérience d’utilisation du site. Les commentaires regroupés sont anonymes et permettent à Microsoft d’améliorer le site web du Portail d’entreprise, afin d’optimiser cette expérience.
<!--- TFS 1313657 checked--->

__iOS__
- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
L’application Microsoft Intune Managed Browser pour iOS a été mise à jour pour prendre en charge les appareils exécutant iOS 8.0 ou version ultérieure. Même si les appareils iOS 7.1 peuvent toujours utiliser l’application Managed Browser existante, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou version ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253 checked--->

### <a name="whats-coming"></a>Nouveautés à venir
__Début de la transition des groupes Intune vers les groupes Azure Active Directory dès septembre 2016__ Intune crée une expérience de gestion de groupe qui utilise les groupes de sécurité Azure Active Directory (AAD) en tant que groupes d’utilisateurs et d’appareils dans Intune. Ces groupes seront utilisés pour la gestion, le déploiement de stratégies et de profils de tous les groupes **lorsque nous introduirons le nouveau portail d’administration Intune basé sur Azure**.

Grâce à cette nouvelle expérience, vous n’aurez plus besoin de dupliquer des groupes entre des services, **ce qui vous permet d’accéder à certaines fonctionnalités de groupes Azure Active Directory Premium (AADP)**, tout en bénéficiant d’une extensibilité lors de l’utilisation de PowerShell et Graph. La gestion des groupes sera également unifiée lors de la gestion de la mobilité d’entreprise.

Pour activer la transition vers les groupes de sécurité, nous allons devoir modifier la **console d’administration actuelle**. **Ces modifications et l’utilisation des groupes de sécurité Azure AD seront consignées dans la documentation d’Intune**.

Les clients qui ne connaissent pas Intune constateront **certaines modifications du groupe de sécurité avant les clients actuels**.

Outre les modifications dans la gestion de groupe, **les fonctionnalités suivantes deviendront obsolètes** :
- Exclusion de membres ou de groupes lors de la création d’un groupe
- Groupes **Utilisateurs non groupés** et **Appareils non groupés**
- **Gérer des groupes** dans le rôle d’administrateur de service
- Alertes personnalisées basées sur le groupe pour les règles de notification
- Glissement des groupes dans les rapports
<!--- TFS 1295329--->

__Ajout de « Notifications » sur le portail d’entreprise pour Android__ En septembre, nous publierons une mise à jour du Portail d’entreprise pour Android, qui présentera la nouvelle icône **Notifications** de la page d’accueil. En appuyant sur cette icône, vous pourrez accéder à la page **Notifications** qui indiquera à votre utilisateur final tous les éléments qui nécessitent son attention particulière dans l’application de portail d’entreprise, tels que la non-conformité d’un appareil, ainsi que les mises à jour ou les activations d’inscriptions. Si vous utilisez également l’application de portail d’entreprise iOS, vous pouvez déjà utiliser ces notifications. Une fois la page **Notifications** en place, si votre appareil est déjà inscrit, vous ne verrez plus la page **Configuration de l’accès à l’entreprise** à chaque fois que vous accédez au portail d’entreprise pour Android ou que vous y revenez. Nous savons que beaucoup d’entre vous ont créé des conseils pour l’utilisateur final et que vous appréciez de recevoir des notifications avancées lorsque vos conseils/captures d’écrans doivent être mis à jour. Mettez à jour votre documentation pour refléter les modifications de l’expérience à venir. Vous trouverez des captures d’écran mises à jour ici : https://aka.ms/androidcpupdate.  

### <a name="service-deprecation"></a>Désapprobation du service
<!---@Barry, we started listing service deprecations earlier this summer. --->
- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
En septembre, tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS devront utiliser la dernière version. Les nouveaux utilisateurs pourront uniquement télécharger la dernière version et les utilisateurs actuels devront effectuer une mise à jour vers cette version. La dernière version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent d’anciennes versions d’iOS ne pourront pas utiliser le portail d’entreprise ni être inscrits tant qu’ils n’auront pas été mis à jour vers iOS 8.0 ou version ultérieure, et que l’application Portail d’entreprise n’aura pas été mise à jour vers la dernière version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.  

- **Mise à jour de la version minimale de Managed Browser pour iOS 8.0**<br/>
En août, Intune publiera une mise à jour de l’application Microsoft Intune Managed Browser pour iOS qui prendra uniquement en charge les appareils exécutant iOS version 8.0 ou ultérieure. Même si les appareils iOS 7.1 pourront toujours utiliser l’application Managed Browser, nous vous recommandons d’inciter vos utilisateurs à procéder à la mise à jour pour iOS 8.0 ou ultérieure. Ils pourront ainsi accéder aux nouvelles fonctionnalités de Managed Browser et en tirer pleinement parti.  
<!---TFS 1313253--->

- **Les applications du portail d’entreprise pour Windows 8 et Windows Phone 8 sont dépréciées depuis septembre 2016** <br/>
À compter de septembre 2016, les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour plateformes Windows Phone 8 et Windows 8 ne pourront plus bénéficier du support Microsoft Intune. Mettez à jour vos appareils vers Windows 8.1 et Windows Phone 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer la distribution des applications sur ces appareils.
<!---TFS 1255391--->

<!--- - **Custom Group Targeting of Notification Rules Removal.**<br/>
Intune notification rules define who an email alert will be sent to from Intune. Currently, you can configure notification rules to send emails to all users of devices in an Intune device group that you created. From around June 1st 2016 moving forward, targeting user-created groups will no longer be supported.

    Today, to target a notification rule to a group you created from the Microsoft Intune administration console, you would take the following steps:

    In the **Admin** workspace, click **Notification Rules** > **Create New Rule**

    In step two of the Create Notification Rule Wizard, select the device groups which the rule will target. This step, “select device groups”, is being removed from the Intune Console.

    The preliminary timeline for this change is as follows:
    - In August, 2016, new tenants will not see step two of the Create Notification Rule Wizard. Exiting tenants are unaffected.
    - Around September, 2016, some existing tenants will not see the “select device groups” in the wizard.
    - Around November, 2016, we expect that all tenants will not see the “select device groups” in the wizard.

--->

## <a name="july-2016"></a>Juillet 2016
### <a name="app-management"></a>Gestion d'applications

__Améliorer l’expérience de mise à jour de profil d’approvisionnement d’application__ Les applications mobiles métier Apple iOS intègrent un profil d’approvisionnement et du code signé avec un certificat. Lorsque l’application s’exécute sur un appareil iOS, iOS confirme l’intégrité de l’application iOS et applique les stratégies définies par le profil de configuration.

Le certificat de signature d’entreprise que vous utilisez pour signer des applications dure généralement 3 ans. Toutefois, le profil de configuration expire au bout d’1 an. Grâce à cette mise à jour, Intune vous offre les outils pour déployer de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration alors que le certificat est toujours valide. Pour plus d’informations, consultez [Utilisation de stratégies de profil de configuration d’applications mobiles iOS pour maintenir vos applications métier à jour](/intune/deploy-use/ios-mobile-app-provisioning-profiles).
<!--- TFS 1280247--->

__Disponibilité du Xamarin SDK pour applications Intune__ Le composant Xamarin SDK pour applications Intune vous permet d’activer les fonctionnalités de gestion des applications mobiles Intune dans vos applications Android et iOS mobiles développées avec Xamarin. Le composant est disponible dans le [Xamarin Store](https://components.xamarin.com/view/Microsoft.Intune.MAM) ou sur la [page Github de Microsoft Intune](https://github.com/msintuneappsdk).
<!--- TFS 1061478 --->

### <a name="device-management"></a>Gestion des appareils
__Augmentation du nombre d’inscriptions d’appareils__ Intune augmente le nombre maximal d’inscriptions d’appareils configurables en repoussant leur limite de 5 appareils par utilisateur à 15.
<!---TFS 1289896 --->

__Intégration de TeamViewer sur les PC Windows exécutant le logiciel client Intune__
L’intégration de [TeamViewer](https://www.teamviewer.com) sur les PC Windows exécutant le client Intune vous permet d’établir des sessions d’assistance à distance avec des PC Windows, afin d’aider les départements de support technique des utilisateurs finaux. Cela inclut Windows 7, 8, 8.1 et Windows 10. Pour plus d’informations, consultez [Tâches courantes de gestion des PC Windows avec le client Microsoft Intune](/intune/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client).
<!---TFS 1284856--->

### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise

__Site web Portail d’entreprise__
- **Amélioration de l’interface d’inscription d’appareils Windows**<br/>
Lorsque vous utilisez l’accès conditionnel, les étapes d’inscription pour Windows 8.1, Windows 10 Desktop et Windows 10 Mobile ont été précisées dans le site web du portail d’entreprise. Les utilisateurs peuvent à présent voir deux étapes distinctes, « Inscription de l’appareil » et « Jonction au lieu de travail », ce qui leur permet de consulter plus facilement l’état de leur appareil et de terminer le processus en cas d’échec de l’outil Workplace Join (WPJ). Ces différentes étapes sont également censées simplifier le processus de résolution des problèmes pour les administrateurs. Auparavant, lorsque les utilisateurs finaux inscrivaient un appareil et que toutes les étapes de l’inscription réussissaient à l’exception de la jonction au lieu de travail, l’appareil inscrit n’apparaissait pas dans la liste des appareils identifiables par les utilisateurs, ce qui pouvait s’avérer déroutant.

__Android__
- **Application Portail d’entreprise Android**<br/>
Si un message d’erreur s’affiche pour les utilisateurs finaux Android en leur indiquant qu’il manque un certificat requis pour leur appareil, ils peuvent appuyer sur un bouton « Comment résoudre ce problème » pour consulter les [étapes](/intune/enduser/your-device-is-missing-a-required-certificate-android#your-device-is-missing-a-certificate-required-by-your-it-administrator) à suivre afin d’installer le certificat manquant. Si les utilisateurs suivent ces étapes, mais qu’un autre message d’erreur indique « Certificat manquant », ils sont invités à contacter leur administrateur et à fournir ce [lien](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), qui mène vers les étapes à suivre pour résoudre ce problème de certificat.

- **Limiter les installations d’applications à chargement indépendant sur les appareils inscrits**<br/>
Les appareils Android ne peuvent plus installer d’applications par le biais du site web du portail d’entreprise, sauf s’ils ont été inscrits dans Intune à l’aide de l’application portail d’entreprise Intune pour Android.
<!---TFS 1299082--->

__iOS__
- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise iOS**<br/>
Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet **Mes appareils** de l’application Portail d’entreprise pour iOS. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise.

L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune. En outre, Intune désapprouve l’utilisation de comptes DEM avec le Programme d’inscription d’appareils Apple ou l’outil Apple Configurator. Ces deux méthodes d'inscription prennent déjà en charge l'inscription sans utilisateur pour les appareils iOS partagés.

Utilisez uniquement les comptes DEM lors l'inscription sans utilisateur d’appareils partagés n'est pas disponible. Pour plus d’informations, consultez [Inscrire des appareils d’entreprise avec le Gestionnaire d’inscription d’appareil dans Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).
<!---TFS 1233681--->

### <a name="change-of-names-for-windows-features"></a>Modification des noms de fonctionnalités Windows
- [Microsoft Passport pour Windows](/intune/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune) se nomme maintenant **Windows Hello Entreprise**.
- [Protection des données d’entreprise](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune) est maintenant appelé **Protection des informations Windows**.

## <a name="june-2016"></a>Juin 2016
### <a name="intune-service-health"></a>État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Ces informations sont désormais disponibles sur le portail de gestion Office 365 sous État du service. Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/enterprisemobility/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).

### <a name="app-management"></a>Gestion d'applications
- **Amélioration de la configuration des stratégies de données d’entreprise Windows 10.** Nous avons amélioré la configuration des stratégies de protection des données d’entreprise Windows 10 au niveau de la création des règles d’application, de la définition des limites du réseau et d’autres paramètres de protection des données d’entreprise. Pour plus d’informations, consultez la rubrique [Create an enterprise data protection (EDP) policy using Microsoft Intune](https://technet.microsoft.com/itpro/windows/keep-secure/create-edp-policy-using-intune).


### <a name="device-management"></a>Gestion des appareils
- **Paramètre de stratégie Windows Defender pour une protection contre les applications potentiellement indésirables.** Un nouveau paramètre Windows Defender nommé **Potentially Unwanted Application Detection** (Détection des applications potentiellement indésirables) a été ajouté à la stratégie de configuration générale pour Windows 10 Desktop et Mobile. Vous pouvez utiliser ce paramètre pour empêcher les postes de travail Windows inscrits d’exécuter des logiciels considérés par Windows Defender comme potentiellement indésirables. Vous pouvez empêcher ces applications d’être exécutées ou utiliser le mode Audit pour être informé lorsqu’une application potentiellement indésirable est installée. Pour plus d’informations, consultez [Paramètres de la stratégie Windows 10 dans Microsoft Intune](https://docs.microsoft.com/en-us/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).
<!---TFS 1244478--->

### <a name="conditional-access"></a>Accès conditionnel
- **Stratégie de contrôle d’accès au réseau Cisco ISE pour Intune.**  Les clients qui utilisent Cisco Identity Service Engine (ISE) 2.1 et Microsoft Intune peuvent définir une stratégie de contrôle d’accès au réseau dans ISE.

    Quand vous utilisez cette stratégie, les appareils qui doivent se connecter au réseau Wi-Fi ou VPN doivent respecter les conditions suivantes avant d’obtenir l’autorisation d’accès :

    * Ils doivent être gérés par Intune
    * Ils doivent être conformes à toutes les stratégies de conformité Intune déployées

 Les utilisateurs finaux d’appareils non conformes sont invités à s’inscrire et à résoudre les problèmes de conformité pour obtenir l’autorisation d’accès.
- **Accès conditionnel pour le navigateur.** Vous ne pourrez pas définir une stratégie d’accès conditionnel pour [Exchange Online](/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune) et [SharePoint Online](/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune) afin que ces applications soient uniquement accessibles à partir de navigateurs web pris en charge sur des appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à des sites Outlook Web Access (OWA) et SharePoint avec des appareils iOS et Android seront invités à inscrire leurs appareils avec Intune, et à résoudre les problèmes d'incompatibilité avant de pouvoir finaliser la connexion.
<!---TFS 1175844--->

- **Dynamics CRM Online prend en charge l’accès conditionnel.** Vous pouvez définir une stratégie d’accès conditionnel pour [Dynamics CRM Online](/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune) afin que cette application soit uniquement accessible aux appareils iOS et Android gérés et conformes. Les utilisateurs finaux qui essaient de se connecter à l’application mobile Dynamics CRM sur un appareil iOS ou Android seront invités à s’inscrire à Intune et à résoudre les éventuels problèmes de non conformité avant de finaliser la connexion.
<!---TFS1295358--->

### <a name="intune-company-portal-updates"></a>Mises à jour du Portail d’entreprise Intune

__Application Portail d’entreprise Android__

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils interdisent l’installation d’applications à partir de sources inconnues (Android 4.0+) », le message « L’installation à partir de sources inconnues doit être désactivée » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Sécurité**, puis désactiver **Sources inconnues**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-off-unknown-sources-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger que les appareils recherchent les menaces de sécurité (Android 4.0+) », le message « Rechercher les menaces de sécurité sur l’appareil » s’affiche aux utilisateurs finaux d’appareils Android 4.0 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Google** > **Sécurité**, puis activer **Rechercher les menaces de sécurité sur l’appareil**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) supplémentaires sur le message et la raison pour laquelle ils doivent activer le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie visant à « Exiger la désactivation du débogage USB (Android 4.2+) », le message « Le débogage USB doit être désactivé » s’affiche aux utilisateurs finaux d’appareils Android 4.2 ou version ultérieure. Les utilisateurs doivent accéder à **Paramètres** > **Options pour développeurs**, puis désactiver **Débogage USB**. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-off-usb-debugging-android) supplémentaires sur le message et la raison pour laquelle ils doivent désactiver le paramètre.

- Quand les administrateurs informatiques appliquent la nouvelle stratégie « Niveau minimal du correctif de sécurité Android (Android 6.0+), le message « Cet appareil n’est pas au niveau minimal du correctif de sécurité Android » s’affiche aux utilisateurs finaux d’appareils Android 6.0 ou version ultérieure. Les utilisateurs doivent installer le correctif de sécurité demandé. Un lien contenu dans le message de compatibilité permet aux utilisateurs d’obtenir des [informations](/Intune/EndUser/you-are-asked-to-turn-on-scan-device-for-security-threats-android) sur la façon d’installer le correctif de sécurité demandé et de voir quel correctif de sécurité est actuellement installé.

__Application Portail d’entreprise iOS__

- Lorsque les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour consulter les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement](/Intune/EndUser/sync-your-device-manually-ios).

- L’application Portail d’entreprise Microsoft Intune pour iOS a été mise à jour pour prendre en charge iOS 8.0 et version ultérieure. Cette mise à jour signifie que les utilisateurs finaux ne peuvent installer l’application Portail d’entreprise et inscrire de nouveaux appareils dans Intune que si l’appareil exécute iOS 8.0 ou version ultérieure. Les utilisateurs qui ont déjà inscrit des appareils exécutant une version non prise en charge d'iOS peuvent continuer à utiliser l'application Portail d'entreprise qui figure sur leur appareil.


## <a name="may-2016"></a>Mai 2016
Toutes ces fonctionnalités sont également prises en charge pour les déploiements hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez la page [Nouveautés hybrides](https://technet.microsoft.com/en-us/library/mt718155.aspx).

### <a name="documentation"></a>Documentation
Bienvenue dans la préversion de [docs.microsoft.com](https://docs.microsoft.com/en-us/intune).
Il s’agit d’une plateforme de contenu moderne, entièrement nouvelle, conçue pour permettre à nos clients de comprendre et d’utiliser plus aisément Intune.
Pour découvrir toutes les nouvelles fonctionnalités, consultez [Introducing docs.microsoft.com](https://docs.microsoft.com/teamblog/introducing-docs-microsoft-com/) (Présentation de docs.microsoft.com).

### <a name="intune-service-health"></a>État du service Intune
Les informations d’état du service d’Intune ont été déplacées vers un emplacement central avec d’autres services Microsoft. Vous trouvez désormais ces informations sur le [portail de gestion Office 365](https://portal.office.com/Admin/Default.aspx) sous **État du service**.
Pour plus d’informations, consultez [ce billet de blog](https://blogs.technet.microsoft.com/microsoftintune/2016/04/28/intune-service-health-is-now-available-in-the-office-365-portal/).


### <a name="app-management"></a>Gestion d'applications
- **SDK GAM : prise en charge de la configuration de longueur de code confidentiel.** Vous pourrez spécifier la longueur du code confidentiel des applications MAM comme s’il s’agissait du code confidentiel d’un appareil. Cette opération obligera les utilisateurs finaux à respecter les nouvelles restrictions que vous définissez. Ils verront un écran légèrement différent pour prendre en compte la saisie d’un code confidentiel plus long. Pour plus d’informations, consultez [Paramètres de stratégie MAM pour Android](/intune/deploy-use/android-mam-policy-settings) et [Paramètres de stratégie MAM pour iOS](/intune/deploy-use/ios-mam-policy-settings).

- **Skype Entreprise pour iOS et Android.** Vous pouvez maintenant cibler Skype Entreprise avec [MAM sans stratégie d’inscription](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune). Une fois les utilisateurs connectés, les stratégies MAM sont appliquées.

- **Nouvelles applications disponibles pour la gestion avec les stratégies GAM.** Les applications Microsoft Word, Excel et PowerPoint pour Android peuvent désormais être associées avec des stratégies MAM sur des appareils qui ne sont pas inscrits auprès d’Intune. Pour obtenir la liste complète des applications prises en charge, accédez à la galerie d’applications mobiles Microsoft Intune sur la page des [partenaires de l’application Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx).


### <a name="company-portal-updates"></a>Mises à jour du Portail d’entreprise

#### <a name="android-company-portal-app"></a>Application Portail d’entreprise Android
- **Notifications toast pour l’utilisateur final** : les utilisateurs finaux voient à présent des notifications toast provenant de l’application Portail d’entreprise Android quand ils inscrivent leurs appareils ou suppriment leurs appareils sur le portail d’entreprise.

- **Modifications apportées aux comptes des gestionnaires d’inscription d’appareil dans l’application Portail d’entreprise Android.** Pour améliorer les performances et la mise à l’échelle, Intune n’affiche plus tous les appareils Gestionnaires d’inscription d’appareil (DEM) dans le volet Mes appareils de l’application Portail d’entreprise Android. Seul l’appareil local qui exécute l'application est affiché et uniquement s'il est inscrit via l'application Portail d'entreprise. L'utilisateur DEM peut effectuer des actions sur l’appareil local, mais la gestion à distance d’autres appareils inscrits ne peut être effectuée à partir de la console d'administration Intune.

#### <a name="company-portal-website"></a>Site web Portail d’entreprise
- **Site web Portail d’entreprise : une bannière d’identification de l’appareil fournit d’autres informations aux utilisateurs finaux.** Désormais, les utilisateurs finaux peuvent facilement identifier l’appareil qu’ils ont sélectionné lorsqu’ils utilisent le site web Portail d’entreprise. Si un appareil incorrect est sélectionné, ils peuvent sélectionner l’appareil approprié en cliquant sur le lien **Tap here** (Appuyer ici) dans la bannière de la page d’accueil.

### <a name="service-deprecation"></a>Désapprobation du service
- **Applications de visionneuse Intune.** Avec la publication de la nouvelle application de partage RMS, nous allons supprimer les applications de visionneuse Intune suivantes à compter du mois d’août 2016 :
    - Intune AV Viewer
    - Intune PDF Viewer
    - Intune Image Viewer pour Android depuis Google Play

  Au lieu d’utiliser les applications de visionneuse Intune, nous vous recommandons d’utiliser la nouvelle application de gestion des droits (partage RMS) pour Android, qui vous permet de déployer une application unique à la place de trois applications distinctes pour afficher en toute sécurité les fichiers d’entreprise sur les appareils Android. En savoir plus sur l’application de partage RMS (avec un lien vers la documentation).

- **Ciblage de groupe personnalisé de suppression des règles de notification.**
Les règles de notification Intune définissent les destinataires d’une alerte par e-mail envoyée par Intune. Actuellement, vous pouvez configurer des règles de notification pour envoyer des e-mails à tous les utilisateurs d’appareils d’un groupe d’appareils Intune que vous avez créé. Aux alentours du 1er juin 2016, le ciblage des groupes créés par l’utilisateur n’est plus pris en charge.

    Aujourd’hui, pour cibler une règle de notification sur un groupe que vous avez créé à partir de la console d’administration Microsoft Intune, procédez comme suit :

    Dans l’espace de travail **Administration**, cliquez sur **Règles de notification** > **Créer une règle**.

    À l’étape 2 de l’Assistant Créer règle de notification, sélectionnez les groupes d’appareils que la règle doit cibler. Cette étape, « Sélection de groupes d’appareils », va être supprimée de la console Intune.

    Le calendrier relatif à cette modification est le suivant :
    - En juin 2016, les nouveaux clients ne verront pas l’étape 2 de l’Assistant Créer règle de notification. Les clients existants ne sont pas affectés.
    - Vers le mois d’aout 2016, certains clients existants ne verront pas l’étape « Sélection de groupes d’appareils » dans l’Assistant.
    - Vers le mois d’octobre 2016, nous prévoyons qu’aucun client ne voie plus l’étape « Sélection de groupes d’appareils » dans l’Assistant.


- **Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**. Au cours des prochains mois, une mise à jour sera publiée pour l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 8.0 ou ultérieure. Les utilisateurs ne pourront pas inscrire de nouveaux appareils exécutant des versions d’iOS inférieures à 8.0. Les appareils inscrits qui exécutent des versions d’iOS inférieures à 8.0 continueront d’être gérés et pourront continuer à utiliser l’application Portail d’entreprise pour une durée limitée. Toutefois, les appareils doivent utiliser iOS version 8.0 ou ultérieure pour accéder aux versions les plus récentes de l’application Portail d’entreprise. Nous vous encourageons à informer les utilisateurs de mettre à jour leur système d’exploitation vers iOS version 8.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  


## <a name="april-2016"></a>Avril 2016
Toutes ces fonctionnalités sont également prises en charge pour les clients hybrides (Configuration Manager intégré à Intune).

### <a name="app-management"></a>Gestion d'applications
- **Conformité GAM de l’utilisateur.**
Vous pouvez désormais afficher l’[état](/intune/deploy-use/monitor-mobile-app-management-policies-with-Microsoft-Intune) de vos stratégies de gestion d’applications pour n'importe quel utilisateur dans votre client Azure Active Directory (AAD). Les opérations à effectuer sont les suivantes :
   - Appareils
   - Applications sur l’appareil

   Valeurs d'état :

   **Activé** : indique que la stratégie a été déployée pour l'utilisateur, que l’application a été utilisée dans un contexte professionnel et qu’elle a reçu avec succès la stratégie.

    **Non activé :** indique que la stratégie a été déployée pour l’utilisateur, mais que l’application n’a pas été utilisée au moins une fois dans un contexte professionnel depuis.


- **Contrôles GAM pour empêcher la synchronisation des contacts Outlook (Android).**
Un nouveau paramètre est disponible pour la [gestion des applications mobiles](/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) sans inscription de l'appareil. Ce paramètre vous permet d’empêcher une application de synchroniser les contacts avec le carnet d'adresses natif sur les appareils Android. Si ce paramètre est activé, les applications ciblées ne pourront plus enregistrer les contacts dans le carnet d'adresses natif. Si ce paramètre est désactivé, les applications ciblées pourront enregistrer les contacts dans le carnet d'adresses natif. Lorsque vous [réinitialisez de façon sélective un appareil ou une application](/intune/deploy-use/wipe-managed-company-app-data-with-Microsoft-Intune), les contacts déjà enregistrés dans le carnet d'adresses natif seront supprimés. Ce nouveau paramètre est initialement pris en charge par l'application Outlook sur les appareils Android.

### <a name="device-management"></a>Gestion des appareils
- **Identification de numéros de téléphone pour les appareils appartenant à l’entreprise.** Les téléphones classés comme « appartenant à l’entreprise » sont identifiés avec leur numéro de téléphone complet, par exemple, lorsque vous exécutez un rapport d’inventaire des appareils mobiles. Les numéros de téléphone de type « BYOD » continuent d’être masqués avec **** ; seuls les 4 derniers chiffres s’affichent.


### <a name="company-portal-updates"></a>Mises à jour de Portail d'entreprise
**Application Portail d’entreprise Android** Les utilisateurs qui n’ont pas inscrit leur appareil dans Intune et qui n’ont pas le bon certificat installé ne peuvent pas se connecter à l’application Portail d’entreprise Android. Le message suivant s’affiche : « Vous ne pouvez pas vous connecter, car il manque un certificat obligatoire à votre appareil ». Le message inclut un lien « Comment résoudre ce problème » permettant aux utilisateurs d’obtenir des instructions pour installer le certificat. Pour connaître les étapes que les utilisateurs finaux doivent suivre pour résoudre ce problème, consultez [Un certificat obligatoire est manquant sur votre appareil](https://technet.microsoft.com/library/mt502762.aspx#BKMK_andr_cert_missing).

**Application Portail d’entreprise iOS** Une prise en charge a été ajoutée pour l’action Tirer pour actualiser permettant d’actualiser le contenu sur l’écran d’accueil, notamment les applications répertoriées, les appareils répertoriés et les informations sur les contacts informatiques. L'action Tirer pour actualiser ne vérifie pas les informations de conformité ou de stratégie, opération qui peut être effectuée en sélectionnant la vignette correspondant à votre appareil puis en appuyant sur le bouton **Sync**.

**Application Portail d’entreprise Windows 10 Mobile et Windows Phone 8.1** Quand les utilisateurs finaux installent des applications métier, ils bénéficient d’une expérience d’installation améliorée. Si l'installation de l'application prend beaucoup de temps, les utilisateurs peuvent synchroniser manuellement leur appareil pour forcer la reprise du processus de synchronisation. Pour obtenir les instructions de l’utilisateur final, consultez [Synchroniser votre appareil manuellement pour accélérer l’installation des applications](https://technet.microsoft.com/library/mt427782.aspx#BKMK_win10m_wp81_sync_manually).

**Site web du portail d’entreprise** Quand les utilisateurs Windows 10 Mobile et Windows Phone 8.1 installent des applications métier, les nouveaux états suivants apparaissent et leur fournissent plus de détails sur l’état de leur installation :

* **En attente de la synchronisation de l’appareil** : l'utilisateur a appuyé sur « Installer » et l'appareil tente à présent de se synchroniser avec l'infrastructure Intune. La synchronisation est nécessaire pour pouvoir finaliser l'installation. Le message « En attente de la synchronisation de l’appareil » contient également un lien sur lequel les utilisateurs peuvent cliquer pour obtenir des [instructions](https://technet.microsoft.com/library/mt590895.aspx#BKMK_iwp_sync_manually) sur la synchronisation manuelle de leur appareil avec Intune si le processus de synchronisation prend beaucoup de temps ou se bloque.
* **Téléchargement** : la demande de téléchargement de l'utilisateur est en cours de traitement et l’appareil télécharge et installe l'application.

Avant l'ajout de ces états, les utilisateurs étaient désorientés lorsque l’installation de l'application prenait beaucoup de temps car seul l’état « Installation » s’affichait à l'écran, parfois pendant des heures. Grâce à l’ajout de ces nouveaux états, au lieu d'appeler le support technique, les utilisateurs peuvent désormais appuyer sur le lien « En attente de la synchronisation de l’appareil » et suivre les instructions pour forcer la reprise du processus de synchronisation.



### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.



<!--HONumber=Nov16_HO3-->


