---
title: "Nouveautés de Microsoft Intune"
titlesuffix: Azure portal
description: "Découvrez les nouveautés du portail Intune Azure"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d5575d02d0c270e9d22e4b858d8fb00753b60448
ms.sourcegitcommit: 5ecb0d6625e6972cc5ccdca7538f41f4aa8da46a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Nouveautés de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Découvrez les nouveautés hebdomadaires dans Microsoft Intune. Vous pouvez également découvrir les [modifications à venir](#whats-coming), les [avis importants](#notices) sur le service et des informations sur les [versions précédentes](whats-new-archive.md).

> [!Note]
> Pour plus d’informations sur les nouvelles fonctionnalités de Gestion des appareils mobiles (MDM) hybride, consultez notre page sur les [Nouveautés pour hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-december-11-2017"></a>Semaine du 11 décembre 2017

### <a name="device-configuration"></a>Configuration des appareils

#### <a name="new-automatic-redeployment-setting----1469168---"></a>Nouveau paramètre de redéploiement automatique <!-- 1469168 -->
Le paramètre **Redéploiement automatique** permet aux utilisateurs avec des droits d’administration de supprimer l’ensemble des données et des paramètres utilisateur à l’aide des touches **Ctrl+Win+R** sur l’écran de verrouillage de l’appareil. L’appareil est automatiquement reconfiguré et réinscrit dans la gestion. Ce paramètre se trouve sous Windows 10 -> Restrictions sur l’appareil -> Général -> Redéploiement automatique. Pour plus d’informations, consultez [Paramètres de restriction d’appareil Intune pour Windows 10](device-restrictions-windows-10.md#general).

#### <a name="support-for-additional-source-editions-in-the-windows-10-edition-upgrade-policy-----903672--1119689---"></a>Prise en charge d’éditions source supplémentaires dans la stratégie de mise à niveau de l’édition Windows 10 <!-- 903672,  1119689 -->
Vous pouvez maintenant utiliser la stratégie de mise à niveau de l’édition Windows 10 pour effectuer une mise à niveau à partir d’autres éditions de Windows 10 (Windows 10 Professionnel, Windows10 Professionnel Éducation, Windows 10 Cloud, etc.). Avant cette version, les chemins de mise à niveau de l’édition pris en charge étaient plus limités. Pour plus d’informations, consultez le [Guide pratique de configuration des mises à niveau Windows 10](edition-upgrade-configure-windows-10.md).

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Nouveaux paramètres pour le profil de configuration d’appareil Windows Defender Security Center (WDSC) <!-- 1335507 -->

Intune ajoute une nouvelle section de paramètres pour le profil de configuration d’appareil, sous la Protection du point de terminaison, nommée **Windows Defender Security Center**. Les administrateurs informatiques peuvent configurer les éléments de base auxquels les utilisateurs finaux de l’application Windows Defender Security Center peuvent accéder. Si un administrateur informatique masque un élément de base dans l’application Windows Defender Security Center, les notifications liées à l’élément de base masqué ne s’affichent pas sur l’appareil de l’utilisateur.

Vous trouverez ci-dessous les éléments de base que les administrateurs peuvent masquer dans les paramètres du profil de configuration d’appareil Windows Defender Security Center :
- Protection contre les menaces et les virus
- Performances et intégrité de l’appareil
- Protections du pare-feu et du réseau
- Contrôle d’application et du navigateur
- Options Famille

Les administrateurs informatiques peuvent également personnaliser les notifications que les utilisateurs reçoivent. Par exemple, vous pouvez décider si les utilisateurs reçoivent toutes les notifications générées par les éléments de base visibles dans WDSC ou uniquement les notifications critiques. Les notifications non critiques incluent des résumés périodiques sur l’activité de l’antivirus Windows Defender et des notifications indiquant lorsque des analyses sont terminées. Toutes les autres notifications sont considérées comme critiques. En outre, vous pouvez aussi personnaliser le contenu même de la notification. Par exemple, vous pouvez fournir les coordonnées du service informatique à inclure dans les notifications qui s’affichent sur les appareils des utilisateurs.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Prise en charge de connecteurs multiples pour le traitement des certificats SCEP et PFX <!-- 1361755 -->

Les clients qui utilisent le connecteur NDES local pour présenter des certificats à des appareils peuvent désormais configurer plusieurs connecteurs dans un seul locataire.

Cette nouvelle fonctionnalité prend en charge le scénario suivant :

- **Haute disponibilité**

Chaque connecteur NDES extraie des demandes de certificat d’Intune.  Si un connecteur NDES a l’état hors connexion, l’autre connecteur peut continuer à traiter les requêtes.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Le nom d’objet du client peut utiliser la variable AAD_DEVICE_ID <!-- 1468599 -->

Lorsque vous créez un profil de certificat SCEP dans Intune, vous pouvez désormais utiliser la variable AAD_DEVICE_ID lorsque vous générez le nom d’objet du client.   Lorsque le certificat est demandé à l’aide de ce profil SCEP, la variable est remplacée par l’ID AAD de l’appareil qui effectue la demande de certificat.


### <a name="device-management"></a>Gestion des appareils

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Gérer les appareils macOS inscrits auprès de Jamf avec le moteur de conformité des appareils d’Intune<!-- 1592747 -->
Vous pouvez utiliser Jamf pour envoyer des informations sur l’état des appareils macOS à Intune, qui évaluera alors la conformité avec les stratégies définies dans la console Intune. En fonction de cet état et d’autres conditions (notamment, l’emplacement, les risques de l’utilisateur, etc.), l’accès conditionnel appliquera des stratégies de conformité aux appareils macOS qui accèdent aux applications cloud et locales reliées à Azure AD, y compris Office 365. En savoir plus sur la [configuration de l’intégration de Jamf](conditional-access-integrate-jamf.md) et la [mise en application de la conformité des appareils Jamf gérés](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Nouvelle action sur appareil iOS   <!-- 1424701 -->

Vous pouvez maintenant arrêter les appareils supervisés iOS 10.3. Cette action arrête immédiatement l’appareil sans avertir l’utilisateur final. L’action **Arrêter (supervisé uniquement)** se trouve dans les propriétés de l’appareil lorsque vous sélectionnez un appareil dans la charge de travail **Appareil**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Interdire les changements de date/heure sur les appareils Samsung Knox <!-- 1468103 -->

Nous avons ajouté une nouvelle fonctionnalité qui vous permet d’empêcher les changements de date et d’heure sur les appareils Samsung Knox. Vous la trouverez dans **Profils de configuration d’appareil** > **Restrictions d’appareil (Android)** > **Général**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Compte de ressource Surface Hub pris en charge <!-- 1566442  -->

Une nouvelle action d’appareil a été ajoutée pour permettre aux administrateurs de définir et de mettre à jour le compte de ressource associé à un Surface Hub.

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

   - **Courrier électronique**

     Adresse e-mail de l’appareil/du compte de ressource.

   - **Serveur Exchange**

     Requis uniquement en cas d’échec de la découverte automatique.

   - **Synchronisation du calendrier**

     Permet de spécifier si la synchronisation du calendrier et d’autres services Exchange Server sont activés. Par exemple : synchronisation de réunion.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Installer des applications Office sur des appareils macOS <!-- 1494311 -->
Vous pourrez maintenant installer des applications Office sur des appareils macOS. Ce nouveau type d’application vous permettra d’installer Word, Excel, PowerPoint, Outlook et OneNote. Ces applications bénéficient également de Microsoft AutoUpdate (MAU) qui garantit que vos applications sont sécurisées et à jour.

### <a name="app-management"></a>Gestion d'applications

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Supprimer un jeton Programme d’achat en volume iOS <!-- 820879 -->
Vous pouvez supprimer le jeton Programme d’achat en volume (VPP) iOS à l’aide de la console. Ceci peut être nécessaire si vous avez des instances dupliquées d’un jeton VPP.

### <a name="intune-apps"></a>Applications Intune

#### <a name="end-user-messaging-for-accounts---1573558-for-1712--"></a>Messagerie d’utilisateur final pour les comptes <!--1573558 for 1712-->

Les utilisateurs du site web Portail d’entreprise ne pourront pas exécuter des actions qui nécessitent un accès en écriture à votre client. Ils recevront un message d’erreur expliquant que leur compte est en cours de maintenance. Des modifications similaires seront bientôt disponibles sur les applications Portail d’entreprise pour Android, iOS, macOS et Windows. Vous pouvez voir cette erreur dans la rubrique [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md).



### <a name="role-based-access-control"></a>Contrôle d'accès en fonction du rôle

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Nouvelle collection d’entités, nommée Utilisateur actuel, limitée aux données des utilisateurs actuellement actifs<!-- 1667026 -->

La collecte d’entités **User** répertorie tous les utilisateurs Azure Active Directory (Azure AD) auxquels des licences ont été attribuées dans votre entreprise. Il est possible, par exemple, qu’un utilisateur soit ajouté à Intune, puis supprimé au cours du mois précédent. Cet utilisateur n’est pas présent au moment du rapport, mais lui et l’état apparaissent quand même dans les données. Vous pourriez créer un rapport qui afficherait la durée de la présence passée de l’utilisateur dans vos données.

En revanche, la nouvelle collection d’entités **Utilisateur actuel** contient uniquement les utilisateurs qui n’ont pas été supprimés. La collection d'entités **Utilisateur actuel** ne contient que des utilisateurs actuellement actifs. Pour plus d’informations sur la collection d’entités **Utilisateur actuel**, consultez la page [Informations de référence sur l’entité Utilisateur actuel](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>API Graph mises à jour <!-- 1736360 -->

Dans cette version, nous avons mis à jour quelques-unes des API Graph pour Intune (actuellement en version bêta). Consultez le [journal mensuel des modifications de l’API Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) pour plus d’informations.


## <a name="week-of-december-4-2017"></a>Semaine du 4 décembre 2017

### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune prend en charge les applications refusées dans Protection des informations Windows <!-- 1479103 -->
Vous pouvez spécifier les applications refusées dans Intune. Si une application est refusée, son accès aux informations d’entreprise est bloqué (ce qui correspond à l’inverse de la liste des applications autorisées). Pour plus d’informations, consultez [Recommended deny list for Windows Information Protection](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection) (Liste d’exclusion recommandée pour la Protection des informations Windows).


## <a name="week-of-november-27-2017"></a>Semaine du 27 novembre 2017

### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Résoudre les problèmes d’inscription  <!-- 746324 -->

L’espace de travail **Résolution des problèmes** montre désormais les problèmes d’inscription des utilisateurs. Des détails sur les problèmes et des suggestions de correction peuvent aider les administrateurs et les agents du support technique à résoudre les problèmes. Certains problèmes d’inscription ne sont pas capturés et certaines erreurs peuvent ne pas avoir de suggestions de correction.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Restrictions d’inscription assignées aux groupes <!-- 747598 -->

En tant qu’administrateur Intune, vous pouvez désormais [créer des restrictions d’inscription Type d’appareil et Limite d’appareils personnalisées pour des groupes d’utilisateurs](enrollment-restrictions-set.md).

Le portail Azure Intune vous permet de créer jusqu’à 25 instances de chaque type de restriction qui peuvent ensuite être assignées aux groupes d’utilisateurs. Les restrictions assignées aux groupes remplacent les restrictions par défaut.

Toutes les instances d’un type de restriction sont conservées dans une liste classée de manière stricte. Cet ordre définit une valeur de priorité pour la résolution des conflits. Un utilisateur impacté par plusieurs instances de restriction est uniquement limité par l’instance ayant la valeur de priorité la plus élevée. Vous pouvez modifier la priorité d’une instance donnée en la faisant glisser vers un autre emplacement de la liste.

Cette fonctionnalité sera disponible quand les paramètres Android for Work seront migrés depuis le menu Inscription Android for Work vers le menu Restrictions d’inscription. Cette migration pouvant prendre plusieurs jours, votre compte peut être mis à niveau pour d’autres parties de la version de novembre avant que l’affectation aux groupes ne soit activée pour les restrictions d’inscription.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Prise en charge de plusieurs connecteurs NDES (Service d’inscription de périphérique réseau)<!-- 1528104 -->

NDES permet aux appareils mobiles s’exécutant sans informations d’identification de domaine d’obtenir des certificats basés sur le protocole d’inscription de certificats simple (SCEP).
Cette mise à jour prend en charge plusieurs connecteurs NDES.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gérer les appareils Android for Work indépendamment des appareils Android <!-- 1490731 EEready-->

**Remarque** : Les changements suivants seront lancés avec la mise à jour de novembre, mais il est possible que leur exécution sur votre compte prenne du temps. Vous recevrez une notification de confirmation dans le portail Office 365 quand ces modifications seront effectives pour votre compte. Après le lancement, vous disposerez d’options d’administration supplémentaires. Durant le lancement, l’expérience utilisateur final reste la même.

Intune prend en charge la gestion de l’inscription des appareils Android for Work indépendamment de la plateforme Android. Ces paramètres sont gérés sous **Inscription de l’appareil** > **Restrictions d’inscription** > **Restrictions de type d’appareil**. (Ils se trouvaient sous **Inscription de l’appareil** > **Inscription Android for Work** > **Paramètres d’inscription d’Android for Work**.)

Par défaut, les paramètres de vos appareils Android for Work sont identiques à ceux de vos appareils Android. Toutefois, ce ne sera plus le cas une fois que vous aurez modifié vos paramètres Android for Work.

Si vous bloquez l’inscription Android for Work personnelle, seuls les appareils Android d’entreprise peuvent s’inscrire en tant qu’Android for Work.

Quand vous utilisez les nouveaux paramètres, tenez compte des éléments suivants :

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Si vous n’avez jamais intégré l’inscription Android for Work

La nouvelle plateforme Android for Work est bloquée dans les restrictions de type d’appareil par défaut. Une fois la fonctionnalité intégrée, vous pouvez autoriser les appareils à s’inscrire auprès d’Android for Work. Pour ce faire, changez le paramétrage par défaut ou créez une restriction de type d’appareil afin de remplacer la restriction de type d’appareil par défaut.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Si vous avez intégré l’inscription Android for Work

Votre situation varie selon le paramètre que vous avez choisi :

| Paramètre | État Android for Work dans la restriction de type d’appareil par défaut | Remarques |
| --- | --- | --- |
| **Gérer tous les appareils comme Android** | Bloqué | Tous les appareils Android doivent s’inscrire sans Android for Work. |
| **Gérer les appareils pris en charge comme Android for Work** | Autorisé | Tous les appareils Android qui prennent en charge Android for Work doivent s’inscrire auprès d’Android for Work. |
| **Gérer les appareils pris en charge pour les utilisateurs uniquement dans ces groupes comme Android for Work** | Bloqué | Une stratégie de restriction de type d’appareil distincte a été créée pour remplacer le paramétrage par défaut. Cette stratégie définit les groupes que vous avez choisis pour autoriser l’inscription Android for Work. Les utilisateurs dans les groupes sélectionnés continueront à être autorisés à inscrire leurs appareils Android for Work. Tous les autres utilisateurs ne peuvent pas s’inscrire auprès Android for Work. |

Dans tous les cas, les règles que vous avez envisagées sont conservées. Aucune action n’est requise de votre part pour gérer l’autorisation globale ou par groupe d’Android for Work dans votre environnement.

### <a name="app-management"></a>Gestion d'applications

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>Mise à jour du rapport d’installation de l’application pour inclure l’état Installation en attente <!-- 1249446 -->  

Le rapport **État de l’installation de l’application** accessible pour chaque application par le biais de la liste **Application** dans la charge de travail **Applications mobiles** contient désormais un nombre **Installation en attente** pour les utilisateurs et les appareils.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>API d’inventaire des applications iOS 11 pour la détection des menaces mobiles <!-- 1391759 -->

Intune collecte les informations d’inventaire des applications à partir des appareils personnels et d’entreprise et les rend disponibles pour les fournisseurs de détection des menaces mobiles, comme Lookout for Work. Vous pouvez collecter un inventaire des applications auprès des utilisateurs d’appareils iOS 11+.

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


### <a name="device-management"></a>Gestion des appareils

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Faire migrer des utilisateurs et appareils MDM hybrides vers la version autonome d’Intune <!-- 1463747 wnready -->
Nous vous proposons un nouveau processus et de nouveaux outils pour déplacer les utilisateurs et leurs appareils de MDM hybride vers Intune dans le portail Azure. Vous pouvez ainsi effectuer les opérations suivantes :
- Copier des stratégies et des profils de la console Configuration Manager vers Intune dans le portail Azure
- Déplacer une partie des utilisateurs vers Intune dans le portail Azure, tout en conservant le reste dans un environnement MDM hybride
- Migrer des appareils vers Intune dans le portail Azure sans avoir à les réinscrire

Pour plus d’informations, consultez [Faire migrer des utilisateurs et appareils MDM hybrides vers la version autonome d’Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Prise en charge d’un haut niveau de disponibilité pour le connecteur Exchange local <!-- 676614 -->
Une fois que le connecteur Exchange crée une connexion à Exchange en utilisant l’autorité de certification spécifiée, le connecteur a désormais la possibilité de découverte d’autres autorités de certification. Si l’autorité de certification principale est indisponible, le connecteur bascule vers une autre autorité de certification disponible, jusqu'à ce que l’autorité de certification principale redevienne disponible. Pour plus de détails, voir [Prise en charge d’un haut niveau de disponibilité pour le connecteur Exchange local](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Redémarrer à distance un appareil iOS (supervisé uniquement) <!-- 1424595 -->

Vous pouvez désormais déclencher le redémarrage d’un appareil iOS 10.3+ supervisé au moyen d’une action d’appareil. Pour plus d’informations sur l’utilisation de l’action de redémarrage d’appareil, consultez [Redémarrer à distance des appareils avec Intune](device-restart.md).

> [!Note]
> Cette commande nécessite un appareil supervisé et le droit d’accès **Verrouillage de l’appareil**. L’appareil redémarre immédiatement. Après le redémarrage, les appareils iOS verrouillés par un code secret ne rejoignent pas un réseau Wi-Fi et peuvent se trouver dans l’impossibilité de communiquer avec le serveur.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Prise en charge de l’authentification unique pour iOS <!-- 1333645 -->  

Vous pouvez utiliser l’authentification unique pour les utilisateurs d’iOS. Les applications iOS qui sont codées pour rechercher les informations d’identification de l’utilisateur dans la charge utile d’authentification unique fonctionnent avec cette mise à jour de la configuration de la charge utile. Vous pouvez également utiliser un UPN et un ID d’appareil Intune pour configurer le nom du principal et le domaine. Pour plus d’informations, consultez [Configurer Intune pour l’authentification unique des appareils iOS](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Ajouter « Rechercher mon iPhone » pour les appareils personnels <!--1427287-->
Vous pouvez désormais savoir si la fonctionnalité Verrou d’activation est activée pour les appareils iOS. Cette fonctionnalité se trouvait avant dans le portail classique.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Verrouiller à distance un appareil macOS géré avec Intune <!-- 1437691 -->

Vous pouvez verrouiller un appareil macOS perdu et définir un code PIN de récupération à 6 chiffres. Une fois le verrouillage effectué, le panneau **Vue d’ensemble des appareils** affiche le code PIN jusqu’à ce qu’une autre action d’appareil soit envoyée.

Pour plus d’informations, consultez [Verrouiller à distance des appareils gérés avec Intune](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Nouveaux détails de profil SCEP pris en charge <!-- 1559808 -->

Les administrateurs peuvent désormais définir des paramètres supplémentaires durant la création d’un profil SCEP sur les plateformes Windows, iOS, macOS et Android.  Les administrateurs peuvent définir un IMEI, un numéro de série ou un nom commun (adresse e-mail incluse) dans le format du nom de l’objet.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Conserver les données pendant une réinitialisation des paramètres d’usine <!--1588489 -->
Une nouvelle fonctionnalité est disponible durant la réinitialisation de Windows 10 version 1709 et ultérieure aux paramètres d’usine. Les administrateurs peuvent spécifier si les données d’inscription des appareils et d’autres données provisionnées sont conservées sur un appareil en cas de réinitialisation aux paramètres d’usine.

Les données suivantes sont conservées pendant une réinitialisation des paramètres d’usine :
- Comptes d’utilisateur associés à l’appareil
- État de l’ordinateur (jonction de domaine, joint à Azure Active Directory)
- Inscription MDM
- Applications OEM installées (applications Win32 et du Store)
- Profil utilisateur
- Données utilisateur hors du profil utilisateur
- Ouverture de session automatique de l’utilisateur

Les données suivantes ne sont pas conservées :
- Fichiers utilisateur
- Applications utilisateur installées (applications Win32 et du Store)
- Paramètres d’appareil autres que les paramètres par défaut

### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Les affectations de boucles de mise à jour de Windows 10 sont affichées <!-- 1621837 -->
Pendant une **résolution de problèmes**, vous pouvez voir les affectations de boucles de mise à jour de Windows 10 pour l’utilisateur affiché.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Paramètres de la fréquence d’émission des rapports Windows Defender - Protection avancée contre les menaces <!-- 1455974  -->
Le service Windows Defender - Protection avancée contre les menaces permet aux administrateurs de gérer la fréquence d’émission des rapports sur les appareils gérés. Avec la nouvelle option **Augmenter la fréquence des rapports de télémétrie**, Windows Defender ATP collecte les données et évalue les risques plus fréquemment. Par défaut, l’émission de rapports optimise le niveau de performance et la vitesse. Augmenter la fréquence d’émission des rapports peut être utile pour les appareils à haut risque. Ce paramètre se trouve dans le profil **Windows Defender ATP** dans **Configurations d’appareil**.

#### <a name="audit-updates----1412961---"></a>Auditer les mises à jour <!-- 1412961 -->  
La fonctionnalité d’audit d’Intune enregistre les opérations de modification relatives à Intune.  Tous les opérations de création, de mise à jour, de suppression et de tâche à distance sont capturées et conservées pendant un an.  Le portail Azure fournit une vue filtrable des 30 derniers jours de données d’audit dans chaque charge de travail.  Une API Graph correspondante permet de récupérer les données d’audit stockées pendant l’année écoulée.

La fonctionnalité d’audit se trouve sous le groupe **SURVEILLER**. Il existe un élément de menu **Journaux d’audit** par charge de travail.




## <a name="week-of-november-20-2017"></a>Semaine du 20 novembre 2017

### <a name="app-management"></a>Gestion d'applications

#### <a name="google-play-protect-support-on-android----908720---"></a>Support de Google Play Protect sur Android <!-- 908720 -->

Avec la publication d’Android Oreo, Google introduit une suite de fonctionnalités de sécurité appelée Google Play Protect qui permet aux utilisateurs et aux organisations d’exécuter des applications sécurisées et des images Android sécurisées. Intune prendra en charge les fonctionnalités de Google Play Protect, notamment l’attestation SafetyNet distante. Les administrateurs peuvent définir des exigences pour la stratégie de conformité afin que Google Play Protect soit configuré et intègre.
Le paramètre **Attestation d’appareil SafetyNet** nécessite que l’appareil se connecte à un service Google pour vérifier que l’appareil est intègre et qu’il n’est pas compromis. Les administrateurs peuvent également définir un paramètre de profil de configuration pour qu’Android for Work exige que les applications installées soient vérifiées par les services Google Play. L’accès conditionnel peut empêcher les utilisateurs d’accéder aux ressources d’entreprise si un appareil n’est pas conforme aux exigences de Google Play Protect.

- Découvrez comment [créer une stratégie de conformité des appareils pour activer Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Protocole de texte autorisé à partir des applications gérées <!-- 1414050  -->

Les applications gérées par le SDK d’application Intune peuvent envoyer des SMS.

## <a name="week-of-november-13-2017"></a>Semaine du 13 novembre 2017

### <a name="intune-apps"></a>Applications Intune
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>L’application Portail d’entreprise pour macOS est disponible<!--1541700-->
L’expérience du Portail d’entreprise Intune sous macOS a été mise à jour. Elle a été optimisée pour afficher clairement toutes les informations et notifications de conformité dont les utilisateurs ont besoin pour tous les appareils qu’ils ont inscrits. Une fois que le Portail d’entreprise Intune a été déployé sur un appareil, il bénéficie de la mise à jour automatique Microsoft (AutoUpdate) pour macOS. Vous pouvez télécharger le nouveau Portail d’entreprise Intune pour macOS en ouvrant une session sur le site web du Portail d’entreprise Intune sur un appareil macOS.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner fait maintenant partie de la liste des applications approuvées de la gestion des applications mobiles (MAM)<!-- 1248473 -->
L’application Microsoft Planner pour iOS et Android fait à présent partie des applications approuvées pour la gestion des applications mobiles (MAM). Elle est configurable par le biais du panneau Intune App Protection sur le Portail Azure de tous les clients.
- Pour plus de détails, consultez la page [Liste MAM des applications approuvées](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Fréquence de mise à jour des exigences du VPN par application sur les appareils iOS<!-- 1547061 -->  
Les administrateurs peuvent à présent supprimer des exigences du VPN par application pour les applications installées sur des appareils iOS ; les appareils concernés seront mis à jour après l’archivage Intune suivant, ce qui se produit généralement dans les 15 minutes.  

### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Prise en charge du pack d’administration de System Center Operations Manager pour le connecteur Exchange<!-- 885457 -->
Le pack d’administration de System Center Operations Manager (SCOM) pour le connecteur Exchange est maintenant disponible pour vous aider à analyser les journaux du connecteur Exchange. Il offre différents moyens de surveiller le service à des fins de résolution des problèmes.

## <a name="week-of-november-6-2017"></a>Semaine du 6 novembre 2017

### <a name="device-enrollment"></a>Inscription des appareils
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogestion pour les appareils Windows 10 <!-- 1243445 -->
La cogestion est une solution qui propose une passerelle entre la gestion classique et la gestion moderne tout en vous donnant la possibilité d’opérer cette transition selon une approche en plusieurs phases. À la base, la cogestion est une solution qui permet aux appareils Windows 10 d’être gérés simultanément par Configuration Manager et Microsoft Intune, et d’être joints à Active Directory (AD) et à Azure Active Directory (Azure AD).  Cette configuration vous offre un moyen de vous moderniser à un rythme qui convient à votre organisation si vous ne pouvez pas le faire d’un coup.  

#### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Nouvelle page d’état pour les inscriptions Windows 10<!--1063201-->    
Vous pouvez désormais configurer un message d’accueil qui apparaît quand vos utilisateurs inscrivent des appareils Windows 10. Utilisez l’**écran d’état des inscriptions** pour configurer un message personnalisé et un lien hypertexte à l’attention de vos utilisateurs finaux quand ceux-ci inscrivent leurs appareils Windows 10.  L’**écran d’état des inscriptions** donne aussi aux utilisateurs finaux une vue de la progression des paramètres de stratégie qui sont actuellement appliqués à leur appareil.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Limiter l’inscription Windows par version de système d’exploitation<!-- 245498 -->
En tant qu’administrateur Intune, vous pouvez maintenant spécifier une version minimale et maximale de Windows 10 pour les inscriptions d’appareils. Vous pouvez définir ces restrictions dans le panneau **Configurations de plateforme**.

Intune continue à prendre en charge l’inscription des PC et téléphones Windows 8.1. Toutefois, seules les versions de Windows 10 peuvent être configurées avec des limites minimale et maximale. Pour autoriser l’inscription d’appareils 8.1, laissez vide la limite minimale.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alertes pour les appareils non affectés Windows AutoPilot  <!-- 1631236 -->
Une nouvelle alerte est disponible pour les appareils non attribués Windows AutoPilot dans la page **Microsoft Intune** > **Inscription de l’appareil** > **Vue d’ensemble**. Cette alerte indique combien d’appareils du programme AutoPilot n’ont pas de profils de déploiement AutoPilot affectés. Utilisez les informations de l’alerte pour créer des profils et les affecter aux appareils non affectés. Quand vous cliquez sur l’alerte, une liste complète des appareils Windows AutoPilot et des informations détaillées les concernant s’affichent. Pour plus d’informations, consultez [Inscrire des appareils Windows à l’aide du programme de déploiement Windows AutoPilot](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Gestion des appareils

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Bouton Actualiser pour la liste des appareils    <!-- 1333581 -->
La liste des appareils ne s’actualisant pas automatiquement, vous pouvez utiliser le bouton Actualiser pour mettre à jour les appareils affichés dans la liste.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Prise en charge de l’Autorité de certification Symantec Cloud  <!-- 1333638 -->    
Intune prend désormais en charge l’Autorité de certification Symantec Cloud qui permet à Intune Certificate Connector d’émettre des certificats PKCS de l’Autorité de certification Symantec Cloud sur des appareils gérés par Intune. Si vous utilisez déjà Intune Certificate Connector avec l’Autorité de certification Microsoft, vous pouvez optimiser la configuration existante d’Intune Certificate Connector en y ajoutant la prise en charge de l’Autorité de certification de Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nouveaux éléments ajoutés à l’inventaire des appareils   <!--1404455 -->
Dans cette version, nous avons ajouté les nouveaux éléments suivants à [l’inventaire effectué par les appareils inscrits](device-inventory.md) :

- Adresse MAC Wi-Fi
- Espace de stockage total
- Espace libre total
- MEID
- Opérateur de l’abonné


### <a name="app-management"></a>Gestion d'applications
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Définir l’accès pour les applications avec un correctif de sécurité Android minimal sur l’appareil<!-- 1278463 -->   
Un administrateur peut définir le correctif de sécurité Android minimal qui doit être installé sur l’appareil pour obtenir l’accès à une application gérée sous un compte géré.

> [!Note]  
> Cette fonctionnalité restreint uniquement les correctifs de sécurité publiés par Google sur les appareils Android 6.0 +.

#### <a name="app-conditional-launch-support----1193313---"></a>Prise en charge du lancement conditionnel d’applications<!-- 1193313 -->
Les administrateurs informatiques peuvent désormais définir une condition dans le portail d’administration Azure permettant d’appliquer un code secret à la place d’un code PIN numérique via la gestion des applications mobiles (MAM) lors du lancement de l’application. Selon la configuration, l’utilisateur doit définir et utiliser un code secret quand il y est invité avant d’obtenir l’accès à des applications compatibles MAM. Un code secret est défini comme un code PIN numérique avec au moins un caractère spécial ou une lettre majuscule/minuscule. Cette version d’Intune propose cette fonctionnalité **sur iOS uniquement**. Intune prend en charge un code secret comme un code PIN numérique, il définit une longueur minimale et autorise la répétition des caractères et des séquences. Cette fonctionnalité nécessite la participation des applications (c’est-à-dire, WXP, Outlook, Managed Browser, Yammer) pour intégrer le Kit de développement logiciel (SDK) Intune App avec le code de cette fonctionnalité en place dans le but d’appliquer les paramètres du code secret dans les applications ciblées.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numéro de version des applications métier dans le rapport d’état d’installation de l’appareil<!-- 1233999 -->
Avec cette version, le rapport d’état d’installation de l’appareil affiche le numéro de version des applications métier pour iOS et Android. Vous pouvez utiliser cette information pour dépanner vos applications ou trouver les appareils qui exécutent des versions d’application anciennes.


### <a name="device-configuration"></a>Configuration des appareils
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Les administrateurs peuvent désormais configurer les paramètres du Pare-feu d’un appareil avec un profil de configuration d’appareil <!-- 951708 -->   
Les administrateurs peuvent activer le Pare-feu sur les appareils et configurer divers protocoles pour les réseaux privés, publics et de domaine.  Ces paramètres de pare-feu se trouvent dans le profil « Endpoint protection ».

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard permet de protéger les appareils des sites web non approuvés, comme défini par votre organisation <!-- 958257 -->   
Les administrateurs peuvent définir les sites comme « approuvés » ou « appartenant à l’entreprise » à l’aide d’un flux de travail Protection des informations Windows ou du nouveau profil « Limite réseau » dans les configurations de l’appareil. Tous les sites qui ne sont pas listés dans la limite réseau approuvée d’un appareil Windows 10 64 bits, s’ils sont consultés dans Microsoft Edge, s’ouvrent à la place dans un navigateur d’une machine virtuelle Hyper-V.

Application Guard se trouve dans les profils de configuration de l’appareil, dans le profil « Endpoint protection ». À partir de là, les administrateurs peuvent configurer une interaction entre le navigateur virtualisé et la machine hôte, les sites non approuvés et les sites approuvés, puis stocker les données générées dans le navigateur virtualisé. Pour utiliser Application Guard sur un appareil, une limite réseau doit d’abord être configurée. Il est important de définir une seule limite réseau pour un appareil.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Control sur Windows 10 Entreprise offre un mode permettant d’approuver uniquement les applications autorisées <!-- 1031096 -->    
Avec des milliers de nouveaux fichiers malveillants créés chaque jour, l’utilisation d’une détection antivirus basée sur les signatures pour lutter contre les programmes malveillants ne constitue probablement plus une défense suffisante contre les nouvelles attaques. En utilisant Windows Defender Application Control sur Windows 10 Entreprise, vous pouvez changer la configuration de l’appareil et passer d’un mode où les applications sont approuvées sauf si elles sont bloquées par un antivirus ou une autre solution de sécurité à un mode où le système d’exploitation approuve uniquement les applications autorisées par votre entreprise. Vous approuvez les applications dans Windows Defender Application Control.

Avec Intune, vous pouvez configurer des stratégies de contrôle d’application en mode « audit uniquement » ou en mode d’application. Les applications ne sont pas bloquées quand vous exécutez le mode « audit uniquement ». Le mode « Audit uniquement » enregistre tous les événements dans les journaux du client local. Vous pouvez également autoriser uniquement l’exécution des composants Windows et des applications du Microsoft Store, ou autoriser l’exécution d’autres applications avec une bonne réputation telle que définie par Intelligent Security Graph.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Windows Defender Exploit Guard est un nouvel ensemble de fonctionnalités de prévention d’intrusion pour Windows 10 <!-- 1063615 -->   
Windows Defender Exploit Guard propose des règles personnalisées permettant de réduire l’exploitabilité des applications, empêche les menaces provenant de macros et de scripts, bloque automatiquement les connexions réseau à des adresses IP de mauvaise réputation et peut sécuriser les données contre des ransomware et des menaces inconnues. Windows Defender Exploit Guard présente les composants suivants :

- **Réduction de la surface d’attaque (ASR)** fournit des règles vous permettant d’empêcher les menaces de macro, de script et d’e-mail.
- **Accès contrôlé au dossier** bloque automatiquement l’accès au contenu des dossiers protégés.
- **Filtre de réseau** bloque la connexion sortante de toutes les applications à une adresse IP/domaine de faible réputation
- **Exploit Protection** fournit la mémoire, le flux de contrôle et les restrictions de stratégie pouvant être utilisés pour protéger les applications contre des attaques.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Gérer des scripts PowerShell dans Intune pour des appareils Windows 10 <!-- 790537 -->

L’extension de gestion Intune vous permet de charger des scripts PowerShell dans Intune pour les exécuter sur des appareils Windows 10. L’extension vient en complément des fonctionnalités de gestion des appareils mobiles (MDM) Windows 10 et facilite l’adoption d’une gestion moderne. Pour plus d’informations, consultez [Gérer des scripts PowerShell dans Intune pour des appareils Windows 10](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nouveaux paramètres de restriction d’appareil pour Windows 10      <!-- 1308850 -->
-    Messagerie (mobile uniquement) - désactivation des tests ou des messages MMS
-    Mot de passe - paramètres pour activer FIPS et l’utilisation d’appareils secondaires Windows Hello pour l’authentification 
-    Affichage - paramètres pour activer ou désactiver la mise à l’échelle GDI pour les applications héritées

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Restrictions des appareils en mode plein écran Windows 10<!-- 1308872 -->   
Vous pouvez restreindre les utilisateurs d’appareils Windows 10 au mode plein écran, ce qui limite les utilisateurs à un ensemble d’applications prédéfinies.  Pour ce faire, créez un profil de restriction d’appareil Windows 10 et définissez les paramètres de plein écran.

Le mode plein écran prend en charge deux modes : **application unique** (permet à l’utilisateur d’exécuter une seule application) ou **applications multiples** (permet l’accès à un ensemble d’applications).  Vous définissez le compte d’utilisateur et le nom de l’appareil, ce qui détermine les applications prises en charge.  Lorsque l’utilisateur est connecté, il est limité aux applications définies.  Pour en savoir plus, consultez [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Conditions requises du mode plein écran :

- Intune doit être l’autorité MDM.
- Les applications doivent déjà être installées sur l’appareil cible.
- L’appareil doit être [correctement provisionné](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions).

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nouveau profil de configuration d’appareil pour la création de limites réseau<!-- 1311967 -->   
Nous avons créé un profil de configuration d’appareil appelé **Limite réseau** que vous trouverez avec vos autres profils de configuration d’appareil. Utilisez ce profil pour définir des ressources en ligne à considérer comme approuvées et appartenant à l’entreprise. Vous devez définir une limite réseau pour un appareil *avant* de pouvoir utiliser les fonctionnalités comme Windows Defender Application Guard et Protection des informations Windows sur l’appareil. Il est important de définir une seule limite réseau pour chaque appareil.

Vous pouvez définir des ressources cloud d’entreprise, des plages d’adresses IP et des serveurs proxy internes à considérer comme approuvées. Une fois définie, la limite réseau peut être utilisée par d’autres fonctionnalités comme Windows Defender Application Guard et Protection des informations Windows.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Deux paramètres supplémentaires pour Windows Defender Antivirus<!-- 1338409 -->  
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

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>VPN Citrix ajouté pour les appareils Windows 10 <!-- 1512457 -->  
Vous pouvez configurer un VPN Citrix pour les appareils Windows 10. Vous pouvez choisir le VPN Citrix dans la liste *Sélectionner un type de connexion* du panneau **VPN de base** quand vous configurez un VPN pour Windows 10 et ultérieur.

> [!Note]
> Une configuration de Citrix existait pour iOS et Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Les connexions Wi-Fi prennent en charge les clés prépartagées sur iOS <!-- 1550823 -->
Les clients peuvent configurer des profils Wi-Fi pour utiliser des clés prépartagées pour les connexions personnelles WPA/WPA2 sur les appareils iOS. Ces profils sont envoyés à l’appareil de l’utilisateur quand l’appareil est inscrit dans Intune.

Quand le profil a été envoyé à l’appareil, l’étape suivante varie en fonction de la configuration du profil.  S’il est configuré pour se connecter automatiquement, il le fait quand l’accès réseau est nécessaire.  Quand le profil se connecte manuellement, l’utilisateur doit activer la connexion manuellement.  

### <a name="intune-apps"></a>Applications Intune

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Accès aux journaux d’applications gérées pour iOS <!-- 1469920 -->
Les utilisateurs finaux disposant de Managed Browser peuvent désormais afficher l’état de gestion de toutes les applications Microsoft publiées, et envoyer les journaux afin de dépannage leurs applications iOS gérées.

Pour découvrir comment activer le mode de dépannage dans Managed Browser sur un appareil iOS, consultez [Comment accéder aux journaux des applications gérées à l’aide de Managed Browser sur iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Améliorations apportées au workflow de configuration des appareils sur le Portail d’entreprise pour iOS dans la version 2.9.0<!-- 1417174 -->

Nous avons amélioré le workflow de configuration des appareils dans l’application Portail d’entreprise pour iOS. La langue est plus conviviale, et nous avons regroupé des écrans dans la mesure du possible. La langue est également plus adaptée à l’entreprise, car nous utilisons à chaque fois son nom dans le texte de configuration. Vous pouvez voir ce workflow mis à jour sur la page  [Nouveautés de l’interface utilisateur de l’application](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>L’entité Utilisateur contient les données utilisateur les plus récentes dans le modèle de données de l’entrepôt de données <!-- 1544273 -->
La première version du modèle de données de l’entrepôt de données Intune ne contenait que des données Intune historiques récentes. Les auteurs de rapports ne pouvaient pas capturer l’état actuel d’un utilisateur. Dans cette mise à jour, **l’entité Utilisateur** est renseignée avec les données utilisateur les plus récentes.


## <a name="week-of-october-30-2017"></a>Semaine du 30 octobre 2017

### <a name="app-management"></a>Gestion d'applications

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Le numéro de version des applications métier iOS et Android est visible <!-- 1380712 -->

Les applications dans Intune affichent désormais le numéro de version des applications métier Android et iOS. Le numéro s’affiche dans le portail Azure, dans la liste des applications et dans le panneau de vue d’ensemble des applications. Les utilisateurs finaux peuvent voir le numéro d’application dans l’application Portail d’entreprise et dans le portail web.

__Numéro de version complet__ Le numéro de version complet identifie une version précise de l’application. Le numéro apparaît sous la forme _Version_(_Build_). Par exemple, 2.2(2.2.17560800)

Le numéro de version complet est composé de deux éléments :

 - **Version**  
   Le numéro de version est le numéro de version explicite de l’application. Il est utilisé par les utilisateurs finaux pour identifier les différentes versions de l’application.

 - **Numéro de build**  
    Le numéro de build est un numéro interne qui peut être utilisé pour la détection de l’application et pour gérer l’application par programmation. Le numéro de build fait référence à une itération de l’application qui référence les changements apportés au code.

Pour découvrir plus en détail les numéros de version et le développement d’applications métier, consultez [Prise en main du kit SDK d’application Microsoft Intune](app-sdk-get-started.md#line-of-business-app-version-numbers).

#### <a name="device-and-app-management-integration----677972---"></a>Intégration de la gestion des appareils et des applications<!-- 677972 -->   
Maintenant que la gestion des appareils mobiles (MDM) et la gestion des applications mobiles (MAM) d’Intune sont accessibles à partir du portail Azure, Intune a commencé à intégrer l’expérience d’administrateur informatique dans la gestion des applications et des appareils. Ces changements sont destinés à simplifier votre expérience de la gestion des appareils et des applications.

Découvrez plus en détail les changements de MDM et de MAM annoncés sur le [blog de l’équipe de support Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nouvelles alertes d’inscription pour les appareils Apple <!-- 1471790 -->
La page de vue d’ensemble de l’inscription affiche les alertes utiles pour les administrateurs informatiques concernant la gestion des appareils Apple. Des alertes s’affichent dans la page Vue d’ensemble quand le certificat push MDM Apple arrive à expiration ou a déjà expiré ; quand le jeton DEP (Programme d’inscription des appareils) expire ou a déjà expiré ; et en présence d’appareils non affectés dans le programme DEP.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Prise en charge du remplacement de jeton pour la configuration d’application sans inscription de l’appareil <!-- 1080364 -->

Vous pouvez utiliser des jetons pour les valeurs dynamiques des configurations des applications des appareils qui ne sont pas inscrits. Pour plus d’informations, consultez [Ajouter des stratégies de configuration pour les applications gérées sans inscription d’appareil](app-configuration-policies-managed-app.md).

### <a name="intune-apps"></a>Applications Intune

#### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Mise à jour de l’application Portail d’entreprise pour Windows 10<!--1299474-->
La page Paramètres de l’application Portail d’entreprise pour Windows 10 a été mise à jour pour rendre les paramètres et les actions prévues de l’utilisateur plus cohérents à travers l’ensemble des paramètres, ainsi que pour correspondre à la disposition d’autres applications Windows. Vous trouverez des images avant/après sur la page [Nouveautés de l’interface utilisateur de l’application](whats-new-app-ui.md).

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Communication d’informations aux utilisateurs finaux au sujet des données consultables sur les appareils Windows 10<!--1337920-->
Nous avons ajouté le **Type de propriété** dans l’écran Détails de l’appareil de l’application Portail d’entreprise pour Windows 10. Les utilisateurs peuvent ainsi trouver plus d’informations sur la confidentialité directement à partir de cette page dans la documentation de l’utilisateur final d’Intune. Ils les trouveront également sur l’écran **À propos de**.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Invites pour entrer des commentaires dans l’application Portail d’entreprise pour Android<!--1165249-->
L’application Portail d’entreprise pour Android demande maintenant un retour d’expérience des utilisateurs finaux. Ces commentaires sont envoyés directement à Microsoft et permettent aux utilisateurs finaux d’évaluer l’application dans le Google Play Store public. Le retour d’expérience n’est pas obligatoire et peut être facilement ignoré de façon à continuer d’utiliser l’application.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Rendre vos utilisateurs autonomes avec l’application Portail d’entreprise pour Android <!-- 1573324, 1573150, 1558616, 1564878 -->

L’application Portail d’entreprise pour Android a ajouté des indications permettant aux utilisateurs finaux de comprendre et, dans la mesure du possible, de résoudre eux-mêmes les nouveaux cas d’usage.
- Les utilisateurs finaux sont redirigés vers le [portail Azure Active Directory](https://account.activedirectory.windowsazure.com/r/#/profile) pour supprimer un appareil s’ils ont atteint le nombre maximal d’appareils qu’ils sont autorisés à ajouter.
- Les utilisateurs finaux reçoivent des instructions pour les aider à [corriger les erreurs d’activation sur les appareils Samsung Knox](https://go.microsoft.com/fwlink/?linkid=859718) ou à [désactiver le mode d’économie d’énergie](/intune-user-help/power-saving-mode-android). Si aucune de ces solutions ne résout leur problème, nous indiquons comment [envoyer les journaux à Microsoft](/intune-user-help/send-logs-to-microsoft-android).

#### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nouvelle action « Résoudre » disponible pour les appareils Android <!-- 1583480 -->

L’application Portail d’entreprise pour Android introduit une action « Résoudre » dans la page _Mettre à jour les paramètres de l’appareil_. Cette option permettra à l’utilisateur final d’accéder directement au paramètre ayant rendu son appareil non conforme. L’application Portail d’entreprise pour Android prend en charge cette action pour les paramètres [Code secret de l’appareil](/intune-user-help/set-your-pin-or-password-android), [Débogage USB](/intune-user-help/you-need-to-turn-off-usb-debugging-android) et [Sources inconnues](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

#### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Indicateur de progression de la configuration de l’appareil sur le Portail d’entreprise Android<!-- 1565657 -->
L’application Portail d’entreprise pour Android affiche un indicateur de progression de la configuration de l’appareil au moment où l’utilisateur l’inscrit. L’indicateur affiche de nouveaux états : tout d’abord, « Configuration de votre appareil en cours... », puis « Inscription de votre appareil en cours... », « Fin de l’inscription de votre appareil... » et enfin « Fin de la configuration de votre appareil... ».

## <a name="week-of-october-23-2017"></a>Semaine du 23 octobre 2017

### <a name="intune-apps"></a>Applications Intune
#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Prise en charge de l’authentification basée sur les certificats sur le portail d’entreprise pour iOS<!--1029830-->
Nous avons ajouté la prise en charge de l’authentification basée sur les certificats dans l’application Portail d’entreprise pour iOS. Les utilisateurs avec cette authentification entrent leur nom d’utilisateur et appuient sur le lien « Se connecter avec un certificat ». L’authentification basée sur les certificats est déjà prise en charge sur les applications du Portail d’entreprise pour Android et Windows. Vous pouvez en savoir plus sur la page [Comment faire pour se connecter à l’application Portail d’entreprise](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Les applications qui sont disponibles avec ou sans inscription peuvent désormais être installées sans invitation à l’inscription. <!-- 1334712 -->

Les applications d’entreprise qui ont été mises à disposition avec ou sans inscription dans l’application Portail d’entreprise Android peuvent désormais être installées sans invitation à l’inscription.

## <a name="week-of-october-16-2017"></a>Semaine du 16 octobre 2017
### <a name="device-enrollment"></a>Inscription des appareils
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Prise en charge du programme de déploiement Windows AutoPilot dans Microsoft Intune  <!-- 747617  -->
Vous pouvez désormais utiliser Microsoft Intune avec le programme de déploiement Windows AutoPilot pour permettre à vos utilisateurs de provisionner eux-mêmes leurs appareils d’entreprise sans passer par le service informatique. Vous pouvez personnaliser l’expérience OOBE (out-of-box experience) pour permettre aux utilisateurs de joindre leurs appareils à Azure AD et de s’inscrire à Intune. Avec Microsoft Intune et Windows AutoPilot, vous n’avez plus à déployer et à gérer les images de système d’exploitation. Pour plus d’informations, consultez [Inscrire des appareils Windows à l’aide du programme Windows AutoPilot Deployment](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Guide de démarrage rapide pour l’inscription d’appareils  <!-- 1425655 --> 
Le guide de démarrage rapide, désormais disponible dans **Inscription d’appareils**, fournit un tableau de références pour gérer les plateformes et configurer la procédure d’inscription. Vous trouverez une brève description de chaque élément et des liens vers des instructions pas à pas pour simplifier le démarrage.

#### <a name="device-categorization----1427491---"></a>Catégorisation des appareils <!-- 1427491 -->
Le graphique des plateformes des appareils inscrits du panneau **Appareils > Vue d’ensemble** organise les appareils par plateforme (Android, iOS, macOS, Windows, Windows Mobile, etc.).  Les appareils qui exécutent d’autres systèmes d’exploitation sont regroupés dans « Autres ».  Il s’agit des appareils fabriqués par Blackberry, NOKIA, etc.  

Pour identifier les appareils affectés dans votre locataire, choisissez **Gérer > Tous les appareils**, puis utilisez **Filtrer** pour limiter le champ **Système d’exploitation**.

### <a name="device-management"></a>Gestion des appareils
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium : nouveau partenaire de Mobile Threat Defense <!-- 954681 -->  
Vous pouvez contrôler l’accès des appareils mobiles aux ressources de l’entreprise à l’aide d’un accès conditionnel basé sur une évaluation des risques effectuée par Zimperium,solution Mobile Threat Defense qui s’intègre à Microsoft Intune.

##### <a name="how-integration-with-intune-works"></a>Déroulement de l’intégration à Intune
Le risque est évalué en fonction des données de télémétrie recueillies par les appareils exécutant Zimperium. Vous pouvez configurer des stratégies d’accès conditionnel EMS basées sur l’évaluation des risques de Zimperium, activée par le biais des stratégies de conformité Intune, que vous pouvez utiliser pour autoriser ou bloquer l’accès des appareils non conformes aux ressources d’entreprise en fonction des menaces détectées.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nouveaux paramètres pour le profil de restriction d’appareils Windows 10  <!--- 978575, 1308849, -->  
Nous ajoutons de nouveaux paramètres au profil de restriction des appareils Windows 10 dans la catégorie Windows Defender SmartScreen.

Pour obtenir plus d’informations sur le profil de restriction des appareils Windows 10, consultez [Paramètres de restriction des appareils Windows 10 et version ultérieure]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Support à distance pour les appareils Windows et Windows Mobile   <!-- 1070473 -->  
Intune peut désormais utiliser le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs qui utilisent des appareils Windows et Windows Mobile.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Analyser les appareils avec Windows Defender <!-- 1280988  1280990   -->
Vous pouvez à présent exécuter une **Analyse rapide**, une **Analyse complète** et **Mettre à jour les signatures** avec l’antivirus Windows Defender sur les appareils Windows 10 gérés. À partir du panneau de présentation de l’appareil, choisissez l’action à exécuter sur l’appareil. Vous êtes invité à confirmer l’action avant l’envoi de la commande à l’appareil. 

**Analyse rapide** : une analyse rapide analyse les emplacements où les programmes malveillants s’enregistrent pour démarrer, comme les clés de registre et les dossiers de démarrage Windows connus. Une analyse rapide prend en moyenne cinq minutes. Associée au paramètre **Protection en temps réel toujours activé** qui analyse les fichiers lorsqu’ils sont ouverts, fermés et à chaque fois qu’un utilisateur accède à un dossier, une analyse rapide fournit une protection contre les programmes malveillants qui peuvent se trouver dans le système ou le noyau. Lorsque l’analyse s’achève, ses résultats s’affichent sur les appareils des utilisateurs. 

**Analyse complète** : une analyse complète peut être utile sur les appareils confrontés à une menace issue de programmes malveillants afin de déterminer s’il existe des composants inactifs qui nécessitent un nettoyage plus approfondi. Elle est également utile pour exécuter des analyses à la demande. Une analyse complète peut prendre une heure. Lorsque l’analyse s’achève, ses résultats s’affichent sur les appareils des utilisateurs. 

**Mettre à jour les signatures** : la commande de mise à jour de signature met à jour les définitions et les signatures des programmes malveillants dans Antivirus Windows Defender. Cela permet de garantir l’efficacité d’Antivirus Windows Defender dans la détection des programmes malveillants. Cette fonctionnalité s’applique uniquement aux appareils Windows 10 et est sujette à la connectivité Internet de l’appareil. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Le bouton Activer/Désactiver n’est plus disponible dans la page Autorité de certification Intune du portail Intune Azure  <!-- 1400455 -->
 Nous avons enlevé une étape du processus de configuration de Certificate Connector sur Intune. Actuellement, vous téléchargez Certificate Connector et vous l’activez dans la console Intune. Mais si vous le désactivez dans la console Intune, il continue d’émettre des certificats.

##### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?
Depuis octobre, le bouton Activer/désactiver n’apparaît plus dans la page Autorité de certification du portail Azure. La fonctionnalité Certificate Connector reste la même. Les certificats sont toujours déployés sur les appareils inscrits à Intune. Vous pouvez continuer à télécharger et à installer Certificate Connector. Pour arrêter l’émission de certificats, vous devez désinstaller Certificate Connector au lieu de le désactiver.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?
Si Certificate Connector est actuellement désactivé, vous devez le désinstaller.

### <a name="device-configuration"></a>Configuration des appareils
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nouveaux paramètres pour le profil de restriction d’appareils Windows 10 Collaboration   <!--- 1308838 -->
Dans cette version, nous avons ajouté un grand nombre de nouveaux paramètres au profil de restriction d’appareils Windows 10 Collaboration pour vous permettre de gérer les appareils Surface Hub.

Pour plus d’informations sur ce profil, consultez [Paramètres de restriction d’appareils Windows 10 Collaboration](device-restrictions-windows-10-teams.md).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Empêcher les utilisateurs d’appareils Android de modifier la date et l’heure de leur appareil  <!-- 1333292 -->
Vous pouvez utiliser la [stratégie d’appareil personnalisée Android](custom-settings-android.md) pour empêcher les utilisateurs d’appareils Android de modifier la date et l’heure de l’appareil.

Pour ce faire, configurez une stratégie personnalisée Android avec le paramètre URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Affectez-lui la valeur **TRUE**, puis attribuez-le aux groupes requis.

#### <a name="bitlocker-device-configuration----1397398---"></a>Configuration d’appareil BitLocker <!-- 1397398 -->
Les paramètres **Chiffrement Windows > Paramètres de Base** incluent un nouveau paramètre **Avertissement sur le chiffrement d’un autre disque** qui vous permet de désactiver le [message d’avertissement](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) sur le chiffrement d’un autre disque qui peut être utilisé sur l’appareil de l’utilisateur.  Le message d’avertissement requiert le consentement de l’utilisateur final avant la configuration de BitLocker sur l’appareil et bloque la configuration de BitLocker jusqu’à ce qu’elle soit confirmée par l’utilisateur final.  Le nouveau paramètre désactive l’avertissement affiché pour l’utilisateur final.


### <a name="app-management"></a>Gestion d'applications
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Le programme d’achat en volume pour les applications d’entreprise est désormais synchronisé avec votre locataire Intune <!-- 800882 -->  
Les développeurs tiers peuvent distribuer des applications en privé aux membres autorisés du programme d’achat en volume (VPP) pour les entreprises. Ces membres du programme d’achat en volume pour les entreprises peuvent se connecter à l’App Store du programme d’achat en volume et acheter leurs applications.

À compter de cette version, les applications du programme d’achat en volume pour les entreprises achetées par l’utilisateur final sont désormais synchronisées avec leurs locataires Intune.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Sélectionner le magasin Apple du pays pour synchroniser les applications VPP<!-- 1332311 -->  
Vous pouvez configurer le magasin du pays pour le programme d’achat en volume (VPP) lors du chargement de votre jeton VPP. Intune synchronise les applications VPP pour tous les paramètres régionaux à partir du magasin du pays VPP spécifié.

> [!NOTE]  
> Actuellement, Intune synchronise uniquement les applications VPP à partir du magasin du pays VPP qui correspond aux paramètres régionaux Intune avec lesquels le client Intune a été créé.


### <a name="intune-apps"></a>Applications Intune
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Bloquer la copie et le collage entre les profils professionnels et personnels dans Android for Work <!-- 1098994 -->
Avec cette version, vous pouvez configurer le profil professionnel Android for Work afin qu’il bloque la copie et le collage entre les applications professionnelles et personnelles. Vous trouverez ce nouveau paramètre dans le profil **Restrictions d’appareils** pour la plateforme **Android for Work** dans **Paramètres du profil professionnel**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Créer des applications iOS limitées à des App Stores Apple locaux spécifiques <!-- 1281692 -->
Vous pourrez spécifier les paramètres régionaux lors de la création d’une application managée App Store Apple.

> [!Note]  
> Actuellement, vous pouvez uniquement créer des applications gérées par l’App Store d’Apple qui sont présentes dans le Store des États-Unis.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Mettre à jour les applications sous licence pour l’appareil et l’utilisateur VPP iOS  <!-- 1305564 -->  
Vous pourrez configurer le jeton VPP iOS pour mettre à jour toutes les applications achetées pour ce jeton via le service Intune. Intune détecte les mises à jour des applications VPP dans le magasin d’applications et les envoie (Push) automatiquement vers l’appareil lorsque ce dernier se connecte.

Pour savoir comment définir un jeton VPP et activer les mises à jour automatiques, consultez Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune (/intune/vpp-apps-ios).


### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Collection d’entité d’association d’appareil utilisateur ajoutée au modèle de données Intune Data Warehouse <!-- 1187917 -->
Vous pouvez désormais générer des rapports et des visualisations des données en utilisant les informations d’association appareil-utilisateur qui associent les collections d’entité utilisateur et appareil. Le modèle de données est accessible par le biais du fichier Power BI (PBIX) extrait de la page Intune Data Warehouse, via le point de terminaison OData, ou en développant un client personnalisé.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Vérifier la conformité de la stratégie pour les boucles de mise à jour de Windows 10 <!-- 1067886 -->
Vous pouvez consulter un rapport sur la stratégie pour vos boucles de mise à jour de Windows 10 à partir de Mises à jour logicielles > État de déploiement par boucle de mise à jour. Le rapport sur la stratégie inclut l’état du déploiement pour les boucles de mise à jour que vous avez configurées. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nouveau rapport qui répertorie les appareils iOS équipés d’anciennes versions iOS   <!-- 1352223 -->
Le rapport **Appareils iOS obsolètes** est disponible à partir de l’espace de travail **Mises à jour logicielles**. Dans ce rapport, vous pouvez afficher la liste des appareils iOS supervisés qui ont été ciblés par une stratégie de mise à jour iOS, et pour lesquels des mises à jour sont disponibles. Pour chaque appareil, vous pouvez afficher un état indiquant la raison pour laquelle l’appareil n’a pas été automatiquement mis à jour. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Afficher les attributions de la stratégie de protection des applications pour la résolution des problèmes <!--  1475003 -->
Dans cette version à venir, l’option **Stratégie de protection des applications** sera ajoutée à la liste déroulante **Affectations** disponible dans le panneau de résolution des problèmes. Vous pouvez maintenant sélectionner des stratégies de protection des applications pour afficher les stratégies de protection des applications affectées aux utilisateurs sélectionnés.



## <a name="week-of-october-2-2017"></a>Semaine du 2 octobre 2017
### <a name="intune-apps"></a>Applications Intune
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Améliorations apportées au workflow de configuration des appareils dans le portail d’entreprise <!--1490692-->
Nous avons amélioré le workflow de configuration des appareils dans l’application Portail d’entreprise pour Android. Le texte de l’interface est plus convivial et spécifique à votre entreprise, et nous avons regroupé des écrans quand cela était possible. Vous pouvez voir cela dans la page [Nouveautés de l’interface utilisateur des applications](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Amélioration de l’aide sur la demande d’accès aux contacts sur les appareils Android <!--1484985-->

L’application Portail d’entreprise pour Android nécessite souvent que l’utilisateur final accepte l’autorisation pour les contacts. Si un utilisateur final refuse cet accès, il voit désormais une notification dans l’application qui lui indique d’accorder l’autorisation pour l’accès conditionnel. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Correction du démarrage sécurisé pour Android <!--1490712-->

Les utilisateurs finaux d’appareils Android peuvent désormais indiquer la raison de la non-conformité dans l’application Portail d’entreprise. Quand c’est possible, ils sont directement positionnés à l’emplacement approprié dans l’application Paramètres pour corriger le problème. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Notifications Push supplémentaires pour les utilisateurs finaux sur l’application Portail d’entreprise pour Android Oreo <!--1475932-->

Les utilisateurs finaux voient des notifications supplémentaires qui leur indiquent quand l’application Portail d’entreprise pour Android Oreo effectue des tâches en arrière-plan, comme la récupération de stratégies auprès du service Intune. La transparence s’en trouve améliorée pour les utilisateurs finaux, qui savent quand le Portail d’entreprise effectue des tâches d’administration sur leur appareil. Cette amélioration fait partie de [l’optimisation générale de l’interface utilisateur du portail d’entreprise](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) pour l’application Portail d’entreprise pour Android Oreo. 

Vous verrez d’autres optimisations relatives aux nouveaux éléments d’interface utilisateur dans Oreo Android.  Les utilisateurs finaux voient des notifications supplémentaires qui leur indiquent quand le portail d’entreprise effectue des tâches en arrière-plan, comme la récupération d’une stratégie auprès du service Intune.  La transparence s’en trouve améliorée pour les utilisateurs finaux, qui savent quand le portail d’entreprise effectue des tâches d’administration sur l’appareil.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nouveaux comportements de l’application Portail d’entreprise pour Android avec les profils professionnels <!-- 1485783 -->

Lorsque vous inscrivez un appareil Android for Work avec un profil professionnel, c’est l’application Portail d’entreprise dans le profil professionnel qui effectue les tâches de gestion sur l’appareil. 

L’application Portail d’entreprise pour Android n’a plus aucune utilité, sauf si vous utilisez une application GAM dans le profil professionnel. Pour améliorer l’expérience liée au profil professionnel, Intune masque automatiquement l’application Portail d’entreprise personnelle après l’inscription réussie d’un profil professionnel.

L’application Portail d’entreprise pour Android peut être activée à tout moment dans le profil personnel en recherchant [Portail d’entreprise dans le Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) et en appuyant sur **Activer**.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Migration du Portail d’entreprise pour Windows 8.1 et Windows Phone 8.1 vers le mode soutenu <!--1428681-->

À partir d’octobre 2017, les applications Portail d’entreprise pour Windows 8.1 et Windows Phone 8.1 passent en mode soutenu. Cela signifie que les applications et les scénarios existants, comme l’inscription et la conformité, seront toujours pris en charge pour ces plateformes. Ces applications resteront disponibles au téléchargement par le biais des canaux de publication existants, comme Microsoft Store. 

Une fois en mode soutenu, ces applications recevront uniquement les mises à jour de sécurité critiques. Aucune mise à jour ou fonctionnalité supplémentaire ne sera publiée pour ces applications. Pour obtenir les nouvelles fonctionnalités, nous vous recommandons de mettre à jour les appareils vers Windows 10 ou Windows 10 Mobile. 


### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Bloquer l’inscription des appareils Samsung Knox non pris en charge <!-- 1490695 -->

L’application Portail d’entreprise tente d’inscrire seulement les appareils Samsung Knox pris en charge. Pour éviter les erreurs d’activation Knox qui empêchent l’inscription à MDM, l’inscription des appareils est tentée seulement si l’appareil apparaît dans la [liste des appareils publiée par Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Les appareils Samsung peuvent avoir des numéros de modèles qui prennent en charge Knox, alors que d’autres ne le prennent pas en charge. Vérifiez la compatibilité de Knox auprès du revendeur de votre appareil avant l’achat et le déploiement. Vous pouvez trouver la liste complète des appareils vérifiés dans les [paramètres de stratégie Android et Samsung Knox Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Fin de la prise en charge d’Android 4.3 et antérieur <!-- 1171126, 1326920 -->
Les applications gérées et l’application Portail d’entreprise pour Android nécessiteront Android 4.4 et ultérieur pour accéder aux ressources de l’entreprise. En décembre, tous les appareils inscrits seront obligatoirement mis hors service et perdront l’accès aux ressources de l’entreprise. Si vous utilisez des stratégies de protection des applications sans MDM, les applications ne recevront aucune mise à jour et perdront en qualité au fil du temps.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Indiquer aux utilisateurs finaux quelles informations de leur appareil peuvent être vues sur les appareils inscrits <!--1165314-->
Nous ajoutons l’information **Type de propriété** dans l’écran des détails des appareils qui se trouve sur toutes les applications du portail d’entreprise. Ainsi, les utilisateurs ont accès à plus d’informations sur la confidentialité directement dans l’article [Quelles informations votre entreprise peut-elle voir ?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune). Ceci sera introduit dans toutes les applications du portail d’entreprise dans un futur proche. Nous avons annoncé ceci pour iOS en [septembre](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Semaine du 25 septembre 2017

### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="intune-supports-ios-11---1428975--"></a>Intune prend en charge iOS 11 <!--1428975-->
Intune prend en charge iOS 11. Ceci avait été annoncé sur le [blog du support technique Intune](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Fin de la prise en charge d’iOS 8.0 <!-- 1164477 -->
Les applications gérées et l’application Portail d’entreprise pour iOS nécessiteront iOS 9.0 et ultérieur pour accéder aux ressources d’entreprise. Les appareils qui ne sont pas mis à jour avant septembre ne seront plus en mesure d’accéder au portail d’entreprise ni à ces applications. 

### <a name="intune-apps"></a>Applications Intune

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Action d’actualisation ajoutée à l’application Portail d’entreprise pour Windows 10 <!--1132468-->
L’application Portail d’entreprise pour Windows 10 permet aux utilisateurs d’actualiser les données dans l’application avec une requête Pull pour actualiser ou, sur les postes de travail, en appuyant sur F5.



## <a name="notices"></a>Remarques

### <a name="plan-for-change-easy-assist-end-of-life----1556480---"></a>Modification planifiée : fin de vie d’Easy Assist <!-- 1556480 -->
Intune utilise Microsoft Easy Assist l’assistance à distance de gestion des PC. Peut-être ignorez-vous que Microsoft Easy Assist est un composant d’Office Live Meeting, un service devenu obsolète le 31 décembre 2017. Par conséquent, l’offre Intune Easy Assist est également devenue obsolète le 31 décembre 2017.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gérer les appareils Android for Work indépendamment des appareils Android <!-- 1490731 EEready-->    
**Remarque** : Les changements suivants seront lancés avec la mise à jour de novembre, mais il est possible que leur exécution sur votre compte prenne du temps. Vous recevrez une notification de confirmation dans le portail Office 365 quand ces modifications seront effectives pour votre compte. Après le lancement, vous disposerez d’options d’administration supplémentaires. Durant le lancement, l’expérience utilisateur final reste la même.

Intune prend en charge la gestion de l’inscription des appareils Android for Work indépendamment de la plateforme Android. Ces paramètres sont gérés sous **Inscription de l’appareil** > **Restrictions d’inscription** > **Restrictions de type d’appareil**. (Ils se trouvaient sous **Inscription de l’appareil** > **Inscription Android for Work** > **Paramètres d’inscription d’Android for Work**.)

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

### <a name="deprecating-support-for-os-x-mavericks-1010-and-previous-versions-of-macos---1489263-plan-for-change-for-1802--"></a>Dépréciation de la prise en charge d’OS X Mavericks 10.10 et versions antérieures de macOS <!--1489263, plan for change for 1802-->
Nous annonçons que nous allons commencer à déconseiller l’inscription des appareils équipés d’OS X Yosemite 10.10 et des versions précédentes de macOS en février 2018. Intune prend entièrement en charge OS X El Capitan 10.11 et les versions ultérieures.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nouveau chemin pour les appareils gérés dans l’API Graph<!-- 1586728 -->
Nous changeons le chemin permettant d’accéder aux appareils gérés dans la version bêta de l’API Graph. 

| | |
|--|--|
| Chemin actuel |  https://graph.microsoft.com/beta/managedDevices |
| Nouveau chemin | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Les deux chemins fonctionnent pendant tout le mois d’octobre. Après la publication du service d’octobre, seul le nouveau chemin fonctionnera.  Si vous utilisez l’API Graph pour accéder aux appareils gérés, mettez à jour et vérifiez vos scripts et vos applications avec le nouveau chemin. Pour connaître les autres changements, consultez le [journal des modifications de l’API Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) mensuel.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail classique Intune. Les comptes Intune créés avant janvier 2017 nécessitent une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder au portail Azure, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure
Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Nouveautés à venir

### <a name="conditional-access-policies-for-intune-will-only-be-available-from-the-azure-portal-----1737088---"></a>Les stratégies d’accès conditionnel pour Intune seront disponibles uniquement à partir du portail Azure  <!-- 1737088 -->
Nous simplifions la configuration et la gestion de l’accès conditionnel. Actuellement, vous pouvez gérer l’accès conditionnel dans le panneau Protection d’application Intune et par le biais de l’expérience Azure AD classique dans le [portail Microsoft Azure](https://manage.windowsazure.com). À partir de janvier, vous pourrez configurer et gérer vos stratégies uniquement dans le [portail Azure](https://portal.azure.com) en accédant à **Azure Active Directory** > **Accès conditionnel**. Pour des raisons pratiques, vous pouvez également accéder à ce panneau à partir d’Intune dans le portail Azure, depuis **Intune** > **Accès conditionnel**.

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747--"></a>Gérer les appareils macOS inscrits auprès de Jamf avec le moteur de conformité des appareils d’Intune<!--1592747-->
À partir du début de l’année 2018, Jamf enverra des informations sur l’état des appareils macOS à Intune, qui évaluera alors la conformité avec les stratégies définies dans la console Intune. En fonction de cet état et d’autres conditions (notamment, l’emplacement, les risques de l’utilisateur, etc.), l’accès conditionnel appliquera des stratégies de conformité aux appareils macOS qui accèdent aux applications cloud et locales reliées à Azure AD, y compris Office 365.

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Modifications apportées à la prise en charge de l’application Portail d’entreprise Intune iOS <!-- 1164474  -->
Une nouvelle version de l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 9.0 ou ultérieure, sera bientôt disponible. La version du portail d’entreprise qui prend en charge iOS 8 sera toujours disponible pendant une très courte période. Toutefois, notez que si vous utilisez également des applications iOS compatibles GAM, nous prenons en charge iOS 9.0 et ultérieur. Vous devez donc vérifier que les utilisateurs finaux effectuent la mise à jour vers le système d’exploitation le plus récent. 

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?
Nous vous donnons cette information à l’avance, même si nous n’avons pas les dates précises, afin que vous ayez le temps de planifier. Vérifiez que vos utilisateurs effectuent la mise à jour vers iOS 9+ et, au moment de la publication de l’application Portail d’entreprise, demandez-leur de mettre à jour leur application Portail d’entreprise.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?
Encouragez les utilisateurs à effectuer la mise à jour vers iOS version 9.0 ou ultérieure pour tirer pleinement parti des nouvelles fonctionnalités d’Intune.  Encouragez les utilisateurs à installer la nouvelle version du portail d’entreprise et à bénéficier des nouvelles fonctionnalités qu’elle propose.

Accédez à Intune dans le portail Azure et affichez Appareils > Tous les appareils, puis filtrez par version d’iOS pour voir tous les appareils actuels avec des systèmes d’exploitation antérieurs à iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Mises à jour requises par Apple pour Application Transport Security <!--748318-->
La société Apple a annoncé qu’elle appliquera des exigences spécifiques pour ATS (Application Transport Security). ATS est utilisé pour renforcer la sécurité de toutes les communications d’application via le protocole HTTPS. Cette modification a une incidence sur les clients Intune qui utilisent les applications de portail d’entreprise iOS.

Nous avons publié, par le biais du programme Apple TestFlight, une version de l’application Portail d’entreprise pour iOS qui respecte les nouvelles exigences d’ATS. Si vous souhaitez l’essayer pour tester votre conformité à ATS, envoyez un e-mail à <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> en indiquant votre prénom, votre nom, votre adresse e-mail et le nom de votre société. Pour plus d’informations, consultez notre [blog de support Intune](https://aka.ms/compportalats).

## <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de l’interface utilisateur du portail d’entreprise](whats-new-app-ui.md)
* [Nouveautés des mois précédents](whats-new-archive.md)
