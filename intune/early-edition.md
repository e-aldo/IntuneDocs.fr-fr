---
title: Édition préliminaire
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95ad588b084319cd8a0f5f5c5d92da0e892eed50
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745041"
---
# <a name="the-early-edition-for-microsoft-intune---june-2018"></a>Édition préliminaire de Microsoft Intune - Juin 2018

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

<!-- 1806 start -->

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>Prise en charge des appareils Android COSU (corporate-owned, single use)<!-- 1630973 -->

Intune prend en charge les appareils Android hautement gérés, verrouillés et de style kiosque. Cela permet aux administrateurs de verrouiller davantage l’utilisation d’un appareil à une seule application ou à un petit ensemble d’applications, et empêche les utilisateurs d’activer d’autres applications ou d’effectuer d’autres actions sur l’appareil.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>Prise en charge de macOS pour le Programme d’inscription des appareils Apple <!-- 747651 -->

Intune prend en charge l’inscription d’appareils macOS dans le Programme d’inscription des appareils (DEP) Apple. Pour cela :

1. Sur deploy.apple.com, affectez les numéros de série macOS à un serveur MDM.
2. Importez les numéros de série dans Intune.
3. Créez un profil de programme d’inscription propre aux appareils macOS.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Changement des noms Google pour Android for Work et Play for Work <!--842873 -->
Intune met à jour la terminologie « Android for Work » pour refléter les changements apportés à la personnalisation de Google.  Les termes « Android for Work » et « Play for Work » ne sont plus utilisés. Une terminologie différente sera utilisée en fonction du contexte :

- « Android Enterprise » fait référence à la pile de gestion Android moderne globale.
- « Profil professionnel » ou « Propriétaire du profil » fait référence à des appareils BYOD gérés avec des profils professionnels.
- « Google Play géré » fait référence à l’App Store Google.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Surveiller l’état de configuration d’applications iOS par appareil <!-- 880037 eeready eestaged -->

En tant qu’administrateur Microsoft Intune, vous pouvez surveiller l’état de configuration d’applications iOS pour chaque appareil géré. À partir de **Microsoft Intune** dans le portail Azure, sélectionnez **Appareils** > **Tous les appareils**. Dans la liste des appareils gérés, sélectionnez un appareil spécifique pour afficher le panneau correspondant. Dans le panneau de l’appareil, sélectionnez **Configuration de l’application**.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Les claviers tiers peuvent être bloqués par des paramètres APP sur iOS <!-- 1248481 -->
Sur les appareils iOS, les administrateurs Intune peuvent bloquer l’utilisation de claviers tiers lors de l’accès à des données d’entreprise dans des applications protégées par une stratégie. Quand la stratégie de protection d’application (APP, Application Protection Policy) est configurée pour bloquer les claviers tiers, l’utilisateur de l’appareil reçoit un message la première fois qu’il interagit avec des données d’entreprise en utilisant un clavier tiers. Toutes les options autres que celles du clavier natif sont bloquées et les utilisateurs d’appareils ne les voient pas. La boîte de message ne s’affiche qu’une seule fois aux utilisateurs. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Créer une stratégie de conformité des appareils à l’aide de paramètres de pare-feu sur ses appareils macOS <!-- 1497640 -->
Quand vous créez une stratégie de conformité macOS (**Conformité de l’appareil** > **Stratégies** > **Créer une stratégie** > **Plateforme : macOS** > **Sécurité du système**), de nouveaux paramètres **Pare-feu** sont disponibles : 
- **Pare-feu** : configurez la façon dont les connexions entrantes sont traitées dans votre environnement.
- **Connexions entrantes** : **Bloquer** toutes les connexions entrantes, à l’exception de celles nécessaires aux services Internet de base, par exemple DHCP, Bonjour et IPsec. Ce paramètre bloque également tous les services de partage.
- **Mode furtif** : **Activer** le mode furtif pour empêcher l’appareil de répondre aux demandes de sondage. L’appareil continue de répondre aux requêtes entrantes des applications autorisées.

