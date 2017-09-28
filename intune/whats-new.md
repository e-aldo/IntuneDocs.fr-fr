---
title: "Nouveautés de Microsoft Intune"
titlesuffix: Azure portal
description: "Découvrez les nouveautés du portail Intune Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/18/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08a22a1fa6829807860b6278181dd638f1049770
ms.sourcegitcommit: 0d9bfd92bf5958261ed83b1f150bf207b7ba7e56
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Nouveautés de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Découvrez les nouveautés hebdomadaires dans Microsoft Intune. Vous pouvez également découvrir les [modifications à venir](#whats-coming), les [avis importants](#notices) sur le service et des informations sur les [versions précédentes](whats-new-archive.md).

> [!Note]
> Nombreuses de ces fonctionnalités seront finalement prises en charge pour les déploiements hybrides avec Configuration Manager. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-september-11-2017"></a>Semaine du 11 septembre 2017

### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo----1475932---"></a>Notifications Push supplémentaires pour les utilisateurs finaux sur l’application Portail d’entreprise pour Android Oreo <!---1475932--->

Les utilisateurs finaux voient des notifications supplémentaires qui leur indiquent quand l’application Portail d’entreprise pour Android Oreo effectue des tâches en arrière-plan, comme la récupération de stratégies auprès du service Intune. Ainsi, les utilisateurs finaux savent clairement quand le Portail d’entreprise effectue des tâches d’administration sur leur appareil. Cette amélioration fait partie de [l’optimisation générale de l’interface utilisateur du portail d’entreprise](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) pour l’application Portail d’entreprise pour Android Oreo. 

#### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Utilisateurs finaux renseignés sur les informations de leur appareil qui sont consultables pour iOS <!--739894--> 

Nous avons ajouté l’information **Type de propriété** dans l’écran des détails de l’appareil qui se trouve sur l’application Portail d’entreprise pour iOS. Les utilisateurs peuvent ainsi trouver plus d’informations sur la confidentialité directement à partir de cette page dans la documentation de l’utilisateur final d’Intune. Ils pourront également trouver cette information dans l’écran À propos de. 

#### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Autoriser les utilisateurs finaux à accéder à l’application Portail d’entreprise pour Android sans inscription <!---1169910--->

Les utilisateurs finaux n’auront bientôt pas à inscrire leur appareil pour accéder à l’application Portail d’entreprise pour Android. Les utilisateurs finaux des organisations qui utilisent des stratégies de protection des applications ne recevront plus d’invites pour inscrire leur appareil quand ils ouvriront l’application Portail d’entreprise. Les utilisateurs finaux pourront également installer des applications à partir du portail d’entreprise sans inscrire l’appareil. 


#### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android----1396349---"></a>Formulation plus facile à comprendre pour l’application Portail d’entreprise pour Android <!---1396349--->  

Le processus d’inscription de l’application Portail d’entreprise pour Android a été simplifié à l’aide d’un nouveau texte afin de faciliter l’inscription des utilisateurs finaux. Si vous avez une documentation personnalisée pour l’inscription, vous pouvez la mettre à jour de façon à refléter les nouveaux écrans. Vous trouverez des exemples d’images sur notre page [Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune](whats-new-app-ui.md#week-of-september-11-2017).

#### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Application Portail d’entreprise Windows 10 ajoutée à la stratégie d’autorisation Protection des informations Windows <!-- 677129 -->

L’application Portail d’entreprise Windows 10 a été mise à jour pour prendre en charge la Protection des informations Windows (WIP). L’application peut être ajoutée à la stratégie d’autorisation WIP. Grâce à cette modification, il n’est plus nécessaire d’ajouter l’application à la liste **Exempté**. 


## <a name="week-of-august-21-2017"></a>Semaine du 21 août 2017

### <a name="device-enrollment"></a>Inscription des appareils
#### <a name="improvements-to-device-overview----1404453---"></a>Vue d’ensemble des améliorations apportées à l’appareil <!-- 1404453 -->  
La vue d’ensemble des améliorations apportées à l’appareil affiche à présent les appareils inscrits mais exclut les appareils gérés par Exchange ActiveSync. Les appareils Exchange ActiveSync n’ont pas les mêmes options de gestion que les appareils inscrits. Pour afficher le nombre d’appareils inscrits et le nombre d’appareils inscrits par plateforme dans le portail Azure d’Intune, accédez à **Appareils** > **Vue d’ensemble**.

### <a name="device-management"></a>Gestion des appareils
#### <a name="improvements-to-device-inventory-collected-by-intune"></a>Améliorations apportées à l’inventaire des appareils collecté par Intune
<!-- 961134, 1104426, 1281327, 1333543 -->
Dans cette version, nous avons apporté les améliorations suivantes aux informations d’inventaire collectées par les appareils que vous gérez :
 
-   Pour les appareils Android, vous pouvez maintenant ajouter une colonne à l’inventaire des appareils qui affiche le dernier niveau de correctif logiciel pour chaque appareil. Ajoutez la colonne **Niveau du correctif de sécurité** à votre liste d’appareils pour afficher cette information.
-   Quand vous filtrez la vue des appareils, vous pouvez désormais filtrer les appareils sur leur date d’inscription. Par exemple, vous pouvez afficher uniquement les appareils qui ont été inscrits après une date que vous spécifiez.
-   Nous avons apporté des améliorations au filtre utilisé par l’élément **Date du dernier archivage**.
-   Dans la liste des appareils, vous pouvez maintenant afficher le numéro de téléphone d’appareils appartenant à l’entreprise.
En outre, vous pouvez utiliser le volet de filtre pour rechercher des appareils par numéro de téléphone.
 
Pour plus d’informations sur l’inventaire des appareils, consultez [Guide d’affichage de l’inventaire des appareils Intune](device-inventory.md).

#### <a name="conditional-access-support-for-macos-devices"></a>Prise en charge de l’accès conditionnel pour les appareils macOS 
<!-- 720172 -->
Vous pouvez maintenant définir une stratégie d’accès conditionnel exigeant que les appareils Mac soient inscrits dans Intune et conformes à ses stratégies de conformité des appareils. Par exemple, les utilisateurs peuvent télécharger l’application Portail d’entreprise Intune pour macOS et inscrire leurs appareils Mac dans Intune. Intune évalue si l’appareil Mac est conforme ou non aux spécifications telles que le code PIN, le chiffrement, la version du système d’exploitation et l’intégrité du système.

- Découvrez plus en détail la [prise en charge de l’accès conditionnel pour les appareils macOS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

#### <a name="company-portal-app-for-macos-is-in-public-preview----1484796---"></a>L’application Portail d’entreprise pour macOS est en préversion publique <!---1484796--->
L’application Portail d’entreprise pour macOS est désormais disponible dans la préversion publique pour l’accès conditionnel dans Enterprise Mobility + Security. Cette version prend en charge macOS 10.11 et ultérieur. Vous pouvez l’obtenir à l’adresse [https://aka.ms/macOScompanyportal](https://aka.ms/macOScompanyportal). 


#### <a name="new-device-restriction-settings-for-windows-10"></a>Nouveaux paramètres de restriction d’appareil pour Windows 10    
<!--1063965, 1308850  -->
Dans cette version, nous avons ajouté de nouveaux paramètres pour le [profil de restriction d’appareil Windows 10](/intune/device-restrictions-windows-10) dans les catégories suivantes :

-   Windows Defender SmartScreen
-   App Store

#### <a name="updates-to-the-windows-10-endpoint-protection-device-profile-for-bitlocker-settings"></a>Mises à jour du profil d’appareil Endpoint Protection Windows 10 pour les paramètres BitLocker
<!--1459533 -->    
Dans cette version, nous avons apporté les améliorations suivantes au fonctionnement des paramètres BitLocker dans un profil d’appareil Endpoint Protection Windows 10 :
 
Sous **Paramètres des lecteurs de système d’exploitation BitLocker**, pour le paramètre **BitLocker avec puce TPM non compatible**, quand vous sélectionniez **Bloquer**, auparavant, BitLocker aurait en fait été autorisé. Nous avons maintenant résolu ce problème pour bloquer BitLocker quand cette option est sélectionnée.
Sous **Paramètres des lecteurs de système d’exploitation BitLocker**, pour le paramètre **Agent de récupération de données basé sur les certificats**, vous pouvez maintenant bloquer explicitement l’agent de récupération de données basé sur le certificat. Toutefois, par défaut, l’agent est autorisé.
Sous **Paramètres des lecteurs de données fixes BitLocker**, pour le paramètre **Agent de récupération de données**, vous pouvez maintenant bloquer explicitement l’agent de récupération de données.
Pour plus d’informations, consultez [Paramètres Endpoint Protection pour Windows 10 et versions ultérieures](endpoint-protection-windows-10.md).


### <a name="app-management"></a>Gestion d'applications
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nouvelle expérience de connexion pour les utilisateurs du portail d’entreprise Android et les utilisateurs de stratégies de protection des applications <!-- 621669 -->
Les utilisateurs peuvent maintenant parcourir les applications, gérer les appareils et consulter les coordonnées du service informatique sur l’application du Portail d’entreprise Android sans inscrire leurs appareils Android. Par ailleurs, si un utilisateur final utilise déjà une application protégée par des stratégies Intune App Protection et qu’il lance le portail d’entreprise Android, il ne reçoit plus d’invite d’inscription pour son appareil.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nouveau paramètre dans l’application Portail d’entreprise Android pour activer/désactiver l’optimisation de batterie <!--1405990-->
La page **Paramètres** dans l’application Portail d’entreprise pour Android propose un nouveau paramètre qui permet aux utilisateurs de désactiver facilement l’optimisation de batterie pour les applications Portail d’entreprise et Microsoft Authenticator. Le nom de l’application qui est indiqué dans le paramètre varie en fonction de l’application qui gère le compte professionnel. Nous préconisons aux utilisateurs de désactiver l’optimisation de batterie pour améliorer les performances des applications professionnelles qui synchronisent les e-mails et les données. 

#### <a name="multi-identity-support-for-onenote-for-ios---------1234281---"></a>Prise en charge de la multi-identité pour OneNote pour iOS      <!-- 1234281 -->
Les utilisateurs finaux peuvent désormais utiliser des comptes différents (professionnels et personnels) avec Microsoft OneNote pour iOS. Il est possible d’appliquer des stratégies de protection des applications à des données d’entreprise dans des blocs-notes professionnels sans affecter leurs blocs-notes personnels. Par exemple, une stratégie peut autoriser un utilisateur à rechercher des informations dans des blocs-notes de travail, mais l’empêcher de copier et de coller des données d’entreprise du bloc-notes professionnel vers un bloc-notes personnel.
 
- En savoir plus sur les applications qui prennent en charge [la protection d’application et les identités multiples](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) avec Intune.

#### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices"></a>Nouveaux paramètres pour autoriser et bloquer des applications sur les appareils Samsung KNOX Standard
<!-- 1305423 822899-->  
Dans cette version, nous ajoutons de nouveaux [paramètres de restriction des appareils](device-restrictions-android.md) qui vous permettent de spécifier les listes d’applications suivantes :
 
- Applications que les utilisateurs sont autorisés à installer
- Applications dont l’exécution est bloquée pour les utilisateurs
- Applications qui sont masquées pour l’utilisateur sur l’appareil
 
Vous pouvez spécifier l’application par URL, par nom de package ou à partir de la liste des applications que vous gérez.

#### <a name="new-azure-ad-app-based-conditional-access-policy-ui-link-from-intune"></a>Lien vers la nouvelle interface utilisateur des stratégies d’accès conditionnel basé sur l’application Azure AD à partir d’Intune
<!-- 1016201 -->
Les administrateurs informatiques peuvent définir des stratégies conditionnelles basées sur l’application par le biais de la nouvelle interface utilisateur des stratégies d’accès conditionnel dans la charge de travail Azure AD. L’accès conditionnel basé sur l’application qui se trouve dans la section Protection d’application Intune dans Azure restera à cet endroit pour l’instant et sera appliqué côte à côte. Par souci pratique, un lien est également prévu vers la nouvelle interface utilisateur des stratégies d’accès conditionnel dans la charge de travail Intune.

- Découvrez plus en détail [l’accès conditionnel basé sur l’application sur Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).


## <a name="notices"></a>Remarques

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Adresses IP pour Intune mises à jour <!-- 1175274 -->
Une [liste mise à jour de noms DNS et d’adresses IP](/intune/network-bandwidth-use) est disponible pour les paramètres de proxy de pare-feu.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Utiliser Azure Active Directory pour l’accès conditionnel <!-- 967947 -->
L’accès conditionnel est disponible dans la section Azure Active Directory du portail Azure et fournit une infrastructure plus puissante et flexible pour la définition de stratégies pour des applications cloud comme Office 365 Exchange Online et SharePoint Online.  Utilisez le panneau **accès conditionnel dans Azure Active Directory** au lieu de la console Intune pour configurer des stratégies. Les stratégies existantes dans la console Intune doivent être recréées dans le portail Azure. Pour plus d’informations, consultez [Créer des stratégies d’accès conditionnel Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail classique Intune. Les comptes Intune créés avant janvier 2017 nécessitent une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder au portail Azure, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure
Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Nouveautés à venir

#### <a name="ios-11-mail-app-will-support-oauth----1196951---"></a>L’application Mail iOS 11 prend en charge OAuth <!---1196951--->
L’accès conditionnel avec Intune prend en charge une authentification plus sécurisée sur les appareils iOS avec OAuth. Pour cela, il y aura désormais un flux différent sur l’application Portail d’entreprise pour iOS afin de permettre une authentification plus sécurisée. Quand des utilisateurs finaux essaieront de se connecter à un nouveau compte Exchange dans l’application Mail, ils recevront une invite de vue web. Lors de leur inscription dans Intune, les utilisateurs recevront une invite pour autoriser l’application Mail native à accéder à un certificat. La plupart des utilisateurs ne verront plus d’e-mails mis en quarantaine. Les comptes de messagerie existants continueront à utiliser le protocole d’authentification de base. Ces utilisateurs recevront donc toujours des e-mails mis en quarantaine. Cette expérience de connexion pour les utilisateurs finaux est semblable à celle des applications mobiles Office.

### <a name="end-of-support-for-ios-80----1164477---"></a>Fin de la prise en charge d’iOS 8.0 <!---1164477--->
Les applications gérées et l’application Portail d’entreprise pour iOS nécessiteront iOS 9.0 et ultérieur pour accéder aux ressources d’entreprise. Les appareils qui ne sont pas mis à jour avant septembre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. 

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Mises à jour apportées à l’interface utilisateur sur le site web Portail d’entreprise <!--1313244 part 2-->
__Mises à jour des applications proposées__  
Nous avons ajouté une page dédiée sur le site où les utilisateurs peuvent rechercher les applications que vous avez choisi de proposer, et nous avons apporté quelques ajustements à l’interface utilisateur de la section correspondante sur la page d’accueil. Vous pouvez voir à quoi ressemblent ces modifications dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).


### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fin de la prise en charge d’Android 4.3 et antérieur <!---1171127, 1326920 --->
Les applications gérées et l’application Portail d’entreprise pour Android nécessiteront Android 4.4 et ultérieur pour accéder aux ressources de l’entreprise. Les appareils qui ne sont pas mis à jour avant début octobre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. En décembre, tous les appareils inscrits seront obligatoirement mis hors service et perdront l’accès aux ressources de l’entreprise. Si vous utilisez des stratégies de protection des applications sans MDM, les applications ne recevront aucune mise à jour et perdront en qualité au fil du temps.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-ended-july-11-2017"></a>Rappel relatif au support de la plateforme : le support standard de Windows Phone 8.1 a pris fin le 11 juillet 2017
<!-- 1327781 -->
Au 11 juillet 2017, le support standard de la plateforme Windows Phone 8.1 a pris fin. Le support des PC Windows 8.1 n’est pas impacté.

Il n’existe aucun impact immédiat sur les appareils Windows Phone 8.1 gérés par le service Intune. Les appareils inscrits continuent de fonctionner, tout comme l’ensemble des stratégies, des configurations et des applications. Notez qu’aucune amélioration n’est prévue pour la plateforme Windows Phone 8.1 au sein du service Intune, ni pour l’application Portail d’entreprise Windows Phone 8.1.

Nous vous recommandons de mettre à niveau les appareils Windows Phone 8.1 éligibles vers Windows 10 Mobile dès que possible. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Modifications apportées à la prise en charge de l’application Portail d’entreprise Intune iOS <!-- 1164474  -->
Une nouvelle version de l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 9.0 ou ultérieure, sera bientôt disponible. La version du portail d’entreprise qui prend en charge iOS 8 sera toujours disponible pendant une très courte période. Toutefois, notez que si vous utilisez également des applications iOS compatibles GAM, nous prenons en charge iOS 9.0 et ultérieur. Vous devez donc vérifier que les utilisateurs finaux effectuent la mise à jour vers le système d’exploitation le plus récent. 

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?
Nous vous donnons cette information à l’avance, même si nous n’avons pas les dates précises, afin que vous ayez le temps de planifier. Vérifiez que vos utilisateurs effectuent la mise à jour vers iOS 9+ et, au moment de la publication de l’application Portail d’entreprise, demandez-leur de mettre à jour leur application Portail d’entreprise.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?
Encouragez les utilisateurs à effectuer la mise à jour vers iOS version 9.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  Encouragez les utilisateurs à installer la nouvelle version du portail d’entreprise et à bénéficier des nouvelles fonctionnalités qu’elle propose.

Accédez à Intune dans le portail Azure et affichez Appareils > Tous les appareils, puis filtrez par version d’iOS pour voir tous les appareils actuels avec des systèmes d’exploitation antérieurs à iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->
La société Apple a annoncé qu’elle appliquera des exigences spécifiques pour ATS (Application Transport Security). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS.

Nous avons publié, par le biais du programme Apple TestFlight, une version de l’application Portail d’entreprise pour iOS qui respecte les nouvelles exigences d’ATS. Si vous souhaitez l’essayer pour tester votre conformité à ATS, envoyez un e-mail à <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> en indiquant votre prénom, votre nom, votre adresse e-mail et le nom de votre société. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de l’interface utilisateur du portail d’entreprise](whats-new-app-ui.md)
* [Nouveautés des mois précédents](whats-new-archive.md)
