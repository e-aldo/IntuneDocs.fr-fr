---
title: "Édition préliminaire"
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d612f0e3ff3f38d51488818916479e8291c9e453
ms.sourcegitcommit: 0f877251e6adf4e45b918cc8dc9193626727f2d9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/03/2017
---
# <a name="the-early-edition-for-microsoft-intune---november-2017"></a>Édition préliminaire pour Microsoft Intune - Novembre 2017

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

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Les administrateurs peuvent désormais configurer les paramètres du Pare-feu d’un appareil avec un profil de configuration d’appareil <!-- 951708 -->   
Les administrateurs peuvent activer le Pare-feu sur les appareils et configurer divers protocoles pour les réseaux privés, publics et de domaine.  Ces paramètres de pare-feu se trouvent dans le profil « Endpoint protection ».

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard permet de protéger les appareils des sites web non approuvés, comme défini par votre organisation <!-- 958257 -->   
Les administrateurs peuvent définir les sites comme « approuvés » ou « appartenant à l’entreprise » à l’aide d’un flux de travail Protection des informations Windows ou du nouveau profil « Limite réseau » dans les configurations de l’appareil. Tous les sites qui ne sont pas listés dans la limite réseau approuvée d’un appareil Windows 10 64 bits, s’ils sont consultés dans Microsoft Edge, s’ouvrent à la place dans un navigateur d’une machine virtuelle Hyper-V.

Application Guard se trouve dans les profils de configuration de l’appareil, dans le profil « Endpoint protection ». À partir de là, les administrateurs peuvent configurer une interaction entre le navigateur virtualisé et la machine hôte, les sites non approuvés et les sites approuvés, puis stocker les données générées dans le navigateur virtualisé. Pour utiliser Application Guard sur un appareil, une limite réseau doit d’abord être configurée. Il est important de définir une seule limite réseau pour un appareil.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Guard sur Windows 10 Entreprise offre un mode permettant d’approuver uniquement les applications autorisées <!-- 1031096 -->    
Avec des milliers de nouveaux fichiers malveillants créés chaque jour, l’utilisation d’une détection antivirus basée sur les signatures pour lutter contre les programmes malveillants ne constitue probablement plus une défense suffisante contre les nouvelles attaques. En utilisant Windows Defender Application Guard sur Windows 10 Entreprise, vous pouvez changer la configuration de l’appareil et passer d’un mode où les applications sont approuvées sauf si elles sont bloquées par un antivirus ou une autre solution de sécurité à un mode où le système d’exploitation approuve uniquement les applications autorisées par votre entreprise. Vous approuvez les applications dans Windows Defender Application Guard.

Avec Intune, vous pouvez configurer des stratégies de contrôle d’application en mode « audit uniquement » ou en mode d’application. Les applications ne sont pas bloquées quand vous exécutez le mode « audit uniquement ». Le mode « Audit uniquement » enregistre tous les événements dans les journaux du client local. Vous pouvez également choisir une configuration où seuls les composants Windows et les applications du Windows Store sont autorisés à s’exécuter ou, où d’autres applications avec une bonne réputation telle que définie par l’Intelligent Security Graph sont autorisées à s’exécuter.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nouvelle page d’état pour les inscriptions Windows 10<!--1063201-->    
Vous pouvez désormais configurer un message d’accueil qui apparaît quand vos utilisateurs inscrivent des appareils Windows 10. Utilisez l’**écran d’état des inscriptions** pour configurer un message personnalisé et un lien hypertexte à l’attention de vos utilisateurs finaux quand ceux-ci inscrivent leurs appareils Windows 10.  L’**écran d’état des inscriptions** donne aussi aux utilisateurs finaux une vue de la progression des paramètres de stratégie qui sont actuellement appliqués à leur appareil.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard est un nouvel ensemble de fonctionnalités de prévention d’intrusion pour Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard propose des règles personnalisées permettant de réduire l’exploitabilité des applications, empêche les menaces provenant de macros et de scripts, bloque automatiquement les connexions réseau à des adresses IP de mauvaise réputation et peut sécuriser les données contre des ransomware et des menaces inconnues. Windows Defender Exploit Guard présente les composants suivants :

- **Réduction de la surface d’attaque (ASR)** fournit des règles vous permettant d’empêcher les menaces de macro, de script et d’e-mail.
- **Accès contrôlé au dossier** bloque automatiquement l’accès au contenu des dossiers protégés.
- **Filtre de réseau** bloque la connexion sortante de toutes les applications à une adresse IP/domaine de faible réputation
- **Exploit Protection** fournit la mémoire, le flux de contrôle et les restrictions de stratégie pouvant être utilisés pour protéger les applications contre des attaques.