S’applique à : macOS 10.12 et versions ultérieures

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Utiliser SamAccountName comme nom d’utilisateur de compte pour les profils de messagerie <!-- 1500307 -->

Vous pouvez utiliser le **SamAccountName** local comme nom d’utilisateur de compte pour les profils de messagerie pour Android, iOS et Windows 10. Vous pouvez également obtenir le domaine à partir de l’attribut `domain` ou `ntdomain` dans Azure Active Directory (Azure AD). Il est également possible d’entrer un domaine statique personnalisé.

Pour utiliser cette fonctionnalité, vous devez synchroniser l’attribut `sAMAccountName` de votre environnement Active Directory local avec Azure AD.

S’applique à : Android, iOS et Windows 10 et versions ultérieures

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Exiger un code secret non biométrique au lancement de l’application et après un délai d’expiration <!-- 1506985 -->

En exigeant un code secret non biométrique au lancement de l’application et après un délai d’expiration spécifié par l’administrateur, Intune offre une sécurité renforcée pour les applications compatibles avec la gestion des applications mobiles (MAM) en limitant l’utilisation de l’identification biométrique pour l’accès aux données d’entreprise. Les paramètres affectent les utilisateurs qui s’appuient sur Touch ID (iOS), Face ID (iOS), Android Biométrique ou d’autres méthodes d’authentification biométriques à venir pour accéder à leurs applications compatibles APP/MAM. Ces paramètres permettent aux administrateurs Intune d’avoir un contrôle plus précis sur l’accès utilisateur, en supprimant les cas où un appareil avec plusieurs empreintes digitales ou d’autres méthodes d’accès biométriques peut révéler des données d’entreprise à un utilisateur inapproprié. Dans le portail Azure, ouvrez **Microsoft Intune**. Sélectionnez **Applications mobiles** > **Stratégies de protection des applications** > **Ajouter une stratégie** > **Paramètres**. Recherchez la section **Accès** pour des paramètres spécifiques.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Réinitialisation sélective des données d’application de l’organisation <!-- 1507030 -->
Les administrateurs peuvent configurer une réinitialisation sélective des données de l’organisation comme une nouvelle action quand les conditions des paramètres d’accès APP (stratégies de protection d’application) ne sont pas remplies.  Cette fonctionnalité permet aux administrateurs de protéger et de supprimer automatiquement des données d’entreprise sensibles dans des applications en fonction de critères préconfigurés.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Révocation d’une application iOS achetée par le biais d’un programme VPP <!-- 1777384 -->
En tant qu’administrateur Microsoft Intune, vous pouvez révoquer la licence pour une application iOS sélectionnée achetée via le programme d’achat en volume (VPP). Vous pouvez notifier les utilisateurs quand une application ne leur est plus affectée. La révocation d’une licence d’application ne désinstalle pas l’application VPP de l’appareil. Pour désinstaller une application VPP, vous devez remplacer l’action d’attribution par **Désinstaller**. Le nombre de licences récupérées est répercutée dans le nœud **Applications sous licence** dans la charge de travail **Application** d’Intune. Pour plus d’informations sur les applications VPP iOS, consultez [Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune](vpp-apps-ios.md).

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Modules linguistiques Office 365 Pro Plus <!-- 1833450 -->
En tant qu’administrateur Intune, vous pouvez déployer des langues supplémentaires pour les applications Office 365 Pro Plus gérées par le biais d’Intune. La liste des langues disponibles inclut le **Type** du module linguistique (principal, partiel et de vérification). Dans le portail Azure, sélectionnez **Microsoft Intune** > **Applications mobiles** > **Applications** > **Ajouter**. Dans la liste **Type d’application** du panneau **Ajouter une application**, sélectionnez **Windows 10** sous la **Suite Office 365**. Sélectionnez **Langues** dans le panneau **Paramètres de la suite d’applications**.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>Révoquer une licence d’application VPP iOS <!-- 1863797 -->
En tant qu’administrateur, vous pouvez récupérer une licence d’application VPP iOS attribuée à un utilisateur ou un appareil. Désinstaller une application VPP iOS vous permet également de récupérer la licence de l’application. Vous pouvez ensuite choisir d’attribuer la licence de l’application à un autre utilisateur ou appareil. Pour plus d’informations sur les licences d’application VPP iOS, consultez [Gérer les applications iOS achetées en volume dans Microsoft Intune](vpp-apps-ios.md).

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nouvelle mise à jour de l’expérience utilisateur du site web Portail d’entreprise<!--2000968 -->
En nous basant sur les commentaires que nous ont envoyés des clients, nous ajoutons de nouvelles fonctionnalités au site web Portail d’entreprise. Vous allez constater une nette amélioration des fonctionnalités existantes et de la facilité d’utilisation dans vos appareils Android, iOS et Windows. Les différentes zones du site, telles que les détails de l’appareil, les commentaires et le support, ainsi que la vue d’ensemble de l’appareil, vont bénéficier d’une nouvelle présentation interactive et moderne. Vous découvrirez également les points suivants :

