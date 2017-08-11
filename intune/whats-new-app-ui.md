---
title: "Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune"
description: "Découvrez ce qui a changé dans l’interface utilisateur des applications qui fonctionnent sur les appareils des utilisateurs finaux avec Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 948a7d2e4e0ad80088d864708db5733f08db77c5
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="ui-updates-for-intune-end-user-apps"></a>Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune
Découvrez les mises à jour apportées à l’interface utilisateur des applications présentées aux utilisateurs finaux dans cette version de Microsoft Intune. Cela peut vous aider pour vos communications avec les utilisateurs et pour la mise à jour de la documentation personnalisée que vous avez créée pour votre déploiement. Cela peut aussi vous être utile pour mieux résoudre les problèmes auxquels font face vos utilisateurs s’ils font appel au support technique à l’aide du Portail d’entreprise.

## <a name="week-of-july-31-2017"></a>Semaine du 31 juillet 2017

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Amélioration de l’expérience de connexion sur l’ensemble des applications du portail d’entreprise pour toutes les plates-formes<!--User Story 1132123-->

Dans les mois à venir, nous introduirons des changements visant à améliorer l’expérience de connexion aux applications Portail d’entreprise Intune pour Android, iOS et Windows. La nouvelle expérience utilisateur s’affiche automatiquement sur toutes les plates-formes utilisées pour l’application du portail d’entreprise lorsqu’Azure AD apporte cette modification. En outre, les utilisateurs peuvent désormais se connecter au portail d’entreprise à partir d’un autre appareil grâce à un code à usage unique automatiquement généré. Cette fonction se révèle particulièrement utile lorsque les utilisateurs doivent se connecter sans informations d’identification.  

Vous trouverez ci-dessous des informations concernant l’expérience de connexion précédente, la nouvelle expérience de connexion avec informations d’identification, ainsi que la nouvelle expérience de connexion depuis un autre appareil.

__Expérience de connexion précédente__

![Page de connexion du Portail d’entreprise, contenant une icône de personne devant une représentation graphique d’un site web. Le bouton de connexion se trouve en dessous. Un lien situé au bas de la page permet d’accéder aux informations Confidentialité et cookies de Microsoft.](./media/cp_ios_aad_signin_before_1704_001.png)

![Après avoir appuyé sur le bouton de connexion, l’utilisateur entre ses informations d’identification sur cette page (à savoir l’adresse e-mail et le mot de passe de l’utilisateur), qui indique également différents moyens de résoudre les problèmes de mot de passe.](./media/cp_ios_aad_signin_before_1704_002.png)

![Une fois le mot de passe saisi, l’application Portail d’entreprise se connecte et indique ce processus par une barre de chargement.](./media/cp_ios_aad_signin_before_1704_003.png)

__Nouvelle expérience de connexion__

![Page de connexion du Portail d’entreprise, contenant une icône de personne devant une représentation graphique d’un site web. Le bouton de connexion se trouve en dessous. Un lien situé au bas de la page permet d’accéder aux informations Confidentialité et cookies de Microsoft.](./media/cp_ios_aad_signin_after_1704_001.png)

![L’utilisateur est invité à renseigner simplement son adresse e-mail, et non plus son adresse e-mail et son mot de passe sur le même écran.](./media/cp_ios_aad_signin_after_1704_002.png)

![Une fois l’adresse e-mail validée, l’utilisateur est invité à saisir son mot de passe.](./media/cp_ios_aad_signin_after_1704_003.png)

