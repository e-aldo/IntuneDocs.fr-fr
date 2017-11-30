---
title: "Édition préliminaire"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4fd810529732d2b24b948eb0ae741d37e0fb59e
ms.sourcegitcommit: d64b03bff0566f08d88ecb488dd48f19af74cab3
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2017
---
# <a name="the-early-edition-for-microsoft-intune---december-2017"></a>Édition préliminaire de Microsoft Intune - Décembre 2017

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

### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Révocation des applications du Programme d’achat en volume iOS  <!-- 820863 -->
Pour un appareil donné disposant d’une ou de plusieurs applications de Programme d’achat en volume (VPP) iOS, vous pourrez révoquer la licence d’application basée sur l’appareil associé. La révocation d’une licence d’application ne désinstalle pas l’application VPP de l’appareil. Pour désinstaller une application VPP, vous devez remplacer l’action d’attribution par **Désinstaller**. Pour plus d’informations, consultez [Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Révoquer des licences pour un jeton Programme d’achat en volume iOS <!-- 820870 -->
Vous pourrez révoquer la licence de toutes les applications de Programme d’achat en volume (VPP) iOS pour un jeton VPP donné.

### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Supprimer un jeton Programme d’achat en volume iOS <!-- 820879 -->
Vous pourrez supprimer le jeton Programme d’achat en volume (VPP) iOS à l’aide de la console. Ceci peut être nécessaire si vous avez des instances dupliquées d’un jeton VPP.

### <a name="network-access-control-nac-device-check-in-reporting-----1232250---"></a>Création d’un rapport d’enregistrement d’appareil de contrôle d’accès réseau (NAC)  <!-- 1232250 -->
Avant cette modification, les administrateurs informatiques ne pouvaient pas déterminer à partir d’Intune si un appareil géré par NAC communiquait ou pas avec leur solution NAC. Lorsqu’un appareil géré par NAC ne communique pas avec leur solution NAC, l’appareil est considéré comme non conforme par la solution NAC. Il est donc bloqué par la solution NAC et bloqué par les stratégies d’accès conditionnel qui reposent sur l’état de conformité de l’appareil.

Grâce à cette modification, les administrateurs informatiques peuvent voir quels appareils gérés par NAC ont bien communiqué avec leur solution NAC. Cette nouvelle fonctionnalité est constituée de deux nouvelles fonctions de monitoring situées dans la charge de travail de conformité Appareil au sein d’Intune. Les statistiques sont illustrées ci-dessous :
- **Moyenne d’appels NAC au cours de la dernière heure**
- **Dernière requête NAC entrante (date/heure)**

### <a name="new-ios-device-action------1244701---"></a>Nouvelle action sur appareil iOS   <!-- 1244701 -->
Vous pouvez arrêter les appareils supervisés iOS 10.3. Cette action arrête immédiatement l’appareil sans avertir l’utilisateur final. L’action **Arrêter (supervisé uniquement)** se trouve dans les propriétés de l’appareil lorsque vous sélectionnez un appareil dans la charge de travail **Appareil**.

### <a name="palo-alto-vpn-now-supported----1333680-eeready---"></a>Réseau privé virtuel (VPN) Palo Alto désormais pris en charge <!-- 1333680 eeready -->
La liste **Type de connexion** inclut le réseau privé virtuel Palo Alto lorsque vous configurez votre VPN de base.

### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755-eeready---"></a>Prise en charge de connecteurs multiples pour le traitement des certificats SCEP et PFX <!-- 1361755 eeready -->
Les clients qui utilisent le connecteur NDES local pour présenter des certificats à des appareils pourront configurer plusieurs connecteurs dans un seul locataire.

Cette nouvelle fonctionnalité prend en charge le scénario suivant :

- **Haute disponibilité**

    Chaque connecteur NDES extraie des demandes de certificat d’Intune.  Si un connecteur NDES a l’état hors connexion, l’autre connecteur peut continuer à traiter les requêtes.

### <a name="new-automatic-redeployment-setting----1469168---"></a>Nouveau paramètre de redéploiement automatique <!-- 1469168 -->
Ce paramètre permet aux utilisateurs avec des droits administratifs de supprimer l’ensemble des données et des paramètres utilisateur à l’aide des touches **CTRL + Win + R** sur l’écran de verrouillage de l’appareil. L’appareil sera automatiquement reconfiguré et réinscrit en gestion.

Ce paramètre se situe sous Windows 10 -> Restrictions d’appareil -> Général -> Redéploiement automatique.

### <a name="install-office-apps-on-macos-devices----1494311---"></a>Installer des applications Office sur des appareils macOS <!-- 1494311 -->
Vous pourrez installer des applications Office sur des appareils macOS. Ce nouveau type d’application vous permettra d’installer Word, Excel, PowerPoint, Outlook et OneNote. Ces applications bénéficient également de Microsoft AutoUpdater (MAU) qui garantit que vos applications sont sécurisées et à jour.

### <a name="surface-hub-resource-account-supported----1566442-eeready---"></a>Compte de ressource Surface Hub pris en charge <!-- 1566442 eeready -->
Une nouvelle action d’appareil sera ajoutée pour permettre aux administrateurs de définir et de mettre à jour le compte de ressource associé à un Surface Hub.

Le compte de ressource est utilisé par un Surface Hub pour l’authentification avec Skype/Exchange afin de prendre part à une réunion. Vous pouvez créer un compte de ressource unique afin que le Surface Hub s’affiche dans la réunion en tant que salle de conférence. Par exemple, le compte de ressource peut s’afficher comme *Salle de conférence B41/6233*. Le compte de ressource (également appelé compte de l’appareil) pour le Surface Hub doit en général être configuré pour l’emplacement de la salle de conférence et également lorsque d’autres paramètres du compte de ressource sont modifiés.

Lorsque les administrateurs veulent mettre à jour le compte de ressource sur un appareil, ils doivent fournir les informations d’identification Active Directory/Azure Active Directory actuelles associées à l’appareil. Si la rotation de mot de passe est activée sur l’appareil, les administrateurs doivent accéder à Azure Active Directory pour trouver le mot de passe.

> [!NOTE]
> Tous les champs sont transmis sous forme de package et écrasent tous les champs précédemment configurés. Les champs vident écrasent également les champs existants.

Vous trouverez ci-dessous les paramètres que les administrateurs peuvent configurer :

- **Compte de ressource**  

   - **Utilisateur Active Directory**   
   Nomdedomaine\nomd’utilisateur ou Nom d’utilisateur principal (UPN) : user@domainname.com
   - **Mot de passe**


- **Paramètres facultatifs du compte de ressource** (à définir à l’aide du compte de ressource spécifié)
   - **Période de rotation du mot de passe**   
     Permet de s’assurer que le mot de passe du compte est automatiquement mis à jour par le Surface Hub chaque semaine à des fins de sécurité. Pour configurer des paramètres une fois cette option activée, il est nécessaire tout d’abord de réinitialiser le mot de passe du compte dans Azure Active Directory.

   - **Adresse du protocole d’initiation de session (SIP)**    
     Utilisée uniquement en cas d’échec de la découverte automatique.

   - **E-mail**    
     Adresse e-mail de l’appareil/du compte de ressource.

   - **Exchange Server**    
     Requis uniquement en cas d’échec de la découverte automatique.

   - **Synchronisation du calendrier**    
     Permet de spécifier si la synchronisation du calendrier et d’autres services Exchange Server sont activés. Par exemple : synchronisation de réunion.

### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune propose désormais l’opération Déplacer le compte  <!-- 1573558, 1579830 -->
L’opération **Déplacer le compte** migre un locataire à partir d’une échelle d’unité Azure (ASU) vers une autre. L’opération **Déplacer le compte** peut être utilisée dans les scénarios initiés par le client, lorsque vous faites la demande de cette opération auprès de l’équipe de support d’Intune, et elle peut être utilisée dans un scénario géré par Microsoft lorsque Microsoft doit apporter des réglages au service dans le serveur principal. Au cours de l’opération **Déplacer le compte**, les locataires sont en mode lecture seule. Durant la période où les locataires sont en lecture seule, les opérations de service comme l’inscription, le changement de nom des appareils, la mise à jour de l’état de conformité, échoueront.

### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nouveaux paramètres pour le profil de configuration d’appareil Windows Defender Security Center (WDSC) <!-- 1335507 -->
Intune ajoute une nouvelle section de paramètres pour le profil de configuration d’appareil, sous la Protection du point de terminaison, nommée **Windows Defender Security Center**. Les administrateurs informatiques peuvent configurer les éléments de base auxquels les utilisateurs finaux de l’application Windows Defender Security Center peuvent accéder. Si un administrateur informatique masque un élément de base dans l’application Windows Defender Security Center, les notifications liées à l’élément de base masqué ne s’affichent pas sur l’appareil de l’utilisateur.

Vous trouverez ci-dessous les éléments de base que les administrateurs peuvent masquer dans les paramètres du profil de configuration d’appareil Windows Defender Security Center :
- Protection contre les menaces et les virus
- Performances et intégrité de l’appareil
- Protections du pare-feu et du réseau
- Contrôle d’application et du navigateur
- Options Famille

Les administrateurs informatiques peuvent également personnaliser les notifications que les utilisateurs reçoivent. Par exemple, vous pouvez décider si les utilisateurs reçoivent toutes les notifications générées par les éléments de base visibles dans WDSC ou uniquement les notifications critiques. Les notifications non critiques incluent des résumés périodiques sur l’activité de l’antivirus Windows Defender et des notifications indiquant lorsque des analyses sont terminées. Toutes les autres notifications sont considérées comme critiques. En outre, vous pouvez aussi personnaliser le contenu même de la notification. Par exemple, vous pouvez fournir les coordonnées du service informatique à inclure dans les notifications qui s’affichent sur les appareils des utilisateurs.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Affecter des applications mobiles Office 365 aux appareils iOS et Android à l’aide du type d’application intégré <!-- 1332318 -->
Le type d’application **Intégré** facilitera la création d’applications Office 365 et leur affectation aux appareils iOS et Android gérés. Ces applications incluent les applications Office 365 telles que Word, Excel, PowerPoint et OneDrive. Vous pouvez affecter des applications spécifiques au type d’application et modifier la configuration des informations des applications.

### <a name="single-sign-on-support-for-ios----1333645---"></a>Prise en charge de l’authentification unique pour iOS <!-- 1333645 -->  
Vous pourrez utiliser l’authentification unique pour les utilisateurs iOS. Les applications iOS qui sont codées pour rechercher les informations d’identification de l’utilisateur dans la charge utile d’authentification unique fonctionnent avec cette mise à jour de la configuration de la charge utile. Vous pouvez également utiliser un UPN et un ID d’appareil Intune pour configurer le nom du principal et le domaine.

### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API d’inventaire des applications iOS 11 pour la détection des menaces mobiles <!-- 1391759 -->
Intune collecte les informations d’inventaire des applications à partir des appareils personnels et d’entreprise et les rend disponibles pour les fournisseurs de détection des menaces mobiles, comme Lookout for Work. Vous pourrez collecter l’inventaire des applications auprès des utilisateurs d’appareils iOS 11+.

**Inventaire des applications**  
Les inventaires à partir des appareils personnels et d’entreprise iOS 11 sont envoyés à votre fournisseur de service de détection des menaces mobiles. Les données de l’inventaire des applications comprennent les informations suivantes :

 - ID de l’application
 - Version de l’application
 - Version abrégée de l’application
 - Nom de l’application
 - Taille du bundle d’applications
 - Taille dynamique de l’application
 - Application validée ou non
 - Application gérée ou non

### <a name="audit-updates----1412961---"></a>Auditer les mises à jour <!-- 1412961 -->  
La fonctionnalité d’audit d’Intune enregistre les opérations de modification relatives à Intune.  Tous les opérations de création, de mise à jour, de suppression et de tâche à distance sont capturées et conservées pendant un an.  Le portail Azure fournit une vue filtrable des 30 derniers jours de données d’audit dans chaque charge de travail.  Une API Graph correspondante permet de récupérer les données d’audit stockées pendant l’année écoulée. 

La fonctionnalité d’audit se trouve sous le groupe **SURVEILLER**. Il existe un élément de menu **Journaux d’audit** par charge de travail.   

### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocole de texte autorisé à partir des applications gérées <!-- 1414050  -->
Les applications gérées par le SDK d’application Intune pourront envoyer des messages SMS.

### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Redémarrer à distance un appareil iOS (supervisé uniquement) <!-- 1424595 -->
Vous pourrez déclencher le redémarrage d’un appareil iOS 10.3+ supervisé au moyen d’une action d’appareil. Pour plus d’informations sur l’utilisation de l’action de redémarrage d’appareil, consultez [Redémarrer à distance des appareils avec Intune](device-restart.md).

> [!Note]  
> Cette commande nécessite un appareil supervisé et le droit d’accès **Verrouillage de l’appareil**. L’appareil redémarre immédiatement. Après le redémarrage, les appareils iOS verrouillés par un code secret ne rejoignent pas un réseau Wi-Fi et peuvent se trouver dans l’impossibilité de communiquer avec le serveur.

### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Verrouiller à distance un appareil macOS géré avec Intune <!-- 1437691 -->
Vous pourrez verrouiller un appareil macOS perdu et définir un code PIN de récupération à 6 chiffres. Une fois le verrouillage effectué, le panneau **Vue d’ensemble des appareils** affiche le code PIN jusqu’à ce qu’une autre action d’appareil soit envoyée.

Pour plus d’informations, consultez [Verrouiller à distance des appareils gérés avec Intune](device-remote-lock.md).

### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings------1455974-----"></a>Paramètres de la fréquence d’émission des rapports Windows Defender ATP <!--- 1455974  --->
Le service Windows Defender ATP permet aux administrateurs de gérer la fréquence d’émission des rapports sur les appareils gérés. Avec la nouvelle option **Augmenter la fréquence des rapports de télémétrie**, Windows Defender ATP collecte les données et évalue les risques plus fréquemment. Par défaut, l’émission de rapports optimise le niveau de performance et la vitesse. Augmenter la fréquence d’émission des rapports peut être utile pour les appareils à haut risque. Ce paramètre se trouve dans le profil **Windows Defender ATP** dans **Configurations d’appareil**.

### <a name="assignment-conflict-resolution-has-changed-for-ios-store-apps----1480316---"></a>La résolution des conflits d’affectation a changé pour les applications de l’App Store iOS <!-- 1480316 -->
Les utilisateurs finaux pourront constater une évolution de la disponibilité des applications de l’App Store iOS. Actuellement, une application qui a été attribuée à deux groupes et présentant un conflit entre **Obligatoire et disponible** et **Non applicable** se résout en **Obligatoire et disponible**. Avec ce changement, une application qui rencontre ce conflit se résout en **Non applicable**.

Ce changement met fin à la confusion liée à l’attribution d’une application à plusieurs groupes avec des intentions d’application différentes.

Si vous souhaitez que votre application soit disponible dans le portail des travailleurs de l’information et dans le portail d’entreprise avant la publication de service de novembre, vous avez deux options :

1. Supprimer l’affectation **Non applicable** pour votre groupe.
2. Créer un groupe qui n’inclut pas de membres auxquels est affectée l’intention **Obligatoire et disponible** et assigner ce groupe en tant que **Non applicable**.

Pour plus d’informations, consultez [Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune](apps-deploy.md).

> [!Note]
> Après la publication, vous ne pouvez plus afficher ou modifier les affectations d’applications MDM avec la console Intune classique. Toutefois, vous pouvez utiliser la console Azure ou l’API Graph Intune pour effectuer vos affectations d’applications.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731---"></a>Gérer les appareils Android for Work indépendamment des appareils Android <!-- 1490731 -->
Intune prendra en charge la gestion de l’inscription des appareils Android for Work indépendamment de la plateforme Android. Ces paramètres sont gérés sous **Inscription de l’appareil** > **Restrictions d’inscription** > **Restrictions de type d’appareil**. (Ils se trouvaient sous **Inscription de l’appareil** > **Inscription Android for Work** > **Paramètres d’inscription d’Android for Work**.)

Par défaut, les paramètres de vos appareils Android for Work seront identiques aux paramètres de vos appareils Android. Toutefois, ce ne sera plus le cas une fois que vous aurez modifié vos paramètres Android for Work.
 
Si vous bloquez l’inscription Android for Work personnelle, seuls les appareils Android d’entreprise peuvent s’inscrire en tant qu’Android for Work.

Quand vous utilisez les nouveaux paramètres, tenez compte des éléments suivants :

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Si vous n’avez jamais intégré l’inscription Android for Work
La nouvelle plateforme Android for Work est bloquée dans les restrictions de type d’appareil par défaut. Une fois la fonctionnalité intégrée, vous pouvez autoriser les appareils à s’inscrire auprès d’Android for Work. Pour ce faire, changez le paramétrage par défaut ou créez une restriction de type d’appareil afin de remplacer la restriction de type d’appareil par défaut.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Si vous avez intégré l’inscription Android for Work
Votre situation varie selon le paramètre que vous avez choisi :

| Paramètre | État Android for Work dans la restriction de type d’appareil par défaut | Remarques |
| --- | --- | --- |
| **Gérer tous les appareils comme Android** | Bloqué | Tous les appareils Android doivent s’inscrire sans Android for Work. |
| **Gérer les appareils pris en charge comme Android for Work** | Autorisé | Tous les appareils Android qui prennent en charge Android for Work doivent s’inscrire auprès d’Android for Work. |
| **Gérer les appareils pris en charge pour les utilisateurs uniquement dans ces groupes comme Android for Work** | Bloqué | Une stratégie de restriction de type d’appareil distincte a été créée pour remplacer le paramétrage par défaut. Cette stratégie définit les groupes que vous avez choisis pour autoriser l’inscription Android for Work. Les utilisateurs dans les groupes sélectionnés continueront à être autorisés à inscrire leurs appareils Android for Work. Tous les autres utilisateurs ne peuvent pas s’inscrire auprès Android for Work. |

Dans tous les cas, les règles que vous avez envisagées sont conservées. Aucune action n’est requise de votre part pour gérer l’autorisation globale ou par groupe d’Android for Work dans votre environnement.

Ces modifications commenceront à s’appliquer avec la mise à jour de novembre, mais leur exécution sur votre compte pourrait prendre du temps. Vous recevrez une notification de confirmation dans le portail Office 365 quand ces modifications seront effectives pour votre compte.

### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Prise en charge de plusieurs connecteurs NDES (Service d’inscription de périphérique réseau)<!-- 1528104 -->
NDES permet aux appareils mobiles s’exécutant sans informations d’identification de domaine d’obtenir des certificats basés sur le protocole d’inscription de certificats simple (SCEP). Avec cette mise à jour, plusieurs connecteurs NDES seront pris en charge.

### <a name="new-scep-profile-details-supported----1559808---"></a>Nouveaux détails de profil SCEP pris en charge <!-- 1559808 -->
Les administrateurs pourront définir des paramètres supplémentaires durant la création d’un profil SCEP sur les plateformes Windows, iOS, Mac OS et Android.  Les administrateurs peuvent définir un IMEI, un numéro de série ou un nom commun (adresse e-mail incluse) dans le format du nom de l’objet.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurer un code PIN d’application iOS <!-- 1586774 -->
Vous pourrez bientôt exiger un code PIN pour des applications iOS ciblées. Vous pouvez configurer l’exigence du code PIN et sa date d’expiration en jours par le biais du portail Azure. Le cas échéant, l’utilisateur devra définir et utiliser un nouveau code PIN avant d’accéder à une application iOS. Seules les applications iOS pour lesquelles la protection d’application est activée avec le SDK d’application Intune prendront en charge cette fonctionnalité.

### <a name="retain-data-during-a-factory-reset-----1588489---"></a>Conserver les données pendant une réinitialisation des paramètres d’usine <!-- 1588489 -->
Nous avons ajouté la prise en charge d’une nouvelle fonctionnalité pour la réinitialisation des paramètres d’usine Windows. À présent, les administrateurs peuvent spécifier si les données d’inscription des appareils et autres données provisionnées sont conservées sur un appareil pendant une réinitialisation des paramètres d’usine. 
 
Les données suivantes sont conservées pendant une réinitialisation des paramètres d’usine :
- Comptes d’utilisateur associés à l’appareil
- État de la machine (jonction de domaine, AADJ)
- Inscription MDM
- Applications OEM installées (applications Win32 et du Store)
- Profil utilisateur
- Données utilisateur hors du profil utilisateur
- Ouverture de session automatique de l’utilisateur
 
Les données suivantes ne sont pas conservées :
- Fichiers utilisateur
- Applications utilisateur installées (applications Win32 et du Store)
- Paramètres d’appareil autres que les paramètres par défaut 

### <a name="app-install-status-report-now-a-bar-chart----1249446---"></a>Rapport d’état de l’installation de l’application désormais présenté sous la forme d’un graphique à barres <!-- 1249446 -->  
Le rapport **État de l’installation de l’application** accessible pour chaque application par le biais de la liste **Application** dans la charge de travail **Applications mobiles** sera bientôt rendu sous la forme d’un graphique à barres.

### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Ajouter « Rechercher mon iPhone » pour les appareils personnels <!--1427287-->
Vous pourrez savoir si la fonctionnalité Verrou d’activation est activée pour les appareils iOS. Cette fonctionnalité se trouvait avant dans le portail classique.

### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrictions d’inscription assignées aux groupes <!-- 747598 -->
En tant qu’administrateur Intune, vous pourrez créer des restrictions d’inscription Type d’appareil et Limite d’appareils personnalisées pour les groupes d’utilisateurs.
 
Le portail Azure Intune vous permet de créer jusqu’à 25 instances de chaque type de restriction qui peuvent ensuite être assignées aux groupes d’utilisateurs. Les restrictions assignées aux groupes remplacent les restrictions par défaut.
 
Toutes les instances d’un type de restriction sont conservées dans une liste classée de manière stricte. Cet ordre définit une valeur de priorité pour la résolution des conflits. Un utilisateur impacté par plusieurs instances de restriction est uniquement limité par l’instance ayant la valeur de priorité la plus élevée. Vous pouvez modifier la priorité d’une instance donnée en la faisant glisser vers un autre emplacement de la liste. 
 
Cette fonctionnalité sera disponible quand les paramètres Android for Work seront migrés depuis le menu Inscription Android for Work vers le menu Restrictions d’inscription. Cette migration pouvant prendre plusieurs jours, votre compte peut être mis à niveau pour d’autres parties de la version de novembre avant que l’affectation aux groupes ne soit activée pour les restrictions d’inscription.

### <a name="windows-10-update-ring-assignments-are-displayed----1621837---"></a>Les affectations d’anneaux de mise à jour de Windows 10 sont affichées <!-- 1621837 -->
Pendant une **résolution de problèmes**, vous pourrez voir les affectations d’anneaux de mise à jour de Windows 10 pour l’utilisateur affiché.  



<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Les sites web Azure Active Directory peuvent nécessiter l’application Intune Managed Browser et la prise en charge de l’authentification unique pour Managed Browser (Préversion publique) <!-- 710595 -->   
Avec Azure Active Directory (Azure AD), vous pouvez restreindre l’accès aux sites web sur des appareils mobiles à l’application Intune Managed Browser. Dans Managed Browser, les données de site web restent sécurisées et séparées des données personnelles de l’utilisateur final. Par ailleurs, Managed Browser prend en charge les fonctionnalités d’authentification unique pour les sites protégés par Azure AD. Si vous vous connectez à Managed Browser ou que vous utilisez Managed Browser sur un appareil avec une autre application gérée par Intune, Managed Browser peut accéder aux sites d’entreprise protégés par Azure AD sans que l’utilisateur ne doive entrer ses informations d’identification. Cette fonctionnalité s’applique aux sites comme Outlook Web Access (OWA) et SharePoint Online, ainsi qu’à d’autres sites d’entreprise tels que les ressources intranet accessibles par le proxy de l’application Azure.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Résoudre les problèmes d’inscription  <!--- 746324 --->  
L’espace de travail Résolution des problèmes montre les problèmes d’inscription des utilisateurs. Des détails sur les problèmes et des suggestions de correction peuvent aider les administrateurs et les agents du support technique à résoudre les problèmes. Certains problèmes d’inscription ne sont pas capturés et certaines erreurs peuvent ne pas avoir de suggestions de correction.


















<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Prise en charge de la stratégie de mise à niveau de l’édition Windows 10   <!-- 903672(archived), 1119689 -->  
Vous pourrez créer une stratégie de mise à niveau de l’édition Windows 10 qui met à niveau les appareils Windows 10 vers Windows 10 Éducation, Windows 10 Éducation N, Windows 10 Professionnel, Windows 10 Professionnel N, Windows 10 Professionnel Éducation et Windows 10 Professionnel Éducation N. Pour plus d’informations sur les mises à niveau de l’édition Windows 10, consultez [Configuration des mises à niveau de l’édition Windows 10 ](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->



### <a name="android-for-work-support-for-lookout----1087312---"></a>Prise en charge d’Android for Work pour Lookout <!-- 1087312 -->   
Le connecteur Intune avec Lookout prendra en charge les appareils Android for Work lors de l’utilisation de l’application Lookout for Work. Vous êtes en mesure de déployer l’application Lookout à l’intérieur ou en dehors du conteneur.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Outils de développement Intune App Protection et Citrix MDX<!-- 709185 -->
Vous pouvez gérer des appareils et des applications en combinant Citrix XenMobile MDX avec Microsoft Intune. Cela vous permet de gérer des applications à l’aide d’une stratégie de protection des applications Intune tout en utilisant la technologie mVPN de Citrix.

Vous êtes en mesure de trouver un dépôt de code, contenant l’outil Intune App Wrapping Tool et le kit SDK d’applications Intune pour iOS et Android, qui s’intègre à la technologie mVPN de Citrix MDX.


### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Prise en charge d’un haut niveau de disponibilité pour le connecteur Exchange local <!-- 676614 -->   
Vous pouvez avoir plusieurs rôles serveur d’accès au client pour le connecteur Exchange local. Par exemple, si le principal serveur d’accès au client échoue, le connecteur Exchange reçoit une requête pour revenir à d’autres serveurs. Cette fonctionnalité garantit que le service n’est pas interrompu.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Pack d’administration de System Center Operations Manager pour le connecteur Exchange <!-- 885457 -->   
Le pack d’administration de System Center Operations Manager pour le connecteur Exchange sera disponible pour vous aider à analyser les journaux du connecteur Exchange. Ce pack d’administration vous donne différents moyens de surveiller Intune lorsque vous devez résoudre des problèmes.





## <a name="intune-apps"></a>Applications Intune

### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Rendre vos utilisateurs autonomes avec l’application Portail d’entreprise pour Android <!---1573324, 1573150, 1558616, 1564878--->
L’application Portail d’entreprise pour Android donne aux utilisateurs finaux des indications pour comprendre et, dans la mesure du possible, résoudre eux-mêmes les nouveaux cas d’usage. 

- Un nouveau message s’affiche expliquant qu’une stratégie de conformité pour le chiffrement a été déployée, mais que le [fabricant de l’appareil ne chiffre pas ce dernier](/intune-user-help/your-device-appears-encrypted-but-cp-says-otherwise-android) selon les [recommandations de Google](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setStorageEncryption(android.content.ComponentName, boolean).
- Les utilisateurs finaux sont redirigés vers le portail Azure Active Directory (https://account.activedirectory.windowsazure.com/r/#/profile) pour supprimer un appareil s’ils ont atteint le nombre maximal d’appareils qu’ils sont autorisés à ajouter. 
- Les utilisateurs finaux reçoivent des instructions pour les aider à [corriger les erreurs d’activation sur les appareils Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) ou à [désactiver le mode d’économie d’énergie](/intune-user-help/power-saving-mode-android). Si aucune de ces solutions ne résout leur problème, nous indiquons comment [envoyer les journaux à Microsoft](/intune-user-help/send-logs-to-microsoft-ios). 


### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nouvelle action « Résoudre » disponible pour les appareils Android <!---1583480--->
L’application Portail d’entreprise pour Android introduit une action « Résoudre » dans la page _Mettre à jour les paramètres de l’appareil_. Cette option permettra à l’utilisateur final d’accéder directement au paramètre ayant rendu son appareil non conforme. L’application Portail d’entreprise pour Android prend en charge cette action pour les paramètres [Code secret de l’appareil](/intune-user-help/set-your-pin-or-password-android), [Chiffrement de l’appareil](/intune-user-help/encrypt-your-device-android), [Débogage USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) et [Sources inconnues](/intune-user-help/you-need-to-turn-off-unknown-sources-android). 




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirection des utilisateurs macOS vers notre nouvelle application Portail d’entreprise<!--1380728-->   
Lorsqu’un utilisateur final se connecte au site web du portail d’entreprise pour inscrire son appareil macOS, il est invité à télécharger la nouvelle application Portail d’entreprise pour macOS pour effectuer la procédure. Ce comportement se produit pour les appareils macOS avec OS X El Capitan 10.11 ou ultérieur. 


<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Les applications qui sont disponibles avec ou sans inscription peuvent désormais être installées sans invitation à l’inscription. <!-- 1334712 -->
Les applications d’entreprise qui ont été mises à disposition avec ou sans inscription dans l’application Portail d’entreprise Android peuvent être installées sans invitation à l’inscription.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Prise en charge d’Intune Managed Browser pour iOS et Android <!-- 1374196 -->
À compter d’octobre 2017, l’application Intune Managed Browser sur l’application Android prendra en charge seulement les appareils exécutant Android 4.4 et ultérieur. L’application Intune Managed Browser sur iOS prendra en charge seulement les appareils exécutant iOS 9.0 et ultérieur. Les versions antérieures d’Android et d’iOS pourront encore utiliser Managed Browser, mais elles ne pourront pas installer les nouvelles versions de l’application et n’auront peut-être pas accès à toutes les fonctionnalités. Nous vous encourageons à mettre à jour le système d’exploitation de ces appareils avec une version prise en charge.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Message d’erreur amélioré quand un utilisateur atteint le nombre maximal d’appareils autorisés à inscrire <!-- 1270370 -->
Au lieu d’un message d’erreur générique, les utilisateurs finaux reçoivent un message d’erreur convivial offrant une possibilité d’action : « Vous avez inscrit le nombre maximal d’appareils autorisés par votre administrateur informatique. Supprimez un appareil inscrit ou demandez de l’aide à votre administrateur informatique ».




## <a name="notices"></a>Remarques

Il n’existe aucun avis actif pour l’instant.




### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