- Flux de travail simplifiés sur toutes les plateformes d’appareils
- Flux d’identification et d’inscription des appareils améliorés
- Plus de messages d’erreur utiles
- Langage plus convivial, avec moins de jargon technique
- Possibilité de partager des liens directs vers les applications
- Performances améliorées des grands catalogues d’applications
- Accessibilité accrue pour tous les utilisateurs

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Modifier vos déploiements d’applications Office 365 Pro Plus <!-- 2150145 -->
En tant qu’administrateur Microsoft Intune, vous avez une plus grande capacité de modification de vos déploiements d’applications Office 365 Pro Plus. Dans le portail Azure, sélectionnez **Microsoft Intune** > **Applications mobiles** > **Applications**. Dans la liste des applications, sélectionnez votre suite Office 365 Pro Plus.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Consultation par ligne des identificateurs d’appareil d’entreprise en double chargés <!-- 2203794 -->
Lors du chargement d’ID d’appareils d’entreprise, Intune fournit une liste de tous les doublons et vous donne la possibilité de remplacer ou de conserver les informations existantes. Le rapport s’affiche s’il existe des doublons après avoir choisi **Inscription de l’appareil** > **Identificateurs d’appareil d’entreprise** > **Ajouter des identificateurs**. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Ajouter manuellement des identificateurs d’appareil d’entreprise <!-- 2203803 -->
Vous pouvez ajouter manuellement des ID d’appareil d’entreprise. Dans **Inscription de l’appareil** > **Identificateurs d’appareils d’entreprise** > **Ajouter**.

### <a name="new-status-for-devices-in-device-configuration----2308882---"></a>Nouveaux états pour les appareils de la configuration de l’appareil <!-- 2308882 -->
Dans **Configuration de l’appareil** > **Vue d’ensemble**, les nouveaux états suivants sont ajoutés :
- réussi
- erreur
- conflit
- en attente
- non applicable. Une image indiquant le nombre d’appareils d’une autre plateforme est également affichée. Par exemple, si vous regardez un profil iOS, la nouvelle vignette indique le nombre d’appareils non iOS qui sont également attribués à ce profil. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>La conformité de l’appareil prend en charge les solutions antivirus tierces <!-- 2325484 -->
Quand vous créez une stratégie de conformité des appareils (**Conformité de l’appareil** > **Stratégies** > **Créer une stratégie** > **Plateforme : Windows 10 et versions ultérieures** > **Paramètres** > **Sécurité du système**), il existe de nouvelles options **Sécurité de l’appareil** : 
- **Antivirus** : quand la valeur définie est **Exiger**, vous pouvez vérifier la conformité en utilisant des solutions antivirus inscrites auprès du Centre de sécurité Windows, comme Symantec. 
- **Logiciel anti-espion** : quand la valeur définie est **Exiger**, vous pouvez vérifier la conformité en utilisant des solutions de logiciel anti-espion inscrites auprès du Centre de sécurité Windows, comme Symantec. 