### <a name="app-conditional-launch-support----1193313---"></a>Prise en charge du lancement conditionnel d’applications<!-- 1193313 -->
Les administrateurs informatiques peuvent désormais définir une condition dans le portail d’administration Azure permettant d’appliquer un code secret à la place d’un code PIN numérique via la gestion des applications mobiles (MAM) lors du lancement de l’application. Selon la configuration, l’utilisateur doit définir et utiliser un code secret quand il y est invité avant d’obtenir l’accès à des applications compatibles MAM. Un code secret est défini comme un code PIN numérique avec au moins un caractère spécial ou une lettre majuscule/minuscule. Cette version d’Intune propose cette fonctionnalité **sur iOS uniquement**. Intune prend en charge un code secret comme un code PIN numérique, il définit une longueur minimale et autorise la répétition des caractères et des séquences. Cette fonctionnalité nécessite la participation des applications (ex : WXP, Outlook, Managed Browser, Yammer) pour intégrer le kit Intune APP SDK avec le code de cette fonctionnalité en place dans le but d’appliquer les paramètres du code secret dans les applications ciblées.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numéro de version des applications métier dans le rapport d’état d’installation de l’appareil <!-- 1233999 -->  
Le rapport d’état d’installation de l’appareil affiche le numéro de version des applications métier pour iOS et Android. Vous pouvez utiliser cette information pour dépanner vos applications ou trouver les appareils qui exécutent des versions d’application anciennes.

### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogestion pour les appareils Windows 10 <!-- 1243445 -->
La cogestion est une solution qui propose une passerelle entre la gestion classique et la gestion moderne tout en vous donnant la possibilité d’opérer cette transition selon une approche en plusieurs phases. À la base, la cogestion est une solution qui permet aux appareils Windows 10 d’être gérés simultanément par Configuration Manager et Microsoft Intune, et d’être joints à Active Directory (AD) et à Azure Active Directory (Azure AD).  Cette configuration vous offre un moyen de vous moderniser à un rythme qui convient à votre organisation si vous ne pouvez pas le faire d’un coup.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Définir l’accès pour les applications avec un correctif de sécurité Android minimal sur l’appareil<!-- 1278463 -->   
Un administrateur peut définir le correctif de sécurité Android minimal qui doit être installé sur l’appareil afin d’obtenir l’accès à une application gérée sous un compte géré.

> [!Note]  
> Cette fonctionnalité restreint uniquement les correctifs de sécurité publiés par Google sur les appareils Android 6.0 +.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nouveaux paramètres de restriction d’appareil pour Windows 10      <!-- 1308850 -->
-    Messagerie (mobile uniquement) - désactivation des tests ou des messages MMS
-    Mot de passe - paramètres pour activer FIPS et l’utilisation d’appareils secondaires Windows Hello pour l’authentification 
-    Affichage - paramètres pour activer ou désactiver la mise à l’échelle GDI pour les applications héritées


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Restrictions des appareils en mode plein écran Windows 10<!-- 1308872 -->   
Vous pouvez restreindre les utilisateurs d’appareils Windows 10 au mode plein écran, ce qui limite les utilisateurs à un ensemble d’applications prédéfinies.  Pour ce faire, créez un profil de restriction d’appareil Windows 10 et définissez les paramètres de plein écran.

