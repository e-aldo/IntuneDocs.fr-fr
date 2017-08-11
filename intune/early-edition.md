---
title: "Édition préliminaire"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 8/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5861c999752bfef05b8a33161d0bf75a6d4daf59
ms.sourcegitcommit: 18cdbdc226f64368de892a8c5cff157c37986c57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="the-early-edition-for-microsoft-intune---august-2017"></a>Édition anticipée pour Microsoft Intune - Août 2017

**L’édition préliminaire** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière limitée et sont susceptibles de changer. Ne partagez pas ces informations en dehors de votre entreprise. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Joignez votre contact de groupe de produits Microsoft si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
>Les modifications suivantes sont en cours de développement pour Intune. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>Intune sur le portail Azure




### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nouvelle action de l’appareil pour forcer les appareils à la synchronisation avec Intune<!-- 711369 -->    
Nous ajoutons une nouvelle action qui force l’appareil sélectionné à s’enregistrer immédiatement auprès d’Intune. Quand un appareil s’enregistre, il reçoit immédiatement les actions ou les stratégies en attente qui lui ont été attribuées.  Cette action peut vous aider à valider et corriger immédiatement les stratégies que vous avez affectées, sans attendre le prochain enregistrement planifié.

### <a name="actions-for-non-compliance----730266--"></a>Actions en cas de non-conformité <!--730266-->     
La fonctionnalité *Actions en cas de non-conformité* est une nouveauté des stratégies de conformité qui vous permet de prendre des mesures au niveau des appareils non conformes. Vous pouvez spécifier une ou plusieurs actions ainsi que la période à laquelle ces actions doivent se produire. Par exemple, vous pouvez avertir par e-mail les utilisateurs d'appareils non conformes immédiatement lorsque ces appareils deviennent non conformes, ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise après une période de grâce de 3 jours via l’accès conditionnel.



### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restriction d’inscription d’appareils Android et iOS par version de système d’exploitation <!--- 1333256,  1245463 --->  
Intune prend désormais en charge la restriction d’inscription d’appareils Android et iOS par numéro de version de système d’exploitation. Sous **Intune** > **Restrictions d’inscription** > **Restrictions de type d’appareil** > **Par défaut** > **Restrictions de plateforme**, l’administrateur informatique peut maintenant définir une configuration de plateforme pour restreindre l’inscription à une plage de valeurs minimale et maximale de système d’exploitation. Les versions de système d’exploitation Android doivent être spécifiées au format Majeure.Mineure.Build.Révision, où Build et Révision sont facultatifs. Les versions d’iOS doivent être spécifiées au format Majeure.Mineure.Build, où Build est facultatif.

>[!NOTE]
>Ce paramètre ne restreint pas l’inscription via les programmes d’inscription Apple, notamment le programme d’inscription des appareils Apple et Apple School Manager ou Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Limiter l’inscription des appareils personnels Android, iOS et macOS <!--- 1333272,  1333275, 1245709 --->
Intune prend désormais en charge la restriction d’inscription des appareils personnels pour iOS, Android et macOS à l’aide des numéros de série des appareils. Certains appareils n’indiquent pas les numéros de série. Contactez les fabricants des appareils pour plus d’informations. En chargeant les numéros de série sur Intune, vous pouvez prédéclarer des appareils comme appartenant à l’entreprise. Les restrictions d’inscription vous permettent de bloquer les appareils personnels (BYOD), ce qui permet l’inscription des appareils de l’entreprise uniquement.

Pour importer des numéros de série dans le portail Intune, accédez à **Inscription d’appareil** > **Identificateurs d’appareil d’entreprise** et cliquez sur **Ajouter**, puis chargez un fichier .CSV. Le fichier ne doit contenir aucun en-tête, mais afficher deux colonnes, une pour le numéro de série et l’autre pour des détails tels que les numéros IMEI.  Pour restreindre les appareils personnels, accédez à **Inscription d’appareil** > **Restrictions d’inscription**. Sous **Restrictions de type d’appareil**, sélectionnez **Par défaut**, puis **Configurations de plateforme**. Vous pouvez **Autoriser** ou **Bloquer** les appareils personnels pour iOS, Android et macOS. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible<!-- 777100 -->   
Une nouvelle stratégie sera disponible dans l’espace de travail des mises à jour logicielles qui vous permet de forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible. Vous serez également en mesure d’afficher un nouveau rapport qui liste les appareils iOS avec des versions antérieures et un résumé de la raison pour laquelle ils sont obsolètes.

### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nouveau rapport qui répertorie les appareils iOS équipés d’anciennes versions iOS   <!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est rendu disponible depuis les **Mises à jour logicielles** de l’espace de travail. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour iOS, et pour lesquels des mises à jour sont disponibles. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour. 

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Nouveaux paramètres pour autoriser et bloquer des applications sur les appareils Samsung KNOX Standard <!-- 822899,  1305423-->   
Nous ajoutons de nouveaux [paramètres de restriction des appareils](device-restrictions-android.md) qui vous permettent de spécifier les listes d’applications suivantes :
  - Applications que les utilisateurs sont autorisés à installer
  - Applications dont l’exécution est bloquée pour les utilisateurs
  - Applications qui sont masquées pour l’utilisateur sur l’appareil  