S’applique à : Windows 10 et versions ultérieures 

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Prise en charge des profils de VPN Palo Alto Networks GlobalProtect <!-- 1333680 eeready ! -->

Avec cette mise à jour, vous pouvez choisir Palo Alto Networks GlobalProtect comme type de connexion VPN pour les profils VPN dans Intune (**Configuration de l’appareil** > **Profils** > **Créer un profil** > **Type de profil** > **VPN**). Dans cette version, les plateformes suivantes sont prises en charge : 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Définir la conformité par emplacement de l’appareil <!-- 851881 ! -->
Dans certains cas, vous souhaiterez peut-être limiter l’accès aux ressources d’entreprise à un emplacement spécifique, défini par une connexion réseau. Vous pourrez créer une stratégie de conformité (**Conformité de l’appareil** > **Emplacements**) en fonction de l’adresse IP de l’appareil. Si l’appareil bascule en dehors de la plage IP, il ne peut plus accéder aux ressources d’entreprise.

S’applique à : appareils Android 6.0 et ultérieur, avec l’application Portail d’entreprise mise à jour

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Amélioration de la résolution des problèmes d’installation des applications <!-- 928990 -->
Sur les appareils gérés par MDM Microsoft Intune, les installations d’applications peuvent parfois échouer. Quand ces installations d’applications échouent, il peut être difficile de comprendre la raison de l’échec ou de résoudre le problème. Nous publions une préversion publique de nos fonctionnalités de résolution des problèmes d’application. Vous remarquerez sous chaque appareil un nouveau nœud appelé **Applications gérées**. Il liste les applications qui ont été distribuées via MDM Intune. À l’intérieur du nœud figure une liste d’états d’installations d’applications. Si vous sélectionnez une application, vous verrez la vue de résolution des problèmes de cette application spécifique. Dans la vue de résolution des problèmes, vous verrez le cycle de vie de bout en bout de l’application, par exemple quand l’application a été créée, modifiée, ciblée et remise à un appareil. De plus, si l’installation de l’application a échoué, vous verrez le code d’erreur et un message utile sur la cause de l’erreur.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Exiger un code secret non biométrique au lancement à froid de l’application et après un délai d’expiration <!-- 1506985 --> 

En exigeant un code secret non biométrique au lancement à froid de l’application et après un délai d’expiration spécifié par l’administrateur, Intune offre une sécurité renforcée pour les applications compatibles avec la gestion des applications mobiles (MAM) en limitant l’utilisation de l’identification biométrique pour l’accès aux données d’entreprise. Les paramètres affectent les utilisateurs qui s’appuient sur Touch ID (iOS), Face ID (iOS), Android Biométrique ou d’autres méthodes d’authentification biométriques à venir pour accéder à leurs applications compatibles APP/MAM. Ces paramètres permettent aux administrateurs Intune d’avoir un contrôle plus précis sur l’accès utilisateur, en supprimant les cas où un appareil avec plusieurs empreintes digitales ou d’autres méthodes d’accès biométriques peut révéler des données d’entreprise à un utilisateur inapproprié. Dans le portail Azure, ouvrez **Microsoft Intune**. Sélectionnez **Applications mobiles** > **Stratégies de protection des applications** > **Ajouter une stratégie** > **Paramètres**. Recherchez la section **Accès** pour des paramètres spécifiques.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>Bloquer l’accès à l’application en fonction des modèles et des fournisseurs d’appareils non approuvés  <!-- 1425689 ! -->
L’administrateur informatique Intune pourra appliquer une liste de fabricants Android et/ou de modèles iOS par le biais de stratégies de protection des applications Intune. L’administrateur informatique peut fournir une liste de fabricants (séparés par des points-virgules) pour les stratégies Android et une liste de modèles d’appareils pour les stratégies iOS. Les stratégies de protection des applications Intune concernent uniquement Android et iOS. Deux actions distinctes pourront être effectuées sur cette liste spécifiée :
- Blocage de l’accès à l’application sur les appareils qui ne figurent pas dans la liste, ou
- Réinitialisation sélective des données d’entreprise sur les appareils qui ne figurent pas dans la liste 

