---
title: "Édition préliminaire"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 09/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31c3d3750aadbe8d302713f081f01f7c51d8ce96
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="the-early-edition-for-microsoft-intune---september-2017"></a>Édition préliminaire pour Microsoft Intune - Septembre 2017

**L’édition préliminaire** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière limitée et sont susceptibles de changer. Ne partagez pas ces informations en dehors de votre entreprise. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Joignez votre contact de groupe de produits Microsoft si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
>Les modifications suivantes sont en cours de développement pour Intune. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-in-the-azure-portal"></a>Intune dans le portail Azure


### <a name="google-play-protect-support-on-android----908720----"></a>Support de Google Play Protect sur Android <!-- 908720  -->  
Avec la publication d’Android Oreo, Google introduit une suite de fonctionnalités de sécurité appelée Google Play Protect qui permet aux utilisateurs et aux organisations d’exécuter des applications sécurisées et des images Android sécurisées. Intune prendra en charge les fonctionnalités de Google Play Protect, notamment l’attestation SafetyNet distante.  Les administrateurs peuvent définir des exigences pour la stratégie de conformité afin que Google Play Protect soit configuré et intègre. Le paramètre **Attestation d’appareil SafetyNet** nécessite que l’appareil se connecte à un service Google pour vérifier que l’appareil est intègre et qu’il n’est pas compromis. Les administrateurs peuvent également définir un paramètre de profil de configuration pour qu’Android for Work exige que les applications installées soient vérifiées par les services Google Play.  L’accès conditionnel peut empêcher les utilisateurs d’accéder aux ressources d’entreprise si un appareil n’est pas conforme aux exigences de Google Play Protect. 

### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Empêcher les utilisateurs d’appareils Android de modifier la date et l’heure de leur appareil  <!-- 1333292 -->
Vous pouvez utiliser la [stratégie d’appareil personnalisée Android](custom-settings-android.md) pour empêcher les utilisateurs d’appareils Android de modifier la date et l’heure de l’appareil.
Pour ce faire, configurez une stratégie personnalisée Android avec le paramètre URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Affectez-lui la valeur **TRUE**, puis attribuez-le aux groupes requis.

### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Afficher les attributions de la stratégie de protection des applications pour la résolution des problèmes <!--  1475003 -->
Dans cette version à venir, l’option **Stratégie de protection des applications** sera ajoutée à la liste déroulante **Affectations** disponible dans le panneau de résolution des problèmes. Vous pouvez maintenant sélectionner des stratégies de protection des applications pour afficher les stratégies de protection des applications affectées aux utilisateurs sélectionnés.

### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Créer des applications iOS limitées à des App Stores Apple locaux spécifiques <!-- 1281692 -->
Vous pourrez spécifier les paramètres régionaux lors de la création d’une application managée App Store Apple.

> [!NOTE]  
> Actuellement, vous ne pouvez que créer des applications managées App Store Apple qui sont présentes le magasin du pays États-Unis.

### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Sélectionner le magasin Apple du pays pour synchroniser les applications VPP<!-- 1332311 -->  
Vous pouvez configurer le magasin du pays pour le programme d’achat en volume (VPP) lors du chargement de votre jeton VPP. Intune synchronise les applications VPP pour tous les paramètres régionaux à partir du magasin du pays VPP spécifié.

> [!NOTE]  
> Actuellement, Intune synchronise uniquement les applications VPP à partir du magasin du pays VPP qui correspond aux paramètres régionaux Intune avec lesquels le client Intune a été créé.

###  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Mettre à jour les applications sous licence pour l’appareil et l’utilisateur VPP iOS  <!-- 1305564 -->  
Vous pourrez configurer le jeton VPP iOS pour mettre à jour toutes les applications achetées pour ce jeton via le service Intune. Intune détecte les mises à jour des applications VPP dans le magasin d’applications et les envoie (Push) automatiquement vers l’appareil lorsque ce dernier se connecte.

### <a name="ios-11-support----1428975---"></a>Prise en charge d’iOS 11 <!-- 1428975 -->
Lors de sa publication par Apple, Intune prendra en charge iOS 11.

