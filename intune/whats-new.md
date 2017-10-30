---
title: "Nouveautés de Microsoft Intune"
titlesuffix: Azure portal
description: "Découvrez les nouveautés du portail Intune Azure"
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b77323c30dccf4c8b9e5c692a40aec7389809891
ms.sourcegitcommit: 128770ecc820f6ff3c99b15752bce7a58257f1d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/21/2017
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
## <a name="week-of-october-16-2017"></a>Semaine du 16 octobre 2017

### <a name="device-enrollment"></a>Inscription des appareils
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Prise en charge du programme de déploiement Windows AutoPilot dans Microsoft Intune  <!-- 747617  -->
Vous pouvez désormais utiliser Microsoft Intune avec le programme de déploiement Windows AutoPilot pour permettre à vos utilisateurs de provisionner eux-mêmes leurs appareils d’entreprise sans passer par le service informatique. Vous pouvez personnaliser l’expérience OOBE (out-of-box experience) pour permettre aux utilisateurs de joindre leurs appareils à Azure AD et de s’inscrire à Intune. Avec Microsoft Intune et Windows AutoPilot, vous n’avez plus à déployer et à gérer les images de système d’exploitation. Pour plus d’informations, consultez [Inscrire des appareils Windows à l’aide du programme Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Guide de démarrage rapide pour l’inscription d’appareils  <!-- 1425655 --> 
Le guide de démarrage rapide, désormais disponible dans **Inscription d’appareils**, fournit un tableau de références pour gérer les plateformes et configurer la procédure d’inscription. Vous trouverez une brève description de chaque élément et des liens vers des instructions pas à pas pour simplifier le démarrage.

#### <a name="device-categorization----1427491---"></a>Catégorisation des appareils <!-- 1427491 -->
Le graphique des plateformes des appareils inscrits du panneau **Appareils > Vue d’ensemble** organise les appareils par plateforme (Android, iOS, macOS, Windows, Windows Mobile, etc.).  Les appareils qui exécutent d’autres systèmes d’exploitation sont regroupés dans « Autres ».  Il s’agit des appareils fabriqués par Blackberry, NOKIA, etc.  

Pour identifier les appareils affectés dans votre locataire, choisissez **Gérer > Tous les appareils**, puis utilisez **Filtrer** pour limiter le champ **Système d’exploitation**.



### <a name="device-management"></a>Gestion des appareils
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium : nouveau partenaire de Mobile Threat Defense <!-- 954681 -->  
Vous pouvez contrôler l’accès des appareils mobiles aux ressources de l’entreprise à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Zimperium,solution Mobile Threat Defense qui s’intègre à Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Déroulement de l’intégration à Intune
Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Zimperium. Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Zimperium, activée par le biais des stratégies de conformité Intune, que vous pouvez utiliser pour autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise en fonction des menaces détectées.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nouveaux paramètres pour le profil de restriction d’appareils Windows 10  <!--- 978575, 1308849, -->  
Nous ajoutons de nouveaux paramètres au profil de restriction des appareils Windows 10 dans la catégorie Windows Defender SmartScreen.

Pour obtenir plus d’informations sur le profil de restriction des appareils Windows 10, consultez [Paramètres de restriction des appareils Windows 10 et version ultérieure]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Support à distance pour les appareils Windows et Windows Mobile   <!-- 1070473 -->  
Intune peut désormais utiliser le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs qui utilisent des appareils Windows et Windows Mobile.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Analyser les appareils avec Windows Defender <!-- 1280988  1280990   -->
Vous pouvez à présent exécuter une **Analyse rapide**, une **Analyse complète** et **Mettre à jour les signatures** avec l’antivirus Windows Defender sur les appareils Windows 10 gérés. À partir du panneau de présentation de l’appareil, choisissez l’action à exécuter sur l’appareil. Vous êtes invité à confirmer l’action avant l’envoi de la commande à l’appareil. 

**Analyse rapide** : une analyse rapide analyse les emplacements où les programmes malveillants s’enregistrent pour démarrer, comme les clés de registre et les dossiers de démarrage Windows connus. Une analyse rapide prend en moyenne cinq minutes. Associée au paramètre **Protection en temps réel toujours activé** qui analyse les fichiers lorsqu’ils sont ouverts, fermés et à chaque fois qu’un utilisateur accède à un dossier, une analyse rapide fournit une protection contre les programmes malveillants qui peuvent se trouver dans le système ou le noyau. Lorsque l’analyse s’achève, ses résultats s’affichent sur les appareils des utilisateurs. 

**Analyse complète** : une analyse complète peut être utile sur les appareils confrontés à une menace issue de programmes malveillants afin de déterminer s’il existe des composants inactifs qui nécessitent un nettoyage plus approfondi. Elle est également utile pour exécuter des analyses à la demande. Une analyse complète peut prendre une heure. Lorsque l’analyse s’achève, ses résultats s’affichent sur les appareils des utilisateurs. 

**Mettre à jour les signatures** : la commande de mise à jour de signature met à jour les définitions et les signatures des programmes malveillants dans Antivirus Windows Defender. Cela permet de garantir l’efficacité d’Antivirus Windows Defender dans la détection des programmes malveillants. Cette fonctionnalité s’applique uniquement aux appareils Windows 10 et est sujette à la connectivité Internet de l’appareil. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Le bouton Activer/Désactiver n’est plus disponible dans la page Autorité de certification Intune du portail Intune Azure  <!-- 1400455 -->
 Nous avons enlevé une étape du processus de configuration de Certificate Connector sur Intune. Actuellement, vous téléchargez Certificate Connector et vous l’activez dans la console Intune. Mais si vous le désactivez dans la console Intune, il continue d’émettre des certificats.

##### <a name="how-does-this-affect-me"></a>En quoi cela m’affecte-t-il ?
Depuis octobre, le bouton Activer/désactiver n’apparaît plus dans la page Autorité de certification du portail Azure. La fonctionnalité Certificate Connector reste la même. Les certificats sont toujours déployés sur les appareils inscrits à Intune. Vous pouvez continuer à télécharger et à installer Certificate Connector. Pour arrêter l’émission de certificats, vous devez désinstaller Certificate Connector au lieu de le désactiver.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?
Si Certificate Connector est actuellement désactivé, vous devez le désinstaller.



### <a name="device-configuration"></a>Configuration des appareils
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nouveaux paramètres pour le profil de restriction d’appareils Windows 10 Collaboration   <!--- 1308838 -->
Dans cette version, nous avons ajouté un grand nombre de nouveaux paramètres au profil de restriction d’appareils Windows 10 Collaboration pour vous permettre de gérer les appareils Surface Hub.

Pour plus d’informations sur ce profil, consultez [Paramètres de restriction d’appareils Windows 10 Collaboration](device-restrictions-windows-10-teams.md).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Empêcher les utilisateurs d’appareils Android de modifier la date et l’heure de leur appareil  <!-- 1333292 -->
Vous pouvez utiliser la [stratégie d’appareil personnalisée Android](custom-settings-android.md) pour empêcher les utilisateurs d’appareils Android de modifier la date et l’heure de l’appareil.

Pour ce faire, configurez une stratégie personnalisée Android avec le paramètre URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Affectez-lui la valeur **TRUE**, puis attribuez-le aux groupes requis.

#### <a name="bitlocker-device-configuration----1397398---"></a>Configuration d’appareil BitLocker <!-- 1397398 -->
Les paramètres **Chiffrement Windows > Paramètres de Base** incluent un nouveau paramètre **Avertissement sur le chiffrement d’un autre disque** qui vous permet de désactiver le [message d’avertissement](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) sur le chiffrement d’un autre disque qui peut être utilisé sur l’appareil de l’utilisateur.  Le message d’avertissement requiert le consentement de l’utilisateur final avant la configuration de BitLocker sur l’appareil et bloque la configuration de BitLocker jusqu’à ce qu’elle soit confirmée par l’utilisateur final.  Le nouveau paramètre désactive l’avertissement affiché pour l’utilisateur final.


### <a name="app-management"></a>Gestion d'applications
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Le programme d’achat en volume pour les applications d’entreprise est désormais synchronisé avec votre locataire Intune <!-- 800882 -->  
Les développeurs tiers peuvent distribuer des applications en privé aux membres autorisés du programme d’achat en volume (VPP) pour les entreprises. Ces membres du programme d’achat en volume pour les entreprises peuvent se connecter à l’App Store du programme d’achat en volume et acheter leurs applications.

À compter de cette version, les applications du programme d’achat en volume pour les entreprises achetées par l’utilisateur final sont désormais synchronisées avec leurs locataires Intune.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Sélectionner le magasin Apple du pays pour synchroniser les applications VPP<!-- 1332311 -->  
Vous pouvez configurer le magasin du pays pour le programme d’achat en volume (VPP) lors du chargement de votre jeton VPP. Intune synchronise les applications VPP pour tous les paramètres régionaux à partir du magasin du pays VPP spécifié.

> [!NOTE]  
> Actuellement, Intune synchronise uniquement les applications VPP à partir du magasin du pays VPP qui correspond aux paramètres régionaux Intune avec lesquels le client Intune a été créé.




### <a name="intune-apps"></a>Applications Intune
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquer la copie et le collage entre les profils professionnels et personnels dans Android for Work <!-- 1098994 -->
Avec cette version, vous pouvez configurer le profil professionnel Android for Work afin qu’il bloque la copie et le collage entre les applications professionnelles et personnelles. Vous trouverez ce nouveau paramètre dans le profil **Restrictions d’appareils** pour la plateforme **Android for Work** dans **Paramètres du profil professionnel**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Créer des applications iOS limitées à des App Stores Apple locaux spécifiques <!-- 1281692 -->
Vous pourrez spécifier les paramètres régionaux lors de la création d’une application managée App Store Apple.

> [!Note]  
> Actuellement, vous pouvez uniquement créer des applications gérées par l’App Store d’Apple qui sont présentes dans le Store des États-Unis.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Mettre à jour les applications sous licence pour l’appareil et l’utilisateur VPP iOS  <!-- 1305564 -->  
Vous pourrez configurer le jeton VPP iOS pour mettre à jour toutes les applications achetées pour ce jeton via le service Intune. Intune détecte les mises à jour des applications VPP dans le magasin d’applications et les envoie (Push) automatiquement vers l’appareil lorsque ce dernier se connecte.

Pour savoir comment définir un jeton VPP et activer les mises à jour automatiques, consultez Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune (/intune/vpp-apps-ios).



### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Collection d’entité d’association appareil-utilisateur ajoutée au modèle de données Intune Data Warehouse <!-- 1187917 -->
Vous pouvez désormais générer des rapports et des visualisations des données en utilisant les informations d’association appareil-utilisateur qui associent les collections d’entité utilisateur et appareil. Le modèle de données est accessible par le biais du fichier Power BI (PBIX) extrait de la page Intune Data Warehouse, via le point de terminaison OData, ou en développant un client personnalisé.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Vérifier la conformité de la stratégie pour les boucles de mise à jour de Windows 10 <!-- 1067886 -->
Vous pouvez consulter un rapport sur la stratégie pour vos boucles de mise à jour de Windows 10 à partir de Mises à jour logicielles > État de déploiement par boucle de mise à jour. Le rapport sur la stratégie inclut l’état du déploiement pour les boucles de mise à jour que vous avez configurées. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nouveau rapport qui répertorie les appareils iOS équipés d’anciennes versions iOS   <!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est disponible à partir de l’espace de travail **Mises à jour logicielles**. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour iOS, et pour lesquels des mises à jour sont disponibles. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Afficher les attributions de la stratégie de protection des applications pour la résolution des problèmes <!--  1475003 -->
Dans cette version à venir, l’option **Stratégie de protection des applications** sera ajoutée à la liste déroulante **Affectations** disponible dans le panneau de résolution des problèmes. Vous pouvez maintenant sélectionner des stratégies de protection des applications pour afficher les stratégies de protection des applications affectées aux utilisateurs sélectionnés.



## <a name="week-of-october-2-2017"></a>Semaine du 2 octobre 2017

### <a name="intune-apps"></a>Applications Intune
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Améliorations apportées au workflow de configuration des appareils dans le portail d’entreprise <!--1490692-->
Nous avons amélioré le workflow de configuration des appareils dans l’application Portail d’entreprise pour Android. Le texte de l’interface est plus convivial et spécifique à votre entreprise, et nous avons regroupé des écrans quand cela était possible. Vous pouvez voir cela dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Amélioration de l’aide sur la demande d’accès aux contacts sur les appareils Android <!--1484985-->

L’application Portail d’entreprise pour Android nécessite souvent que l’utilisateur final accepte l’autorisation pour les contacts. Si un utilisateur final refuse cet accès, il voit désormais une notification dans l’application qui lui indique d’accorder l’autorisation pour l’accès conditionnel. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Correction du démarrage sécurisé pour Android <!--1490712-->

Les utilisateurs finaux d’appareils Android peuvent désormais indiquer la raison de la non-conformité dans l’application Portail d’entreprise. Quand c’est possible, ils sont directement positionnés à l’emplacement approprié dans l’application Paramètres pour corriger le problème. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Notifications Push supplémentaires pour les utilisateurs finaux sur l’application Portail d’entreprise pour Android Oreo <!--1475932-->

Les utilisateurs finaux voient des notifications supplémentaires qui leur indiquent quand l’application Portail d’entreprise pour Android Oreo effectue des tâches en arrière-plan, comme la récupération de stratégies auprès du service Intune. La transparence s’en trouve améliorée pour les utilisateurs finaux, qui savent quand le Portail d’entreprise effectue des tâches d’administration sur leur appareil. Cette amélioration fait partie de [l’optimisation générale de l’interface utilisateur du portail d’entreprise](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) pour l’application Portail d’entreprise pour Android Oreo. 

Vous verrez d’autres optimisations relatives aux nouveaux éléments d’interface utilisateur dans Oreo Android.  Les utilisateurs finaux voient des notifications supplémentaires qui leur indiquent quand le portail d’entreprise effectue des tâches en arrière-plan, comme la récupération d’une stratégie auprès du service Intune.  La transparence s’en trouve améliorée pour les utilisateurs finaux, qui savent quand le portail d’entreprise effectue des tâches d’administration sur l’appareil.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nouveaux comportements de l’application Portail d’entreprise pour Android avec les profils professionnels <!---1485783--->

Lorsque vous inscrivez un appareil Android for Work avec un profil professionnel, c’est l’application Portail d’entreprise dans le profil professionnel qui effectue les tâches de gestion sur l’appareil. 

L’application Portail d’entreprise pour Android n’a plus aucune utilité, sauf si vous utilisez une application MAM dans le profil professionnel. Pour améliorer l’expérience liée au profil professionnel, Intune masque automatiquement l’application Portail d’entreprise personnelle après l’inscription réussie d’un profil professionnel.

L’application Portail d’entreprise pour Android peut être activée à tout moment dans le profil personnel en recherchant [Portail d’entreprise dans le Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) et en appuyant sur **Activer**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Migration du Portail d’entreprise pour Windows 8.1 et Windows Phone 8.1 vers le mode soutenu <!--1428681-->

À partir d’octobre 2017, les applications Portail d’entreprise pour Windows 8.1 et Windows Phone 8.1 passent en mode soutenu. Cela signifie que les applications et les scénarios existants, comme l’inscription et la conformité, seront toujours pris en charge pour ces plateformes. Ces applications resteront disponibles au téléchargement par le biais des canaux de publication existants, comme Microsoft Store. 

Une fois en mode soutenu, ces applications recevront uniquement les mises à jour de sécurité critiques. Aucune mise à jour ou fonctionnalité supplémentaire ne sera publiée pour ces applications. Pour obtenir les nouvelles fonctionnalités, nous vous recommandons de mettre à jour les appareils vers Windows 10 ou Windows 10 Mobile. 


### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Bloquer l’inscription des appareils Samsung Knox non pris en charge <!--- 1490695 --->

L’application Portail d’entreprise tente d’inscrire seulement les appareils Samsung Knox pris en charge. Pour éviter les erreurs d’activation KNOX qui empêchent l’inscription à MDM, l’inscription des appareils est tentée seulement si l’appareil apparaît dans la [liste des appareils publiée par Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Les appareils Samsung peuvent avoir des numéros de modèles qui prennent en charge KNOX, alors que d’autres ne le prennent pas en charge. Vérifiez la compatibilité de Knox auprès du revendeur de votre appareil avant l’achat et le déploiement. Vous pouvez trouver la liste complète des appareils vérifiés dans les [paramètres de stratégie Android et Samsung KNOX Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Fin de la prise en charge d’Android 4.3 et antérieur <!---1171126, 1326920 --->
Les applications gérées et l’application Portail d’entreprise pour Android nécessiteront Android 4.4 et ultérieur pour accéder aux ressources de l’entreprise. En décembre, tous les appareils inscrits seront obligatoirement mis hors service et perdront l’accès aux ressources de l’entreprise. Si vous utilisez des stratégies de protection des applications sans MDM, les applications ne recevront aucune mise à jour et perdront en qualité au fil du temps.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Indiquer aux utilisateurs finaux quelles informations de leur appareil peuvent être vues sur les appareils inscrits <!--1165314-->
Nous ajoutons l’information **Type de propriété** dans l’écran des détails des appareils qui se trouve sur toutes les applications du portail d’entreprise. Ainsi, les utilisateurs ont accès à plus d’informations sur la confidentialité directement dans l’article [Quelles informations votre entreprise peut-elle voir ?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Ceci sera introduit dans toutes les applications du portail d’entreprise dans un futur proche. Nous avons annoncé ceci pour iOS en [septembre](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Semaine du 25 septembre 2017

### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="intune-supports-ios-11---1428975--"></a>Intune prend en charge iOS 11 <!--1428975-->
Intune prend en charge iOS 11. Ceci avait été annoncé sur le [blog du support technique Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Fin de la prise en charge d’iOS 8.0 <!---1164477--->
Les applications gérées et l’application Portail d’entreprise pour iOS nécessiteront iOS 9.0 et ultérieur pour accéder aux ressources d’entreprise. Les appareils qui ne sont pas mis à jour avant septembre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. 

### <a name="intune-apps"></a>Applications Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Action d’actualisation ajoutée à l’application Portail d’entreprise pour Windows 10 <!--1132468-->
L’application Portail d’entreprise pour Windows 10 permet aux utilisateurs d’actualiser les données dans l’application avec une requête Pull pour actualiser ou, sur les postes de travail, en appuyant sur F5.



## <a name="notices"></a>Remarques

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nouveau chemin pour les appareils gérés dans l’API Graph<!-- 1586728 -->
Nous changeons le chemin permettant d’accéder aux appareils gérés dans la version bêta de l’API Graph. 

| | |
|--|--|
| Chemin actuel |  https://graph.microsoft.com/beta/managedDevices |
| Nouveau chemin | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Les deux chemins fonctionnent pendant tout le mois d’octobre. Après la publication du service d’octobre, seul le nouveau chemin fonctionnera.  Si vous utilisez l’API Graph pour accéder aux appareils gérés, mettez à jour et vérifiez vos scripts et vos applications avec le nouveau chemin. Pour connaître les autres changements, consultez le [journal des modifications de l’API Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) mensuel.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Avant, la préversion de l’inscription Apple était uniquement accessible à partir de liens dans le portail classique Intune. Les comptes Intune créés avant janvier 2017 nécessitent une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder au portail Azure, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure
Les rôles d’administration de la gestion des applications mobiles (MAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Nouveautés à venir

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Modifications apportées à la prise en charge de l’application Portail d’entreprise Intune iOS <!-- 1164474  -->
Une nouvelle version de l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 9.0 ou ultérieure, sera bientôt disponible. La version du portail d’entreprise qui prend en charge iOS 8 sera toujours disponible pendant une très courte période. Toutefois, notez que si vous utilisez également des applications iOS compatibles MAM, nous prenons en charge iOS 9.0 et ultérieur. Vous devez donc vérifier que les utilisateurs finaux effectuent la mise à jour vers le système d’exploitation le plus récent. 

#### <a name="how-does-this-affect-me"></a>En quoi cela m’affecte-t-il ?
Nous vous donnons cette information à l’avance, même si nous n’avons pas les dates précises, afin que vous ayez le temps de planifier. Vérifiez que vos utilisateurs effectuent la mise à jour vers iOS 9+ et, au moment de la publication de l’application Portail d’entreprise, demandez-leur de mettre à jour leur application Portail d’entreprise.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?
Encouragez les utilisateurs à effectuer la mise à jour vers iOS version 9.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  Encouragez les utilisateurs à installer la nouvelle version du portail d’entreprise et à bénéficier des nouvelles fonctionnalités qu’elle propose.

Accédez à Intune dans le portail Azure et affichez Appareils > Tous les appareils, puis filtrez par version d’iOS pour voir tous les appareils actuels avec des systèmes d’exploitation antérieurs à iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->
La société Apple a annoncé qu’elle appliquera des exigences spécifiques pour ATS (Application Transport Security). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS.

Nous avons publié, par le biais du programme Apple TestFlight, une version de l’application Portail d’entreprise pour iOS qui respecte les nouvelles exigences d’ATS. Si vous souhaitez l’essayer pour tester votre conformité à ATS, envoyez un e-mail à <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> en indiquant votre prénom, votre nom, votre adresse e-mail et le nom de votre société. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

## <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de l’interface utilisateur du portail d’entreprise](whats-new-app-ui.md)
* [Nouveautés des mois précédents](whats-new-archive.md)