L’utilisateur ne peut pas accéder à l’application cible si les conditions requises par la stratégie ne sont pas remplies. En fonction des paramètres, l’utilisateur peut être bloqué ou une réinitialisation sélective de ses données d’entreprise est effectuée dans l’application. Sur les appareils iOS, cette fonctionnalité nécessite la participation des applications (par exemple WXP, Outlook, Managed Browser, Yammer) pour intégrer le kit Intune APP SDK dans le but d’appliquer les paramètres de version minimale dans les applications ciblées. Cette intégration se produit par propagation et dépend des équipes d’application spécifiques. Sur Android, cette fonctionnalité nécessite la version la plus récente du portail d’entreprise. 

Sur les appareils de l’utilisateur final, le client Intune effectuerait une action sur la base d’une mise en correspondance simple des chaînes spécifiées dans le panneau Intune pour les stratégies de protection d’application. Cela dépend entièrement de la valeur signalée par l’appareil. Par conséquent, il est conseillé à l’administrateur informatique de vérifier que le comportement prévu est exact. Pour ce faire, vous pouvez tester ce paramètre en ciblant différents fabricants d’appareils et modèles sur un petit groupe d’utilisateurs. Dans Microsoft Intune, sélectionnez **Applications mobiles** > **Stratégies de protection des applications** pour afficher et ajouter des stratégies de protection des applications. Pour plus d’informations sur les stratégies de protection d’application, consultez [Que sont les stratégies de protection des applications](app-protection-policy.md).

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Activer le mode kiosque sur les appareils Windows 10 <!-- 1560072 ! -->
Sur les appareils Windows 10, vous pouvez créer un profil de configuration et activer le mode kiosque (**Configuration de l’appareil** > **Profils** > **Créer un profil** > **Windows 10** > **Restrictions de l’appareil** > **Kiosque**). Dans cette mise à jour, le paramètre **Kiosque (préversion)** est renommé **Kiosque (obsolète)**. **Kiosque (obsolète)** n’est plus recommandé, mais continuera à fonctionner jusqu’à la mise à jour de juillet. **Kiosque (obsolète)** est remplacé par le nouveau type de profil **Kiosque** (**Créer un profil** > **Windows 10** > **Kiosque (préversion)**), qui contiendra les paramètres permettant de configurer des kiosques sur Windows 10 RS4 et ultérieur.

S’applique à Windows 10 et versions ultérieures.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>Récupérer l’ID de modèle utilisateur de l’application associé (AUMID) pour les applications Microsoft Store pour Entreprises en mode kiosque <!-- 1560077 ! -->
Intune pourra récupérer les ID de modèle utilisateur de l’application (AUMID) pour les applications Microsoft Store pour Entreprises afin de fournir une configuration améliorée du profil Kiosque.

Pour plus d’informations sur les applications Microsoft Store pour Entreprises, consultez [Gérer des applications à partir du Microsoft Store pour Entreprises](windows-store-for-business.md).

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Actions d’accès pour les stratégies de protection des applications <!-- 1483510 EEready -->
Vous pourrez bientôt configurer des stratégies de protection des applications afin de réinitialiser explicitement, de bloquer ou d’avertir les appareils non conformes. La nouvelle action *Réinitialiser* supprime d’un appareil les données d’entreprise de votre société. Si une réinitialisation se produit, l’utilisateur de l’appareil est informé de la raison de la réinitialisation et des étapes de correction. Pour certains paramètres, comme la version minimale du système d’exploitation, vous pourrez appliquer plusieurs actions telles que le blocage et la réinitialisation. Ces actions sont déclenchées quand l’application est lancée.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nouvelles informations d’inventaire pour les appareils Windows <!-- 1333569 eeready -->

