---
title: Édition préliminaire
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b003fde011fd3a727c7c7a163fedb1dae6779425
ms.sourcegitcommit: 407191a92ef356a3d196b6f9959b9b033190ca2c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2018
---
# <a name="the-early-edition-for-microsoft-intune---april-2018"></a>Édition préliminaire pour Microsoft Intune - Avril 2018

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

<!-- 1804 start -->

### <a name="show-caller-id-in-personal-profile---android-for-work---1098984---"></a>Afficher l’ID d’appelant dans un profil personnel - Android for Work <!--1098984 -->
Quand vous utilisez un profil personnel sur un appareil, les utilisateurs finaux ne voient pas forcément les détails relatifs à l’ID d’appelant d’un contact professionnel. 

Avec cette mise à jour, il existe un nouveau paramètre dans **Android for Work** > **Restrictions sur l’appareil** > **Paramètres du profil professionnel** :
- Afficher l’ID d’appelant du contact professionnel dans le profil personnel

Quand ce paramètre est activé (non configuré), les détails de l’ID d’appelant du contact professionnel sont affichés dans le profil personnel. Quand ce paramètre est désactivé, le numéro d’appelant du contact professionnel ne s’affiche pas dans le profil personnel. 

S’applique aux appareils avec profil professionnel Android pour le système d’exploitation Android v6.0 et les versions ultérieures

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252-----from-1802--"></a>Nouveaux paramètres Windows Defender Credential Guard ajoutés aux paramètres Endpoint Protection <!--1102252 --><!--from 1802-->

De nouveaux paramètres [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard) seront ajoutés à **Configuration de l’appareil** > **Profils** > **Endpoint Protection**. Les paramètres suivants seront ajoutés :

- Niveau de sécurité de plateforme : spécifiez si le niveau de sécurité de plateforme est activé lors du prochain redémarrage. La sécurité basée sur la virtualisation nécessite un démarrage sécurisé. La sécurité basée sur la virtualisation peut éventuellement être activée avec l’utilisation de protections d’accès direct à la mémoire (DMA). Les protections DMA nécessitent une prise en charge matérielle et ne seront activées que sur des appareils configurés correctement.
- Sécurité basée sur la virtualisation : spécifiez si la sécurité basée sur la virtualisation est activée lors du prochain redémarrage.
- Windows Defender Credential Guard : activez Credential Guard avec la sécurité basée sur la virtualisation pour protéger les informations d’identification au prochain redémarrage quand le niveau de sécurité de plateforme avec un démarrage sécurisé et la sécurité basée sur la virtualisation sont tous deux activés. Les options disponibles sont notamment **Désactivé**, **Activé avec le verrouillage UEFI**, **Activé sans verrouillage** et **Non configuré**.
  - L’option « Désactivé » désactive Credential Guard à distance s’il a été préalablement activé avec l’option « Activé sans verrouillage ».

  - L’option « Activé avec le verrouillage UEFI » garantit que Credential Guard ne peut pas être désactivé avec une clé de Registre ni en utilisant une stratégie de groupe. Pour désactiver Credential Guard après avoir utilisé ce paramètre, vous devez définir la stratégie de groupe sur « Désactivé » et supprimer la fonction de sécurité de chaque ordinateur, avec un utilisateur présent physiquement, afin d’effacer la configuration incluse dans UEFI. Tant que la configuration UEFI persiste, Credential Guard est activé.

  - L’option « Activé sans verrouillage » permet de désactiver Credential Guard à distance à l’aide d’une stratégie de groupe. Les appareils utilisant ce paramètre doivent exécuter au moins Windows 10 (version 1511).

  - L’option « Non configuré » laisse le paramètre de stratégie non défini. La stratégie de groupe n’écrit pas le paramètre de stratégie dans le Registre et il n’a donc pas d’impact sur les ordinateurs ou les utilisateurs. Si un paramètre existe dans le Registre, il n’est pas modifié.

### <a name="passcode-support-for-mam-pin-on-android---1438086---"></a>Prise en charge des codes secrets pour les codes PIN MAM sur Android<!-- 1438086 -->