Le mode plein écran prend en charge deux modes : **application unique** (permet à l’utilisateur d’exécuter une seule application) ou **applications multiples** (permet l’accès à un ensemble d’applications).  Vous définissez le compte d’utilisateur et le nom de l’appareil, ce qui détermine les applications prises en charge.  Lorsque l’utilisateur est connecté, il est limité aux applications définies.  Pour en savoir plus, consultez [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Conditions requises du mode plein écran :

- Intune doit être l’autorité MDM.
- Les applications doivent déjà être installées sur l’appareil cible.
- L’appareil doit être [correctement provisionné](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nouveau profil de configuration d’appareil pour la création de limites réseau<!-- 1311967 -->   
Nous avons créé un profil de configuration d’appareil appelé **Limite réseau** que vous trouverez avec vos autres profils de configuration d’appareil. Utilisez ce profil pour définir des ressources en ligne à considérer comme approuvées et appartenant à l’entreprise. Vous devez définir une limite réseau pour un appareil *avant* de pouvoir utiliser les fonctionnalités comme Windows Defender Application Guard et Protection des informations Windows sur l’appareil. Il est important de définir une seule limite réseau pour chaque appareil.

Vous pouvez définir des ressources cloud d’entreprise, des plages d’adresses IP et des serveurs proxy internes à considérer comme approuvées. Une fois définie, la limite réseau peut être utilisée par d’autres fonctionnalités comme Windows Defender Application Guard et Protection des informations Windows.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Deux paramètres supplémentaires pour Windows Defender Antivirus<!-- 1338409 -->  
**Niveau de blocage des fichiers**

| | |
|---|---|
| non configuré | **Non configuré** utilise le niveau de blocage de Windows Defender Antivirus par défaut et offre une détection solide sans augmenter le risque de détection des fichiers légitimes. |
| Importante | **Haut** s’applique à un niveau fort de détection.
| Élevé +  | **Haut +** fournit le niveau Haut avec des mesures de protection supplémentaires pouvant impacter les performances du client.
| Tolérance zéro  | **Tolérance zéro** bloque tous les exécutables inconnus. |

Bien qu’improbable, la définition sur **Haut** risque d’entraîner la détection de certains fichiers légitimes.
Nous vous recommandons de définir le niveau de blocage des fichiers avec la valeur par défaut, **Non configuré**.

**Extension du délai d’attente pour l’analyse des fichiers par le cloud**  

| | |
|--|--|
| Nombre de secondes (0-50) | Spécifiez la durée maximale avant que Windows Defender Antivirus ne bloque un fichier lors de l’attente d’un résultat du cloud. La durée par défaut est de 10 secondes : tout temps supplémentaire spécifié ici (jusqu'à 50 secondes) est ajouté à ces 10 secondes. Dans la plupart des cas, l’analyse prend beaucoup moins de temps que la valeur maximale. Prolonger la durée permet au cloud de rechercher des fichiers suspects de manière plus approfondie. Nous vous recommandons d’activer ce paramètre et de spécifier au moins 20 secondes supplémentaires. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Prise en charge de l’Autorité de certification Symantec Cloud  <!-- 1333638 -->    
Intune prend désormais en charge l’Autorité de certification Symantec Cloud qui permet à Intune Certificate Connector d’émettre des certificats PKCS de l’Autorité de certification Symantec Cloud sur des appareils gérés par Intune. Si vous utilisez déjà Intune Certificate Connector avec l’Autorité de certification Microsoft, vous pouvez optimiser la configuration existante d’Intune Certificate Connector en y ajoutant la prise en charge de l’Autorité de certification de Symantec.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>VPN Citrix ajouté pour les appareils Windows 10 <!-- 1512457 -->  
Le client sera en mesure de configurer un VPN Citrix pour ses appareils Windows 10. Vous pouvez choisir le VPN Citrix dans la liste *Sélectionner un type de connexion* du panneau **VPN de base** quand vous configurez un VPN pour Windows 10 et ultérieur.

> [!Note]
> Une configuration de Citrix existait pour iOS et Android.



<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Support de Google Play Protect sur Android <!-- 908720  -->  
Avec la publication d’Android Oreo, Google introduit une suite de fonctionnalités de sécurité appelée Google Play Protect qui permet aux utilisateurs et aux organisations d’exécuter des applications sécurisées et des images Android sécurisées. Intune prendra en charge les fonctionnalités de Google Play Protect, notamment l’attestation SafetyNet distante.  Les administrateurs peuvent définir des exigences pour la stratégie de conformité afin que Google Play Protect soit configuré et intègre. Le paramètre **Attestation d’appareil SafetyNet** nécessite que l’appareil se connecte à un service Google pour vérifier que l’appareil est intègre et qu’il n’est pas compromis. Les administrateurs peuvent également définir un paramètre de profil de configuration pour qu’Android for Work exige que les applications installées soient vérifiées par les services Google Play.  L’accès conditionnel peut empêcher les utilisateurs d’accéder aux ressources d’entreprise si un appareil n’est pas conforme aux exigences de Google Play Protect. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Prise en charge de la stratégie de mise à niveau de l’édition Windows 10   <!-- 903672(archived), 1119689 -->  
Vous pourrez créer une stratégie de mise à niveau de l’édition Windows 10 qui met à niveau les appareils Windows 10 vers Windows 10 Éducation, Windows 10 Éducation N, Windows 10 Professionnel, Windows 10 Professionnel N, Windows 10 Professionnel Éducation et Windows 10 Professionnel Éducation N. Pour plus d’informations sur les mises à niveau de l’édition Windows 10, consultez [Configuration des mises à niveau de l’édition Windows 10 ](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Actions en cas de non-conformité <!--730266  846515 -->     
*Actions en cas de non-conformité* est une nouvelle fonctionnalité de stratégies de conformité qui vous permet de prendre des mesures au niveau des appareils non conformes. Vous pouvez spécifier une ou plusieurs actions ainsi que la période à laquelle ces actions doivent se produire. Par exemple, vous pouvez avertir par e-mail les utilisateurs d'appareils non conformes immédiatement lorsque ces appareils deviennent non conformes, ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise après une période de grâce de 3 jours via l’accès conditionnel.


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




## <a name="notices"></a>Avis

Il n’existe aucun avis actif pour l’instant.




### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
