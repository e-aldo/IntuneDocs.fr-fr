---
title: Édition préliminaire
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e24414d28b8adeae7dfbedb606ca1a7d21497a3f
ms.sourcegitcommit: 698af815f6de2c4f003f6da428bbfb0680daafa0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43093195"
---
# <a name="the-early-edition-for-microsoft-intune---august-2018"></a>Édition préliminaire pour Microsoft Intune - Août 2018

> [!Note]
> Notification de l’accord de confidentialité : Les modifications suivantes sont en cours de développement pour Intune. Ces informations sont partagées selon les termes de l’accord de confidentialité, de façon très limitée. Ne publiez aucune de ces informations sur des médias sociaux ou des sites web publics comme Twitter, UserVoice, Reddit, etc. 

**L’édition préliminaire** fournit la liste des fonctionnalités, partagée selon les termes de l’accord de confidentialité, qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière limitée et sont susceptibles de changer. Ne tweetez pas, ne publiez sur UserVoice et ne partagez pas ces informations en dehors de votre entreprise. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Joignez votre contact de groupe de produits Microsoft si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune dans le portail Azure

<!-- 1808 start -->

### <a name="windows-hello-will-target-users-and-devices----1106609---"></a>Windows Hello cible les utilisateurs et appareils <!-- 1106609 -->
Quand vous créez une stratégie [Windows Hello Entreprise](windows-hello.md), elle s’applique à tous les utilisateurs au sein de l’organisation (au niveau locataire). Avec cette mise à jour, la stratégie peut également être appliquée à des utilisateurs ou des appareils spécifiques à l’aide d’une stratégie de configuration d’appareil (**Configuration de l’appareil** > **Profils** > **Créer un profil** > **Identity Protection** > **Windows Hello Entreprise**).

Dans le portail Azure d’Intune, la configuration et les paramètres Windows Hello existent à la fois dans **Inscription de l’appareil** et **Configuration de l’appareil**. **Inscription de l’appareil** cible toute l’organisation (au niveau locataire) et prend en charge Windows AutoPilot (OOBE). **Configuration de l’appareil** cible des appareils et des utilisateurs à l’aide d’une stratégie appliquée lors de l’archivage.

S'applique à :  
- Windows 10 et versions ultérieures
- Windows Holographic for Business

