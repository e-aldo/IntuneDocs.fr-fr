---
title: Édition préliminaire
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f3cbfad85e4a7a97d9bbf98e2ad239fda7cc29e4
ms.sourcegitcommit: d40bfb6af66f2ce7026c0151ace98ec23f1cf76e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/10/2018
---
# <a name="the-early-edition-for-microsoft-intune---may-2018"></a>Édition préliminaire pour Microsoft Intune - Mai 2018

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

<!-- 1805 start -->

### <a name="set-compliance-by-device-location----851881----"></a>Définir la conformité par emplacement de l’appareil <!-- 851881 ! -->
Dans certains cas, vous souhaiterez peut-être limiter l’accès aux ressources d’entreprise à un emplacement spécifique, défini par une connexion réseau. Vous pourrez créer une stratégie de conformité (**Conformité de l’appareil** > **Emplacements**) en fonction de l’adresse IP de l’appareil. Si l’appareil bascule en dehors de la plage IP, il ne peut plus accéder aux ressources d’entreprise.

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Amélioration de la résolution des problèmes d’installation des applications <!-- 928990 -->
Sur les appareils gérés par MDM Microsoft Intune, les installations d’applications peuvent parfois échouer. Quand ces installations d’applications échouent, il peut être difficile de comprendre la raison de l’échec ou de résoudre le problème. Nous publions une préversion publique de nos fonctionnalités de résolution des problèmes d’application. Vous remarquerez sous chaque appareil un nouveau nœud appelé **Applications gérées**. Il liste les applications qui ont été distribuées via MDM Intune. À l’intérieur du nœud figure une liste d’états d’installations d’applications. Si vous sélectionnez une application, vous verrez la vue de résolution des problèmes de cette application spécifique. Dans la vue de résolution des problèmes, vous verrez le cycle de vie de bout en bout de l’application, par exemple quand l’application a été créée, modifiée, ciblée et remise à un appareil. De plus, si l’installation de l’application a échoué, vous verrez le code d’erreur et un message utile sur la cause de l’erreur. 

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
Vous pourrez bientôt configurer des stratégies de protection des applications afin de réinitialiser explicitement, de bloquer ou d’avertir les appareils non conformes. La nouvelle action *Réinitialiser* supprime d’un appareil les données d’entreprise de votre société. Si une réinitialisation se produit, l’utilisateur de l’appareil est informé de la raison de la réinitialisation et des étapes de correction. Pour certains paramètres, comme la version minimale du système d’exploitation, vous pourrez appliquer plusieurs actions telles que le blocage et la réinitialisation.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nouvelles informations d’inventaire pour les appareils Windows <!-- 1333569 eeready -->

Pour les appareils Windows, les informations d’inventaire suivantes seront disponibles par appareil sous l’onglet **Matériel** (**Groupes** > **Tous les appareils mobiles** > **Appareils** > choisissez l’appareil de l’utilisateur > **Afficher les propriétés** > **Matériel**) :
- TPM
- Intégration antivirus
- Logiciel anti-espion
- Pare-feu
- Contrôle de compte d’utilisateur
- Batterie
- Nom du domaine

Pour plus d’informations sur la façon dont ces données sont récupérées par le fournisseur de service de configuration, consultez les entrées DeviceGuard dans l’article [DeviceStatus CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp).

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune et le navigateur Microsoft Edge <!-- 1818969 -->
Le navigateur Microsoft Edge pour les appareils mobiles (iOS et Android) prend désormais en charge les stratégies de protection des applications Intune. Les utilisateurs qui se connectent avec leur compte d’entreprise Azure AD dans l’application de navigateur Edge seront protégés par Intune. 

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
Vous pourrez affecter tous les utilisateurs, tous les appareils, et tous les utilisateurs et tous les appareils dans des groupes d’étendue.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Déplacement des profils AutoPilot vers le ciblage de groupe <!-- 1877935 -->
Actuellement, vous pouvez attribuer des profils de déploiement AutoPilot à des appareils sélectionnés. Une fois cette fonctionnalité publiée, voici ce que vous devrez faire pour affecter ces profils :
- Créer des groupes (Azure AD) contenant des appareils AutoPilot
- Affecter les profils souhaités à un groupe Azure AD. Le profil AutoPilot sera désormais attribué aux appareils AutoPilot dans ce groupe.

### <a name="management-name-field-will-be-editable----1875989---"></a>Le champ de nom de gestion sera modifiable <!-- 1875989 -->
Vous pourrez modifier le champ de nom de gestion dans le panneau **Propriétés** d’un appareil. Pour modifier ce champ, choisissez **Appareils** > **Tous les appareils** > choisissez l’appareil > **Propriétés**. Vous pouvez utiliser le champ de nom de gestion pour identifier un appareil de manière unique.

