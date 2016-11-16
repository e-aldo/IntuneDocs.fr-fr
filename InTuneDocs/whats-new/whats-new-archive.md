---
title: "Archive des nouveautés | Microsoft Intune"
description: 
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
ms.sourcegitcommit: 861b5ea3bb0772d2853942e2b3f11f607dad3774
ms.openlocfilehash: 25128cfe93280e38a03779a7e6f38ddeb3c15612


---
# <a name="whats-new-archive"></a>Archive des nouveautés

Cette page est une archive des annonces récentes dévoilées dans [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md).

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

### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new-in-microsoft-intune.md) pour en savoir plus sur les derniers développements.



<!--HONumber=Nov16_HO2-->