### <a name="control-s-mode-on-windows-10-and-later-devices---public-preview----1958649---"></a>Contrôler le mode S sur des appareils Windows 10 et ultérieur- préversion publique <!-- 1958649 -->
Vous serez en mesure de créer un profil de configuration d’appareil qui sort un appareil Windows 10 du mode S, ou d’empêcher les utilisateurs de sortir l’appareil du mode S. Cette fonctionnalité sera dans Intune > **Configuration de l’appareil** > **Profils** >  **Windows 10 et versions ultérieures** > **Mise à niveau d’édition et changement de mode**.
[Présentation de Windows 10 en mode S](https://www.microsoft.com/windows/s-mode) propose d’autres informations sur le mode S.
S’applique à : Windows 10 et ultérieur (1809 et ultérieur)

### <a name="modern-vpn-support-updates-for-ios----2459928-1819876-and-2650856---"></a>Mises à jour de la prise en charge VPN moderne pour iOS <!-- 2459928, 1819876, and 2650856 -->
Une prochaine mise à jour prendra en charge les clients VPN iOS suivants : 
- F5 Access (versions 3.0.1 et ultérieures)
- Citrix SSO
- Palo Alto Networks GlobalProtect (versions 5.0 et ultérieures). Par ailleurs, dans une prochaine mise à jour :
- Les types de connexions **F5 Access** existants seront renommés **F5 Access Legacy** (selon les mises à jour de personnalisation F5)
- Les types de connexions **Palo Alto Networks GlobalProtect** existants seront renommés **Legacy Palo Alto Networks GlobalProtect** (selon les mises à jour de personnalisation Palo Alto) 

Les profils avec ces types de connexions existants continuent de fonctionner avec le client VPN hérité. Si vous utilisez Cisco Legacy AnyConnect, F5 Access Legacy, Citrix VPN ou Legacy Palo Alto Networks GlobalProtect avec iOS, vous devez passer aux nouvelles applications. Faites-le dès que possible pour vous assurer que l’accès VPN est disponible pour les appareils iOS quand ils effectuent la mise à jour vers iOS 12.

### <a name="lock-the-company-portal-in-single-app-mode-until-user-sign-in---1067692---"></a>Verrouiller le portail d’entreprise en mode Application unique jusqu’à la connexion de l’utilisateur <!--1067692 --> 
Vous aurez la possibilité d’exécuter le portail d’entreprise en mode Application unique si vous authentifiez un utilisateur via le portail d’entreprise au lieu de l’Assistant Configuration lors de l’inscription DEP. Cette option verrouille l’appareil immédiatement après l’exécution de l’Assistant Configuration afin qu’un utilisateur soit obligé de se connecter pour accéder à l’appareil. Ce processus permet de s’assurer que l’appareil termine l’intégration et qu’il n’est pas laissé orphelin dans un état sans aucun utilisateur lié.

### <a name="scope-tags-for-policies---1081974-eeready--"></a>Balises d’étendue pour les stratégies <!--1081974 eeready-->

Vous serez en mesure de créer des balises d’étendue pour limiter l’accès aux ressources Intune. Ajoutez une balise d’étendue à une attribution de rôle, puis la balise d’étendue à un profil de configuration. Le rôle a uniquement accès aux ressources avec des profils de configuration qui ont des balises d’étendue correspondantes (ou aucune balise d’étendue).
Pour créer une balise d’étendue, choisissez **Rôles Intune** > **Étendue (balises)** > **Créer**.
Pour ajouter une balise d’étendue à une attribution de rôle, choisissez **Rôles Intune** > **Tous les rôles** > **Gestionnaire de stratégies et de profils** > **Attributions** > **Étendue (balises)**.
Pour ajouter une balise d’étendue à un profil de configuration, choisissez **Configuration de l’appareil** > **Profils** > choisissez un profil > **Propriétés** > **Étendue (balises)**.

### <a name="assign-a-user-and-friendly-name-to-an-autopilot-device---1346521---"></a>Affecter un utilisateur et un nom convivial à un appareil Autopilot <!--1346521 -->
Une prochaine préversion publique permettra aux administrateurs d’affecter un utilisateur à un seul appareil Autopilot.  Les administrateurs pourront également donner des noms conviviaux pour accueillir l’utilisateur lors de la configuration de leur appareil avec Autopilot.

S’applique à : Windows Insider 1809 ou ultérieur (dans la préversion).

### <a name="apple-vpp-token-used-by-another-mdm----1488946---"></a>Jeton VPP Apple utilisé par une autre gestion MDM <!-- 1488946 -->
Intune détectera et affichera des détails si un jeton du Programme d’achat en volume (VPP) Apple est utilisé à la fois par Intune et une autre gestion MDM.

### <a name="packet-tunnel-support-for-ios-per-app-vpn-profiles-for-custom-and-pulse-secure-connection-types----1520957---"></a>Prise en charge du tunnel de paquets pour les profils VPN par application iOS pour les types de connexions personnalisés et Pulse Secure <!-- 1520957 -->
Lors de l’utilisation de profils VPN par application iOS, vous serez en mesure d’employer le tunneling de couche application (proxy d’application) ou de niveau paquet (tunnel de paquets). Ces options seront disponibles avec les types de connexions suivants :
- VPN personnalisé
- Pulse Secure. Si vous ne savez pas quelle valeur utiliser, consultez la documentation de votre fournisseur VPN.
S’applique à : iOS

### <a name="zscaler-is-an-available-connection-for-vpn-profiles-on-ios----1769858-eeready---"></a>Zscaler est une connexion disponible pour les profils VPN sur iOS <!-- 1769858 eeready -->
Quand vous créez un profil de configuration d’appareil VPN iOS (**Configuration de l’appareil** > **Profils** > **Créer un profil** >  plateforme **iOS** > type de profil **VPN**), il existe plusieurs types de connexions, notamment Cisco, Citrix et bien plus encore. Une prochaine mise à jour ajoutera Zscaler comme type de connexion. 
[Paramètres VPN pour les appareils exécutant iOS](vpn-settings-ios.md) liste les types de connexions disponibles.

### <a name="block-windows-personal-device-enrollments----1849498---"></a>Bloquer les inscriptions d’appareils personnels Windows <!-- 1849498 -->
Vous serez en mesure de bloquer l’inscription des appareils personnels Windows avec la [gestion des appareils mobiles](windows-enroll.md) dans Intune. Les appareils inscrits avec [l’agent de PC Intune](manage-windows-pcs-with-microsoft-intune.md) ne peuvent pas être bloqués avec cette fonctionnalité.
Pour voir cette fonctionnalité, choisissez **Inscription de l’appareil** > **Restrictions sur l’appareil**.
L’activation de cette restriction n’a aucun effet sur les appareils déjà inscrits.
Une fois qu’une restriction est activée, Intune vérifie que chaque nouvelle demande d’inscription Windows a été autorisée comme inscription d’entreprise. Les méthodes suivantes sont qualifiées comme étant autorisées en tant qu’inscription d’entreprise :
- L’utilisateur qui s’inscrit utilise un [compte de gestionnaire d’inscription d’appareil]( device-enrollment-manager-enroll.md).
- L’appareil s’inscrit via [Windows Autopilot](enrollment-autopilot.md).
- Le numéro IMEI de l’appareil est listé dans **Inscription de l’appareil** > **[Identificateurs d’appareil d’entreprise]( corporate-identifiers-add.md)**).
- L’appareil s’inscrit via un [package de provisionnement en bloc](windows-bulk-enroll.md).
- L’appareil s’inscrit via [l’inscription automatique à partir de SCCM pour la cogestion](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management).