### <a name="new-settings-for-windows-10-team-device-restriction-profile------1308838----"></a>Nouveaux paramètres pour le profil de restriction d’appareils Windows 10 Collaboration <!--- 1308838  -->
Dans cette version, nous ajoutons de nombreux nouveaux paramètres au profil de restriction d’appareils Windows 10 Collaboration pour vous aider à contrôler les appareils Surface Hub.
Pour plus d’informations sur ce profil, consultez [Paramètres de restriction d’appareils Windows 10 Collaboration](device-restrictions-windows-10-teams.md).

### <a name="support-for-windows-10-edition-upgrade-policy------903672-1119689---"></a>Prise en charge de la stratégie de mise à niveau de l’édition Windows 10   <!-- 903672, 1119689 -->  
Vous pourrez créer une stratégie de mise à niveau de l’édition Windows 10 qui met à niveau les appareils Windows 10 vers Windows 10 Éducation, Windows 10 Éducation N, Windows 10 Professionnel, Windows 10 Professionnel N, Windows 10 Professionnel Éducation et Windows 10 Professionnel Éducation N. Pour plus d’informations sur les mises à niveau de l’édition Windows 10, consultez [Configuration des mises à niveau de l’édition Windows 10 ](edition-upgrade-configure-windows-10.md).

### <a name="review-policy-compliance-for-windows-10-update-rings----1352223---"></a>Vérifier la conformité de la stratégie pour les boucles de mise à jour de Windows 10 <!-- 1352223 -->  
Vous pourrez consulter un rapport sur la stratégie pour vos boucles de mise à jour de Windows 10 à partir de **Mises à jour logicielles** > **État de déploiement par boucle de mise à jour**. Le rapport sur la stratégie inclut l’état du déploiement pour les boucles de mise à jour que vous avez configurées. 

### <a name="windows-10-company-portal-app-added-to-windows-information-protection-allow-policy----677129---"></a>Application Portail d’entreprise Windows 10 ajoutée à la stratégie d’autorisation Protection des informations Windows <!-- 677129 -->  
L’application Portail d’entreprise Windows 10 sera mise à jour pour prendre en charge la Protection des informations Windows (WIP). L’application peut être ajoutée à la stratégie d’autorisation WIP. Grâce à cette modification, il n’est plus nécessaire d’ajouter l’application à la liste **Exempté**. 

### <a name="remote-support-for-windows-and-windows-mobile-devices-----1070473---"></a>Support distant de Windows et des appareils Windows Mobile <!-- 1070473 -->    
Intune pourra utiliser le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs qui utilisent des appareils Windows et Windows Mobile.

### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Analyser les appareils avec Windows Defender <!-- 1280988  1280990   -->
Vous pourrez exécuter une **Analyse rapide**, une **Analyse complète** et **Mettre à jour les signatures** avec Antivirus Windows Defender sur les appareils Windows 10 gérés. À partir du panneau de présentation de l’appareil, choisissez l’action à exécuter sur l’appareil. Vous êtes invité à confirmer l’action avant l’envoi de la commande à l’appareil. 

**Analyse rapide** : une analyse rapide analyse les emplacements où les programmes malveillants s’enregistrent pour démarrer, comme les clés de registre et les dossiers de démarrage Windows connus. Une analyse rapide prend en moyenne cinq minutes. Associée au paramètre **Protection en temps réel toujours activé** qui analyse les fichiers lorsqu’ils sont ouverts, fermés et à chaque fois qu’un utilisateur accède à un dossier, une analyse rapide fournit une protection contre les programmes malveillants qui peuvent se trouver dans le système ou le noyau. Lorsque l’analyse s’achève, ses résultats s’affichent sur les appareils des utilisateurs. 

**Analyse complète** : une analyse complète peut être utile sur les appareils confrontés à une menace issue de programmes malveillants afin de déterminer s’il existe des composants inactifs qui nécessitent un nettoyage plus approfondi. Elle est également utile pour exécuter des analyses à la demande. Une analyse complète peut prendre une heure. Lorsque l’analyse s’achève, ses résultats s’affichent sur les appareils des utilisateurs. 

**Mettre à jour les signatures** : la commande de mise à jour de signature met à jour les définitions et les signatures des programmes malveillants dans Antivirus Windows Defender. Cela permet de garantir l’efficacité d’Antivirus Windows Defender dans la détection des programmes malveillants. Cette fonctionnalité s’applique uniquement aux appareils Windows 10 et est sujette à la connectivité Internet de l’appareil. 