Les administrateurs Intune pourront définir une exigence de lancement d’application pour appliquer un code secret au lieu d’un code PIN MAM numérique. Selon la configuration, l’utilisateur doit définir et utiliser un code secret quand il y est invité avant d’obtenir l’accès à des applications compatibles MAM. Un code secret est défini comme un code PIN numérique avec au moins un caractère spécial ou une lettre majuscule/minuscule. Intune prend en charge un code secret comme le code PIN numérique existant, pouvant définir une longueur minimale et autorisant la répétition des caractères et des séquences par le biais de la console d’administration. Cette fonctionnalité nécessite la version la plus récente du Portail d’entreprise sur Android. Cette fonctionnalité est déjà disponible pour iOS.

###  <a name="block-camera-and-screen-captures-on-android-for-work----1098977-eeready--"></a>Blocage des appareils photo et des captures d’écran sur Android for Work <!-- 1098977 eeready-->
Vous disposerez de deux nouvelles propriétés de blocage au moment de configurer des restrictions d’appareil pour les appareils Android : 
- Appareil photo : bloque l’accès à tous les appareils photo sur l’appareil
- Capture d’écran : bloque la capture d’écran et empêche également que le contenu soit affiché sur les écrans dépourvus de sortie vidéo sécurisée

S’applique à Android for Work.

### <a name="line-of-business-lob-app-support-for-macos----1473977---"></a>Prise en charge des applications métier pour macOS <!-- 1473977 -->
Microsoft Intune permettra d’installer des applications métier macOS à partir du portail Azure. Vous pourrez ajouter une application métier macOS à Intune après qu’elle a été prétraitée par l’outil disponible dans GitHub. Dans le portail Azure, choisissez **Applications mobiles** à partir du panneau **Intune**. Dans le panneau **Applications mobiles**, choisissez **Applications** > **Ajouter**. Dans le panneau **Ajouter une application**, sélectionnez **Application métier**. 

### <a name="support-for-user-less-devices----1637553---"></a>Prise en charge des appareils sans utilisateurs <!-- 1637553 -->
Intune permettra d’évaluer la conformité sur un appareil sans utilisateur, comme Microsoft Surface Hub. La stratégie de conformité peut cibler des appareils spécifiques. Ainsi, la conformité, et la non-conformité, peuvent être déterminées pour les appareils auxquels aucun utilisateur n’est associé.

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Ajouts aux paramètres Options de sécurité locales de l’appareil <!-- 1403702 -->
Vous pourrez configurer des paramètres Options de sécurité locales de l’appareil pour les appareils Windows 10. Des paramètres supplémentaires seront disponibles dans les domaines Client réseau Microsoft, Serveur réseau Microsoft, de l’accès et la sécurité réseau, ainsi que de l’ouverture de session interactive. Recherchez ces paramètres dans la catégorie Endpoint Protection quand vous créez une stratégie de configuration d’appareil Windows 10.

### <a name="require-installation-of-policies-apps-certificate-and-network-profiles----1553555---"></a>Nécessitent l’installation de stratégies, d’applications et de profils de certificat et de réseau <!-- 1553555 -->
Les administrateurs pourront empêcher les utilisateurs finaux d’accéder au bureau Windows 10 RS4 jusqu’à ce qu’Intune installe les stratégies, les applications et les profils de certificat et de réseau pendant le provisionnement des appareils AutoPilot.

### <a name="rules-for-removing-devices----1609459---"></a>Règles de suppression des appareils <!-- 1609459 -->
De nouvelles règles seront disponibles pour vous permettre de supprimer automatiquement les appareils qui n’ont fait l’objet d’aucun archivage pendant un nombre de jours défini par vous-même. Pour voir la nouvelle règle, accédez au volet **Intune**, sélectionnez **Appareils**, puis sélectionnez **Règles de suppression d’appareil**.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>Empêcher l’installation d’applications et d’expériences consommateur sur les appareils AutoPilot Windows 10 Entreprise RS4 <!-- 1621980 -->
Vous pourrez empêcher l’installation d’applications et d’expériences consommateur sur vos appareils AutoPilot Windows 10 Entreprise RS4. Pour voir cette fonctionnalité, accédez à **Intune** > **Inscription de l’appareil** > **Inscription Windows** > **Profils Windows AutoPilot** > **Créer** > **Paramètres d’inscription**. 