Vous pouvez spécifier l’application par URL, par nom de package ou à partir de la liste des applications que vous gérez.

### <a name="new-settings-for-windows-10-device-restriction-profile"></a>Nouveaux paramètres pour le profil de restriction des appareils Windows 10
<!--- 978575, 1308849, 1308850 -->
Nous ajoutons de nouveaux paramètres au profil de restriction des appareils Windows 10 dans la catégorie Windows Defender SmartScreen.

Pour obtenir plus d’informations sur le profil de restriction des appareils Windows 10, consultez [Paramètres de restriction des appareils Windows 10 et version ultérieure]( device-restrictions-windows-10.md).

### <a name="new-device-restriction-settings-for-windows-10------1063965---"></a>Nouveaux paramètres de restriction d’appareils pour Windows 10   <!-- 1063965 -->
Nous ajoutons de nouveaux paramètres au [profil de restriction d’appareils Windows 10](/intune/device-restrictions-windows-10) dans les catégories suivantes :
- Windows Defender SmartScreen
- App Store


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

### <a name="conditional-access-support-for-mac-devices-----720172---"></a>Prise en charge de l’accès conditionnel pour les appareils Mac <!-- 720172 -->   
Vous pourrez bientôt définir une stratégie d’accès conditionnel exigeant que les appareils Mac soient inscrits dans Intune et conformes à ses stratégies de conformité. Par exemple, les utilisateurs peuvent télécharger l’application Portail d’entreprise Intune pour macOS et inscrire leurs appareils Mac dans Intune. Intune évalue si l’appareil Mac est conforme ou non aux spécifications telles que le code PIN, le chiffrement, la version du système d’exploitation et l’intégrité du système.

### <a name="end-of-support-for-ios-80----1164477---"></a>Fin de la prise en charge d’iOS 8.0 <!---1164477--->
Les applications gérées et l’application Portail d’entreprise pour iOS nécessiteront iOS 9.0 et ultérieur pour accéder aux ressources d’entreprise. Les appareils qui ne sont pas mis à jour avant septembre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. En décembre, tous les accès aux ressources d’entreprise, notamment l’e-mail, seront bloqués. 

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fin de la prise en charge d’Android 4.3 et antérieur <!---1171127, 1326920 --->
Les applications gérées et l’application Portail d’entreprise pour Android nécessiteront Android 4.4 et ultérieur pour accéder aux ressources de l’entreprise. Les appareils qui ne sont pas mis à jour avant début octobre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. En décembre, tous les appareils inscrits seront obligatoirement mis hors service et perdront l’accès aux ressources de l’entreprise. Si vous utilisez des stratégies de protection des applications sans MDM, les applications ne recevront aucune mise à jour et perdront en qualité au fil du temps.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017----1327781---"></a>Rappel concernant le support de la plateforme : le support standard de Windows Phone 8.1 prend fin le 11 juillet 2017 <!-- 1327781 -->  
Le 11 juillet 2017, le support standard de la plateforme Windows Phone 8.1 prend fin. Le support des PC Windows 8.1 n’est pas impacté.

Il n’existe aucun impact immédiat sur les appareils Windows Phone 8.1 gérés par le service Intune. Les appareils inscrits continuent de fonctionner, tout comme l’ensemble des stratégies, des configurations et des applications. Notez qu’aucune amélioration n’est prévue pour la plateforme Windows Phone 8.1 au sein du service Intune, ni pour l’application Portail d’entreprise Windows Phone 8.1.

Nous vous recommandons de mettre à niveau les appareils Windows Phone 8.1 éligibles vers Windows 10 Mobile dès que possible. 




## <a name="intune-apps"></a>Applications Intune

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modes clair et sombre disponibles pour l’application Portail d’entreprise pour Windows 10 <!---676547--->
Les utilisateurs finaux seront en mesure de personnaliser le mode de couleur de l’application Portail d’entreprise pour Windows 10. Ils pourront apporter la modification dans la section Paramètres de l’application Portail d’entreprise. Le changement apparaîtra une fois que les utilisateurs auront redémarré l’application. Pour Windows 10 versions 1607 et ultérieures, le mode d’application par défaut est le paramètre système. Pour les postes de travail qui exécutent Windows 10 versions 1511 et antérieures, le mode d’application par défaut sera le mode clair.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Autoriser les utilisateurs finaux à accéder à l’application Portail d’entreprise pour Android sans inscription <!---1169910--->  
Les utilisateurs finaux n’auront bientôt pas à inscrire leur appareil pour accéder à l’application Portail d’entreprise pour Android. Les utilisateurs finaux des organisations qui utilisent des stratégies de protection des applications ne recevront plus d’invites pour inscrire leur appareil quand ils ouvriront l’application Portail d’entreprise. Les utilisateurs finaux pourront également installer des applications à partir du portail d’entreprise sans inscrire l’appareil. 

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Message d’erreur amélioré quand un utilisateur atteint le nombre maximal d’appareils autorisés à inscrire <!-- 1270370 -->
Au lieu d’un message d’erreur générique, les utilisateurs finaux reçoivent un message d’erreur convivial offrant une possibilité d’action : « Vous avez inscrit le nombre maximal d’appareils autorisés par votre administrateur informatique. Supprimez un appareil inscrit ou demandez de l’aide à votre administrateur informatique ».