Pour les appareils Windows, les informations d’inventaire suivantes seront disponibles par appareil sous l’onglet **Matériel** (**Groupes** > **Tous les appareils mobiles** > **Appareils** > choisissez l’appareil de l’utilisateur > **Afficher les propriétés** > **Matériel**) :
- TPM
- Intégration antivirus
- Logiciel anti-espion
- Pare-feu
- Contrôle de compte d’utilisateur
- Batterie
- Nom du domaine

Pour plus d’informations sur la façon dont ces données sont récupérées par le fournisseur de services de configuration, consultez les entrées DeviceStatus dans l’article [Fournisseur de services de configuration DeviceStatus](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp).

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune et le navigateur Microsoft Edge <!-- 1818969 -->
Le navigateur Microsoft Edge pour les appareils mobiles (iOS et Android) prend désormais en charge les stratégies de protection des applications Intune. Les utilisateurs qui se connectent avec leur compte d’entreprise Azure AD dans l’application de navigateur Edge sont protégés par Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nouveau paramètre de langue/région lors de la configuration OOBE pour AutoPilot <!-- 1821766 -->
Un nouveau paramètre de configuration sera disponible pour définir la langue et la région des profils AutoPilot pendant l’expérience OOBE (Out of Box Experience).

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nouveau paramètre de configuration du clavier de l’appareil <!-- 1821768 -->
Un nouveau paramètre sera disponible pour configurer le clavier pour les profils AutoPilot pendant l’expérience OOBE.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>Utiliser TeamViewer pour partager l’écran des appareils iOS et MacOS <!-- 1985547 -->
Actuellement, vous pouvez utiliser TeamViewer pour administrer à distance les [appareils Android et Windows gérés par Intune](device-profile-android-teamviewer.md).

Les administrateurs pourront se connecter à TeamViewer et démarrer une session de partage d’écran avec des appareils iOS et macOS. Les utilisateurs d’iPhone, iPad et macOS pourront partager leurs écrans en direct avec tout autre appareil de bureau ou portable. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>Le graphique utilisateur des profils d’appareil est de retour <!-- 2160133 -->
Tout en améliorant les chiffres indiqués sur le graphique des profils d’appareil (**Configuration de l’appareil** > **Profils** > sélectionnez un profil existant > **Vue d’ensemble** ), le graphique utilisateur avait été supprimé temporairement.

Avec cette mise à jour, le graphique utilisateur est de retour et affiché dans le portail Azure.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Affecter tous les utilisateurs et tous les appareils en tant que groupes d’étendue <!-- 2196803 -->
Vous pourrez affecter tous les utilisateurs, tous les appareils, et tous les utilisateurs et tous les appareils dans des groupes d’étendue. Pour ce faire, choisissez **Rôles Intune** > **Tous les rôles** > **Gestionnaire de stratégie et de profils** > **Affectations**  > choisissez une affectation > **Étendue (Groupes)**.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Déplacement des profils AutoPilot vers le ciblage de groupe <!-- 1877935 -->
Actuellement, vous pouvez attribuer des profils de déploiement AutoPilot à des appareils sélectionnés. Une fois cette fonctionnalité publiée, voici ce que vous devrez faire pour affecter ces profils :
- Créer des groupes (Azure AD) contenant des appareils AutoPilot
- Affecter les profils souhaités à un groupe Azure AD. Le profil AutoPilot sera désormais attribué aux appareils AutoPilot dans ce groupe.