Les inscriptions non autorisées seront bloquées. Les inscriptions suivantes sont marquées comme étant d’entreprise par Intune mais, dans la mesure où elles n’offrent pas le contrôle par appareil d’administrateur Intune, elles seront bloquées :
- [Inscription automatique à MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) avec [jonction Azure Active Directory lors de la configuration de Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).
- [Inscription automatique à MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) avec [jonction Azure Active Directory à partir du programme d’installation de Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx.md).

Les méthodes d’inscription personnelle suivantes seront également bloquées :
- [Inscription automatique à MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) avec [Ajouter un compte professionnel à partir de Paramètres Windows](https://docs.microsoft.com/azure/active-directory/user-help/device-management-azuread-registered-devices-windows10-setup).
- Option [Inscription à MDM uniquement]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) à partir de Paramètres Windows.

### <a name="specify-machine-name-patterns-in-an-autopilot-profile---1849855--"></a>Spécifier des modèles de nom d’ordinateur dans un profil Autopilot <!--1849855-->
Vous serez en mesure de spécifier un modèle de nom d’ordinateur pour générer et définir le [nom de l’ordinateur](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) lors de l’inscription Autopilot. Vous aurez besoin de le spécifier dans le profil Autopilot situé dans **Inscription de l’appareil** > **Inscription Windows** > **Service Windows Autopilot Deployment** > **Profils**. Seuls les caractères alphanumériques et les traits d’union peuvent être utilisés.
S’applique à : Windows Insider 1809 ou ultérieur (dans la préversion).

### <a name="ios-version-number-and-build-number-are-shown----1892471---"></a>Le numéro de version et le numéro de build d’iOS sont affichés <!-- 1892471 -->
Dans **Conformité de l’appareil** > **Conformité de l’appareil**, la version du système d’exploitation iOS s’affiche. Dans une prochaine mise à jour, le numéro de build sera également affiché.
Quand des mises à jour de sécurité sont publiées, Apple laisse généralement le numéro de version tel quel, mais met à jour le numéro de build. En affichant le numéro de build, vous pouvez vérifier facilement si une mise à jour des vulnérabilités est installée.

