---
title: "Nouveautés de Microsoft Intune"
titlesuffix: Azure portal
description: "Découvrez les nouveautés du portail Intune Azure"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5058428dca9212d8b20364f58ac463939a699221
ms.sourcegitcommit: 6d69403266dbcb31c879432719798935c94917fa
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="whats-new-in-microsoft-intune"></a>Nouveautés de Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Découvrez les nouveautés hebdomadaires dans Microsoft Intune. Vous pouvez également découvrir les [modifications à venir](#whats-coming), les [avis importants](#notices) sur le service et des informations sur les [versions précédentes](whats-new-archive.md).

> [!Note]
> Pour plus d’informations sur les nouvelles fonctionnalités de gestion des appareils mobiles (MDM) hybride, consultez la page sur les [nouveautés de la gestion hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-february-5-2018"></a>Semaine du 5 février 2018

### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625-eeready---"></a>Nouvelle option pour l’authentification utilisateur dans le cadre de l’inscription en bloc Apple <!-- 747625 eeready -->

> [!NOTE]
> Les nouveaux locataires la verront tout de suite. Pour les locataires existants, cette fonctionnalité sera déployée en avril. Tant que ce déploiement ne sera pas terminé, vous n’aurez peut-être pas accès à ces nouvelles fonctionnalités.

Intune vous donne maintenant la possibilité d’authentifier les appareils à l’aide de l’application Portail d’entreprise pour les méthodes d’inscription suivantes :

- Programme d'inscription d'appareils Apple
- Apple School Manager
- Inscription à Apple Configurator

Lorsque vous utilisez l’option Portail d’entreprise, l’authentification multifacteur Azure Active Directory peut être appliquée sans bloquer ces méthodes d’inscription.

Lorsque vous utilisez l’option Portail d’entreprise, Intune ignore l’authentification utilisateur dans l’Assistant Réglages iOS pour l’inscription d’affinité utilisateur. Cela signifie que l’appareil est initialement inscrit comme appareil sans utilisateur et, par conséquent, vous ne recevez pas les configurations ou stratégies des groupes d’utilisateurs. Il reçoit uniquement les configurations et les stratégies des groupes d’appareils. Toutefois, Intune installera automatiquement l’application Portail d’entreprise sur l’appareil. Le premier utilisateur à lancer l’application Portail d’entreprise et à s’y connecter sera associé à l’appareil dans Intune. À ce stade, l’utilisateur reçoit les configurations et les stratégies de ses groupes d’utilisateurs. L’association de l’utilisateur ne peut pas être modifiée sans réinscription.

#### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685-eeready---"></a>Prise en charge d’Intune pour plusieurs comptes DEP / Apple School Manager <!-- 747685 eeready -->

Intune prend maintenant en charge l’inscription des appareils jusqu'à la limite de 100 comptes dans le cadre du Programme d’inscription des appareils (DEP) ou Apple School Manager. Chaque jeton téléchargé peut être géré séparément pour les profils d’inscription et les appareils. Un profil d’inscription différent peut être affecté automatiquement pour chaque jeton DEP/School Manager téléchargé. Si plusieurs jetons School Manager sont téléchargés, un seul jeton peut être partagé avec Microsoft School Data Sync à la fois.

Après la migration, les API Graph en version bêta et les scripts publiés pour la gestion DEP Apple ou ASM via Graph ne fonctionneront plus. De nouvelles versions bêta des API Graph sont en cours de développement et seront publiées après la migration.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impression à distance sur un réseau sécurisé <!-- 1709994  -->
Les solutions d’impression mobiles sans fil PrinterOn permettront aux utilisateurs d’imprimer à distance depuis n’importe où et à tout moment via un réseau sécurisé. PrinterOn s’intégrera au Kit SDK APP d’Intune à la fois pour iOS et Android. Vous pourrez cibler les stratégies de protection d’application pour cette application via le panneau des **stratégies de protection d’application** d’Intune, dans la console d’administration. Les utilisateurs finaux pourront télécharger l’application « PrinterOn for Microsoft » via le Google Play Store ou iTunes afin de l’utiliser dans leur écosystème Intune.

## <a name="week-of-january-29-2018"></a>Semaine du 29 janvier 2018

### <a name="device-enrollment"></a>Inscription des appareils

#### <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertes pour les jetons expirés et les jetons qui arrivent à expiration <!-- 1639263 -->
La page de vue d’ensemble affiche maintenant des alertes pour les jetons expirés et ceux qui arrivent à expiration. Lorsque vous cliquez sur une alerte pour un jeton unique, vous accéderez à la page des détails de ce jeton.  Si vous cliquez sur une alerte comportant plusieurs jetons, vous accéderez à une liste de tous les jetons avec leur état. Les administrateurs doivent renouveler leurs jetons avant la date d’expiration.

### <a name="device-management"></a>Gestion des appareils

#### <a name="remote-erase-command-support-for-macos-devices----1438084---"></a>Prise en charge de la commande d’effacement à distance pour les appareils macOS <!-- 1438084 -->

Les administrateurs peuvent exécuter une commande d’effacement à distance pour les appareils macOS.

> [!IMPORTANT]
> La commande d’effacement ne peut pas être annulée et doit être utilisée avec précaution.

La commande d’effacement supprime toutes les données, y compris le système d’exploitation, d’un appareil. Elle entraîne aussi la suppression de l'appareil de la gestion Intune. Aucun avertissement n’est envoyé à l’utilisateur, et l’effacement se produit dès l’envoi de la commande.

Vous pouvez configurer un code PIN de récupération à 6 chiffres. Ce code PIN peut servir à déverrouiller l’appareil effacé avant de lancer la réinstallation du système d’exploitation. Une fois que l’effacement a démarré, le code PIN apparaît dans une barre d’état sur le panneau de présentation de l’appareil dans Intune. Le code PIN restera affiché tant que l’effacement est en cours. Une fois l’effacement terminé, l’appareil disparaît totalement de la gestion Intune. Veillez à enregistrer le code PIN de récupération afin que toute personne qui restaure l’appareil puisse l’utiliser.

#### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Révoquer des licences pour un jeton Programme d’achat en volume iOS <!-- 820870 --> 
Vous pouvez révoquer la licence de toutes les applications de Programme d’achat en volume (VPP) iOS pour un jeton VPP donné.

### <a name="app-management"></a>Gestion d'applications

#### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Révocation des applications du Programme d’achat en volume iOS  <!-- 820863 -->
Pour un appareil donné qui a une ou plusieurs applications de Programme d’achat en volume (VPP) iOS, vous pouvez révoquer pour l’appareil la licence d’application associée basée sur l’appareil. La révocation d’une licence d’application ne désinstalle pas l’application VPP de l’appareil. Pour désinstaller une application VPP, vous devez remplacer l’action d’attribution par **Désinstaller**. Pour plus d’informations, consultez [Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune](vpp-apps-ios.md).

#### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Affecter des applications mobiles Office 365 aux appareils iOS et Android à l’aide du type d’application intégré <!-- 1332318 -->
Le type d’application **Intégré** facilite la création d’applications Office 365 et leur affectation aux appareils iOS et Android gérés. Ces applications incluent les applications Office 365 telles que Word, Excel, PowerPoint et OneDrive. Vous pouvez affecter des applications spécifiques au type d’application et modifier la configuration des informations des applications.

#### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusion et exclusion d’affectations d’applications en fonction de groupes <!-- 1406920 -->

Pendant l’affectation d’une application et après avoir sélectionné un type d’affectation, vous pouvez sélectionner les groupes à inclure et ceux à exclure.

#### <a name="website-learning-mode----1631908---"></a>Mode d’apprentissage de site web (Website Learning Mode) <!-- 1631908 -->

Intune propose maintenant une extension du mode d’apprentissage de la Protection des informations Windows (WIP). En plus de l’affichage des informations sur les applications WIP, vous pouvez consulter un récapitulatif des appareils qui partagent des données de travail avec des sites web. Ces informations vous permettront d’identifier les sites web à ajouter aux stratégies WIP des utilisateurs et des groupes.

#### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Approuver l’application Portail d’entreprise pour Android for Work <!--1797090 -->
Si votre organisation utilise Android for Work, vous devrez approuver manuellement l’application Portail d’entreprise pour Android afin qu’elle continue à recevoir les mises à jour automatiques du magasin Google Play managé.

#### <a name="faceid-on-ios-devices----1807377---"></a>FaceID sur les appareils iOS <!-- 1807377 -->
Les stratégies de protection des applications Intune prennent désormais en charge un paramètre qui gère FaceID sur les appareils iOS. Ce paramètre est destiné aux appareils qui prennent en charge la fonctionnalité FaceID (uniquement l’iPhone X pour l’instant). Ce paramètre est indépendant des contrôles TouchID actuellement pris en charge. Les organisations ont la possibilité de choisir FaceID comme code PIN valide en remplacement des commandes TouchID.

### <a name="device-configuration"></a>Configuration des appareils

#### <a name="you-can-assign-an-application-configuration-policy-to-groups-by-including-and-excluding-assignments-----1480316---"></a>Vous pouvez attribuer une stratégie de configuration d’application à des groupes en incluant et excluant des affectations  <!-- 1480316 --> 

Vous pouvez attribuer une stratégie de configuration d’application à un groupe d’utilisateurs et d’appareils à l’aide d’une combinaison d’affectations d’inclusion et d’exclusion. Les affectations peuvent être choisies sous la forme d’une sélection personnalisée de groupes ou d’un groupe virtuel. Un groupe virtuel peut être notamment **Tous les utilisateurs**, **Tous les appareils** ou **Tous les utilisateurs + Tous les appareils**.

#### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Prise en charge de la stratégie de mise à niveau de l’édition Windows 10   <!-- 903672(archived), 1119689 -->  
Vous pouvez créer une stratégie de mise à niveau d’édition Windows 10 qui met à niveau les appareils Windows 10 vers Windows 10 Éducation, Windows 10 Éducation N, Windows 10 Professionnel, Windows 10 Professionnel N, Windows 10 Professionnel Éducation et Windows 10 Professionnel Éducation N. Pour plus d’informations sur les mises à niveau d’édition Windows 10, consultez [Guide pratique pour configurer les mises à niveau d’édition Windows 10 ](edition-upgrade-configure-windows-10.md).

#### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Les stratégies d’accès conditionnel pour Intune sont disponibles uniquement à partir du portail Azure <!-- 1737088 1634311 -->

À partir de cette version, vous pouvez configurer et gérer vos stratégies d’accès conditionnel dans le [portail Azure](https://portal.azure.com) en accédant à **Azure Active Directory** > **Accès conditionnel**. Pour des raisons pratiques, vous pouvez également accéder à ce panneau à partir d’Intune dans le portail Azure, depuis **Intune** > **Accès conditionnel**.

#### <a name="updates-to-compliance-emails---1637547---"></a>Mises à jour des e-mails de conformité <!--1637547 -->

Quand un e-mail est envoyé pour signaler un appareil non conforme, des informations sur cet appareil non conforme sont ajoutées. 


## <a name="week-of-january-22-2018"></a>Semaine du 22 janvier 2018

### <a name="intune-apps"></a>Applications Intune

#### <a name="new-functionality-for-the-resolve-action-for-android-devices---1583480--"></a>Nouvelles fonctionnalités de l’action « Résoudre » pour les appareils Android <!--1583480-->

L’application Portail d’entreprise pour Android étend l’action « Résoudre » sur **Mettre à jour les paramètres d’appareil** afin de résoudre les [problèmes de chiffrement d’appareil](/intune-user-help/encrypt-your-device-android).

#### <a name="remote-lock-available-in-company-portal-app-for-windows-10---676506--"></a>Verrouillage à distance disponible dans l’application Portail d’entreprise pour Windows 10 <!--676506-->
Les utilisateurs finaux peuvent désormais verrouiller à distance leurs appareils à partir de l’application Portail d’entreprise pour Windows 10. Cela ne s’affichera pas pour l’appareil local qu’ils utilisent de manière active.

#### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546--"></a>Résolution plus rapide des problèmes de conformité affectant l’application Portail d’entreprise pour Windows 10 <!--676546-->
Les utilisateurs finaux d’appareils Windows peuvent choisir la raison de la non-conformité dans l’application Portail d’entreprise. Quand c’est possible, ils sont directement positionnés à l’emplacement approprié dans l’application Paramètres pour corriger le problème.

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

Vous pouvez désormais bloquer les changements de date et d’heure sur les appareils Samsung Knox. Vous trouverez cette fonctionnalité dans **Profils de configuration d’appareil** > **Restrictions d’appareil (Android)** > **Général**.

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
Vous pourrez maintenant installer des applications Office sur des appareils macOS. Ce nouveau type d’application vous permet d’installer Word, Excel, PowerPoint, Outlook et OneNote. Ces applications bénéficient également de Microsoft AutoUpdate (MAU) qui garantit que vos applications sont sécurisées et à jour.

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

Nous avons mis à jour quelques-unes des API Graph pour Intune (actuellement en version bêta). Pour plus d’informations, consultez le [journal mensuel des modifications de l’API Graph](https://developer.microsoft.com/graph/docs/concepts/changelog).


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

Quand vous utilisez les nouveaux paramètres, tenez compte des points suivants :

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
De nouveaux processus et de nouveaux outils sont maintenant disponibles pour déplacer les utilisateurs et leurs appareils de MDM hybride vers Intune dans le portail Azure. Vous pouvez ainsi effectuer les tâches suivantes :
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

Avec la publication d’Android Oreo, Google introduit une suite de fonctionnalités de sécurité appelée Google Play Protect qui permet aux utilisateurs et aux organisations d’exécuter des applications sécurisées et des images Android sécurisées. Intune prend maintenant en charge les fonctionnalités de Google Play Protect, notamment l’attestation SafetyNet distante. Les administrateurs peuvent définir des critères de stratégie de conformité pour que Google Play Protect soit configuré et sain.
Le paramètre **Attestation d’appareil SafetyNet** nécessite que l’appareil se connecte à un service Google pour vérifier que l’appareil est intègre et qu’il n’est pas compromis. Les administrateurs peuvent également définir un paramètre de profil de configuration pour qu’Android for Work exige que les applications installées soient vérifiées par les services Google Play. Si un appareil n’est pas conforme aux exigences de Google Play Protect, l’accès conditionnel peut empêcher les utilisateurs d’accéder aux ressources de l’entreprise.

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
Le pack d’administration de System Center Operations Manager (SCOM) pour le connecteur Exchange est maintenant disponible pour vous aider à analyser les journaux du connecteur Exchange. Cette fonctionnalité offre différents moyens de surveiller le service à des fins de résolution des problèmes.

## <a name="week-of-november-6-2017"></a>Semaine du 6 novembre 2017

### <a name="device-enrollment"></a>Inscription des appareils
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Cogestion pour les appareils Windows 10 <!-- 1243445 -->
La cogestion est une solution qui propose une passerelle entre la gestion classique et la gestion moderne tout en vous donnant la possibilité d’opérer cette transition selon une approche en plusieurs phases. À la base, la cogestion est une solution qui permet aux appareils Windows 10 d’être gérés simultanément par Configuration Manager et Microsoft Intune, et d’être joints à Active Directory (AD) et à Azure Active Directory (Azure AD).  Cette configuration vous offre un moyen de vous moderniser à un rythme qui convient à votre organisation si vous ne pouvez pas le faire d’un coup.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Limiter l’inscription Windows par version de système d’exploitation<!-- 245498 -->
En tant qu’administrateur Intune, vous pouvez maintenant spécifier une version minimale et maximale de Windows 10 pour les inscriptions d’appareils. Vous pouvez définir ces restrictions dans le panneau **Configurations de plateforme**.

Intune continue à prendre en charge l’inscription des PC et téléphones Windows 8.1. Toutefois, seules les versions de Windows 10 peuvent être configurées avec des limites minimale et maximale. Pour autoriser l’inscription d’appareils 8.1, laissez vide la limite minimale.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Alertes pour les appareils non affectés Windows AutoPilot  <!-- 1631236 -->
Une nouvelle alerte est disponible pour les appareils non attribués Windows AutoPilot dans la page **Microsoft Intune** > **Inscription de l’appareil** > **Vue d’ensemble**. Cette alerte indique combien d’appareils du programme AutoPilot n’ont pas de profils de déploiement AutoPilot affectés. Utilisez les informations de l’alerte pour créer des profils et les affecter aux appareils non affectés. Quand vous cliquez sur l’alerte, une liste complète des appareils Windows AutoPilot et des informations détaillées les concernant s’affichent. Pour plus d’informations, consultez [Inscrire des appareils Windows à l’aide du programme de déploiement Windows AutoPilot](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Gestion des appareils

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Bouton Actualiser pour la liste des appareils    <!-- 1333581 -->
La liste des appareils ne s’actualisant pas automatiquement, vous pouvez utiliser le bouton Actualiser pour mettre à jour les appareils affichés dans la liste.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Prise en charge de l’Autorité de certification Symantec Cloud  <!-- 1333638 -->    
Intune prend désormais en charge l’Autorité de certification Symantec Cloud qui permet à Intune Certificate Connector d’émettre des certificats PKCS de l’Autorité de certification Symantec Cloud sur des appareils gérés par Intune. Si vous utilisez déjà Intune Certificate Connector avec l’Autorité de certification Microsoft, vous pouvez utiliser la configuration existante d’Intune Certificate Connector en y ajoutant la prise en charge de l’Autorité de certification de Symantec.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nouveaux éléments ajoutés à l’inventaire des appareils   <!--1404455 -->
Les nouveaux éléments suivants sont maintenant disponibles dans [l’inventaire effectué par les appareils inscrits](device-inventory.md) :

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
Les administrateurs informatiques peuvent désormais définir une condition dans le portail d’administration Azure permettant d’appliquer un code secret à la place d’un code PIN numérique via la gestion des applications mobiles (MAM) lors du lancement de l’application. Selon la configuration, l’utilisateur doit définir et utiliser un code secret quand il y est invité avant d’obtenir l’accès à des applications compatibles MAM. Un code secret est défini comme un code PIN numérique avec au moins un caractère spécial ou une lettre majuscule/minuscule. Cette version d’Intune propose cette fonctionnalité **sur iOS uniquement**. Intune prend en charge un code secret comme un code PIN numérique, il définit une longueur minimale et autorise la répétition des caractères et des séquences. Cette fonctionnalité nécessite la participation des applications (c’est-à-dire, WXP, Outlook, Managed Browser, Yammer) pour intégrer le kit SDK Intune App avec le code de cette fonctionnalité en place dans le but d’appliquer les paramètres du code secret dans les applications ciblées.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>Numéro de version des applications métier dans le rapport d’état d’installation de l’appareil<!-- 1233999 -->
Avec cette version, le rapport d’état d’installation de l’appareil affiche le numéro de version des applications métier pour iOS et Android. Vous pouvez utiliser cette information pour dépanner vos applications ou trouver les appareils qui exécutent des versions d’application anciennes.


### <a name="device-configuration"></a>Configuration des appareils
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Les administrateurs peuvent désormais configurer les paramètres du Pare-feu d’un appareil avec un profil de configuration d’appareil <!-- 951708 -->   
Les administrateurs peuvent activer le Pare-feu sur les appareils et configurer divers protocoles pour les réseaux privés, publics et de domaine.  Ces paramètres de pare-feu se trouvent dans le profil « Endpoint protection ».

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard permet de protéger les appareils des sites web non approuvés, comme défini par votre organisation <!-- 958257 -->   
Les administrateurs peuvent définir les sites comme « approuvés » ou « appartenant à l’entreprise » à l’aide d’un flux de travail Protection des informations Windows ou du nouveau profil « Limite réseau » dans les configurations de l’appareil. S’ils sont consultés dans Microsoft Edge, les sites qui ne sont pas listés dans la limite réseau approuvée d’un appareil Windows 10 64 bits s’ouvrent à la place dans un navigateur d’une machine virtuelle Hyper-V.

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
Vous trouverez un nouveau profil de configuration d’appareil appelé **Limite réseau** avec vos autres profils de configuration d’appareil. Utilisez ce profil pour définir des ressources en ligne à considérer comme approuvées et appartenant à l’entreprise. Vous devez définir une limite réseau pour un appareil *avant* de pouvoir utiliser les fonctionnalités comme Windows Defender Application Guard et Protection des informations Windows sur l’appareil. Il est important de définir une seule limite réseau pour chaque appareil.

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

Le workflow de configuration des appareils a été amélioré dans l’application Portail d’entreprise pour iOS. La langue est plus conviviale, et nous avons regroupé des écrans dans la mesure du possible. La langue est également plus adaptée à l’entreprise, car nous utilisons à chaque fois son nom dans le texte de configuration. Vous pouvez voir ce workflow mis à jour sur la page  [Nouveautés de l’interface utilisateur de l’application](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Surveiller et dépanner

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>L’entité Utilisateur contient les données utilisateur les plus récentes dans le modèle de données de l’entrepôt de données <!-- 1544273 -->
La première version du modèle de données de l’entrepôt de données Intune ne contenait que des données Intune historiques récentes. Les auteurs de rapports ne pouvaient pas capturer l’état actuel d’un utilisateur. Dans cette mise à jour, **l’entité Utilisateur** est renseignée avec les données utilisateur les plus récentes.


## <a name="notices"></a>Remarques

### <a name="plan-for-change-update-where-you-configure-your-app-protection-policies"></a>Modification prévue : mise à jour au niveau de la configuration de vos stratégies de protection d’application

À partir de mars 2018, nous allons vous rediriger temporairement du panneau du service Protection d’application Intune du portail Azure vers le panneau Application mobile dans Intune dans le portail Azure. Notez que toutes vos stratégies de protection d’application sont déjà dans le panneau Application mobile dans Intune sous Configuration de l’application. Au lieu d’aller sur Protection d’application Intune, vous allez juste sur Intune. En avril, nous arrêterons la redirection et supprimerons totalement le panneau du service Protection d’application Intune, car celui-ci fait double emploi avec ce qui est maintenant intégré dans Intune. 

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?
Cette modification affecte à la fois les clients autonomes Intune et les clients hybrides (Intune avec Configuration Manager). Cette intégration permet de simplifier l’administration de votre gestion cloud. En effet, vous n’avez plus qu’un seul panneau dans Azure – le panneau Intune – pour gérer des groupes, des stratégies, des applications et toute gestion d’appareils mobiles.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?
Mettez Intune en favori à la place du panneau du service Protection d’application Intune et veillez à vous familiariser avec le workflow de stratégie de protection d’application dans le panneau Application mobile dans Intune. Pendant une courte période, nous assurerons la redirection puis nous supprimerons le panneau Protection d’application. N’oubliez pas que toutes les stratégies de protection d’application sont déjà hors service dans Intune et que vous pouvez modifier les stratégies d’accès conditionnel en suivant la documentation ici : [https://aka.ms/azuread_ca](https://aka.ms/azuread_ca).

**Informations supplémentaires** : [https://aka.ms/intuneapppolicy](https://aka.ms/intuneapppolicy)

### <a name="updated-new-security-enhancements-in-the-intune-service-----1637539---"></a>Mise à jour : Nouvelles améliorations de la sécurité dans le service Intune  <!-- 1637539 -->   

Nous déployons actuellement des améliorations de la sécurité dans le service Intune. Dans le cadre de cette modification, avec la mise à jour de mars du service Intune, vous aurez un bouton bascule dans la console Intune sur Azure qui vous permettra d’activer ou de désactiver cette fonctionnalité de sécurité. Lorsque la fonctionnalité est activée, les appareils avec aucune stratégie de conformité affectée sont marqués « non conformes ».

**Clients hybrides** : nous ne proposons pas cette modification pour les clients hybrides pour l’instant. Aucune action de votre part n’est nécessaire. Toutefois, nous vous encourageons vivement à vérifier que vos appareils ont au moins une stratégie de conformité qui leur est affectée.

#### <a name="how-does-this-affect-me"></a>Comment cela m’affecte-t-il ?

Lorsque nous allons commencer à déployer cette modification dans la mise à jour de mars, cette fonctionnalité va vous affecter différemment selon que vous avez déjà des stratégies de conformité affectées ou non.

- Si vous êtes un locataire nouveau ou existant et que vous n’avez pas de stratégie de conformité affectée à vos appareils, le bouton bascule est automatiquement défini sur **conforme**. La fonctionnalité est désactivée par défaut dans la console. Il n’y a aucun impact sur les utilisateurs finaux.
- Si vous êtes un locataire existant et que tous vos appareils ont une stratégie de conformité qui leur est affectée, le bouton bascule est automatiquement défini sur « non conforme ». La fonctionnalité sera activée par défaut lors du déploiement de la mise à jour de mars. 

Si vous utilisez des stratégies de conformité avec un accès conditionnel et que la fonctionnalité est activée, les appareils sans au moins une stratégie de conformité qui leur est affectée sont désormais bloqués par une Autorité de certification. Les utilisateurs finaux associés à ces appareils, qui ont été précédemment autorisés à accéder à l’e-mail, perdent leur accès, sauf si vous affectez au moins une stratégie de conformité à tous les appareils.   
 
#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Que dois-je faire pour me préparer à cette modification ?  

Si vous utilisez l’accès conditionnel, nous vous recommandons d’activer cette fonctionnalité et de laisser le bouton bascule sur **Non conforme**. Pour éviter que vos utilisateurs finaux perdent l’accès à l’e-mail, vérifiez que tous vos appareils ont au moins une stratégie de conformité qui leur est affectée. Voici certaines modifications que nous apportons pour vous aider à réaliser cela :   

- Nous avons créé un rapport appelé **Appareils sans stratégie de conformité** dans le portail Intune, que vous pouvez utiliser pour identifier tous les appareils de votre environnement qui n’ont pas de stratégie de conformité affectée. 
- L’option **Tous les utilisateurs** facilite l’affectation d’une stratégie de conformité à tous les utilisateurs.

Si vous choisissez de laisser le bouton bascule désactivé, aucune action supplémentaire n’est requise de votre part.

**Informations supplémentaires** : [https://aka.ms/compliance_policies](https://aka.ms/compliance_policies)

### <a name="plan-for-change-change-in-support-for-the-microsoft-intune-app-sdk-for-cordova-plugin"></a>Modification prévue : modification de la prise en charge du plug-in Cordova dans le SDK de l’application Microsoft Intune
Intune met fin au support du [plug-in Cordova du SDK de l’application Microsoft Intune](app-sdk-cordova.md) le 1er mai 2018. Nous vous recommandons d’utiliser l’outil de création de package de restrictions d’application Intune à la place, pour préparer vos applications basées sur Cordova afin qu’elles soient gérables et disponibles dans Intune. À la prise d’effet de ce changement, le SDK de l’application Microsoft Intune pour le plug-in Cordova ne sera plus tenu à jour et ne recevra pas de mises à jour. Les développeurs d’applications ne pourront pas utiliser ce plug-in. Intune prévoit de continuer la prise en charge des applications créées avec Cordova. Toutefois, toutes les applications créées avec le SDK de l’application Microsoft Intune pour le plug-in Cordova auront des fonctionnalités réduites dans Intune. Une fois traitées avec l’outil de création de package de restrictions d’application Intune, les applications peuvent être déployées pour les utilisateurs finaux de façon habituelle. Pour les applications Android basées sur Cordova publiées dans Google Play Store :
- Les utilisateurs finaux sont invités à indiquer leurs informations d’identification pour recevoir la stratégie Intune au premier lancement.
- Les applications doivent être publiées dans l’App Store ciblé pour les utilisateurs Intune, par exemple « Application Contoso pour Intune ». 

Pour plus d’informations sur l’outil de création de package de restrictions d’application, consultez [Outil de création de package de restrictions d’application pour iOS](app-wrapper-prepare-ios.md) et [Outil de création de package de restrictions d’application pour Android](app-wrapper-prepare-android.md). Pour tout problème ou toute question, contactez [ msintuneappsdk@microsoft.com ](mailto:msintuneappsdk@microsoft.com). 

### <a name="plan-for-change-use-intune-on-azure-now-for-your-mdm-management----1227338---"></a>Modification planifiée : utiliser Intune sur Azure maintenant pour la gestion des appareils mobiles<!-- 1227338 -->
Il y a plus d’un an, nous avons annoncé une [préversion publique d’Intune sur Azure](https://cloudblogs.microsoft.com/enterprisemobility/2016/12/07/public-preview-of-intune-on-azure/) et avons donné suite six mois auparavant avec la [disponibilité générale de la nouvelle expérience d’administration](https://cloudblogs.microsoft.com/enterprisemobility/2017/06/08/the-new-intune-and-conditional-access-admin-consoles-are-ga/) pour Intune. À compter du 2 avril 2018, nous allons désactiver la gestion des appareils mobiles dans la console Silverlight classique pour les clients qui utilisent la version autonome d’Intune. Vous pouvez utiliser à la place [Intune sur Azure](https://aka.ms/Intune_on_Azure) pour vos besoins de gestion des appareils mobiles. Si vous utilisez toujours la console classique pour la gestion des appareils mobiles, arrêtez et familiarisez-vous avec Intune sur Azure. Cette modification ne devrait pas avoir d’impact sur les utilisateurs finaux. La gestion classique des PC restera dans Silverlight. Vous trouverez plus d’informations sur cette modification et la façon dont elle vous affecte [ici](https://aka.ms/Intune_on_Azure_mdm).


### <a name="plan-for-change-easy-assist-end-of-life----1556480---"></a>Modification planifiée : fin de vie d’Easy Assist <!-- 1556480 -->
Intune utilise Microsoft Easy Assist l’assistance à distance de gestion des PC. Peut-être ignorez-vous que Microsoft Easy Assist est un composant d’Office Live Meeting, un service devenu obsolète le 31 décembre 2017. Par conséquent, l’offre Intune Easy Assist est également devenue obsolète le 31 décembre 2017.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Gérer les appareils Android for Work indépendamment des appareils Android <!-- 1490731 EEready-->    
**Remarque** : Les changements suivants seront lancés avec la mise à jour de novembre, mais il est possible que leur exécution sur votre compte prenne du temps. Vous recevrez une notification de confirmation dans le portail Office 365 quand ces modifications seront effectives pour votre compte. Après le lancement, vous disposerez d’options d’administration supplémentaires. Durant le lancement, l’expérience utilisateur final reste la même.

Intune prend en charge la gestion de l’inscription des appareils Android for Work indépendamment de la plateforme Android. Ces paramètres sont gérés sous **Inscription de l’appareil** > **Restrictions d’inscription** > **Restrictions de type d’appareil**. (Ils se trouvaient sous **Inscription de l’appareil** > **Inscription Android for Work** > **Paramètres d’inscription d’Android for Work**.)

Par défaut, les paramètres de vos appareils Android for Work seront identiques aux paramètres de vos appareils Android. Toutefois, ce ne sera plus le cas une fois que vous aurez modifié vos paramètres Android for Work.

Si vous bloquez l’inscription Android for Work personnelle, seuls les appareils Android d’entreprise peuvent s’inscrire en tant qu’Android for Work.

Quand vous utilisez les nouveaux paramètres, tenez compte des points suivants :

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
La dépréciation de l’inscription des appareils OS X Yosemite 10.10 et versions précédentes de macOS débutera en février 2018. Intune prend entièrement en charge OS X El Capitan 10.11 et les versions ultérieures.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nouveau chemin pour les appareils gérés dans l’API Graph<!-- 1586728 -->
Le chemin utilisé pour accéder aux appareils gérés dans la version bêta de l’API Graph change. 

| | |
|--|--|
| Chemin actuel |  https://graph.microsoft.com/beta/managedDevices |
| Nouveau chemin | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Les deux chemins fonctionnent pendant tout le mois d’octobre. Après la publication du service d’octobre, seul le nouveau chemin fonctionnera.  Si vous utilisez l’API Graph pour accéder aux appareils gérés, mettez à jour et vérifiez vos scripts et vos applications avec le nouveau chemin. Pour connaître les autres changements, consultez le [journal des modifications de l’API Graph](https://developer.microsoft.com/graph/docs/concepts/changelog) mensuel.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->
Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail classique Intune. Les comptes Intune créés avant janvier 2017 nécessitent une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder au portail Azure, nous vous recommandons vivement de créer un compte d’essai afin de tester la nouvelle expérience.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Rôles d’administration remplacés dans le portail Azure
Les rôles d’administration de la gestion des applications mobiles (GAM), à savoir Contributeur, Propriétaire et Lecture seule, qui sont utilisés dans le portail Intune classique, sont remplacés par un nouvel ensemble complet de contrôles d’administration basés sur des rôles (RBAC) dans le portail Intune Azure. Une fois la migration effectuée vers le portail Azure, vous devez associer vos administrateurs à ces nouveaux rôles d’administration. Pour en savoir plus sur les contrôles RBAC et les nouveaux rôles, voir [Rôles Intune (RBAC) pour Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>Nouveautés à venir

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Mise à jour de l’expérience utilisateur dans l’application Portail d’entreprise pour iOS <!--1412866-->

Nous publierons une mise à jour importante de l’expérience utilisateur dans l’application Portail d’entreprise pour iOS. La mise à jour présentera une toute nouvelle apparence, plus moderne, avec une amélioration de l’accessibilité et de l’utilisation. Toutes les fonctionnalités actuelles de l’application Portail d’entreprise pour iOS seront conservées.

Nous vous offrons une préversion de l’application Portail d’entreprise pour iOS mise à jour via le programme Apple TestFlight pour que vous l’utilisiez et nous fassiez part de vos commentaires. Inscrivez-vous à l’adresse https://aka.ms/intune_ios_cp_testflight pour accéder à TestFlight.

### <a name="conditional-access-policies-for-intune-will-only-be-available-from-the-azure-portal-----1737088---"></a>Les stratégies d’accès conditionnel pour Intune seront disponibles uniquement à partir du portail Azure  <!-- 1737088 -->
Nous simplifions la configuration et la gestion de l’accès conditionnel. Actuellement, vous pouvez gérer l’accès conditionnel dans le panneau Protection d’application Intune et par le biais de l’expérience Azure AD classique dans le [portail Microsoft Azure](https://manage.windowsazure.com). À partir de janvier, vous pourrez configurer et gérer vos stratégies uniquement dans le [portail Azure](https://portal.azure.com) en accédant à **Azure Active Directory** > **Accès conditionnel**. Pour des raisons pratiques, vous pouvez également accéder à ce panneau à partir d’Intune dans le portail Azure, depuis **Intune** > **Accès conditionnel**.

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747--"></a>Gérer les appareils macOS inscrits auprès de Jamf avec le moteur de conformité des appareils d’Intune<!--1592747-->
À partir du début de l’année 2018, Jamf enverra des informations sur l’état des appareils macOS à Intune, qui évaluera alors la conformité avec les stratégies définies dans la console Intune. En fonction de cet état et d’autres conditions (notamment, l’emplacement, les risques de l’utilisateur, etc.), l’accès conditionnel appliquera des stratégies de conformité aux appareils macOS qui accèdent aux applications cloud et locales reliées à Azure AD, y compris Office 365.

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Modifications apportées à la prise en charge de l’application Portail d’entreprise Intune iOS <!-- 1164474  -->
Une nouvelle version de l’application Portail d’entreprise Microsoft Intune pour iOS, qui prendra en charge uniquement les appareils exécutant iOS version 9.0 ou ultérieure, sera bientôt disponible. La version du portail d’entreprise qui prend en charge iOS 8 sera toujours disponible pendant une courte période. Toutefois, si vous utilisez également des applications iOS compatibles MAM, nous prenons en charge iOS 9.0 et ultérieur. Vous devez donc vérifier que les utilisateurs finaux effectuent la mise à jour vers le système d’exploitation le plus récent. 

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