### <a name="new-signed-in-experience-for-android-company-portal-users-and-app-protection-policy-users----621669---"></a>Nouvelle expérience de connexion pour les utilisateurs du portail d’entreprise Android et les utilisateurs de stratégies de protection des applications <!-- 621669 -->
Les utilisateurs finaux seront en mesure de parcourir les applications, de gérer des appareils et d’afficher des informations de contact informatique au moyen de l’application Portail d’entreprise Android sans inscrire leurs appareils Android. De plus, si un utilisateur final utilise déjà une application protégée par des stratégies de protection d’applications Intune et qu’il lance le portail d’entreprise Android, il ne recevra plus d’invite d’inscription pour son appareil. 

### <a name="inform-end-users-what-device-information-can-be-seen-for-ios---739894--"></a>Utilisateurs finaux renseignés sur les informations de leur appareil qui sont consultables pour iOS <!--739894-->
Nous ajoutons l’information **Type de propriété** dans l’écran des détails de l’appareil qui se trouve sur l’application Portail d’entreprise pour iOS. Les utilisateurs peuvent ainsi trouver plus d’informations sur la confidentialité des données, directement à partir de cette page dans la documentation de l’utilisateur final d’Intune. Ils pourront également trouver cette information dans l’écran À propos de.

### <a name="apps-details-pages-display-new-information-for-android-devices---1287476--"></a>Les pages de détails des applications affichent de nouvelles informations pour les appareils Android <!--1287476-->
La page de détails des applications sur le portail d’entreprise pour Android affiche les catégories d’application que l’administrateur informatique a définies pour cette application.

### <a name="intune-mobile-application-management-mam-dialog-boxes-now-have-a-modern-interface----1199015---"></a>Les boîtes de dialogue Gestion des applications mobiles (GAM) Intune ont désormais une interface modernisée <!-- 1199015 -->
Les boîtes de dialogue Gestion des applications mobiles (GAM) Intune ont été mises à jour et affichent une apparence plus actuelle. Ces boîtes de dialogue fonctionnent de la même façon qu’avec le précédent style.

Sur les appareils Android modernes, les boîtes de dialogue d’erreur ou de notification affichées par Intune offrent maintenant un nouveau design.

### <a name="new-setting-in-the-android-company-portal-app-to-toggle-battery-optimization---1405990--"></a>Nouveau paramètre dans l’application Portail d’entreprise Android pour activer/désactiver l’optimisation de batterie <!--1405990-->
La page **Paramètres** dans l’application Portail d’entreprise pour Android propose un nouveau paramètre qui va faciliter aux utilisateurs la désactivation de l’optimisation de batterie pour les applications Portail d’entreprise et Microsoft Authenticator. Le nom de l’application qui est indiqué dans le paramètre varie en fonction de l’application qui gère le compte professionnel. Nous préconisons aux utilisateurs de désactiver l’optimisation de batterie pour améliorer les performances des applications professionnelles qui synchronisent les e-mails et les données. 




## <a name="notices"></a>Remarques

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->   
La société Apple a annoncé qu’à compter du printemps 2017, elle appliquera des exigences de sécurité spécifiques pour Application Transport Security (ATS). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->   
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure en version préliminaire. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessiteront une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder à la version préliminaire, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Modification planifiée : Intune transforme l’expérience du portail pour les partenaires Intune<!-- 1050016 -->
Nous supprimons la page des partenaires Intune du site manage.microsoft.com à compter de la mise à jour de service prévue mi-mai 2017.  

Si vous êtes un administrateur de partenaires, vous ne pourrez plus afficher la page des partenaires Intune et agir pour le compte de vos clients, et vous devrez vous connecter à un des deux autres portails des partenaires sur le site de Microsoft.

Le [Centre pour partenaires Microsoft](https://partnercenter.microsoft.com/) et l[’Espace d’administration des partenaires Microsoft Office 365](https://portal.office.com/) vous permettent de vous connecter aux comptes client que vous gérez. En tant que partenaire, utilisez à partir de maintenant l’un de ces sites pour gérer vos clients.



### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
