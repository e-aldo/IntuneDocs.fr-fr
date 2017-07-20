---
title: "Édition préliminaire"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b8d281e3af2458bd5ab343dfa5123b31075d28ed
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/13/2017
---
# <a name="the-early-edition-for-microsoft-intune---july-2017"></a>Édition anticipée pour Microsoft Intune - Juillet 2017

**L’édition préliminaire** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière très limitée et sont susceptibles de changer. Ne partagez pas ces informations en dehors de votre entreprise. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Joignez votre contact de groupe de produits Microsoft si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
>Les modifications suivantes sont en cours de développement pour Intune. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez notre page [Nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--

## What's coming to Intune on the Azure portal  
## What's coming to Intune apps
## Notices

-->



## <a name="intune-on-the-azure-portal"></a>Intune sur le portail Azure

### <a name="easier-installation-of-office-365-apps-----1121362----"></a>Installation plus facile des applications Office 365 <!--- 1121362 --->
À l’aide d’un nouveau type d’application **Office 365 ProPlus**, vous pouvez affecter plus facilement les applications Office 365 ProPlus aux appareils que vous gérez et qui exécutent la dernière version de Windows 10. Vous pouvez aussi installer Microsoft Project et Microsoft Visio si vous avez les licences appropriées. Les applications souhaitées sont regroupées et apparaissent en tant qu’application unique dans la liste des applications de la console Intune.


### <a name="new-device-action-to-force-devices-to-sync-with-intune----711369---"></a>Nouvelle action de l’appareil pour forcer les appareils à la synchronisation avec Intune<!-- 711369 -->    
Nous ajoutons une nouvelle action qui force l’appareil sélectionné à s’enregistrer immédiatement auprès d’Intune. Quand un appareil s’enregistre, il reçoit immédiatement les actions ou les stratégies en attente qui lui ont été attribuées.  Cette action peut vous aider à valider et corriger immédiatement les stratégies que vous avez affectées, sans attendre le prochain enregistrement planifié.

### <a name="actions-for-non-compliance----730266--"></a>Actions en cas de non-conformité <!--730266-->     
*Actions en cas de non-conformité* est une nouvelle fonctionnalité de stratégies de conformité qui vous permet de prendre des mesures au niveau des appareils non conformes. Vous pouvez spécifier une ou plusieurs actions ainsi que la période à laquelle ces actions doivent se produire. Par exemple, vous pouvez avertir par e-mail les utilisateurs d'appareils non conformes immédiatement lorsque ces appareils deviennent non conformes, ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise après une période de grâce de 3 jours via l’accès conditionnel.


### <a name="new-app-configuration-settings-for-the-intune-managed-browser-----682951----"></a>Nouveaux paramètres de configuration d’application pour Intune Managed Browser <!--- 682951 --->
Nous ajouterons de nouvelles configurations pour l’application Intune Managed Browser. Vous serez en mesure d’utiliser une stratégie de configuration d’application pour configurer la page d’accueil par défaut et les signets du navigateur.

### <a name="restrict-android-and-ios-device-enrollment-restriction-by-os-version------1333256--1245463----"></a>Restriction d’inscription d’appareils Android et iOS par version de système d’exploitation <!--- 1333256,  1245463 --->  
Intune prend désormais en charge la restriction d’inscription d’appareils Android et iOS par numéro de version de système d’exploitation. Sous **Intune** > **Restrictions d’inscription** > **Restrictions de type d’appareil** > **Par défaut** > **Restrictions de plateforme**, l’administrateur informatique peut maintenant définir une configuration de plateforme pour restreindre l’inscription à une plage de valeurs minimale et maximale de système d’exploitation. Les versions de système d’exploitation Android doivent être spécifiées au format Majeure.Mineure.Build.Révision, où Build et Révision sont facultatifs. Les versions d’iOS doivent être spécifiées au format Majeure.Mineure.Build, où Build est facultatif.

>[!NOTE]
>Ce paramètre ne restreint pas l’inscription via les programmes d’inscription Apple, notamment le programme d’inscription des appareils Apple et Apple School Manager ou Apple Configurator.

### <a name="restrict-android-ios-and-macos-device-personally-owned-device-enrollment------1333272--1333275-1245709----"></a>Limiter l’inscription des appareils personnels Android, iOS et macOS <!--- 1333272,  1333275, 1245709 --->
Intune prend désormais en charge la restriction d’inscription des appareils personnels pour iOS, Android et macOS à l’aide des numéros de série des appareils. Certains appareils n’indiquent pas les numéros de série. Contactez les fabricants des appareils pour plus d’informations. En chargeant les numéros de série sur Intune, vous pouvez prédéclarer des appareils comme appartenant à l’entreprise. Les restrictions d’inscription vous permettent de bloquer les appareils personnels (BYOD), ce qui permet l’inscription des appareils de l’entreprise uniquement.

Pour importer des numéros de série dans le portail Intune, accédez à **Inscription d’appareil** > **Identificateurs d’appareil d’entreprise** et cliquez sur **Ajouter**, puis chargez un fichier .CSV (pas d’en-tête, deux colonnes pour le numéro de série et des détails tels que les numéros IMEI).  Pour restreindre les appareils personnels, accédez à **Inscription d’appareil** > **Restrictions d’inscription**. Sous **Restrictions de type d’appareil**, sélectionnez **Par défaut**, puis **Configurations de plateforme**. Vous pouvez **Autoriser** ou **Bloquer** les appareils personnels pour iOS, Android et macOS. 

### <a name="force-supervised-ios-devices-to-automatically-install-the-latest-available-software-update----777100---"></a>Forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible<!-- 777100 -->   
Une nouvelle stratégie sera disponible dans l’espace de travail des mises à jour logicielles qui vous permet de forcer les appareils iOS supervisés à installer automatiquement la dernière mise à jour logicielle disponible. Vous serez également en mesure d’afficher un nouveau rapport qui liste les appareils iOS avec des versions antérieures et un résumé de la raison pour laquelle ils sont obsolètes.

### <a name="new-settings-to-allow-and-block-apps-on-samsung-knox-standard-devices-----822899--1305423--"></a>Nouveaux paramètres pour autoriser et bloquer des applications sur les appareils Samsung KNOX Standard <!-- 822899,  1305423-->   
Nous ajoutons de nouveaux [paramètres de restriction des appareils](device-restrictions-android.md) qui vous permettent de spécifier les listes d’applications suivantes :
  - Applications que les utilisateurs sont autorisés à installer
  - Applications dont l’exécution est bloquée pour les utilisateurs
  - Applications qui sont masquées pour l’utilisateur sur l’appareil  

Vous pouvez spécifier l’application par URL, par nom de package ou à partir de la liste des applications que vous gérez.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Prise en charge d’Android for Work pour Lookout <!-- 1087312 -->   
Le connecteur Intune avec Lookout prendra en charge les appareils Android for Work lors de l’utilisation de l’application Lookout for Work. Vous serez en mesure de déployer l’application Lookout à l’intérieur ou en dehors du conteneur.


### <a name="check-point-sandblast-mobile---new-mobile-threat-defense-partner-----954651--and--1172027----"></a>Check Point SandBlast Mobile : nouveau partenaire de Mobile Threat Defense <!-- 954651  and  1172027 ? -->  
Vous pourrez contrôler l’accès des appareils mobiles aux ressources de l’entreprise à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Check Point SandBlast Mobile, solution Mobile Threat Defense qui s’intègre à Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Déroulement de l’intégration à Intune
Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Check Point SandBlast Mobile. Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Check Point SandBlast Mobile, activée par le biais des stratégies de conformité Intune. Vous pouvez autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise en fonction des menaces détectées.

### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium : nouveau partenaire de Mobile Threat Defense <!-- 954681 -->
Vous pourrez contrôler l’accès des appareils mobiles aux ressources de l’entreprise à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Zimperium, solution Mobile Threat Defense qui s’intègre à Microsoft Intune.

#### <a name="how-integration-with-intune-works"></a>Déroulement de l’intégration à Intune
Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Zimperium. Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Zimperium, activée par le biais des stratégies de conformité Intune, que vous pouvez utiliser pour autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise en fonction des menaces détectées.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Prise en charge d’un haut niveau de disponibilité pour le connecteur Exchange local <!-- 676614 -->   
Vous pourrez avoir plusieurs rôles serveur d’accès au client pour le connecteur Exchange local. Par exemple, si le principal serveur d’accès au client échoue, le connecteur Exchange reçoit une requête pour revenir à d’autres serveurs. Cette fonctionnalité garantit que le service n’est pas interrompu.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pack d’administration de System Center Operations Manager pour le connecteur Exchange <!-- 885457 -->   
Le pack d’administration de System Center Operations Manager pour le connecteur Exchange sera disponible pour vous aider à analyser les journaux du connecteur Exchange. Cela vous donnera différents moyens de surveiller Intune lorsque vous avez besoin de résoudre des problèmes.

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

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Amélioration de l’expérience de connexion sur l’ensemble des applications du portail d’entreprise pour toutes les plates-formes<!--User Story 1132123-->    
Dans les mois à venir, nous introduirons des changements visant à améliorer l’expérience de connexion aux applications Portail d’entreprise Intune pour Android, iOS et Windows. La nouvelle expérience utilisateur s’affiche automatiquement sur toutes les plates-formes utilisées pour l’application du portail d’entreprise lorsqu’Azure AD apporte cette modification. En outre, les utilisateurs peuvent désormais se connecter au portail d’entreprise à partir d’un autre appareil grâce à un code à usage unique automatiquement généré. Cette fonction se révèle particulièrement utile lorsque les utilisateurs doivent se connecter sans informations d’identification.

La page [Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune](whats-new-app-ui.md) contient des captures d’écran illustrant l’expérience de connexion précédente, la nouvelle expérience de connexion avec informations d’identification, ainsi que la nouvelle expérience de connexion depuis un autre appareil.

### <a name="light-and-dark-modes-available-for-the-company-portal-app-for-windows-10----676547---"></a>Modes clair et sombre disponibles pour l’application Portail d’entreprise pour Windows 10 <!---676547--->
Les utilisateurs finaux seront en mesure de personnaliser le mode de couleur de l’application Portail d’entreprise pour Windows 10. Ils pourront apporter la modification dans la section Paramètres de l’application Portail d’entreprise. Le changement apparaîtra une fois que les utilisateurs auront redémarré l’application. Pour Windows 10 versions 1607 et ultérieures, le mode d’application par défaut sera le paramètre système. Pour les postes de travail qui exécutent Windows 10 versions 1511 et antérieures, le mode d’application par défaut sera le mode clair.

### <a name="enable-end-users-to-tag-their-device-group-in-the-company-portal-app-for-windows-10----807046--"></a>Permettre aux utilisateurs finaux de baliser leur groupe d’appareils dans l’application Portail d’entreprise pour Windows 10 <!---807046-->    
Les utilisateurs finaux pourront sélectionner le groupe auquel leur appareil appartient en le balisant directement à partir de l’application Portail d’entreprise pour Windows 10.

### <a name="allow-end-users-to-access-the-company-portal-app-for-android-without-enrollment----1169910---"></a>Autoriser les utilisateurs finaux à accéder à l’application Portail d’entreprise pour Android sans inscription <!---1169910--->  
Les utilisateurs finaux n’auront bientôt pas à inscrire leur appareil pour accéder à l’application Portail d’entreprise pour Android. Les utilisateurs finaux des organisations qui utilisent des stratégies de protection des applications ne recevront plus d’invites pour inscrire leur appareil quand ils ouvriront l’application Portail d’entreprise. Les utilisateurs finaux pourront également installer des applications à partir du portail d’entreprise sans inscrire l’appareil. 

### <a name="users-who-are-signed-in-to-exchange-can-automatically-access-the-company-portal-website-on-windows-10-devices---1323204--"></a>Les utilisateurs qui sont connectés à Exchange peuvent automatiquement accéder au site web du portail d’entreprise sur les appareils Windows 10 <!--1323204-->  
Les utilisateurs Windows 10 qui sont déjà authentifiés dans Exchange, reçoivent l’e-mail mis en quarantaine d’accès conditionnel et cliquent sur le lien dans l’e-mail ne devront plus se réauthentifier dans le navigateur avant de commencer la configuration de l’accès à l’entreprise.


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