### <a name="management-name-field-will-be-editable----1875989---"></a>Le champ de nom de gestion sera modifiable <!-- 1875989 -->
Vous pourrez modifier le champ de nom de gestion dans le panneau **Propriétés** d’un appareil. Pour modifier ce champ, choisissez **Appareils** > **Tous les appareils** > choisissez l’appareil > **Propriétés**. Vous pouvez utiliser le champ de nom de gestion pour identifier un appareil de manière unique.

<!-- 1804 start -->

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Ajouts aux paramètres Options de sécurité locales de l’appareil <!-- 1403702 -->
Vous pourrez configurer des paramètres Options de sécurité locales de l’appareil pour les appareils Windows 10. Des paramètres supplémentaires seront disponibles dans les domaines Client réseau Microsoft, Serveur réseau Microsoft, de l’accès et la sécurité réseau, ainsi que de l’ouverture de session interactive. Recherchez ces paramètres dans la catégorie Endpoint Protection quand vous créez une stratégie de configuration d’appareil Windows 10.

### <a name="rules-for-removing-devices----1609459---"></a>Règles de suppression des appareils <!-- 1609459 -->
De nouvelles règles seront disponibles pour vous permettre de supprimer automatiquement les appareils qui n’ont fait l’objet d’aucun archivage pendant un nombre de jours défini par vous-même. Pour voir la nouvelle règle, accédez au volet **Intune**, sélectionnez **Appareils**, puis sélectionnez **Règles de suppression d’appareil**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Empêcher l’installation d’applications et d’expériences consommateur sur les appareils AutoPilot Windows 10 Entreprise RS4 <!-- 1621980 -->
Vous pourrez empêcher l’installation d’applications et d’expériences consommateur sur vos appareils AutoPilot Windows 10 Entreprise RS4. Pour voir cette fonctionnalité, accédez à **Intune** > **Inscription de l’appareil** > **Inscription Windows** > **Profils Windows AutoPilot** > **Créer** > **Paramètres d’inscription**. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Prise en charge de connecteurs Exchange multiples <!-- 2070451 -->

Vous ne serez plus limité à un seul connecteur Exchange Microsoft Intune par client. Intune prendra en charge plusieurs connecteurs Exchange afin que vous puissiez configurer l’accès conditionnel Intune avec plusieurs organisations Exchange locales.

Avec un connecteur Exchange local Intune, vous pouvez gérer l’accès de l’appareil aux boîtes aux lettres Exchange locales en fonction de l’inscription ou non d’un appareil dans Intune et de sa conformité aux stratégies de conformité Intune. Pour configurer un connecteur, téléchargez le connecteur Exchange local Intune à partir du portail Azure et installez-le sur un serveur de votre organisation Exchange. Dans le tableau de bord Microsoft Intune, choisissez **Accès local**, puis sous **Installation**, choisissez **Connecteur Exchange ActiveSync**. Téléchargez le connecteur Exchange local et installez-le sur un serveur de votre organisation Exchange. Maintenant que vous n’êtes plus limité à un seul connecteur Exchange par client, si vous avez d’autres organisations Exchange, vous pouvez suivre le même processus pour télécharger et installer un connecteur pour chaque organisation Exchange supplémentaire.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Possibilité de déployer les applications métier requises pour tous les utilisateurs sur les appareils Windows 10 Desktop <!-- 1627835 RS4 -->
Les clients pourront déployer les applications Windows 10 métier requises à installer dans les contextes d’appareils. Ces applications seront alors disponibles pour tous les utilisateurs sur l’appareil. Seuls les appareils Windows 10 Desktop sont concernés.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inscription par le biais de l’application Portail d’entreprise améliorée <!-- 1874230-->
Les utilisateurs qui s’inscrivent à l’aide du Portail d’entreprise sur Windows 10 build 1703 et supérieure pourront effectuer la première étape de l’inscription sans quitter l’application.

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