### <a name="bitlocker-device-configuration----1397398---"></a>Configuration d’appareil BitLocker <!-- 1397398 -->  
Les paramètres **Chiffrement Windows > Paramètres de Base** incluront un nouveau paramètre **Avertissement sur le chiffrement d’un autre disque** qui vous permet de désactiver le [message d’avertissement](https://docs.microsoft.com/en-us/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) sur le chiffrement d’un autre disque qui peut être utilisé sur l’appareil de l’utilisateur.  Le message d’avertissement requiert le consentement de l’utilisateur final avant la configuration de BitLocker sur l’appareil et bloque la configuration de BitLocker jusqu’à ce qu’elle soit confirmée par l’utilisateur final.  Le nouveau paramètre désactive l’avertissement affiché pour l’utilisateur final.

### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Migration du Portail d’entreprise pour Windows 8.1 et Windows Phone 8.1 vers le mode soutenu <!--1428681-->
À partir d’octobre 2017, les applications Portail d’entreprise pour Windows 8.1 et Windows Phone 8.1 passent en mode soutenu. Cela signifie que les applications et les scénarios existants, comme l’inscription et la conformité, seront toujours pris en charge pour ces plateformes. Ces applications resteront disponibles au téléchargement par le biais des canaux de publication existants, comme Microsoft Store. 

Une fois en mode soutenu, ces applications recevront uniquement les mises à jour de sécurité critiques. Aucune mise à jour ou fonctionnalité supplémentaire ne sera publiée pour ces applications. Pour obtenir les nouvelles fonctionnalités, nous vous recommandons de mettre à jour les appareils vers Windows 10 ou Windows 10 Mobile. 

###  <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquer la copie et le collage entre les profils professionnels et personnels dans Android for Work <!-- 1098994 -->   
Avec cette version, vous pouvez configurer le profil professionnel Android for Work afin qu’il bloque la copie et le collage entre les applications professionnelles et personnelles. Vous trouverez ce nouveau paramètre dans le profil **Restrictions d’appareils** pour la plateforme **Android for Work** dans **Paramètres du profil professionnel**.

### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nouveaux comportements de l’application Portail d’entreprise pour Android avec les profils professionnels <!---1485783--->
Lorsque vous inscrivez un appareil Android for Work avec un profil professionnel, c’est l’application Portail d’entreprise dans le profil professionnel qui effectue les tâches de gestion sur l’appareil. L’application Portail d’entreprise pour Android n’a plus aucune utilité, sauf si vous utilisez une application GAM dans le profil professionnel. Pour améliorer l’expérience liée au profil professionnel, Intune masque automatiquement l’application Portail d’entreprise personnelle après l’inscription réussie d’un profil professionnel.

L’application Portail d’entreprise pour Android peut être activée à tout moment dans le profil personnel en recherchant [Portail d’entreprise dans le Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) et en appuyant sur **Activer**.

### <a name="intune-mam--outlook-for-android-add-ins-----1450688---"></a>GAM Intune et Outlook pour les compléments Android  <!-- 1450688 -->
Dans quelques semaines, l’équipe Office présentera des compléments pour Outlook sur Android. Cet ensemble de fonctionnalités complémentaires existe déjà dans Outlook sur Windows, iOS, web et Mac. Étant donné que les compléments sont gérés par Exchange, les utilisateurs pourront copier et partager des données et des messages entre Outlook et les applications complémentaires non gérées, sauf si l’accès aux compléments est désactivé par votre administrateur Exchange. 

Pour gérer les autorisations d’accès utilisateur aux compléments, contactez votre administrateur Exchange pour vous assurer que vos stratégies de protection des données GAM s’appliquent aux compléments.

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?
Si vos stratégies Exchange sont déjà définies pour empêcher le chargement d’une version test ou l’installation des compléments, inutile de poursuivre votre lecture. Vos stratégies GAM s’appliqueront comme prévu. Si, toutefois, vous avez défini des stratégies dans la GAM pour restreindre les opérations couper, copier et coller dans Outlook sur Android et si vous n’avez pas défini votre stratégie complémentaire dans Exchange, vous devez savoir que par défaut, les utilisateurs pourront installer des compléments dans Outlook. Ces compléments peuvent accéder au corps du message, à l’objet et à d’autres propriétés du message. Vous pouvez désactiver la capacité de l’utilisateur final à installer des compléments en demandant à votre administrateur Exchange de supprimer les rôles « Mes applications personnalisées » et « Mes applications de la Place de marché ». Pour plus d’informations, consultez le lien vers des informations supplémentaires indiqué ci-dessous.

Notez que la modification du paramètre dans Exchange s’appliquera à Outlook sur Windows, iOS, web, Mac et les appareils mobiles. 

#### <a name="what-do-i-need-to-do"></a>Que dois-je faire ?
Passez en revue vos stratégies Exchange dès aujourd’hui. Informez votre service informatique et le personnel du support technique. Contactez notre équipe de support si vous avez des questions ou si vous rencontrez des problèmes. 

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Collection d’entité d’association d’appareil utilisateur ajoutée au modèle de données Intune Data Warehouse <!-- 1187917 -->
Vous pourrez générer des rapports et des visualisations des données en utilisant les informations d’association d’appareil utilisateur qui associent les collections d’entité utilisateur et appareil. Le modèle de données est accessible par le biais du fichier Power BI (PBIX) extrait de la page Intune Data Warehouse, via le point de terminaison OData, ou en développant un client personnalisé.


<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--"></a>Actions en cas de non-conformité <!--730266-->     
La fonctionnalité *Actions en cas de non-conformité* est une nouveauté des stratégies de conformité qui vous permet de prendre des mesures au niveau des appareils non conformes. Vous pouvez spécifier une ou plusieurs actions ainsi que la période à laquelle ces actions doivent se produire. Par exemple, vous pouvez avertir par e-mail les utilisateurs d'appareils non conformes immédiatement lorsque ces appareils deviennent non conformes, ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise après une période de grâce de 3 jours via l’accès conditionnel.


### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nouveau rapport qui répertorie les appareils iOS équipés d’anciennes versions iOS   <!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est rendu disponible depuis les **Mises à jour logicielles** de l’espace de travail. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour iOS, et pour lesquels des mises à jour sont disponibles. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour. 

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nouveaux paramètres pour le profil de restriction des appareils Windows 10
<!--- 978575, 1308849, -->
Nous ajoutons de nouveaux paramètres au profil de restriction des appareils Windows 10 dans la catégorie Windows Defender SmartScreen.

Pour obtenir plus d’informations sur le profil de restriction des appareils Windows 10, consultez [Paramètres de restriction des appareils Windows 10 et version ultérieure]( device-restrictions-windows-10.md).

### <a name="android-for-work-support-for-lookout----1087312---"></a>Prise en charge d’Android for Work pour Lookout <!-- 1087312 -->   
Le connecteur Intune avec Lookout prendra en charge les appareils Android for Work lors de l’utilisation de l’application Lookout for Work. Vous êtes en mesure de déployer l’application Lookout à l’intérieur ou en dehors du conteneur.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Outils de développement Intune App Protection et Citrix MDX<!-- 709185 -->
Vous pouvez gérer des appareils et des applications en combinant Citrix XenMobile MDX avec Microsoft Intune. Cela vous permet de gérer des applications à l’aide d’une stratégie de protection des applications Intune tout en utilisant la technologie mVPN de Citrix.

Vous êtes en mesure de trouver un dépôt de code, contenant l’outil Intune App Wrapping Tool et le kit SDK d’applications Intune pour iOS et Android, qui s’intègre à la technologie mVPN de Citrix MDX.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium : nouveau partenaire de Mobile Threat Defense <!-- 954681 -->
Vous pouvez contrôler l’accès des appareils mobiles aux ressources de l’entreprise grâce à un accès conditionnel reposant sur une évaluation des risques qui est effectuée par Zimperium, solution Mobile Threat Defense qui s’intègre à Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Déroulement de l’intégration à Intune
Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Zimperium. Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Zimperium, activée par le biais des stratégies de conformité Intune, que vous pouvez utiliser pour autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise en fonction des menaces détectées.

### <a name="new-azure-ad-conditional-access-policy-ui-link-from-intune-----1016201---"></a>Lien vers la nouvelle interface utilisateur des stratégies d’accès conditionnel Azure AD à partir d’Intune  <!-- 1016201 -->
Les administrateurs informatiques peuvent définir des stratégies conditionnelles s’appuyant sur les application via la nouvelle interface utilisateur des stratégies d’accès conditionnel dans la charge de travail Azure AD. Les stratégies d’accès conditionnel reposant sur les applications qui se trouvent à la section Application Protection Intune dans Azure restent à cet endroit pour l’instant et sont appliquées côte à côte. Par souci pratique, un lien est également prévu vers la nouvelle interface utilisateur des stratégies d’accès conditionnel dans Azure AD, à partir de la charge de travail d’Intune.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Prise en charge d’un haut niveau de disponibilité pour le connecteur Exchange local <!-- 676614 -->   
Vous pouvez avoir plusieurs rôles serveur d’accès au client pour le connecteur Exchange local. Par exemple, si le principal serveur d’accès au client échoue, le connecteur Exchange reçoit une requête pour revenir à d’autres serveurs. Cette fonctionnalité garantit que le service n’est pas interrompu.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pack d’administration de System Center Operations Manager pour le connecteur Exchange <!-- 885457 -->   
Le pack d’administration de System Center Operations Manager pour le connecteur Exchange sera disponible pour vous aider à analyser les journaux du connecteur Exchange. Ce pack d’administration vous donne différents moyens de surveiller Intune lorsque vous devez résoudre des problèmes.

### <a name="end-of-support-for-ios-80----1164477---"></a>Fin de la prise en charge d’iOS 8.0 <!---1164477--->
Les applications gérées et l’application Portail d’entreprise pour iOS nécessiteront iOS 9.0 et ultérieur pour accéder aux ressources d’entreprise. Les appareils qui ne sont pas mis à jour avant septembre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. En décembre, tous les accès aux ressources d’entreprise, notamment l’e-mail, seront bloqués. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fin de la prise en charge d’Android 4.3 et antérieur <!---1171127, 1326920 --->
Les applications gérées et l’application Portail d’entreprise pour Android nécessiteront Android 4.4 et ultérieur pour accéder aux ressources de l’entreprise. Les appareils qui ne sont pas mis à jour avant début octobre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. En décembre, tous les appareils inscrits seront obligatoirement mis hors service et perdront l’accès aux ressources de l’entreprise. Si vous utilisez des stratégies de protection des applications sans MDM, les applications ne recevront aucune mise à jour et perdront en qualité au fil du temps.

### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Rappel concernant le support de la plateforme : le support standard de Windows Phone 8.1 prend fin le 11 juillet 2017 <!-- 1327781 -->  
Le 11 juillet 2017, le support standard de la plateforme Windows Phone 8.1 prend fin. Le support des PC Windows 8.1 n’est pas impacté.

Il n’existe aucun impact immédiat sur les appareils Windows Phone 8.1 gérés par le service Intune. Les appareils inscrits continuent de fonctionner, tout comme l’ensemble des stratégies, des configurations et des applications. Notez qu’aucune amélioration n’est prévue pour la plateforme Windows Phone 8.1 au sein du service Intune, ni pour l’application Portail d’entreprise Windows Phone 8.1.

Nous vous recommandons de mettre à niveau les appareils Windows Phone 8.1 éligibles vers Windows 10 Mobile dès que possible. 





## <a name="intune-apps"></a>Applications Intune
### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Action d’actualisation ajoutée à l’application Portail d’entreprise pour Windows 10 <!--1132468-->
L’application Portail d’entreprise pour Windows 10 permettra aux utilisateurs d’actualiser les données dans l’application avec une requête Pull pour actualiser ou en appuyant sur F5.


### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Les applications qui sont disponibles avec ou sans inscription peuvent désormais être installées sans invitation à l’inscription. <!-- 1334712 -->
Les applications d’entreprise qui ont été mises à disposition avec ou sans inscription dans l’application Portail d’entreprise Android peuvent être installées sans invitation à l’inscription.

### <a name="ios-company-portal-display-large-icons----1454593---"></a>Affichage de grandes icônes dans le Portail d’entreprise iOS <!-- 1454593 -->
Nous résolvons un problème connu sur la façon dont le Portail d’entreprise iOS affiche les icônes dans la vignette de l’application. Si vous chargez des icônes de l’application de 120 x 120 pixels ou plus, elles s’affichent désormais sur le [site web Portail d’entreprise] (https://portal.manage.microsoft.com) et les pages de l’application Portail d’entreprise iOS en respectant la taille complète de la vignette de l’application.

### <a name="easier-to-understand-phrasing-for-the-company-portal-app-for-android------1396349---"></a>Formulation plus facile à comprendre pour l’application Portail d’entreprise pour Android <!---1396349--->    
Le processus d’inscription de l’application Portail d’entreprise pour Android a été simplifié à l’aide d’un nouveau texte afin de faciliter l’inscription des utilisateurs finaux. 


<!-- the following are present prior to 1709 -->


### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Prise en charge d’Intune Managed Browser pour iOS et Android <!---1374196--->
À compter d’octobre 2017, l’application Intune Managed Browser sur l’application Android prendra en charge seulement les appareils exécutant Android 4.4 et ultérieur. L’application Intune Managed Browser sur iOS prendra en charge seulement les appareils exécutant iOS 9.0 et ultérieur. Les versions antérieures d’Android et d’iOS pourront encore utiliser Managed Browser, mais elles ne pourront pas installer les nouvelles versions de l’application et n’auront peut-être pas accès à toutes les fonctionnalités. Nous vous encourageons à mettre à jour le système d’exploitation de ces appareils avec une version prise en charge.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Autoriser les utilisateurs finaux à accéder à l’application Portail d’entreprise pour Android sans inscription <!---1169910--->  
Les utilisateurs finaux n’auront bientôt pas à inscrire leur appareil pour accéder à l’application Portail d’entreprise pour Android. Les utilisateurs finaux des organisations qui utilisent des stratégies de protection des applications ne recevront plus d’invites pour inscrire leur appareil quand ils ouvriront l’application Portail d’entreprise. Les utilisateurs finaux pourront également installer des applications à partir du portail d’entreprise sans inscrire l’appareil. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Message d’erreur amélioré quand un utilisateur atteint le nombre maximal d’appareils autorisés à inscrire <!-- 1270370 -->
Au lieu d’un message d’erreur générique, les utilisateurs finaux reçoivent un message d’erreur convivial offrant une possibilité d’action : « Vous avez inscrit le nombre maximal d’appareils autorisés par votre administrateur informatique. Supprimez un appareil inscrit ou demandez de l’aide à votre administrateur informatique ».

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Utilisateurs finaux renseignés sur les informations de leur appareil qui sont consultables pour iOS <!--739894-->
Nous ajoutons l’information **Type de propriété** dans l’écran des détails de l’appareil qui se trouve sur l’application Portail d’entreprise pour iOS. Les utilisateurs peuvent ainsi trouver plus d’informations sur la confidentialité des données, directement à partir de cette page dans la documentation de l’utilisateur final d’Intune. Ils pourront également trouver cette information dans l’écran À propos de.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Les pages de détails des applications affichent de nouvelles informations pour les appareils Android <!--1287476-->
La page de détails des applications sur le portail d’entreprise pour Android affiche les catégories d’application que l’administrateur informatique a définies pour cette application.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Les boîtes de dialogue Gestion des applications mobiles (GAM) Intune ont désormais une interface modernisée <!-- 1199015 -->
Les boîtes de dialogue Gestion des applications mobiles (GAM) Intune ont été mises à jour et affichent une apparence plus actuelle. Ces boîtes de dialogue fonctionnent de la même façon qu’avec le précédent style.

Sur les appareils Android modernes, les boîtes de dialogue d’erreur ou de notification affichées par Intune offrent maintenant un nouveau design.



## <a name="notices"></a>Remarques
### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->   
La société Apple a annoncé qu’à compter du printemps 2017, elle appliquera des exigences de sécurité spécifiques pour Application Transport Security (ATS). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Modification planifiée : Intune transforme l’expérience du portail pour les partenaires Intune<!-- 1050016 -->
Nous supprimons la page des partenaires Intune du site manage.microsoft.com à compter de la mise à jour de service prévue mi-mai 2017.  

Si vous êtes un administrateur de partenaires, vous ne pourrez plus afficher la page des partenaires Intune et agir pour le compte de vos clients, et vous devrez vous connecter à un des deux autres portails des partenaires sur le site de Microsoft.

Le [Centre pour partenaires Microsoft](https://partnercenter.microsoft.com/) et l[’Espace d’administration des partenaires Microsoft Office 365](https://portal.office.com/) vous permettent de vous connecter aux comptes client que vous gérez. En tant que partenaire, utilisez à partir de maintenant l’un de ces sites pour gérer vos clients.



### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