### <a name="advanced-threat-protection-integrated-with-intune----1629303---"></a>Advanced Threat Protection intégré à Intune <!-- 1629303 -->
[Protection avancée contre les menaces (ATP)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection) indique le niveau de risque des appareils Windows 10. Quand Intune évalue la conformité des appareils Windows 10, le score de risque ATP est inclus dans cette évaluation. Vous pouvez utiliser ATP avec l’accès conditionnel pour renforcer la protection de votre réseau.

### <a name="new-enrollment-steps-for-users-on-devices-with-macos-high-sierra-10132---1734567---"></a>Nouvelles étapes d’inscription pour les utilisateurs sur les appareils dotés de macOS High Sierra 10.13.2+ <!--1734567 -->
macOS High Sierra 10.13.2 a introduit le concept d’inscription MDM « approuvée par l’utilisateur ». À l’avenir, les inscriptions approuvées permettront à Intune de gérer certains paramètres sensibles du point de vue de la sécurité. Pour plus d’informations, consultez la documentation de prise en charge d’Apple ici : https://support.apple.com/HT208019.

Les appareils inscrits à l’aide du Portail d’entreprise macOS seront considérés comme « non approuvés par l’utilisateur », sauf si l’utilisateur final ouvre les préférences système et fournit une approbation manuellement. À cette fin, le Portail d’entreprise macOS invite désormais les utilisateurs sur macOS 10.13.2 et ultérieur à approuver manuellement leur inscription à la fin du processus d’inscription. La console d’administration Intune indiquera si un appareil inscrit est approuvé par l’utilisateur.

### <a name="delete-autopilot-devices----1713650---"></a>Supprimer les appareils AutoPilot <!-- 1713650 -->
Les administrateurs Intune pourront supprimer les appareils AutoPilot.

### <a name="built-in-all-users-and-all-devices-group-for-android-for-work-afw-app-assignment----1813073---"></a>Intégration des groupes Tous les utilisateurs et Tous les appareils pour l’affectation d’applications Android for Work (AFW) <!-- 1813073 -->
Vous pourrez tirer parti des groupes intégrés **Tous les utilisateurs** et **Tous les appareils** pour l’affectation d’applications AFW. Pour plus d’informations, consultez [Inclure et exclure des affectations d’applications dans Microsoft Intune](apps-inc-exl-assignments.md).

### <a name="improved-device-deletion-experience---1832333---"></a>Amélioration de l’expérience de suppression d’appareil <!--1832333 -->
Vous n’aurez plus besoin de supprimer les données d’entreprise ou de réinitialiser un appareil aux paramètres d’usine avant de le supprimer d’Intune.

Pour voir la nouvelle expérience, connectez-vous à Intune et sélectionnez **Appareils** > **Tous les appareils** > nom de l’appareil > **Supprimer**.

 Si vous souhaitez toujours la confirmation de réinitialisation/mise hors service, vous pouvez suivre le cycle de vie d’appareil standard en utilisant les commandes **Supprimer les données d’entreprise** et **Réinitialisation aux paramètres d’usine** avant la commande **Supprimer**. 

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>Déplacement des profils AutoPilot vers le ciblage de groupe <!-- 1877935 -->
Actuellement, vous pouvez attribuer des profils de déploiement AutoPilot à des appareils sélectionnés. Vers la fin du mois d’avril, voici les étapes que vous suivrez pour affecter ces profils :
- Créer des groupes (Azure AD) contenant des appareils AutoPilot
- Affecter les profils souhaités à un groupe Azure AD. Le profil AutoPilot sera désormais attribué aux appareils AutoPilot dans ce groupe.

### <a name="play-sounds-on-ios-when-in-lost-mode----1629303---"></a>Lire les sons sur iOS en mode Perdu <!-- 1629303 -->
Quand les appareils iOS supervisés sont en [mode Perdu](device-lost-mode.md) MDM (Mobile Device Management), vous pouvez lire un son (**Appareils** > **Tous les appareils** > sélectionnez un appareil iOS > **Vue d’ensemble** > **Plus**). La lecture du son se poursuit jusqu’à ce que l’appareil soit retiré du mode Perdu ou qu’un utilisateur désactive le son sur l’appareil. S’applique aux appareils iOS 9.3 et ultérieur.

