---
title: "Édition préliminaire"
description: 
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 01/18/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 12f4a09fe10ec792abe8183369a21f53c23f5d1a
ms.sourcegitcommit: 53d272defd2ec061dfdfdae3668d1b676c8aa7c6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/23/2018
---
# <a name="the-early-edition-for-microsoft-intune---january-2018"></a>Édition anticipée pour Microsoft Intune - Janvier 2018

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

### <a name="easier-resolution-of-compliance-issues-for-the-company-portal-app-for-windows-10---676546---"></a>Résolution plus rapide des problèmes de conformité affectant l’application Portail d’entreprise pour Windows 10 <!--676546 -->

Les utilisateurs finaux d’appareils Windows peuvent désormais indiquer la raison de la non-conformité dans l’application Portail d’entreprise. Quand c’est possible, ils sont directement positionnés à l’emplacement approprié dans l’application Paramètres pour corriger le problème.

### <a name="new-option-for-user-authentication-for-apple-bulk-enrollment----747625---"></a>Nouvelle option pour l’authentification utilisateur dans le cadre de l’inscription en bloc Apple <!-- 747625 -->
Intune vous donnera la possibilité d’authentifier les appareils à l’aide de l’application Portail d’entreprise pour les méthodes d’inscription suivantes :

- Programme d'inscription d'appareils Apple
- Apple School Manager
- Inscription à Apple Configurator

Lorsque vous utilisez l’option Portail d’entreprise, l’authentification multifacteur Azure Active Directory peut être appliquée sans bloquer ces méthodes d’inscription.

Lorsque vous utilisez l’option Portail d’entreprise, Intune ignore l’authentification utilisateur dans l’Assistant Réglages iOS pour l’inscription d’affinité utilisateur. Cela signifie que l’appareil est initialement inscrit comme appareil sans utilisateur et, par conséquent, vous ne recevrez pas les configurations ou stratégies des groupes d’utilisateurs. Il recevra uniquement les configurations et les stratégies des groupes d’appareils. Toutefois, Intune installera automatiquement l’application Portail d’entreprise sur l’appareil. Le premier utilisateur à lancer l’application Portail d’entreprise et à s’y connecter sera associé à l’appareil dans Intune. À ce stade, l’utilisateur recevra les configurations et les stratégies de ses groupes d’utilisateurs. L’association de l’utilisateur ne peut pas être modifiée sans réinscription.

### <a name="intune-support-for-multiple-apple-dep--apple-school-manager-accounts----747685---"></a>Prise en charge d’Intune pour plusieurs comptes DEP / Apple School Manager <!-- 747685 -->
Intune prendra en charge l’inscription des appareils jusqu'à la limite de 100 comptes dans le cadre du Programme d’inscription des appareils (DEP) ou Apple School Manager. Chaque jeton téléchargé peut être géré séparément pour les profils d’inscription et les appareils. Un profil d’inscription différent peut être affecté automatiquement pour chaque jeton DEP/School Manager téléchargé. Si plusieurs jetons School Manager sont téléchargés, un seul jeton peut être partagé avec Microsoft School Data Sync à la fois.

Après la migration, les API Graph en version bêta et les scripts publiés pour la gestion DEP Apple ou ASM via Graph ne fonctionneront plus. De nouvelles versions bêta des API Graph sont en cours de développement et seront publiées après la migration.