### <a name="for-windows-autopilot-profiles-hide-the-change-account-options-on-the-company-sign-in-page-and-domain-error-page---1901669---"></a>Pour les profils Windows Autopilot, masquer les options de changement de compte dans la page de connexion de l’entreprise et la page d’erreur de domaine <!--1901669 -->
Une préversion publique contiendra de nouvelles options de profil Windows Autopilot pour que les administrateurs puissent masquer les options de changement de compte dans la page de connexion de l’entreprise et la page d’erreur de domaine. Pour masquer ces options, il est nécessaire de configurer la marque de société dans Azure Active Directory. S’applique à : Windows Insider 1809 ou version ultérieure (dans la préversion).

### <a name="delay-when-ios-software-updates-are-shown-on-the-device----1949583---"></a>Différer le moment où les mises à jour logicielles iOS sont affichées sur l’appareil <!-- 1949583 -->
Dans Intune > **Mises à jour logicielles** > **Mettre à jour les stratégies pour iOS**, vous pouvez configurer les jours et heures où vous ne souhaitez pas que les appareils installent des mises à jour. Dans une prochaine mise à jour, vous serez en mesure de différer le moment où une mise à jour logicielle est visiblement indiquée sur l’appareil, entre 1 et 90 jours. 
[Configurer des stratégies de mise à jour iOS dans Microsoft Intune](software-updates-ios.md) liste les paramètres actuels.

### <a name="retired-devices-in-the-device-compliance-dashboard----1981119---"></a>Appareils mis hors service dans le tableau de bord de conformité des appareils <!-- 1981119 -->
Dans une prochaine mise à jour, les appareils mis hors service seront retirés du tableau de bord de conformité des appareils. Cela changera vos numéros de conformité.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nouvelle mise à jour de l’expérience utilisateur du site web Portail d’entreprise<!--2000968 -->
En nous basant sur les commentaires que nous ont envoyés des clients, de nouvelles fonctionnalités seront ajoutées au site web Portail d’entreprise. Vous allez constater une nette amélioration des fonctionnalités existantes et de la facilité d’utilisation dans vos appareils Android, iOS et Windows. Les différentes zones du site, telles que les détails de l’appareil, les commentaires et le support, ainsi que la vue d’ensemble de l’appareil, vont bénéficier d’une nouvelle présentation interactive et moderne. Vous découvrirez également les points suivants :
- Flux de travail simplifiés sur toutes les plateformes d’appareils
- Flux d’identification et d’inscription des appareils améliorés
- Plus de messages d’erreur utiles
- Langage plus convivial, avec moins de jargon technique
- Possibilité de partager des liens directs vers les applications
- Performances améliorées des grands catalogues d’applications
- Accessibilité accrue pour tous les utilisateurs

