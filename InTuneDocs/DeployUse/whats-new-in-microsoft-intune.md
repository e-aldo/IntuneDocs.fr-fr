---
title: "Nouveautés | Microsoft Intune"
description: "Découvrir les nouveautés de la version de Microsoft Intune de ce mois-ci et des versions précédentes"
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: mamoriss
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5b3256852431efb83fb2cc9fa067dd3f4a68a050
ms.openlocfilehash: cef0a26204a22c95d2b639500246e435fcf7f9f7


---

# Nouveautés de Microsoft Intune -- Septembre
Découvrez les nouveautés de la version de Microsoft Intune de ce mois-ci. Vous pouvez également découvrir les modifications à venir que vous devez planifier, ainsi que des informations sur les versions précédentes.

Toutes ces fonctionnalités seront finalement prises en charge pour les déploiements de clients hybrides (Configuration Manager avec Intune). Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](https://technet.microsoft.com/library/mt718155.aspx).
<!---@Barry, the above blurb stays in each version, but make sure Tyler signs off each time. Also, remember to set the ms.date in the metadata to the sprint release. --->

>[!IMPORTANT]
>Billet de blog : S’assurer que les appareils mobiles sont à jour avec Microsoft Intune<br>
>Suite aux récentes attaques des programmes malveillants « Trident » sur les appareils iOS, nous avons publié un nouveau billet de blog, [S’assurer que les appareils mobiles sont à jour avec Microsoft Intune](https://blogs.technet.microsoft.com/enterprisemobility/2016/08/26/ensuring-mobile-devices-are-up-to-date-using-microsoft-intune/), pour vous permettre de découvrir comment Intune peut vous aider à garder des appareils sécurisés et à jour.

## Prise en charge d’iOS 10
Les scénarios existants pour la gestion Intune MDM et GAM sont compatibles avec iOS 10. Pour obtenir des conseils, consultez le [blog de l’équipe de support technique Intune](https://blogs.technet.microsoft.com/intunesupport/2016/09/13/support-tip-intune-support-for-ios-10/).

## L’outil de création de package de restrictions d’application prend en charge la gestion des applications mobiles (GAM) sans inscription d’appareils pour Android et iOS
Cet outil de ligne de commande permet d’activer la fonctionnalité GAM d’Intune dans les applications métier pour iOS et Android. C’est la façon la plus simple d’incorporer le SDK Intune MAM dans votre application, pour que celle-ci applique les stratégies de gestion des appareils mobiles déployées via Intune. Avec les stratégies de gestion des appareils mobiles, vous pouvez :

1. Chiffrer les données de l’application.
2. Exiger que l’utilisateur entre un code confidentiel au démarrage de l’application.
3. Autoriser l’application à transférer des données uniquement vers d’autres applications gérées.
4. Interdire à l’application de sauvegarder des données sur Android, iTunes et iCloud.
5. Autoriser uniquement les opérations couper, copier et coller vers et depuis d’autres applications gérées.

La préversion publique du dernier outil de création de package de restrictions d’application Intune prend désormais en charge la gestion des applications mobiles (GAM) sans inscription des appareils dans des applications métier internes pour iOS et Android. Cela signifie que vos utilisateurs finaux n’ont pas besoin d’inscrire leurs appareils dans Intune pour utiliser des applications métier avec la fonctionnalité GAM.

Toute personne peut tester la préversion publique du logiciel et lire la documentation d’aide, disponible dans msintuneappsdk sur GitHub :

http://www.github.com/msintuneappsdk/intune-app-wrapper-ios-preview

http://www.github.com/msintuneappsdk/intune-app-wrapper-android-preview

Avant d’installer et d’utiliser la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android et iOS, effectuez les opérations suivantes :

* Lisez les termes du contrat de licence Microsoft applicables à la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android et iOS.
* Imprimez et conservez une copie des termes du contrat de licence pour vos archives. En téléchargeant et en utilisant la préversion de l’outil de création de package de restrictions d’application Microsoft Intune pour Android, vous reconnaissez accepter ces termes du contrat de licence. Si vous ne les acceptez pas, n'utilisez pas le logiciel.
<!---TFS 1235607--->

## Début de la transition des groupes Intune vers les groupes Azure Active Directory en septembre
Certains nouveaux comptes Intune utiliseront les groupes de sécurité Active Directory Azure au lieu des groupes d’utilisateurs Intune. Vous serez averti que vous utilisez des groupes de sécurité par l’ajout d’un lien vers le Portail de gestion Azure dans la page Groupes du Portail Intune.

## Intégration de la protection Lookout pour les appareils Android
Microsoft intègre la solution de protection contre les menaces mobiles de Lookout, qui permet de protéger les appareils mobiles Android en détectant les programmes malveillants, les applications à risque et autres menaces présents sur les appareils. La solution de Lookout vous aide à déterminer le niveau de menace et à le configurer. Vous pouvez créer une règle de stratégie de conformité dans Intune pour déterminer la conformité de l’appareil d’après l’évaluation du risque réalisée par Lookout. À l’aide de stratégies d’accès conditionnel, vous pouvez autoriser ou bloquer l’accès aux ressources d’entreprise en fonction de l’état de conformité de l’appareil.

Les utilisateurs d’appareils non conformes seront invités à inscrire leurs appareils. Ils devront également installer l’application Lookout for Work sur les appareils Android, activer l’application et corriger les menaces signalées dans l’application Lookout for Work pour pouvoir accéder aux ressources. Pour plus d’informations, consultez [Restrict access based on device, network, and application risk](restrict-access-based-on-device-network-app-risk.md) (Restreindre l’accès en fonction du risque évalué pour l’appareil, le réseau et l’application).


## Mises à jour du Portail d’entreprise

### Android

**Ajout de « Notifications » dans le Portail d’entreprise pour Android**<br/>
Une nouvelle icône Notifications a été ajoutée dans la page d’accueil du Portail d’entreprise pour Android. En appuyant sur cette icône, vous accédez directement à la page Notifications. Cette page affiche aux utilisateurs finaux tous les éléments importants à examiner dans l’application Portail d’entreprise, par exemple, la non-conformité d’un appareil, une mise à jour de l’inscription ou l’activation d’une inscription. L’application Portail d’entreprise iOS offre déjà cette fonctionnalité de notifications. Avec la nouvelle page Notifications, si l’appareil est déjà inscrit, l’utilisateur ne verra pas la page Configuration de l’accès à l’entreprise s’afficher chaque fois qu’il accède ou revient au Portail d’entreprise. Si vous rédigez votre propre guide de l’utilisateur final, mettez à jour votre documentation pour refléter cette modification. Vous trouverez des captures d’écran mises à jour [ici](https://aka.ms/androidcpupdate).  
<!---TFS 1095560--->

**Envoi de commentaires dans le portail d’entreprise pour Android**</br>
Un nouvel élément a été ajouté au menu du portail d’entreprise pour Android. Quand vous appuyez sur **Aide et commentaires**, trois actions s’affichent :
* Utilisez **Obtenir de l’aide** pour signaler un problème à votre service informatique au sujet du portail d’entreprise. Ce service crée un e-mail en utilisant votre client d’e-mail et y joint les journaux du portail d’entreprise. **Obtenir de l’aide** remplace la fonctionnalité **Envoyer les données** dans la page **paramètres**.
* Utilisez **Commentaires** pour envoyer des commentaires à l’équipe du portail d’entreprise.
* Utilisez **Évaluer notre application** pour laisser dans l’application du portail d’entreprise une évaluation ou un avis sur Google Play.

### iOS
**Modifications apportées à la prise en charge de l’application Portail d’entreprise iOS**<br/>
Tous les utilisateurs de l’application Portail d’entreprise Microsoft Intune pour iOS doivent maintenant utiliser la version la plus récente. Les nouveaux utilisateurs peuvent uniquement télécharger la dernière version, et les utilisateurs actuels doivent effectuer une mise à jour vers cette version. La nouvelle version nécessite iOS 8.0 ou version ultérieure. Les appareils qui exécutent des versions antérieures d’iOS ne pourront pas accéder au Portail d’entreprise ni être inscrits si les utilisateurs ne mettent pas à jour ces appareils vers iOS 8.0 ou une version ultérieure, et ne mettent pas à jour l’application Portail d’entreprise vers la nouvelle version. Les appareils inscrits qui exécutent les versions antérieures à iOS 8.0 continueront d’être gérés et répertoriés dans la Console d’administration Intune.
<!---TFS 1283165--->

**Améliorations apportées à l’accès des utilisateurs finaux iOS à leurs applications**<br/>
Les modifications suivantes ont été apportées aux vignettes d’applications dans l’application Portail d’entreprise pour iOS. Ces vignettes dirigent les utilisateurs vers différentes vues dans un emplacement unique, à savoir le site web du Portail d’entreprise, pour toutes leurs applications. Les restrictions d’Apple n’autorisent pas l’affichage des applications métier et gérées de l’App Store dans l’application Portail d’entreprise, ce qui oblige les utilisateurs à consulter plusieurs vues pour trouver leurs différentes applications.

- La vignette **Applications d’entreprise** pointait auparavant vers une liste de toutes les applications dans l’onglet TOUT du site web du Portail d’entreprise. Elle a toujours le même comportement, mais son nom a été remplacé par **Toutes les applications**.
- La vignette **Autres applications** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les applications dont l’affichage dans le Portail d’entreprise était autorisé par Apple. Cette vignette s’appelle maintenant **Applications proposées**. Quand l’utilisateur appuie dessus, il accède à l’onglet SÉLECTION du site web du Portail d’entreprise.
-  La vignette **Catégories** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les catégories d’applications. Son nom n’a pas changé, mais la vignette pointe maintenant vers l’onglet CATÉGORIES du site web du Portail d’entreprise.
Vous trouverez des captures d’écran mises à jour [ici](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).
<!---TFS 1317133--->

**Invitation à l’installation de l’application Managed Browser iOS si IT Pro définit cette obligation pour une application**<br/>
Si vous avez configuré un clip web pour qu’il s’ouvre uniquement dans le navigateur géré, et que ce navigateur n’est pas installé sur l’appareil, l’application Portail d’entreprise sur l’appareil invitera l’utilisateur à installer le navigateur géré pour permettre l’ouverture du clip web.
<!---TFS 1228570--->

### Windows
**Bouton Commentaires ajouté à l’application Portail d’entreprise Windows Phone 8.1**<br/>
L’application Portail d’entreprise Windows Phone 8.1 comporte un nouveau bouton « Envoyer des commentaires » qui permet aux utilisateurs d’envoyer des commentaires sur l’application. Pour afficher le bouton, les utilisateurs appuient sur le menu « points de suspension » en bas à droite de l’écran de l’application Portail d’entreprise, puis sur **Envoyer des commentaires**. Les commentaires, après avoir été regroupés et rendus anonymes, sont utilisés par Microsoft pour améliorer l’expérience utilisateur dans l’application Portail d’entreprise.
<!---TFS 1317806--->


## Nouveautés à venir

### Transition des groupes Intune vers les groupes Azure Active Directory
Intune crée une nouvelle expérience de gestion de groupe qui utilise les groupes de sécurité Azure Active Directory (AAD) en tant que groupes d’utilisateurs et d’appareils dans Intune. Ces groupes seront utilisés pour la gestion, le déploiement de stratégies et de profils de tous les groupes **lorsque nous introduirons le nouveau portail d’administration Intune basé sur Azure**.

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

### Nouvelles stratégies d’accès conditionnel par les applications pour Exchange Online et SharePoint Online
Vous pourrez restreindre l’accès à Exchange Online et à SharePoint Online en autorisant uniquement l’accès à partir d’applications Office Mobile, comme Outlook, Word, Excel et OneDrive. Cette nouvelle fonctionnalité est complémentaire des stratégies Intune de gestion des applications mobiles (GAM), car vous pouvez bloquer l’accès aux clients de messagerie intégrés ou autres applications qui n’ont pas été configurés avec les stratégies Intune GAM. Cela permet de vous assurer que tous les utilisateurs accèdent aux données de votre organisation à l’aide d’applications qui peuvent être protégées avec la gestion des applications mobiles Intune. Vous pouvez démarrer la gestion des applications mobiles Intune via le Portail Azure, dans la nouvelle section Accès conditionnel du panneau « Paramètres ».



### Désapprobation du service

- **Les applications du portail d’entreprise pour Windows 8 et Windows Phone 8 sont obsolètes** <br/>
À partir d’octobre 2016, Microsoft Intune ne prendra plus en charge les applications Portail d’entreprise Windows 8 et Windows Phone 8. Microsoft Intune cessera également de prendre en charge la plateforme Windows Phone 8. Ainsi, vous ne pourrez plus inscrire ni mettre à jour des appareils Windows Phone 8. Néanmoins, vous pourrez continuer à gérer les appareils Windows Phone 8 et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.



### Feuille de route du cloud
Restez informé des développements à venir pour Intune avec la [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune).


## Versions précédentes d’Intune
Les dernières améliorations apportées à Intune au cours des six derniers mois sont répertoriées dans l’article [Versions précédentes d’Intune](previous-intune-releases.md).

### Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)



<!--HONumber=Sep16_HO4-->