### <a name="select-device-categories-by-using-the-access-work-or-school-settings----1058963-eeready---"></a>Sélectionnez les catégories d’appareils en utilisant les paramètres Accès scolaire ou professionnel <!-- 1058963 eeready -->
Si vous avez activé le [mappage de groupe d’appareils](https://docs.microsoft.com/en-us/intune/device-group-mapping), les utilisateurs de Windows 10 seront invités à sélectionner une catégorie d’appareils après l’inscription via le bouton **Se connecter** situé dans **Paramètres**  >  **Comptes** > **Accès scolaire ou professionnel** ou au cours de l'expérience OOBE (out-of-box experience).

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Ciblage des stratégies de conformité pour les appareils dans des groupes d’appareils <!--1307012 -->

Vous pourrez cibler des stratégies de conformité pour les utilisateurs dans des groupes d’utilisateurs. Vous pourrez cibler des stratégies de conformité pour les appareils dans des groupes d’appareils.

### <a name="including-and-excluding-app-assignment-based-on-groups----1406920---"></a>Inclusion et exclusion d’affectations d’applications en fonction de groupes <!-- 1406920 -->

Lors de l’affectation d’une application et après avoir sélectionné un type d’affectation, vous pourrez sélectionner les groupes à inclure ainsi que les groupes à exclure.

### <a name="remote-erase-command-support----1438084---"></a>Prise en charge de la commande d’effacement à distance <!-- 1438084 -->

Les administrateurs pourront déclencher une commande d’effacement à distance.

> [!IMPORTANT]
> La commande d’effacement ne peut pas être annulée et doit être utilisée avec précaution.

La commande d’effacement supprime toutes les données, y compris le système d’exploitation, d’un appareil. Elle entraîne aussi la suppression de l'appareil de la gestion Intune. Aucun avertissement n’est envoyé à l’utilisateur, et l’effacement se produit dès l’envoi de la commande.

Vous pourrez configurer un code PIN de récupération à 6 chiffres. Ce code PIN peut servir à déverrouiller l’appareil effacé avant de lancer la réinstallation du système d’exploitation. Une fois que l’effacement a démarré, le code PIN apparaît dans une barre d’état sur le panneau de présentation de l’appareil dans Intune. Le code PIN restera affiché tant que l’effacement est en cours. Une fois l’effacement terminé, l’appareil disparaît totalement de la gestion Intune. Veillez à enregistrer le code PIN de récupération afin que toute personne qui restaure l’appareil puisse l’utiliser.

### <a name="windows-information-protection-wip-encrypted-data-in-windows-search-results----1469193---"></a>Données chiffrées Windows Information Protection (WIP) dans les résultats de la recherche Windows <!-- 1469193 -->

Un nouveau paramètre dans la stratégie Protection des informations Windows (WIP) vous permettra de choisir d’inclure les données chiffrées par WIP dans les résultats de la recherche Windows.

### <a name="website-learning-mode----1631908---"></a>Mode d’apprentissage de site web (Website Learning Mode) <!-- 1631908 -->

Intune proposera une extension du mode d’apprentissage de la Protection des informations Windows (WIP). Outre l’affichage des informations sur les applications compatibles avec WIP, vous pourrez consulter un résumé des appareils qui partagent des données de travail avec des sites web. Ces informations vous permettront d’identifier les sites web à ajouter aux stratégies WIP des utilisateurs et des groupes.

### <a name="updates-to-compliance-emails---1637547---"></a>Mises à jour des e-mails de conformité <!--1637547 -->

Lorsqu’un e-mail est envoyé pour signaler un appareil non conforme, d’autres d’informations sur cet appareil non conforme seront incluses. L’article suivant sera mis à jour pour indiquer ce point : [Automatiser des actions en cas de non-conformité](#actions-for-noncompliance).

### <a name="conditional-access-policies-for-intune-is-only-available-from-the-azure-portal-----1737088-1634311---"></a>Les stratégies d’accès conditionnel pour Intune sont disponibles uniquement à partir du portail Azure <!-- 1737088 1634311 -->
Nous simplifierons la configuration et la gestion de l’accès conditionnel. Vous pourrez configurer et gérer vos stratégies uniquement dans le [portail Azure](https://portal.azure.com) en accédant à **Azure Active Directory** > **Accès conditionnel**. Pour des raisons pratiques, vous pourrez également accéder à ce panneau à partir d’Intune dans le portail Azure, depuis **Intune** > **Accès conditionnel**.

###  <a name="alerts-for-expired-tokens-and-tokens-that-will-soon-expire----1639263---"></a>Alertes pour les jetons expirés et les jetons qui arrivent à expiration <!-- 1639263 -->
La page de présentation affichera des alertes pour les jetons expirés et ceux qui arrivent à expiration. Lorsque vous cliquez sur une alerte pour un jeton unique, vous accéderez à la page des détails de ce jeton.  Si vous cliquez sur une alerte comportant plusieurs jetons, vous accéderez à une liste de tous les jetons avec leur état. Les administrateurs doivent renouveler leurs jetons avant la date d’expiration.

### <a name="remote-printing-over-a-secure-network----1709994----"></a>Impression à distance sur un réseau sécurisé <!-- 1709994  -->
Les solutions d’impression mobiles sans fil PrinterOn permettront aux utilisateurs d’imprimer à distance depuis n’importe où et à tout moment via un réseau sécurisé. PrinterOn s’intégrera au Kit SDK APP d’Intune à la fois pour iOS et Android. Vous pourrez cibler les stratégies de protection d’application pour cette application via le panneau des **stratégies de protection d’application** d’Intune, dans la console d’administration. Les utilisateurs finaux pourront télécharger l’application « PrinterOn for Microsoft » via le Google Play Store ou iTunes afin de l’utiliser dans leur écosystème Intune.

### <a name="approve-the-company-portal-app-for-android-for-work---1797090---"></a>Approuver l’application Portail d’entreprise pour Android for Work <!--1797090 -->
Si votre organisation utilise Android for Work, vous devrez approuver manuellement l’application Portail d’entreprise pour Android afin qu’elle continue à recevoir les mises à jour automatiques du magasin Google Play managé.

### <a name="faceid-on-ios-devices----1807377---"></a>FaceID sur les appareils iOS <!-- 1807377 -->
Les stratégies de protection des applications Intune prennent désormais en charge un paramètre qui gère FaceID sur les appareils iOS. Ce paramètre est destiné aux appareils qui prennent en charge la fonctionnalité FaceID (uniquement l’iPhone X pour l’instant). Ce paramètre est indépendant des contrôles TouchID actuellement pris en charge. Les organisations ont la possibilité de choisir FaceID comme code PIN valide en remplacement des commandes TouchID.

### <a name="microsoft-graph-api-for-intune---general-availability-----1833289---"></a>API Graph Microsoft pour Intune - disponibilité générale <!-- 1833289 -->
Les API Intune dans Microsoft Graph fourniront un accès par programme aux données et méthodes pour automatiser les actions d’administration du service Intune.  Avec la **disponibilité générale** de ces API, clients, partenaires et développeurs pourront utiliser les API pour intégrer des solutions internes ou commerciales liées à ou nécessitant la prise en charge d’Intune ou d’autres services Microsoft disponibles via Microsoft Graph.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Stratégies de protection des applications  <!-- 679615 -->
Les stratégies Intune App Protection permettent de créer des stratégies globales, par défaut, afin d’activer rapidement la protection pour tous les utilisateurs dans l’ensemble du locataire.

### <a name="revoking-ios-volume-purchase-program-apps-----820863---"></a>Révocation des applications du Programme d’achat en volume iOS  <!-- 820863 -->
Pour un appareil donné disposant d’une ou de plusieurs applications de Programme d’achat en volume (VPP) iOS, vous pourrez révoquer la licence d’application basée sur l’appareil associé. La révocation d’une licence d’application ne désinstalle pas l’application VPP de l’appareil. Pour désinstaller une application VPP, vous devez remplacer l’action d’attribution par **Désinstaller**. Pour plus d’informations, consultez [Guide pratique pour gérer les applications iOS achetées par le biais d’un programme d’achat en volume avec Microsoft Intune](vpp-apps-ios.md).

### <a name="revoke-licenses-for-an-ios-volume-purchasing-program-token----820870---"></a>Révoquer des licences pour un jeton Programme d’achat en volume iOS <!-- 820870 -->
Vous pourrez révoquer la licence de toutes les applications de Programme d’achat en volume (VPP) iOS pour un jeton VPP donné.

### <a name="new-ios-device-action------1244701---"></a>Nouvelle action sur appareil iOS   <!-- 1244701 -->
Vous pouvez arrêter les appareils supervisés iOS 10.3. Cette action arrête immédiatement l’appareil sans avertir l’utilisateur final. L’action **Arrêter (supervisé uniquement)** se trouve dans les propriétés de l’appareil lorsque vous sélectionnez un appareil dans la charge de travail **Appareil**.


### <a name="intune-now-provides-the-account-move-operation-----1573558-1579830---"></a>Intune propose désormais l’opération Déplacer le compte  <!-- 1573558, 1579830 -->
L’opération **Déplacer le compte** migre un locataire à partir d’une échelle d’unité Azure (ASU) vers une autre. L’opération **Déplacer le compte** peut être utilisée dans les scénarios initiés par le client, lorsque vous faites la demande de cette opération auprès de l’équipe de support d’Intune, et elle peut être utilisée dans un scénario géré par Microsoft lorsque Microsoft doit apporter des réglages au service dans le serveur principal. Au cours de l’opération **Déplacer le compte**, les locataires sont en mode lecture seule. Durant la période où les locataires sont en lecture seule, les opérations de service comme l’inscription, le changement de nom des appareils, la mise à jour de l’état de conformité, échoueront.




<!-- the following are present prior to 1712 -->
### <a name="assign-office-365-mobile-apps-to-ios-and-android-devices-using-built-in-app-type----1332318---"></a>Affecter des applications mobiles Office 365 aux appareils iOS et Android à l’aide du type d’application intégré <!-- 1332318 -->
Le type d’application **Intégré** facilitera la création d’applications Office 365 et leur affectation aux appareils iOS et Android gérés. Ces applications incluent les applications Office 365 telles que Word, Excel, PowerPoint et OneDrive. Vous pouvez affecter des applications spécifiques au type d’application et modifier la configuration des informations des applications.


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


### <a name="configure-an-ios-app-pin----1586774---"></a>Configurer un code PIN d’application iOS <!-- 1586774 -->
Vous pourrez bientôt exiger un code PIN pour des applications iOS ciblées. Vous pouvez configurer l’exigence du code PIN et sa date d’expiration en jours par le biais du portail Azure. Le cas échéant, l’utilisateur devra définir et utiliser un nouveau code PIN avant d’accéder à une application iOS. Seules les applications iOS pour lesquelles la protection d’application est activée avec le SDK d’application Intune prendront en charge cette fonctionnalité.

### <a name="user-experience-update-for-the-company-portal-app-for-ios---1412866--"></a>Mise à jour de l’expérience utilisateur dans l’application Portail d’entreprise pour iOS <!--1412866-->

Nous publierons une mise à jour importante de l’expérience utilisateur dans l’application Portail d’entreprise pour iOS. La mise à jour présentera une toute nouvelle apparence, plus moderne, avec une amélioration de l’accessibilité et de l’utilisation. Toutes les fonctionnalités actuelles de l’application Portail d’entreprise pour iOS seront conservées.

Nous vous offrons une préversion de l’application Portail d’entreprise pour iOS mise à jour via le programme Apple TestFlight pour que vous l’utilisiez et nous fassiez part de vos commentaires. Inscrivez-vous à l’adresse https://aka.ms/intune_ios_cp_testflight pour accéder à TestFlight. 

![images d’annonce de la nouvelle application Portail d’entreprise pour iOS](./media/ios-cp-app-redesign-1801-teaser.png)


<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Les sites web Azure Active Directory peuvent nécessiter l’application Intune Managed Browser et la prise en charge de l’authentification unique pour Managed Browser (Préversion publique) <!-- 710595 -->   
Avec Azure Active Directory (Azure AD), vous pouvez restreindre l’accès aux sites web sur des appareils mobiles à l’application Intune Managed Browser. Dans Managed Browser, les données de site web restent sécurisées et séparées des données personnelles de l’utilisateur final. Par ailleurs, Managed Browser prend en charge les fonctionnalités d’authentification unique pour les sites protégés par Azure AD. Si vous vous connectez à Managed Browser ou que vous utilisez Managed Browser sur un appareil avec une autre application gérée par Intune, Managed Browser peut accéder aux sites d’entreprise protégés par Azure AD sans que l’utilisateur ne doive entrer ses informations d’identification. Cette fonctionnalité s’applique aux sites comme Outlook Web Access (OWA) et SharePoint Online, ainsi qu’à d’autres sites d’entreprise tels que les ressources intranet accessibles par le proxy de l’application Azure.


<!-- the following are present prior to 1710 -->



### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Prise en charge de la stratégie de mise à niveau de l’édition Windows 10   <!-- 903672(archived), 1119689 -->  
Vous pourrez créer une stratégie de mise à niveau de l’édition Windows 10 qui met à niveau les appareils Windows 10 vers Windows 10 Éducation, Windows 10 Éducation N, Windows 10 Professionnel, Windows 10 Professionnel N, Windows 10 Professionnel Éducation et Windows 10 Professionnel Éducation N. Pour plus d’informations sur les mises à niveau de l’édition Windows 10, consultez [Configuration des mises à niveau de l’édition Windows 10 ](edition-upgrade-configure-windows-10.md).




<!-- the following are present prior to 1709 -->


### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Outils de développement Intune App Protection et Citrix MDX<!-- 709185 -->
Vous pouvez gérer des appareils et des applications en combinant Citrix XenMobile MDX avec Microsoft Intune. Cela vous permet de gérer des applications à l’aide d’une stratégie de protection des applications Intune tout en utilisant la technologie mVPN de Citrix.

Vous êtes en mesure de trouver un dépôt de code, contenant l’outil Intune App Wrapping Tool et le kit SDK d’applications Intune pour iOS et Android, qui s’intègre à la technologie mVPN de Citrix MDX.




<!-- the following are present prior to 1711 -->


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>Redirection des utilisateurs macOS vers notre nouvelle application Portail d’entreprise<!--1380728-->   
Lorsqu’un utilisateur final se connecte au site web du portail d’entreprise pour inscrire son appareil macOS, il est invité à télécharger la nouvelle application Portail d’entreprise pour macOS pour effectuer la procédure. Ce comportement se produit pour les appareils macOS avec OS X El Capitan 10.11 ou ultérieur. 



<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Prise en charge d’Intune Managed Browser pour iOS et Android <!-- 1374196 -->
À compter d’octobre 2017, l’application Intune Managed Browser sur l’application Android prendra en charge seulement les appareils exécutant Android 4.4 et ultérieur. L’application Intune Managed Browser sur iOS prendra en charge seulement les appareils exécutant iOS 9.0 et ultérieur. Les versions antérieures d’Android et d’iOS pourront encore utiliser Managed Browser, mais elles ne pourront pas installer les nouvelles versions de l’application et n’auront peut-être pas accès à toutes les fonctionnalités. Nous vous encourageons à mettre à jour le système d’exploitation de ces appareils avec une version prise en charge.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Message d’erreur amélioré quand un utilisateur atteint le nombre maximal d’appareils autorisés à inscrire <!-- 1270370 -->
Au lieu d’un message d’erreur générique, les utilisateurs finaux d’appareils Android reçoivent un message d’erreur convivial offrant une possibilité d’action : « Vous avez inscrit le nombre maximal d’appareils autorisés par votre administrateur informatique. Supprimez un appareil inscrit ou demandez de l’aide à votre administrateur informatique ».




## <a name="notices"></a>Remarques

Il n’existe aucun avis actif pour l’instant.




### <a name="see-also"></a>Voir aussi
Voir [Nouveautés de Microsoft Intune](whats-new.md) pour en savoir plus sur les derniers développements.