### <a name="office-365-proplus-version----2213968-eeready---"></a>Version d’Office 365 ProPlus <!-- 2213968 eeready -->
Lors de l’attribution des applications Office 365 ProPlus aux appareils Windows 10 à l’aide d’Intune, vous serez en mesure de sélectionner la version d’Office. Dans le portail Azure, sélectionnez **Microsoft Intune** > **Applications** > **Ajouter une application**. Sélectionnez ensuite **Suite Office 365 ProPlus (Windows 10)** à partir de la liste déroulante **Type**. Sélectionnez **Paramètres de la suite d’applications** pour afficher le panneau correspondant. Affectez une valeur à **Canal de mise à jour**, par exemple **Tous les mois**. Supprimez éventuellement l’autre version d’Office (msi) des appareils des utilisateurs finaux en sélectionnant **Oui**. Sélectionnez **Spécifique** pour installer une version spécifique de Microsoft Office pour le canal sélectionné sur les appareils des utilisateurs finaux. À ce stade, vous pouvez sélectionner la **Version spécifique** d’Office à utiliser. Les versions disponibles changeront au fil du temps. Par conséquent, quand vous créez un déploiement, les versions disponibles peuvent être plus récentes et ne pas disposer de certaines versions antérieures. Les déploiements actuels continuent de déployer l’ancienne version, mais la liste des versions est en permanence actualisée par canal. Pour plus d’informations, consultez [Présentation des canaux de mise à jour pour Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470---"></a>Configurer le profil pour ignorer certains écrans lors de l’exécution de l’Assistant Configuration <!-- 2276470 -->
Lors de la création d’un profil d’inscription macOS, vous serez en mesure de le configurer pour ignorer les écrans suivants quand un utilisateur exécute l’Assistant Configuration :
- Migration Android
- Display Tone (Indiquer la tonalité)
- Confidentialité
- iCloudStorage

### <a name="change-in-the-update-process-for-on-premises-connectors----2277554---"></a>Changer le processus de mise à jour pour les connecteurs locaux <!-- 2277554 -->
Suite aux commentaires que nous ont envoyés des clients, le mode de mise à jour des connecteurs locaux va changer. Après avoir installé initialement un connecteur local, les mises à jour se produiront automatiquement. Ce changement commence par le nouveau connecteur PFX Certificate Connector pour Microsoft Intune et s’appliquera par la suite aux autres types de connecteurs locaux. 

### <a name="support-for-register-dns-setting-for-windows-10-vpn----2282852---"></a>Prise en charge du paramètre d’inscription DNS pour VPN Windows 10 <!-- 2282852 -->
Vous serez en mesure de configurer des profils VPN Windows 10 pour inscrire dynamiquement les adresses IP attribuées à l’interface VPN auprès du DNS interne, sans avoir besoin d’utiliser des profils personnalisés.
[Paramètres VPN Windows 10](vpn-settings-windows-10.md) liste les paramètres de profil VPN actuels disponibles. 

### <a name="restricts-apps-and-block-access-to-company-resources-on-ios-and-android-for-work-devices----2451462---"></a>Restreindre les applications et bloquer l’accès aux ressources d’entreprise sur les appareils Android for Work et iOS <!-- 2451462 -->
Dans **Conformité de l’appareil** > **Stratégies** > **Créer une stratégie** > **Android for Work** > **Sécurité système**, il existera un nouveau paramètre, **Applications restreintes**. Ce nouveau paramètre utilise une stratégie de conformité pour bloquer l’accès aux ressources d’entreprise si certaines applications sont installées sur l’appareil. L’appareil est considéré comme non conforme jusqu’à ce que les applications restreintes soient supprimées de l’appareil.
S'applique à : 
- iOS

### <a name="export-azure-classic-portal-compliance-policies-to-csv-file----2469637---"></a>Exporter des stratégies de conformité du portail Azure Classic vers un fichier .csv <!-- 2469637 -->
Les stratégies de conformité créées dans le portail Azure Classic seront dépréciées.  Dans ce cas, vous pouvez consulter et supprimer les stratégies existantes, mais vous ne pouvez pas les mettre à jour. Vous pouvez exporter les stratégies en tant que fichier de valeurs séparées par des virgules (fichier .csv). Ensuite, utilisez les détails dans le fichier pour recréer ces stratégies dans le portail Intune Azure.
> [!IMPORTANT]
> Quand le portail Azure Classic sera mis hors service, vous ne pourrez pas accéder à vos stratégies ni même les voir. Par conséquent, veillez à les exporter et à les recréer dans le portail Azure avant la mise hors service du portail Azure Classic.

### <a name="change-terminology-to-retire-and-wipe----2175759---"></a>Modifier la terminologie pour « mettre hors service » et « réinitialiser » <!-- 2175759 -->
Pour être cohérent avec l’API Graph, l’interface et la documentation utilisateur Intune change les termes suivants :
- **Supprimer les données d’entreprise** est remplacé par **mettre hors service**
- **Réinitialisation d’usine** est remplacé par **réinitialiser**

### <a name="delete-jamf-devices----2653306---"></a>Supprimer des appareils Jamf <!-- 2653306 -->
Pour supprimer des appareils gérés par JAMF, accédez à **Appareils** > choisissez l’appareil Jamf > **Supprimer**.

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Nouvelles opportunités de synchronisation dans l’application Portail d’entreprise pour Windows <!-- 2683177 -->
L’application Portail d’entreprise pour Windows ajoute une action de synchronisation d’appareils à la barre des tâches Windows et aux listes de raccourcis du menu Démarrer. Cliquez sur l’un de ces éléments pour synchroniser rapidement vos appareils et accéder aux ressources d’entreprise.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Réinitialiser les codes secrets des appareils à partir de l’application Portail d’entreprise pour Windows 10 <!-- 2101282 --> 
Vos employés seront bientôt en mesure de réinitialiser le code PIN ou le code secret de leur appareil directement de l’application Portail d’entreprise pour Windows 10. Cette fonctionnalité sera disponible sur les appareils locaux et distants gérés par Intune qui prennent en charge les réinitialisations de codes secrets. Selon le type d’appareil, les demandes pour un appareil distant supprimeront le code secret actuel de l’appareil ou créeront un code secret temporaire. Les utilisateurs qui demanderont une réinitialisation pour un appareil local seront redirigés vers l’application des paramètres de l’appareil.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nouvelles expériences d’exploration dans l’application Portail d’entreprise pour Windows <!-- 2317227 -->  
Quand vous parcourez les applications dans l’application Portail d’entreprise pour Windows, ou y en recherchez, vous pouvez basculer entre la vue **Vignettes** existante et la nouvelle vue **Détails**. La nouvelle vue répertorie les détails des applications, tels que le nom, l’éditeur, la date de publication et l’état d’installation.  

La page **Applications** introduit une vue **Installée** qui vous permet de voir les détails concernant les installations d’application terminées et en cours. Vous souhaitez partager des commentaires ou des réflexions sur les nouvelles modifications ? Envoyez-nous vos commentaires dans l’application Portail d’entreprise.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Amélioration de l’expérience de l’application Portail d’entreprise pour les utilisateurs du gestionnaire d’inscription d’appareil <!-- 675800 -->
Quand un gestionnaire d’inscription d’appareil se connecte à l’application Portail d’entreprise pour Windows, l’application affiche uniquement l’appareil en cours d’exécution actuel du gestionnaire. Cette amélioration permet de réduire les délais d’attente qui se produisaient auparavant quand l’application essayait de charger tous les appareils inscrits par le gestionnaire d’inscription d’appareil.  

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Ajout automatique du package de configuration de Windows Defender ATP au profil de configuration <!-- 2144658 -->
Actuellement, quand vous utilisez des appareils [ATP (Advanced Threat Protection) et d’intégration](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile) dans Intune, vous téléchargez un package de configuration et vous l’ajoutez à votre profil de configuration. Dans une prochaine mise à jour, Intune prendra automatiquement le package dans le Centre de sécurité Windows Defender et l’ajoutera à votre profil.

S’applique à Windows 10 et versions ultérieures.

### <a name="check-for-sccm-compliance----2192052---"></a>Vérification de la conformité SCCM <!-- 2192052 -->
Une prochaine mise à jour va offrir un nouveau paramètre de conformité System Center Configuration Manager (SCCM) (**Conformité de l’appareil** > **Stratégies** > **Créer une stratégie**   >  **Windows 10**). SCCM envoie des signaux pour la conformité Intune. À l’aide du paramètre Intune, vous pouvez exiger que tous les signaux SCCM retournent « conforme ».

Par exemple, vous voulez que toutes les mises à jour logicielles soient installées sur les appareils. Dans SCCM, cette exigence présente l’état « Installé ». Si les programmes de l’appareil sont dans un état inconnu, l’appareil est non conforme dans Intune.

S’applique à Windows 10 et ultérieur

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Alertes pour l’expiration du jeton VPP ou pour le nombre insuffisant de licences du portail d’entreprise <!-- 2237572 -->
Si vous utilisez le programme d’achat en volume (VPP) pour préprovisionner le portail d’entreprise lors de l’inscription DEP, Intune vous alerte quand le jeton VPP est sur le point d’expirer et qu’il ne reste plus beaucoup de licences pour le portail d’entreprise.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Confirmation obligatoire pour supprimer un jeton VPP utilisé pour le préprovisionnement du portail d'entreprise <!-- 2237634 -->
Une confirmation sera obligatoire pour supprimer un jeton VPP (Volume Purchase Program) si celui-ci est utilisé pour préprovisionner le portail d’entreprise lors d’une inscription DEP.

#### <a name="additional-security-settings-for-windows-installer----2282430---"></a>Paramètres de sécurité supplémentaires pour le programme d’installation de Windows <!-- 2282430 -->
Vous pourrez permettre aux utilisateurs de contrôler les installations d’applications. Si cette fonctionnalité est activée, les installations qui sinon pourraient être arrêtées en raison d’une violation de sécurité sont autorisées à poursuivre leur exécution. Vous pourrez faire en sorte que le programme d’installation de Windows utilise des autorisations élevées quand il installe un programme sur un système. Vous pourrez en outre autoriser l’indexation des éléments de la Protection des informations Windows et le stockage de leurs métadonnées dans un emplacement non chiffré. Quand la stratégie est désactivée, les éléments protégés par la Protection des informations Windows ne seront pas indexés et n’apparaîtront pas dans les résultats de Cortana ou de l’Explorateur de fichiers. Les fonctionnalités de ces options seront désactivées par défaut. 

<!-- 1806 start -->

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Les claviers tiers peuvent être bloqués par des paramètres APP sur iOS <!-- 1248481 -->
Sur les appareils iOS, les administrateurs Intune peuvent bloquer l’utilisation de claviers tiers lors de l’accès à des données d’entreprise dans des applications protégées par une stratégie. Quand la stratégie de protection d’application (APP, Application Protection Policy) est configurée pour bloquer les claviers tiers, l’utilisateur de l’appareil reçoit un message la première fois qu’il interagit avec des données d’entreprise en utilisant un clavier tiers. Toutes les options autres que celles du clavier natif sont bloquées et les utilisateurs d’appareils ne les voient pas. La boîte de message ne s’affiche qu’une seule fois aux utilisateurs. 

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Exiger un code secret non biométrique au lancement de l’application et après un délai d’expiration <!-- 1506985 -->

En exigeant un code secret non biométrique au lancement de l’application et après un délai d’expiration spécifié par l’administrateur, Intune offre une sécurité renforcée pour les applications compatibles avec la gestion des applications mobiles (MAM) en limitant l’utilisation de l’identification biométrique pour l’accès aux données d’entreprise. Les paramètres affectent les utilisateurs qui s’appuient sur Touch ID (iOS), Face ID (iOS), Android Biométrique ou d’autres méthodes d’authentification biométriques à venir pour accéder à leurs applications compatibles APP/MAM. Ces paramètres permettent aux administrateurs Intune d’avoir un contrôle plus précis sur l’accès utilisateur, en supprimant les cas où un appareil avec plusieurs empreintes digitales ou d’autres méthodes d’accès biométriques peut révéler des données d’entreprise à un utilisateur inapproprié. Dans le portail Azure, ouvrez **Microsoft Intune**. Sélectionnez **Applications mobiles** > **Stratégies de protection des applications** > **Ajouter une stratégie** > **Paramètres**. Recherchez la section **Accès** pour des paramètres spécifiques.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Modules linguistiques Office 365 Pro Plus <!-- 1833450 -->
En tant qu’administrateur Intune, vous pouvez déployer des langues supplémentaires pour les applications Office 365 Pro Plus gérées par le biais d’Intune. La liste des langues disponibles inclut le **Type** du module linguistique (principal, partiel et de vérification). Dans le portail Azure, sélectionnez **Microsoft Intune** > **Applications mobiles** > **Applications** > **Ajouter**. Dans la liste **Type d’application** du panneau **Ajouter une application**, sélectionnez **Windows 10** sous la **Suite Office 365**. Sélectionnez **Langues** dans le panneau **Paramètres de la suite d’applications**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Aperçu d’une nouvelle mise à jour de l’expérience utilisateur du site web Portail d’entreprise<!--2000968 -->
En nous basant sur les commentaires que nous ont envoyés des clients, nous ajoutons de nouvelles fonctionnalités au site web Portail d’entreprise/Catalogue d’applications iOS. Vous allez constater une nette amélioration des fonctionnalités existantes et de la facilité d’utilisation dans vos appareils Android, iOS et Windows. Les différentes zones du site, telles que les détails de l’appareil, les commentaires et le support, ainsi que la vue d’ensemble de l’appareil, vont bénéficier d’une nouvelle présentation interactive et moderne. Vous découvrirez également les points suivants :

- Flux de travail simplifiés sur toutes les plateformes d’appareils
- Flux d’identification et d’inscription des appareils améliorés
- Plus de messages d’erreur utiles
- Langage plus convivial, avec moins de jargon technique
- Possibilité de partager des liens directs vers les applications
- Performances améliorées des grands catalogues d’applications
- Accessibilité accrue pour tous les utilisateurs

La mise à jour est actuellement en préversion. Vous pouvez vous inscrire pour accéder à la préversion http://aka.ms/webcpflighting

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Exiger un code secret non biométrique au lancement à froid de l’application et après un délai d’expiration <!-- 1506985 --> 

En exigeant un code secret non biométrique au lancement à froid de l’application et après un délai d’expiration spécifié par l’administrateur, Intune offre une sécurité renforcée pour les applications compatibles avec la gestion des applications mobiles (MAM) en limitant l’utilisation de l’identification biométrique pour l’accès aux données d’entreprise. Les paramètres affectent les utilisateurs qui s’appuient sur Touch ID (iOS), Face ID (iOS), Android Biométrique ou d’autres méthodes d’authentification biométriques à venir pour accéder à leurs applications compatibles APP/MAM. Ces paramètres permettent aux administrateurs Intune d’avoir un contrôle plus précis sur l’accès utilisateur, en supprimant les cas où un appareil avec plusieurs empreintes digitales ou d’autres méthodes d’accès biométriques peut révéler des données d’entreprise à un utilisateur inapproprié. Dans le portail Azure, ouvrez **Microsoft Intune**. Sélectionnez **Applications mobiles** > **Stratégies de protection des applications** > **Ajouter une stratégie** > **Paramètres**. Recherchez la section **Accès** pour des paramètres spécifiques.

<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Possibilité de déployer les applications métier requises pour tous les utilisateurs sur les appareils Windows 10 Desktop <!-- 1627835 RS4 -->
Les clients pourront déployer les applications Windows 10 métier requises à installer dans les contextes d’appareils. Ces applications seront alors disponibles pour tous les utilisateurs sur l’appareil. Seuls les appareils Windows 10 Desktop sont concernés.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Mise à jour de l’expérience Aide et commentaires sur l’application Portail d’entreprise pour Android <!--1631531 -->

L’expérience Aide et commentaires sur l’application Portail d’entreprise pour Android sera mise à jour de manière à pour se conformer aux bonnes pratiques pour les applications Android. L’application Portail d’entreprise pour Android sera mise à jour dans les prochains mois de manière à scinder l’élément de menu **Aide et commentaires** en deux éléments distincts **Aide** et **Envoyer des commentaires**. La page **Aide** contiendra une section **Questions fréquentes (FAQ)** et un bouton **Assistance par e-mail** pour amener les utilisateurs finaux à transmettre les journaux à Microsoft et à envoyer un e-mail au service de support de l’entreprise décrivant le problème. L’élément de menu **Envoyer des commentaires** permettra à l’utilisateur d’envoyer des commentaires à Microsoft. L’utilisateur devra choisir entre « J’aime quelque chose », « Je n’aime pas quelque chose » ou « J’ai une idée ».

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Remarques

Il n’existe aucun avis actif pour l’instant.

### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.



