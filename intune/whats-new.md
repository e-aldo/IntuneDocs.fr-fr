---
title: "Nouveautés de Microsoft Intune"
titleSuffix: Intune on Azure
description: "Découvrez les nouveautés du portail Intune Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 08/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f28ce989b5907f7e7474543c364508424dc0c9cf
ms.sourcegitcommit: 0b164f806165d312acfc88815a60e325e3d02672
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Nouveautés de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Découvrez les nouveautés hebdomadaires dans Microsoft Intune. Vous pouvez également découvrir les [modifications à venir](#whats-coming), les [avis importants](#notices) sur le service et des informations sur les [versions précédentes](whats-new-archive.md).

> [!Note]
> Nombreuses de ces fonctionnalités seront finalement prises en charge pour les déploiements hybrides avec Configuration Manager. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Intune apps
-->   


## <a name="week-of-august-21-2017"></a>Semaine du 21 août 2017
### <a name="app-management"></a>Gestion d'applications
#### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nouvelle expérience de connexion pour les utilisateurs du portail d’entreprise Android et les utilisateurs de stratégies de protection des applications <!-- 621669 -->

Les utilisateurs finaux peuvent désormais parcourir les applications, gérer les appareils et afficher des informations de contact informatique au moyen de l’application Portail d’entreprise Android sans inscrire leurs appareils Android. Par ailleurs, si un utilisateur final utilise déjà une application protégée par des stratégies Intune App Protection et qu’il lance le portail d’entreprise Android, il ne reçoit plus d’invite d’inscription pour son appareil.

## <a name="week-of-july-31-2017"></a>Semaine du 31 juillet 2017
### <a name="device-enrollment"></a>Inscription des appareils  

#### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restriction d’inscription d’appareils Android et iOS par version de système d’exploitation <!--- 1333256,  1245463 --->
Intune prend désormais en charge la restriction d’inscription d’appareils Android et iOS par numéro de version de système d’exploitation. Sous **Restriction de type d’appareil**, l’administrateur informatique peut désormais définir une configuration de plateforme pour restreindre l’inscription à une plage de valeurs de système d’exploitation minimale et maximale. Les versions du système d’exploitation Android doivent être spécifiées au format Majeure.Mineure.Build.Révision, où Mineure, Build et Révision sont facultatifs. Les versions d’iOS doivent être spécifiées au format Majeure.Mineure.Build, où Build est facultatif. Découvrez plus d’informations sur les [restrictions d’inscription d’appareils](enrollment-restrictions-set.md).

>[!NOTE]
>Ne limite pas l’inscription avec des programmes d’inscription Apple ou Apple Configurator.

#### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Limiter l’inscription des appareils personnels Android, iOS et macOS <!--- 1333272,  1333275, 1245709 --->
Intune peut limiter l’inscription d’appareils personnels avec des listes vertes de numéros IMEI d’appareils d’entreprise. Intune a récemment étendu cette fonctionnalité à iOS, Android et macOS avec des numéros de série d’appareils. En chargeant les numéros de série sur Intune, vous pouvez prédéclarer des appareils comme appartenant à l’entreprise. Les restrictions d’inscription vous permettent de bloquer les appareils personnels (BYOD), ce qui permet l’inscription des appareils de l’entreprise uniquement. Découvrez plus d’informations sur les [restrictions d’inscription d’appareils](enrollment-restrictions-set.md).

Pour importer des numéros de série, accédez à **Inscription d’appareil** > **Identificateurs d’appareil d’entreprise** et cliquez sur **Ajouter**, puis chargez un fichier .CSV (pas d’en-tête, deux colonnes pour le numéro de série et des détails comme les numéros IMEI).  Pour restreindre les appareils personnels, accédez à **Inscription d’appareil** > **Restrictions d’inscription**. Sous **Restrictions de type d’appareil**, sélectionnez **Par défaut**, puis **Configurations de plateforme**. Vous pouvez **Autoriser** ou **Bloquer** les appareils personnels pour iOS, Android et macOS. 


### <a name="device-management"></a>Gestion des appareils   

#### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nouvelle action de l’appareil pour forcer les appareils à la synchronisation avec Intune<!-- 711369 -->
Dans cette version, nous avons ajouté une nouvelle action qui force l’appareil sélectionné à s’enregistrer immédiatement auprès d’Intune. Quand un appareil s’enregistre, il reçoit immédiatement les actions ou les stratégies en attente qui lui ont été affectées.  Cette action peut vous aider à valider et corriger immédiatement les stratégies que vous avez affectées, sans attendre le prochain enregistrement planifié.
Pour plus d’informations, consultez [Synchroniser un appareil](device-sync.md).

#### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible<!-- 777100 -->
Une nouvelle stratégie est disponible dans l’espace de travail des mises à jour logicielles, qui vous permet de forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible. Pour plus d’informations, consultez [Configurer les stratégies de mise à jour iOS](/intune/software-updates-ios)

#### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651-1172027---"></a>Check Point SandBlast Mobile : nouveau partenaire de Mobile Threat Defense <!-- 954651, 1172027 -->
Vous pouvez contrôler l’accès des appareils mobiles aux ressources de l’entreprise avec un accès conditionnel basé sur une évaluation des risques effectuée par CheckPoint SandBlast Mobile, qui est une solution de protection contre les menaces mobiles qui s’intègre à Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Déroulement de l’intégration à Intune
Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant CheckPoint SandBlast Mobile. Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de CheckPoint SandBlast Mobile, activée par le biais des stratégies de conformité Intune. Vous pouvez autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise en fonction des menaces détectées.


### <a name="app-management"></a>Gestion d'applications

#### <a name="deploy-an-app-as-available-in-the-microsoft-store-for-business----748101---"></a>Déployer une application en tant qu’application disponible dans le Microsoft Store pour Entreprises <!-- 748101 -->
Avec cette version, les administrateurs peuvent désormais indiquer que le Microsoft Store pour Entreprises est disponible. Quand il est déclaré disponible, les utilisateurs finaux peuvent installer l’application à partir de l’application ou du site web Portail d’entreprise sans être redirigé vers le Microsoft Store.


### <a name="intune-apps"></a>Applications Intune  

#### <a name="ui-updates-to-the-company-portal-website---1313244-part-1--"></a>Mises à jour apportées à l’interface utilisateur sur le site web Portail d’entreprise <!--1313244 part 1-->
Nous avons procédé à quelques mises à jour sur l’interface utilisateur du [site Web Portail d’entreprise](https://portal.manage.microsoft.com) pour améliorer l’expérience de l’utilisateur final.

- __Améliorations apportées aux vignettes des applications__ : des icônes d’application s’affichent désormais avec un arrière-plan généré automatiquement en fonction de la couleur dominante de l’icône (si elle peut être détectée). Quand il est applicable, cet arrière-plan remplace la bordure grise qui apparaissaît sur les vignettes des applications.

    Dans une prochaine version, le site web Portail d’entreprise affichera des grandes icônes quand cela sera possible. Nous recommandons aux administrateurs informatiques de publier des applications en utilisant des icônes d’une taille minimale de 120 x 120 pixels. 

- __Modifications de la navigation__ : les éléments de la barre de navigation sont déplacés dans le menu hamburger situé en haut à gauche. La page Catégories est supprimée. Les utilisateurs peuvent désormais filtrer le contenu par catégorie lors de l’exploration.

- __Mises à jour des applications proposées__  : nous avons ajouté une page dédiée sur le site où les utilisateurs peuvent rechercher les applications que vous avez choisi de proposer, et nous avons apporté quelques ajustements à l’interface utilisateur de la section correspondante sur la page d’accueil.

#### <a name="ibooks-support-for-the-company-portal-website---1231841--"></a>Prise en charge des iBooks pour le site web Portail d'entreprise <!--1231841-->
Nous avons ajouté une page dédiée au site web Portail d'entreprise qui permet aux utilisateurs de parcourir et de télécharger des iBooks. 

### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner

#### <a name="additional-help-desk-troubleshooting-details------applies-to-1263399-1326964-1341642----"></a>Détails supplémentaires de résolution des problèmes pour le support technique<!---  Applies to 1263399, 1326964, 1341642 --->
 
Intune a mis à jour l’affichage de la résolution des problèmes et a ajouté aux informations qu’il fournit des informations pour les administrateurs et le personnel du support technique. Vous pouvez maintenant voir un tableau **Attributions** qui récapitule toutes les attributions de l’utilisateur en fonction de l’appartenance au groupe. La liste comprend :
- Applications mobiles
- Stratégies de conformité
- Profils de configuration
 
Par ailleurs, le tableau **Appareils** inclut désormais les colonnes **Type de jointure Azure AD** et **Conforme Azure AD**. Pour plus d’informations, consultez [Aider les utilisateurs à résoudre les problèmes](help-desk-operators.md).

### <a name="reporting"></a>Création de rapports

#### <a name="intune-data-warehouse-public-preview"></a>Entrepôt de données Intune (préversion publique)

L’entrepôt de données Intune échantillonne quotidiennement les données pour fournir une vue historique de votre locataire. Vous pouvez accéder aux données via un fichier Power BI (PBIX), via un lien OData qui est compatible avec de nombreux outils analytiques ou en interagissant avec l’API REST. Pour plus d’informations, consultez [Utiliser l’entrepôt de données Intune](reports-nav-create-intune-reports.md).

## <a name="week-of-july-23rd-2017"></a>Semaine du 23 juillet 2017

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modes clair et sombre disponibles pour l’application Portail d’entreprise pour Windows 10 <!---676547--->
Les utilisateurs finaux seront en mesure de personnaliser le mode de couleur de l’application Portail d’entreprise pour Windows 10. Ils pourront apporter la modification dans la section Paramètres de l’application Portail d’entreprise. Le changement apparaîtra une fois que les utilisateurs auront redémarré l’application. Pour Windows 10 versions 1607 et ultérieures, le mode des applications est par défaut le paramètre système. Pour Windows 10 versions 1511 et antérieures, le mode des applications est par défaut le mode clair.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Permettre aux utilisateurs finaux de baliser leur groupe d’appareils dans l’application Portail d’entreprise pour Windows 10 <!---807046-->
Les utilisateurs finaux peuvent désormais sélectionner le groupe auquel leur appareil appartient, en le balisant directement à partir de l’application Portail d’entreprise pour Windows 10.




## <a name="notices"></a>Remarques

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Adresses IP pour Intune mises à jour <!-- 1175274 -->
Une [liste mise à jour de noms DNS et d’adresses IP](/intune/network-bandwidth-use) est disponible pour les paramètres de proxy de pare-feu.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Utiliser Azure Active Directory pour l’accès conditionnel <!-- 967947 -->
L’accès conditionnel est disponible dans la section Azure Active Directory de la console Azure et fournit une infrastructure plus puissante et flexible pour la définition de stratégies pour des applications cloud comme Office 365 Exchange Online et SharePoint Online.  Utilisez le panneau **accès conditionnel dans Azure Active Directory** au lieu de la console Intune classique pour configurer des stratégies. Les stratégies existantes dans la console Intune classique doivent être recréées dans la console Azure. Pour plus d’informations, consultez [Créer des stratégies d’accès conditionnel Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessitent une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder au portail Azure, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure
Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Nouveautés à venir

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