![Une fois le processus d’authentification terminé, l’application Portail d’entreprise procède à la connexion et affiche une barre de chargement pour indiquer l’avancement du processus.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

__Nouvelle expérience de connexion lors d’une connexion à partir d’un autre appareil__

![Page de connexion du Portail d’entreprise, contenant une icône de personne devant une représentation graphique d’un site web. Le bouton de connexion se trouve en dessous. Un lien situé au bas de la page permet d’accéder aux informations Confidentialité et cookies de Microsoft.](./media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

Cliquez sur le lien __Se connecter à partir d’un autre appareil__.

![Suivez les instructions fournies pour accéder à la page aka.ms/devicelogin avec un code d’accès unique à partir de votre ordinateur, puis utilisez le code pour vous connecter.](./media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

Ouvrez un navigateur et accédez à [http://aka.ms/devicelogin](https://aka.ms/devicelogin).

![Une image du navigateur de l’utilisateur sur son ordinateur de travail plutôt sur son application Portail d’entreprise. La page « Connexion à l’appareil » invite l’utilisateur à saisir le code qu’il a reçu dans l’application Portail d’entreprise.](./media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

Entrez le code que vous avez reçu dans l’application Portail d’entreprise. Si vous sélectionnez __Continuer__, vous serez en mesure de vous authentifier à l’aide de n’importe quelle méthode prise en charge par votre entreprise, par exemple une carte à puce.

![L’utilisateur a saisi son code unique dans le champ, et le site « Connexion à l’appareil » lui a demandé de confirmer que le portail d’entreprise Intune était l’application appropriée pour recevoir l’autorisation de se connecter.](./media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

![Une page de confirmation indiquant que l’utilisateur est maintenant connecté à l’application Portail d’entreprise sur son appareil et qu’il peut fermer cette page.](./media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

L’application Portail d’entreprise commence la procédure de connexion.

![Une fois le processus d’authentification terminé, l’application Portail d’entreprise procède à la connexion et affiche une barre de chargement pour indiquer l’avancement du processus.](./media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="week-of-june-12-2017"></a>Semaine du 12 juin 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>L’application Portail d’entreprise pour Android présente désormais une nouvelle expérience d’utilisateur final pour les stratégies de protection des applications <!--1305217-->
En fonction des commentaires des clients, nous avons modifié l’application Portail d’entreprise pour Android afin d’afficher un bouton **Accéder au contenu de l’entreprise**. Le but est d’empêcher les utilisateurs finaux de passer inutilement par le processus d’inscription quand ils ont uniquement besoin d’accéder aux applications qui prennent en charge les stratégies de protection des applications, une fonctionnalité de gestion des applications mobiles Intune.

L’utilisateur appuie sur le bouton **Accéder au contenu de l’entreprise** au lieu de commencer à inscrire l’appareil.

![Image de l’application Portail d’entreprise Android, qui affiche en grand « Accéder au contenu de l’entreprise » au milieu plutôt que de proposer immédiatement des options d’inscription comme c’est le cas habituellement](./media/and_access_company_content_after_1706.png)

L’utilisateur est ensuite dirigé vers le site web Portail d’entreprise pour autoriser l’utilisation de l’application sur son appareil, où le site web Portail d’entreprise vérifie ses informations d’identification.

![Image du site web Portail d’entreprise confirmant la connexion.](./media/and_iwp_sign_in_auth_page_after_1706.png)

L’appareil peut toujours être inscrit pour la gestion complète en appuyant sur le menu **Action**.

![Image de l’application Portail d’entreprise pour Android montrant le menu du coin supérieur droit de l’écran avec une option pour inscrire l’appareil.](./media/and_sign_in_menu_after_app_protection_policy_enrolled_after_1706.png)

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Améliorations apportées à la synchronisation des applications avec Windows 10 Creators Update<!--676505-->

L’application Portail d’entreprise pour Windows 10 démarre maintenant automatiquement une synchronisation pour les demandes d’installation d’application sur les appareils exécutant Windows 10 Creators Update (version 1703). Cela permet de réduire le problème de blocage des installations d’applications à l’état « Synchronisation en attente ». En outre, les utilisateurs peuvent lancer manuellement une synchronisation à partir de l’application.

![Image de l’application Portail d’entreprise Windows 10, où le téléchargement de Microsoft Word à partir de l’App Store du portail d’entreprise est à l’état d’attente.](./media/w10_download_pending_after_1706.png)

![Image de l’application Portail d’entreprise Windows 10, avec le nouvel état de synchronisation automatique affichant un message d’état signalant que l’appareil est en cours de synchronisation et tente de télécharger l’application.](./media/w10_download_pending_syncing_after_1706.png)

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nouvelle expérience interactive pour le portail d’entreprise Windows 10 <!---1058938--->
L’application Portail d’entreprise pour Windows 10 inclura une expérience de procédure pas à pas Intune interactive pour les appareils qui n’ont pas été identifiés ou inscrits. La nouvelle expérience fournit des instructions détaillées qui guident les utilisateurs lors de l’inscription à Azure Active Directory (requis pour les fonctionnalités d’accès conditionnel) et de l’inscription MDM (obligatoire pour les fonctionnalités de gestion des appareils). L’expérience guidée sera accessible à partir de la page d’accueil de portail d’entreprise. Les utilisateurs peuvent continuer à utiliser l’application s’ils ne terminent pas l’inscription, mais les fonctionnalités seront limitées.

Cette mise à jour est visible uniquement sur les appareils exécutant la Mise à jour anniversaire Windows 10 (build 1607) ou version ultérieure.

![Image de la page de lancement de l’application Portail d’entreprise Windows 10, avec un message d’état au centre dans la liste « Appareils » qui signale à l’utilisateur que son appareil n’a pas encore été configuré pour une utilisation professionnelle, et qu’il doit sélectionner le message pour commencer l’installation.](./media/win10_guided_enroll_select_setup_after_1706.png)

![Image de la page de configuration de l’application Portail d’entreprise Windows 10, qui avertit l’utilisateur qu’il doit ajouter un compte d’entreprise à cet appareil avant de pouvoir l’inscrire pour la gestion.](./media/win10_guided_enroll_we_help_setup_after_1706.png)

![Image de la page Ajouter un compte d’entreprise à cet appareil de l’application Portail d’entreprise Windows 10, qui signale à l’utilisateur qu’il devra accéder à l’application Paramètres et sélectionner « Se connecter » pour effectuer l’inscription. Après cela, l’écran lui indique qu’il doit retourner à l’application Portail d’entreprise pour terminer l’inscription.](./media/win10_guided_enroll_leaving_for_iwp_after_1706.png)

![Image de l’écran Inscrire à la gestion de l’application Portail d’entreprise Windows 10, qui affiche un message d’état de fin indiquant que l’appareil de l’utilisateur est maintenant inscrit et qu’il doit appuyer sur le bouton « Suivant » pour continuer.](./media/win10_guided_enroll_youre_now_enrolled_after_1706.png)

![Image de l’écran d’achèvement de l’application Portail d’entreprise Windows 10, informant l’utilisateur qu’il a terminé, que l’appareil est inscrit et qu’un compte d’entreprise a été correctement ajouté.](./media/win10_guided_enroll_youre_all_set_after_1706.png)

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nouvelle action de menu pour supprimer facilement le portail d’entreprise <!--1164569-->
Suite aux commentaires des utilisateurs, l’application Portail d’entreprise pour Android offre désormais une nouvelle action de menu pour lancer la suppression du portail d’entreprise à partir de votre appareil. Cette action supprime l’appareil de la gestion Intune afin que l’application puisse être supprimée à partir de l’appareil par l’utilisateur.

![Une image de l’application Portail d’entreprise Android, avec le menu Action ouvert en haut à droite. La nouvelle option « Supprimer le portail d’entreprise » est disponible en tant que troisième option, sous « Mon profil » et « Paramètres », et au-dessus de « Conditions générales », « Aide et commentaires » et « À propos ».](./media/android_remove_cp_menu_action_after_1705.png)

![Une image de la boîte de dialogue de confirmation, qui est disponible après avoir sélectionné la nouvelle option « Supprimer le portail d’entreprise » dans le menu Action. La boîte de dialogue informe l’utilisateur comme suit : « en supprimant le portail d’entreprise, votre appareil ne sera plus géré par votre administrateur informatique et pourrait perdre l’accès à la messagerie, aux applications et aux données de l’entreprise. » L’utilisateur doit ensuite confirmer qu’il souhaite supprimer l’application Portail d’entreprise en sélectionnant « Oui ».](./media/android_remove_cp_menu_confirmation_after_1705.png)

## <a name="week-of-june-5-2017"></a>Semaine du 5 juin 2017

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Améliorations des vignettes d’application dans l’application Portail d’entreprise pour iOS
Nous avons mis à jour l’apparence des vignettes d’application sur la page d’accueil afin de refléter la couleur de marque que vous définissez pour le portail d’entreprise.

**Avant**

![Une image de l’application Portail d’entreprise pour iOS à compter de la mise à jour, avec des images de remplissage prédéfini pour « Toutes les applications », « Applications proposées » et « Catégories ».](./media/cp_ios_homepage_before_1705.png)

**Après**

![Une image de l’application Portail d’entreprise pour iOS à compter la mise à jour, qui reflète la nouvelle fonctionnalité de sélection des couleurs qui sont pertinentes pour votre organisation.](./media/cp_ios_homepage_after_1705.png)

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Un sélecteur de compte est désormais disponible dans l’application Portail d’entreprise pour iOS
Si des utilisateurs ont utilisé leur compte professionnel ou scolaire pour se connecter dans d’autres applications Microsoft sur leur appareil iOS, ils peuvent voir notre nouveau sélecteur de compte quand ils se connectent pour la première fois au portail d’entreprise.

![Une image du sélecteur de compte, qui montre un utilisateur de test « Robin Swanson » qui choisit entre une de ses deux adresses e-mail. Un bouton présent sous les deux adresses permet à l’utilisateur de se connecter avec un autre compte.](./media/cp_ios_multi-account-selector-after-1705.png)

## <a name="april-2017"></a>Avril 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nouvelles icônes pour Managed Browser et le portail d’entreprise <!--918433, 918431-->

Managed Browser reçoit des icônes mises à jour pour les versions iOS et Android de l’application. La nouvelle icône contient le badge Intune mis à jour, pour une meilleure cohérence avec d’autres applications Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

Le portail d’entreprise reçoit également des icônes mises à jour pour les versions Android, iOS et Windows de l’application, afin d’améliorer la cohérence avec d’autres applications dans EM + S. Ces icônes seront publiées progressivement sur toutes les plateformes du mois d’avril jusqu’à fin mai.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Indicateur de progression de connexion dans le portail d’entreprise Android <!--953374-->

Une mise à jour de l’application Portail d’entreprise Android affiche un indicateur de progression de connexion quand l’utilisateur lance l’application ou effectue une reprise. L’indicateur affiche successivement les nouveaux états, en commençant par « Connexion... », puis « Connexion en cours », puis « Vérification des exigences de sécurité... », avant d’autoriser l’utilisateur à accéder à l’application.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Amélioration de l’état d’installation de l’application pour l’application Portail d’entreprise Windows 10 <!--676495-->
L’application Portail d’entreprise Windows 10 fournit désormais une barre de progression de l’installation dans la page des détails de l’application. Elle est prise en charge pour les applications modernes sur les appareils exécutant au minimum Mise à jour anniversaire Windows 10.

__Avant__ ![Image de la version précédente de l’écran de chargement, où l’état indique simplement « installation ».](./media/cp_win10_install_status_before_1704.png)

__Après__ ![Image de la version mise à jour de l’écran de chargement, qui affiche à présent une barre de progression de l’installation.](./media/cp_win10_install_status_after_1704.png)

## <a name="february-2017"></a>Février 2017

### <a name="new-user-experience-for-the-company-portal-app-for-android---621622-announced-1702--"></a>Nouvelle expérience utilisateur dans l’application Portail d’entreprise pour Android <!--621622, announced 1702-->
À compter de mars, l’application Portail d’entreprise pour Android suit les [directives de conception matérielle](https://material.io/guidelines/material-design/introduction.html) pour créer une apparence plus moderne. Cette expérience utilisateur améliorée inclut les éléments suivants :

* __Couleurs__ : La couleur de l’en-tête des onglets peut être assortie à votre palette de couleurs personnalisée.

![À gauche, une image de l’application Portail d’entreprise pour Android avant la mise à jour. À droite, une image de l’application Portail d’entreprise pour Android après la mise à jour. Les deux images montrent l’onglet Appareils comme onglet sélectionné parmi les trois onglets disponibles Applications, Appareils et Contacter le service informatique.](./media/CP_Android_DevicesTab_BeforeAfter.png)

* __Interface__ : Les boutons __Applications proposées__ et __Toutes les applications__ ont été mis à jour sous l’onglet __Applications__. Le bouton __Rechercher__ est désormais un bouton d’action flottant.

![À gauche, une image de l’application Portail d’entreprise pour Android avant la mise à jour. À droite, une image de l’application Portail d’entreprise pour Android après la mise à jour. Les deux images montrent l’onglet Applications sélectionné parmi les trois onglets disponibles Applications, Appareils et Contacter le service informatique.](./media/CP_Android_AppsTab_BeforeAfter.png)

* __Navigation__ : Le bouton Toutes les applications propose une vue comprenant les onglets __Applications proposées__, __Toutes les applications__ et __Catégories__ pour faciliter la navigation. L’onglet __Contacter le service informatique__ a été simplifié pour une meilleure lisibilité.

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Janvier 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernisation du site web du portail d’entreprise <!--753980, announced 1701-->
À compter de février, le site web du portail d’entreprise prend en charge les applications destinées aux utilisateurs qui n’ont pas d’appareils gérés. Le site web s’aligne sur les autres produits et services Microsoft et utilise un nouveau modèle de couleurs contrastées, des illustrations dynamiques et un « menu hamburger », ![Petite image du menu hamburger désormais ajouté en haut à gauche du site web du portail d’entreprise](./media/CP_hamburger_menu.png) qui contient les coordonnées du support technique et des informations sur les appareils gérés existants. Nous avons réorganisé la page d’accueil pour mettre en évidence les applications disponibles en les affichant dans des carrousels sous Applications proposées et Applications récemment mises à jour.

![L’image de gauche représente la version actuelle du site web du portail d’entreprise, avec les versions précédentes des vues Applications, Mes appareils, Applications proposées et Catégories. L’image de droite représente la version mise à jour du site web du portail d’entreprise, avec un carrousel d’applications repensé, la liste des applications récemment publiées et la vue Catégories mise à jour.](./media/CP_Website_BeforeAfter_Feb2016.png)

## <a name="coming-soon-in-the-ui"></a>Bientôt disponible dans l’interface utilisateur
Voici les moyens envisagés pour améliorer l’expérience utilisateur en mettant à jour l’interface utilisateur.

> [!Note]
> Notez que les images ci-dessous peuvent être en préversion. Le produit annoncé peut différer des versions présentées.

### <a name="ui-updates-to-the-company-portal-website---1313244-part-2--"></a>Mises à jour apportées à l’interface utilisateur sur le site web Portail d’entreprise <!--1313244 part 2-->

__Mises à jour des applications proposées__  Nous avons ajouté une page dédiée sur le site où les utilisateurs peuvent rechercher les applications que vous avez choisi de proposer, et nous avons apporté quelques ajustements à l’interface utilisateur de la section correspondante sur la page d’accueil.

![Les vignettes de couleur qui signalent les applications. Il s’agit de grands carrés de couleur en dessous de chaque application, où la couleur est extraite de la teinte principale du logo de l’application. La section « Applications proposées » s’affiche dans la partie supérieure de l’application Portail d’entreprise.](./media/cp_win10_colorful_tiles_after_1708.png)

### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés d’Intune](https://docs.microsoft.com/intune/whats-new)