<!-- 1804 start -->


### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Ajouts aux paramètres Options de sécurité locales de l’appareil <!-- 1403702 -->
Vous pourrez configurer des paramètres Options de sécurité locales de l’appareil pour les appareils Windows 10. Des paramètres supplémentaires seront disponibles dans les domaines Client réseau Microsoft, Serveur réseau Microsoft, de l’accès et la sécurité réseau, ainsi que de l’ouverture de session interactive. Recherchez ces paramètres dans la catégorie Endpoint Protection quand vous créez une stratégie de configuration d’appareil Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Nécessitent l’installation de stratégies, d’applications et de profils de certificat et de réseau <!-- 1553555 -->
Les administrateurs pourront empêcher les utilisateurs finaux d’accéder au bureau Windows 10 RS4 jusqu’à ce qu’Intune installe les stratégies, les applications et les profils de certificat et de réseau pendant le provisionnement des appareils AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Règles de suppression des appareils <!-- 1609459 -->
De nouvelles règles seront disponibles pour vous permettre de supprimer automatiquement les appareils qui n’ont fait l’objet d’aucun archivage pendant un nombre de jours défini par vous-même. Pour voir la nouvelle règle, accédez au volet **Intune**, sélectionnez **Appareils**, puis sélectionnez **Règles de suppression d’appareil**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Empêcher l’installation d’applications et d’expériences consommateur sur les appareils AutoPilot Windows 10 Entreprise RS4 <!-- 1621980 -->
Vous pourrez empêcher l’installation d’applications et d’expériences consommateur sur vos appareils AutoPilot Windows 10 Entreprise RS4. Pour voir cette fonctionnalité, accédez à **Intune** > **Inscription de l’appareil** > **Inscription Windows** > **Profils Windows AutoPilot** > **Créer** > **Paramètres d’inscription**. 

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

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Possibilité de déployer les applications métier requises pour tous les utilisateurs sur les appareils Windows 10 Desktop <!-- 1627835 RS4 -->
Les clients pourront déployer les applications Windows 10 métier requises à installer dans les contextes d’appareils. Ces applications seront alors disponibles pour tous les utilisateurs sur l’appareil. Seuls les appareils Windows 10 Desktop sont concernés.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inscription par le biais de l’application Portail d’entreprise améliorée <!-- 1874230-->
Les utilisateurs qui s’inscrivent à l’aide du Portail d’entreprise sur Windows 10 build 1703 et supérieure pourront effectuer la première étape de l’inscription sans quitter l’application.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>Mise à jour de l’expérience Aide et commentaires sur l’application Portail d’entreprise pour Android <!--1631531 -->

Nous allons mettre à jour l’expérience Aide et commentaires sur l’application Portail d’entreprise pour Android de manière à l’harmoniser avec les bonnes pratiques pour les applications Android. Nous allons mettre à jour l’application Portail d’entreprise pour Android dans les prochains mois de manière à scinder l’élément de menu **Aide et commentaires** en deux éléments distincts **Aide** et **Envoyer des commentaires**. La page **Aide** contiendra une section **Questions fréquentes (FAQ)** et un bouton **Assistance par e-mail** pour amener les utilisateurs finaux à transmettre les journaux à Microsoft et à envoyer un e-mail au service de support de l’entreprise décrivant le problème. L’élément de menu **Envoyer des commentaires** permettra à l’utilisateur d’envoyer des commentaires à Microsoft. L’utilisateur devra choisir entre « J’aime quelque chose », « Je n’aime pas quelque chose » ou « J’ai une idée ».

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Les sites web Azure Active Directory peuvent nécessiter l’application Intune Managed Browser et la prise en charge de l’authentification unique pour Managed Browser (Préversion publique) <!-- 710595 -->   
Avec Azure Active Directory (Azure AD), vous pouvez restreindre l’accès aux sites web sur des appareils mobiles à l’application Intune Managed Browser. Dans Managed Browser, les données de site web restent sécurisées et séparées des données personnelles de l’utilisateur final. Par ailleurs, Managed Browser prend en charge les fonctionnalités d’authentification unique pour les sites protégés par Azure AD. Si vous vous connectez à Managed Browser ou que vous utilisez Managed Browser sur un appareil avec une autre application gérée par Intune, Managed Browser peut accéder aux sites d’entreprise protégés par Azure AD sans que l’utilisateur ne doive entrer ses informations d’identification. Cette fonctionnalité s’applique aux sites comme Outlook Web Access (OWA) et SharePoint Online, ainsi qu’à d’autres sites d’entreprise tels que les ressources intranet accessibles par le proxy de l’application Azure.


## <a name="notices"></a>Remarques

Il n’existe aucun avis actif pour l’instant.

### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