### <a name="intune-will-reinstall-required-apps-that-are-uninstalled-by-users----1947010---"></a>Intune réinstalle les applications nécessaires qui sont désinstallées par les utilisateurs <!-- 1947010 -->
Si un utilisateur final désinstalle une application obligatoire, Intune la réinstalle automatiquement en moins de 24 heures au lieu d’attendre le cycle de réévaluation de 7 jours.

### <a name="use-a-custom-subject-name-on-scep-certificate----2064190---"></a>Utiliser un nom d’objet personnalisé sur le certificat SCEP <!-- 2064190 -->
Vous pourrez utiliser le nom courant **OnPremisesSamAccountName** dans un objet personnalisé sur un profil de certificat SCEP. Par exemple, vous pouvez utiliser `CN={OnPremisesSamAccountName})`.

### <a name="send-diagnostic-reports-in-company-portal-app-for-macos----2216677---"></a>Envoyer des rapports de diagnostic dans l’application Portail d’entreprise pour macOS <!-- 2216677 -->
L’application Portail d’entreprise pour les appareils macOS sera mise à jour pour améliorer la façon dont les utilisateurs signalent les erreurs relatives à Intune. À partir de l’application Portail d’entreprise, vos employés pourront :
- Charger des rapports de diagnostic directement remis à l’équipe de développement Microsoft.
- Envoyer par e-mail un ID d’incident à l’équipe de support informatique de votre entreprise.

### <a name="always-on-vpn-for-windows-10---1333666---"></a>VPN Always On pour Windows 10 <!--1333666 -->

Actuellement, [Always On](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-auto-trigger-profile#always-on) peut être utilisé sur les appareils Windows 10 à l’aide d’un profil de réseau privé virtuel (VPN) personnalisé créé à l’aide d’OMA-URI.

Avec cette mise à jour, les administrateurs pourront activer les profils VPN Always On pour Windows 10 directement dans Intune au sein du portail Azure. Les profils VPN Always On se connecteront automatiquement :

- À la connexion des utilisateurs à leurs appareils
- Au changement du réseau sur l’appareil
- À la réactivation de l’écran de l’appareil

### <a name="improved-error-messaging-for-apple-mdm-push-certificate-upload-failure----2172331---"></a>Amélioration des messages d’erreur liés à l’échec du chargement du certificat Push MDM Apple <!-- 2172331 -->

Le message d’erreur expliquera que le même ID Apple doit être utilisé au moment du renouvellement d’un certificat MDM existant.

###  <a name="device-profile-chart-and-status-list-show-all-devices-in-a-group----1449153-eeready---"></a>Le graphique des profils d’appareil et la liste d’états affichent tous les appareils contenus dans un groupe <!-- 1449153 eeready -->
Quand vous configurez un profil d’appareil (**Configuration de l’appareil** > **Profils**), vous choisissez le profil d’appareil, par exemple iOS. Vous affectez ce profil à un groupe qui inclut les appareils iOS et les appareils non-iOS. Le nombre sur le graphique indique que le profil est appliqué aux appareils iOS *et* non-iOS (**Configuration de l’appareil** > **Profils** > sélectionnez un profil existant > **Vue d’ensemble**). Quand vous sélectionnez le graphique sous l’onglet **Vue d’ensemble**, la section **État de l’appareil** liste tous les appareils contenus dans le groupe, au lieu des appareils iOS uniquement. 

Avec cette mise à jour, le graphique (**Configuration de l’appareil** > **Profils** > sélectionnez un profil existant > **Vue d’ensemble**) n’affiche que le nombre associé à un profil d’appareil spécifique. Par exemple, si le profil d’appareil de la configuration s’applique aux appareils iOS, le graphique indique uniquement le nombre des appareils iOS. Quand l’utilisateur sélectionne le graphique et ouvre la section **État de l’appareil**, seuls les appareils iOS sont listés.

Le graphique utilisateur est supprimé le temps que cette mise à jour soit effectuée. 


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

<!-- 1802 start -->

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nouveaux paramètres d’imprimante pour les profils Éducation <!-- 1308900 -->

Pour les profils Éducation, de nouveaux paramètres seront disponibles sous la catégorie **Imprimantes** : **Imprimantes**, **Imprimante par défaut**, **Ajouter de nouvelles imprimantes**.

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


