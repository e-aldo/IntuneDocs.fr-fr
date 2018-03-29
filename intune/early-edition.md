---
title: Édition préliminaire
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99b1436fdf718b54f54f7e90835668d4a632b7ce
ms.sourcegitcommit: 390a4be5aa36007c36fb6a5abcfe8d20bc862a4b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>Édition préliminaire de Microsoft Intune - Mars 2018

**L’édition préliminaire** fournit la liste des fonctionnalités qui seront intégrées dans les prochaines versions de Microsoft Intune. Ces informations sont fournies de manière limitée et sont susceptibles de changer. Ne partagez pas ces informations en dehors de votre entreprise. Certaines fonctionnalités répertoriées ici risquent de ne pas être prêtes d’ici la date limite et d’être repoussées à une version ultérieure. D’autres fonctionnalités sont en cours de test dans un pilote (version d’évaluation) pour s’assurer qu'elles sont prêtes à l'emploi. Joignez votre contact de groupe de produits Microsoft si vous avez des questions ou rencontrez des problèmes.

Cette page est mise à jour périodiquement. Consultez-la régulièrement pour savoir si des mises à jour supplémentaires sont disponibles.

> [!Note]
>Les modifications suivantes sont en cours de développement pour Intune. Pour plus d’informations sur les nouvelles fonctionnalités hybrides, consultez la [page des nouveautés hybrides](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune dans le portail Azure

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Prise en charge de connecteurs Exchange multiples <!-- 2070451 -->

Vous ne serez plus limité à un seul connecteur Exchange Microsoft Intune par client. Intune prendra en charge plusieurs connecteurs Exchange afin que vous puissiez configurer l’accès conditionnel Intune avec plusieurs organisations Exchange locales.

Avec un connecteur Exchange local Intune, vous pouvez gérer l’accès de l’appareil aux boîtes aux lettres Exchange locales en fonction de l’inscription ou non d’un appareil dans Intune et de sa conformité aux stratégies de conformité Intune. Pour configurer un connecteur, téléchargez le connecteur Exchange local Intune à partir du portail Azure et installez-le sur un serveur de votre organisation Exchange. Dans le tableau de bord Microsoft Intune, choisissez **Accès local**, puis sous **Installation**, choisissez **Connecteur Exchange ActiveSync**. Téléchargez le connecteur Exchange local et installez-le sur un serveur de votre organisation Exchange. Maintenant que vous n’êtes plus limité à un seul connecteur Exchange par client, si vous avez d’autres organisations Exchange, vous pouvez suivre le même processus pour télécharger et installer un connecteur pour chaque organisation Exchange supplémentaire.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Arrivée de la prise en charge du nouveau client Cisco AnyConnect pour iOS <!-- 1333708 -->

Les nouveaux profils VPN créés pour Cisco AnyConnect pour iOS fonctionneront avec Cisco AnyConnect 4.0.7x et les versions supérieures. Les profils VPN Cisco AnyConnect pour iOS existants porteront l’étiquette **Cisco Legacy AnyConnect** et continueront de fonctionner avec Cisco AnyConnect 4.0.5x.

> [!NOTE]
> Cette modification ne concerne qu’iOS. Il continuera de n’y avoir qu’une seule option Cisco AnyConnect pour Android, Android for Work et macOS.

#### <a name="more-information"></a>Plus d’informations

Vous devez créer un nouveau profil VPN Cisco AnyConnect pour iOS afin de prendre en charge la nouvelle application Cisco AnyConnect car celle-ci et l’application Cisco Legacy AnyConnect sont des applications distinctes. Si vous gérez le client AnyConnect dans votre environnement, vous devez également déployer la nouvelle application Cisco AnyConnect. Pour effectuer une mise à niveau, vous devez aussi supprimer votre profil VPN Cisco Legacy AnyConnect et l’application Cisco Legacy AnyConnect.

L’intégration du contrôle d’accès réseau ne fonctionnera pas pour le nouveau client AnyConnect dans la version initiale. Nous travaillons avec Cisco pour proposer l’intégration du contrôle d’accès réseau dans une prochaine version de Microsoft Intune.

### <a name="enhanced-jailbreak-detection----846515---"></a>Détection de jailbreak améliorée <!-- 846515 -->

La détection de jailbreak améliorée est un nouveau paramètre de conformité qui améliorera la manière dont Intune évalue les appareils jailbreakés. Elle utilisera les services de localisation de l’appareil pour déclencher plus fréquemment l’archivage de l’appareil dans Intune et impactera l’utilisation de la batterie.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Possibilité de déployer les applications métier requises pour tous les utilisateurs sur les appareils Windows 10 Desktop <!-- 1627835 RS4 -->
Les clients pourront déployer les applications Windows 10 métier requises à installer dans les contextes d’appareils. Ces applications seront alors disponibles pour tous les utilisateurs sur l’appareil. Seuls les appareils Windows 10 Desktop sont concernés.

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Expiration des applications métier pour Microsoft Intune <!-- 748789 -->
Dans le portail Azure, Intune vous avertira quand des applications métier seront sur le point d’expirer. Dès qu’une nouvelle version de l’application métier sera chargée, Intune supprimera la notification d’expiration de la liste des applications.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inscription par le biais de l’application Portail d’entreprise améliorée <!-- 1874230-->
Les utilisateurs qui s’inscrivent à l’aide du Portail d’entreprise sur Windows 10 build 1703 et supérieure pourront effectuer la première étape de l’inscription sans quitter l’application.

### <a name="new-management-name-column----1333586---"></a>Nouvelle colonne Nom d’administration <!-- 1333586 -->
Une nouvelle colonne intitulée **Nom d’administration** sera ajoutée au panneau Appareils. Il s’agit d’un nom généré automatiquement, non modifiable affecté par appareil, reposant sur la formule suivante :
- Nom par défaut pour tous les appareils : <username>_<devicetype>_<enrollmenttimestamp>
- Pour les appareils ajoutés en bloc : <ID_de_package/ID_de_profil>_<DeviceType>_<EnrollmentTime>

Il s’agit d’une colonne facultative dans le panneau Appareils. Elle ne sera pas disponible par défaut et vous ne pourrez y accéder que via le sélecteur de colonne. Le nom de l’appareil n’est pas affecté par cette nouvelle colonne.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Nouveaux paramètres pour le profil de configuration d’appareil pour les notifications Windows Defender Security Center (WDSC) <!-- 1631906 -->

Trois nouveaux paramètres seront ajoutés au profil de configuration d’appareil pour les notifications Windows Defender Security Center (WDSC).

Les administrateurs pourront :

- Masquer le pilier Identité
- Masquer le pilier Matériel et ses sous-paramètres
- Masquer le pilier Ransomware (restauration de fichiers OneDrive Entreprise)

Si vous masquez ces piliers de l’application WDSC, les utilisateurs finaux ne pourront pas configurer ces paramètres et toutes les notifications associées aux composants masqués ne seront pas générées.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Stratégies MAM ciblées en fonction de l’état de gestion <!-- 1665993 -->

Vous pourrez cibler des stratégies MAM en fonction de l’état de gestion de l’appareil :

- **Appareils iOS** : vous pourrez cibler des appareils non gérés (MAM uniquement) ou des appareils gérés par Intune.
- **Appareils Android** : vous pourrez cibler des appareils non gérés, des appareils gérés par Intune et des profils d’entreprise Android gérés par Intune (anciennement Android for Work).

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>Configurer Gatekeeper pour contrôler la source de téléchargement des applications macOS <!-- 1690459-->

Vous pourrez configurer Gatekeeper pour protéger vos appareils en contrôlant les sources de téléchargement des applications. Vous pourrez configurer les sources de téléchargement suivantes : **Mac App Store**, **Mac App Store et développeurs identifiés** ou **N’importe où**. Vous pourrez également configurer la possibilité pour les utilisateurs d’installer une application en maintenant la touche Ctrl enfoncée pour passer outre ces contrôles Gatekeeper.

Ces paramètres se trouvent sous **Configuration de l’appareil** -> **Créer un profil** -> **macOS**  ->  **Endpoint protection**.

### <a name="configure-the-mac-application-firewall----1690461---"></a>Configurer le coupe-feu applicatif Mac <!-- 1690461 -->

Vous pourrez configurer le coupe-feu applicatif Mac. Vous serez ainsi en mesure de contrôler les connexions au niveau de chaque application, plutôt qu’au niveau de chaque port. Il permet ainsi d’empêcher les applications indésirables de contrôler les ports réseau ayant été ouverts pour des applications légitimes, et de profiter d’une protection optimale.

Cette fonctionnalité se trouve sous **Configuration de l’appareil** -> **Créer un profil** -> **macOS**  ->  **Endpoint protection**.

Une fois le paramètre de coupe-feu activé, vous pouvez configurer le coupe-feu à l’aide de deux stratégies :

- Bloquer toutes les connexions entrantes

   Vous pouvez bloquer toutes les connexions entrantes pour les appareils ciblés. Les connexions entrantes seront alors bloquées pour toutes les applications.

- Autoriser ou bloquer des applications spécifiques

   Vous pouvez autoriser ou bloquer la réception de connexions entrantes pour des applications spécifiques. Vous pouvez également activer le mode furtif de manière à empêcher les réponses aux demandes de détection.

#### <a name="more-information"></a>Plus d’informations

- Bloquer toutes les connexions entrantes

   La réception de connexions entrantes est bloquée pour tous les services de partage (par exemple, le partage de fichiers et le partage d’écran). Les services système qui sont toujours autorisés à recevoir des connexions entrantes sont :
   - configd : implémente DHCP et d’autres services de configuration réseau
   - mDNSResponder : implémente Bonjour
   - racoon : implémente IPSec

   Pour utiliser les services de partage, assurez-vous que **Connexions entrantes** a la valeur **Non configuré** (pas **Bloquer**).

- Mode furtif

   Activez cette option pour empêcher l’ordinateur de répondre aux demandes de détection. L’ordinateur continue de répondre aux demandes entrantes pour les applications autorisées. Les demandes inattendues, comme ICMP (ping), sont ignorées.


### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Mise à jour de l’expérience Aide et commentaires sur l’application Portail d’entreprise pour Android <!--1631531 -->

Nous allons mettre à jour l’expérience Aide et commentaires sur l’application Portail d’entreprise pour Android de manière à l’harmoniser avec les bonnes pratiques pour les applications Android. Nous allons mettre à jour l’application Portail d’entreprise pour Android dans les prochains mois de manière à scinder l’élément de menu **Aide et commentaires** en deux éléments distincts **Aide** et **Envoyer des commentaires**. La page **Aide** contiendra une section **Questions fréquentes (FAQ)** et un bouton **Assistance par e-mail** pour amener les utilisateurs finaux à transmettre les journaux à Microsoft et à envoyer un e-mail au service de support de l’entreprise décrivant le problème. L’élément de menu **Envoyer des commentaires** permettra à l’utilisateur d’envoyer des commentaires à Microsoft. L’utilisateur devra choisir entre « J’aime quelque chose », « Je n’aime pas quelque chose » ou « J’ai une idée ».

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Catégories de livres personnalisées pour les livres électroniques achetés dans le cadre d’un programme d’achat en volume <!-- 1488911 -->
Vous pourrez créer des catégories de livres électroniques personnalisées, puis attribuer des livres électroniques achetés en volume à ces catégories personnalisées. Les utilisateurs finaux pourront ensuite voir les nouvelles catégories de livres électroniques et les livres affectés à ces catégories.

### <a name="hololens-and-surface-hub-now-appear-in-device-lists---1725868--"></a>HoloLens et Surface Hub apparaissent désormais dans les listes d’appareils <!--1725868-->

Nous avons ajouté la prise en charge de l’affichage des appareils HoloLens et Surface Hub inscrits auprès d’Intune dans l’application Portail d’entreprise pour Android.

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Prise en charge mobile Edge pour les stratégies de protection des applications Intune <!-- 1817882 -->

Le navigateur Microsoft Edge pour appareils mobiles prend en charge les stratégies de protection des applications définies dans Intune.

### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763-eeready--"></a>Utiliser le nom unique en tant que sujet de certificat SCEP <!--2221763 eeready-->
Quand vous créez un profil de certificat SCEP, vous entrez le nom du sujet. Vous pouvez utiliser le nom complet en tant que sujet. Dans **Nom du sujet**, sélectionnez **Personnalisé**, puis entrez `CN={{OnPrem_Distinguished_Name}}`. Pour utiliser la variable `{{OnPrem_Distinguished_Name}}`, veillez à synchroniser l’attribut utilisateur `onpremisesdistingishedname` qui utilise [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) avec Azure AD.

### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837-eeready--"></a>Les appareils iOS sont invités à entrer un code confidentiel toutes les 15 minutes <!--1550837 eeready-->
Une fois qu’une stratégie de conformité ou de configuration est appliquée à un appareil iOS, les utilisateurs sont invités à définir un code confidentiel toutes les 15 minutes. Les utilisateurs y sont invités continuellement jusqu’à ce qu’un code confidentiel soit défini.

### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983-eeready--"></a>Activer le partage de contacts Bluetooth - Android for Work <!--1098983 eeready-->
Par défaut, Android empêche les contacts inclus dans le profil professionnel de se synchroniser avec des appareils Bluetooth. Ainsi, les contacts de profil professionnel ne s’affichent pas sur l’ID de l’appelant des appareils Bluetooth.

Un nouveau paramètre fait son apparition dans **Android for Work** > **Restrictions sur l’appareil** > **Paramètres du profil professionnel** :
- Partage de contacts via Bluetooth

L’administrateur Intune peut configurer ces paramètres pour activer le partage. Cette démarche s’avère utile lors de l’appariement d’un appareil avec un appareil Bluetooth de voiture qui affiche l’ID de l’appelant à des fins d’utilisation en mode mains libres. Quand ce paramètre est activé, les contacts de profil professionnel sont affichés. Dans le cas contraire, ils n’apparaissent pas.

S’applique aux appareils avec profil professionnel Android sur le système d’exploitation Android 6.0 et versions ultérieures.

### <a name="schedule-your-automatic-updates---1805514---"></a>Planifier vos mises à jour automatiques <!--1805514 -->

Intune vous permet de contrôler l’installation des mises à jour automatiques à l’aide des [paramètres des anneaux de mise à jour Windows](windows-update-for-business-configure.md). Vous pouvez planifier les mises à jour récurrentes, notamment la semaine, le jour et l’heure.

### <a name="disable-checks-on-device-restart---1805490---"></a>Désactiver les vérifications au redémarrage de l’appareil <!--1805490 -->

Intune vous permet de contrôler la [gestion des mises à jour logicielles](windows-update-for-business-configure.md). La propriété **Vérifications de redémarrage** est ajoutée et activée par défaut. Pour ignorer les vérifications usuelles qui se produisent au redémarrage d’un appareil (comme les utilisateurs actifs, les niveaux de batterie, etc.), sélectionnez **Ignorer**.

<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nouveau graphique de tendance des échecs d’inscription et tableau des raisons de ces échecs <!-- 1471783 -->

Dans la page Vue d’ensemble de l’inscription, vous pourrez voir la tendance des échecs d’inscription et les cinq premières causes de ces échecs. En cliquant sur le graphique ou le tableau, vous pourrez explorer les détails et trouver des conseils de dépannage et des suggestions de correction.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>Personnaliser vos thèmes de portail d’entreprise avec des codes hexadécimaux<!--1049561 -->

Vous serez en mesure de personnaliser la couleur de thème dans les applications Portail d’entreprise à l’aide de codes hexadécimaux. Quand vous entrez votre code hexadécimal, Intune détermine la couleur du texte qui fournit le plus haut niveau de contraste entre la couleur du texte et la couleur d’arrière-plan selon les [normes WCAG 2.0](http://www.w3.org/TR/WCAG20). Vous pouvez afficher un aperçu de la couleur du texte et du logo de votre société par rapport à la couleur dans **Applications mobiles** > **Portail d’entreprise**.

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Nouveaux paramètres Windows Defender Credential Guard ajoutés aux paramètres Endpoint Protection <!--1102252 -->

De nouveaux paramètres [Windows Defender Credential Guard] (https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] sont ajoutés à **Configuration de l’appareil** > **Profils** > **Endpoint Protection**. Les paramètres suivants seront ajoutés :

- Niveau de sécurité de plateforme : spécifiez si le niveau de sécurité de plateforme est activé lors du prochain redémarrage. La sécurité basée sur la virtualisation nécessite un démarrage sécurisé. La sécurité basée sur la virtualisation peut éventuellement être activée avec l’utilisation de protections d’accès direct à la mémoire (DMA). Les protections DMA nécessitent une prise en charge matérielle et ne seront activées que sur des appareils configurés correctement.
- Sécurité basée sur la virtualisation : spécifiez si la sécurité basée sur la virtualisation est activée lors du prochain redémarrage.
- Windows Defender Credential Guard : activez Credential Guard avec la sécurité basée sur la virtualisation pour protéger les informations d’identification au prochain redémarrage quand le niveau de sécurité de plateforme avec un démarrage sécurisé et la sécurité basée sur la virtualisation sont tous deux activés. Les options disponibles sont notamment **Désactivé**, **Activé avec le verrouillage UEFI**, **Activé sans verrouillage** et **Non configuré**.
  - L’option « Désactivé » désactive Credential Guard à distance s’il a été préalablement activé avec l’option « Activé sans verrouillage ».

  - L’option « Activé avec le verrouillage UEFI » garantit que Credential Guard ne peut pas être désactivé avec une clé de Registre ni en utilisant une stratégie de groupe. Pour désactiver Credential Guard après avoir utilisé ce paramètre, vous devez définir la stratégie de groupe sur « Désactivé » et supprimer la fonction de sécurité de chaque ordinateur, avec un utilisateur présent physiquement, afin d’effacer la configuration incluse dans UEFI. Tant que la configuration UEFI persiste, Credential Guard est activé.

  - L’option « Activé sans verrouillage » permet de désactiver Credential Guard à distance à l’aide d’une stratégie de groupe. Les appareils utilisant ce paramètre doivent exécuter au moins Windows 10 (version 1511).

  - L’option « Non configuré » laisse le paramètre de stratégie non défini. La stratégie de groupe n’écrit pas le paramètre de stratégie dans le Registre et il n’a donc pas d’impact sur les ordinateurs ou les utilisateurs. Si un paramètre existe dans le Registre, il n’est pas modifié.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Réinitialiser les mots de passe pour les appareils Android O <!-- 1238299 -->
Vous serez en mesure de réinitialiser les mots de passe pour les appareils Android O inscrits. Quand vous envoyez une demande « Réinitialiser le mot de passe » à un appareil Android O, il définit un nouveau mot de passe de déverrouillage d’appareil ou une vérification de profil géré pour l’utilisateur actuel. Le mot de passe ou la vérification est envoyé selon si l’appareil a un propriétaire de profil ou un propriétaire d’appareil, et entre immédiatement en vigueur.

### <a name="local-device-security-option-settings----1251887---"></a>Paramètres d’option de sécurité d’appareil local <!-- 1251887 -->
Vous pourrez activer les paramètres de sécurité sur les appareils Windows 10 avec les nouveaux paramètres d’option de sécurité d’appareil local. Recherchez ces paramètres dans la catégorie Endpoint Protection quand vous créez une stratégie de configuration d’appareil Windows 10.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nouveaux paramètres d’imprimante pour les profils Éducation <!-- 1308900 -->

Pour les profils Éducation, de nouveaux paramètres seront disponibles sous la catégorie **Imprimantes** : **Imprimantes**, **Imprimante par défaut**, **Ajouter de nouvelles imprimantes**.

### <a name="ios-app-provisioning-configuration----1581650---"></a>Configuration du provisionnement des applications iOS <!-- 1581650 -->
Vous serez en mesure d’assigner des profils de provisionnement des applications iOS pour empêcher vos applications d’arriver à expiration en incluant ou excluant des groupes de sécurité.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nouveaux paramètres Windows Defender Application Guard <!-- 1631890 -->

- **Activer l’accélération graphique**

Les administrateurs pourront activer un processeur graphique virtuel pour Windows Defender Application Guard. Ce paramètre permet à l’UC de décharger l’affichage graphique sur l’unité de traitement graphique virtuelle. Cela peut améliorer les performances quand vous utilisez des sites web qui consomment beaucoup de graphiques ou regardez une vidéo au sein du conteneur.

- **SaveFilestoHost**

Les administrateurs pourront activer les fichiers à transférer de Microsoft Edge en cours d’exécution dans le conteneur au système de fichiers hôte. L’activation de ce paramètre permet aux utilisateurs de télécharger des fichiers à partir de Microsoft Edge dans le conteneur sur le système de fichiers hôte.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>Inclusion et exclusion d’affectations d’applications en fonction de groupes pour Android Enterprise <!-- 1813081 -->
Lors des affectations d’applications et après avoir sélectionné un type d’affectation, Android Enterprise (anciennement Android for Work) prend en charge la fonctionnalité d’exclusion.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Ciblage des stratégies de conformité pour les appareils dans des groupes d’appareils <!--1307012 -->

Vous pourrez cibler des stratégies de conformité pour les utilisateurs dans des groupes d’utilisateurs. Vous pourrez cibler des stratégies de conformité pour les appareils dans des groupes d’appareils.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

### <a name="configure-an-ios-app-pin----1586774---"></a>Configurer un code PIN d’application iOS <!-- 1586774 -->
Vous pourrez bientôt exiger un code PIN pour des applications iOS ciblées. Vous pouvez configurer l’exigence du code PIN et sa date d’expiration en jours par le biais du portail Azure. Le cas échéant, l’utilisateur devra définir et utiliser un nouveau code PIN avant d’accéder à une application iOS. Seules les applications iOS pour lesquelles la protection d’application est activée avec le SDK d’application Intune prendront en charge cette fonctionnalité.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Les sites web Azure Active Directory peuvent nécessiter l’application Intune Managed Browser et la prise en charge de l’authentification unique pour Managed Browser (Préversion publique) <!-- 710595 -->   
Avec Azure Active Directory (Azure AD), vous pouvez restreindre l’accès aux sites web sur des appareils mobiles à l’application Intune Managed Browser. Dans Managed Browser, les données de site web restent sécurisées et séparées des données personnelles de l’utilisateur final. Par ailleurs, Managed Browser prend en charge les fonctionnalités d’authentification unique pour les sites protégés par Azure AD. Si vous vous connectez à Managed Browser ou que vous utilisez Managed Browser sur un appareil avec une autre application gérée par Intune, Managed Browser peut accéder aux sites d’entreprise protégés par Azure AD sans que l’utilisateur ne doive entrer ses informations d’identification. Cette fonctionnalité s’applique aux sites comme Outlook Web Access (OWA) et SharePoint Online, ainsi qu’à d’autres sites d’entreprise tels que les ressources intranet accessibles par le proxy de l’application Azure.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>Redirection des utilisateurs macOS vers notre nouvelle application Portail d’entreprise <!--1380728-->   
Lorsqu’un utilisateur final se connecte au site web du portail d’entreprise pour inscrire son appareil macOS, il est invité à télécharger la nouvelle application Portail d’entreprise pour macOS pour effectuer la procédure. Ce comportement se produit pour les appareils macOS avec OS X El Capitan 10.11 ou ultérieur. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Message d’erreur amélioré quand un utilisateur atteint le nombre maximal d’appareils autorisés à inscrire <!-- 1270370 -->
Au lieu d’un message d’erreur générique, les utilisateurs finaux d’appareils Android reçoivent un message d’erreur convivial offrant une possibilité d’action : « Vous avez inscrit le nombre maximal d’appareils autorisés par votre administrateur informatique. Supprimez un appareil inscrit ou demandez de l’aide à votre administrateur informatique ».



## <a name="notices"></a>Remarques

Il n’existe aucun avis actif pour l’instant.



### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
