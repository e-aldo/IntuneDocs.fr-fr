---
title: "Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune | Microsoft Docs"
description: "Découvrez ce qui a changé dans l’interface utilisateur des applications qui fonctionnent sur les appareils des utilisateurs finaux avec Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b782e382-8deb-48a7-a437-d7c5a17163f1
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 629a091c1016186700a95bf76b9feed9ef0adb79
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---
# <a name="ui-updates-for-intune-end-user-apps"></a>Mises à jour de l’interface utilisateur pour les applications utilisateur final Intune
Découvrez les mises à jour apportées à l’interface utilisateur des applications présentées aux utilisateurs finaux dans cette version de Microsoft Intune. Cela peut vous aider pour vos communications avec les utilisateurs et pour la mise à jour de la documentation personnalisée que vous avez créée pour votre déploiement. Cela peut aussi vous être utile pour mieux résoudre les problèmes auxquels font face vos utilisateurs s’ils font appel au support technique à l’aide du Portail d’entreprise.

## <a name="coming-soon-in-the-ui"></a>Bientôt disponible dans l’interface utilisateur
Voici les moyens envisagés pour améliorer l’expérience utilisateur en mettant à jour l’interface utilisateur.

> [!Note]
> Notez que les images ci-dessous peuvent être en préversion. Le produit annoncé peut différer des versions présentées.

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

## <a name="april-2017"></a>Avril 2017

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nouvelles icônes pour Managed Browser et le portail d’entreprise <!--918433, 918431-->

Managed Browser reçoit des icônes mises à jour pour les versions iOS et Android de l’application. La nouvelle icône contient le badge Intune mis à jour, pour une meilleure cohérence avec d’autres applications Enterprise Mobility + Security (EM+S).

<html>
<body>
   <table id="wrapper">
      <tr>
         <td>
            <img src="/intune-classic/whats-new/media/cp_manbro_before_042017.png" alt="The previous version of the Managed Browser app icon." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_manbro_after_042017.png" alt="The updated version of the Managed Browser app icon." width=200 height=366 align=center>
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
            <img src="/intune-classic/whats-new/media/cp_android_connecting_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Connecting' underneath it." width=200 height=366 align=center>
          </td>
          <td>
             <img src="/intune-classic/whats-new/media/cp_android_signing_in_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Signing in' underneath it." width=200 height=366 align=center>
           </td>
           <td>
              <img src="/intune-classic/whats-new/media/cp_android_checking_security_reqs_042017.png" alt="The Company Portal app for Android sign in screen that shows a partially filled loading bar with the phrase 'Checking for security requirements' underneath it." width=200 height=366 align=center>
           </td>
      </tr>
   </table>
</body>
</html>

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Amélioration de l’état d’installation de l’application pour l’application Portail d’entreprise Windows 10 <!--676495-->
L’application Portail d’entreprise Windows 10 fournit désormais une barre de progression de l’installation dans la page des détails de l’application. Elle est prise en charge pour les applications modernes sur les appareils exécutant au minimum Mise à jour anniversaire Windows 10.

__Avant__
  ![Image de la version précédente de l’écran de chargement, où l’état indique simplement « installation ».](./media/cp_win10_install_status_before_1704.png)

__Après__
  ![Image de la version mise à jour de l’écran de chargement, qui affiche à présent une barre de progression de l’installation.](./media/cp_win10_install_status_after_1704.png)

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
            <img src="/intune-classic/whats-new/media/cp_android_contactit_after.png" alt="The Company Portal app for Android displaying an updated version of the Contact IT tab. The tab shows available contact information for IT, including phone number, email address, IT website, and IT contact information." width=200 height=366 align=center>
          </td>
      </tr>
   </table>
</body>
</html>

## <a name="january-2017"></a>Janvier 2017

### <a name="modernizing-the-company-portal-website---753980-announced-1701--"></a>Modernisation du site web du portail d’entreprise <!--753980, announced 1701-->
À compter de février, le site web du portail d’entreprise prend en charge les applications destinées aux utilisateurs qui n’ont pas d’appareils gérés. Le site web s’aligne sur les autres produits et services Microsoft et utilise un nouveau modèle de couleurs contrastées, des illustrations dynamiques et un « menu hamburger », ![Petite image du menu hamburger désormais ajouté en haut à gauche du site web du portail d’entreprise](./media/CP_hamburger_menu.png) qui contient les coordonnées du support technique et des informations sur les appareils gérés existants. Nous avons réorganisé la page d’accueil pour mettre en évidence les applications disponibles en les affichant dans des carrousels sous Applications proposées et Applications récemment mises à jour.

![L’image de gauche représente la version actuelle du site web du portail d’entreprise, avec les versions précédentes des vues Applications, Mes appareils, Applications proposées et Catégories. L’image de droite représente la version mise à jour du site web du portail d’entreprise, avec un carrousel d’applications repensé, la liste des applications récemment publiées et la vue Catégories mise à jour.](./media/CP_Website_BeforeAfter_Feb2016.png)


### <a name="see-also"></a>Voir aussi
* [Blog Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Feuille de route de la plateforme cloud](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Nouveautés de la préversion Azure](https://docs.microsoft.com/intune/whats-new)
* [Archive des nouveautés](whats-new-archive.md)

