---
title: "Inscrire un appareil macOS dans Intune | Microsoft Docs"
description: Cette rubrique explique comment inscrire un appareil macOS dans Intune
keywords: "Mac OS X, macOS, OS X"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: e2a507ff6f803cf022536824ca2f12f6d6a64d75
ms.openlocfilehash: 4b532299070bdb8ddf0e9de1e6b598e8dcd8ffb3
ms.lasthandoff: 02/24/2017


---

# <a name="enroll-your-macos-device-in-intune"></a>Inscrire votre appareil macOS dans Intune

L’accès aux applications, aux données et aux ressources de votre organisation est essentiel pour que vous puissiez travailler. Si vous utilisez un appareil macOS au travail, cela signifie que vous devez installer un __profil de gestion__. Il s’agit simplement d’un fichier configuré par votre administrateur informatique qui charge les paramètres et les informations d’accès sur votre Mac. Vous voulez en savoir plus ? Découvrez [ce qui se passe lorsque vous installez l’application Portail d’entreprise et que vous inscrivez votre appareil dans Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

  > [!NOTE]
  > Si vous essayez d’inscrire un appareil iOS, tel qu’un iPhone ou un iPad, [suivez plutôt ces instructions](enroll-your-device-in-intune-ios.md).

1. Sur votre __station d’accueil__, recherchez __Safari__ et ouvrez une nouvelle fenêtre, puis ouvrez le [site web du portail d’entreprise](http://portal.manage.microsoft.com).
2. Connectez-vous au site web du portail d’entreprise avec votre compte professionnel ou scolaire.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Quand vous vous connectez, tous les onglets __Accueil__, __Applications__ et __Catégories__ disponibles s’affichent. Cette page présente toutes les applications pouvant être installées. Si vous n’avez encore aucun appareil inscrit, une remarque indique que **nous ne pouvons vous proposer aucune application**. Pour continuer, sélectionnez __Mes appareils__.

 ![Capture d’écran de la page d’accueil du portail web avec le portail web indiquant qu’aucune application ne peut encore être installée, avec un bouton Mes appareils en dessous.](./media/macOS_enroll_001_landing_page.png)

4. Dans la page __Mes appareils__, une liste d’appareils inscrits ou simplement une bannière s’affiche. Cela dépend si un appareil, macOS ou autre, est déjà inscrit ou non. Pour inscrire un appareil qui n’est pas listé, sélectionnez la bannière qui indique __Si votre appareil est répertorié, appuyez ici pour l’identifier. Vous pouvez aussi appuyer ici pour inscrire votre appareil s’il n’est pas listé__.

  ![Capture d’écran de la page Mes appareils, avec quelques appareils non identifiés au-dessus de la bannière invitant à inscrire les appareils non listés ou à identifier ceux qui ne le sont pas.](./media/macOS_enroll_002_tap_here_banner.png)

5. Une fenêtre contextuelle s’affiche avec une brève description de la raison pour laquelle vous vous apprêtez à __identifier ou inscrire cet appareil__. Passez en revue ces informations, puis cliquez sur __Inscription__ pour continuer.

 ![Identifier ou inscrire cet appareil macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. Une deuxième fenêtre contextuelle s’affiche avec une brève description de ce qui se produit lorsque vous __inscrivez cet appareil__. Passez en revue ces informations, puis cliquez sur __Installation__ pour continuer.

 ![Inscrire cet appareil macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > Intune doit avoir accès à votre ordinateur pour vérifier que votre appareil est suffisamment sécurisé pour accéder aux ressources de votre organisation. Découvrez [ce qui se produit lorsque vous inscrivez votre appareil dans Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).

7. __Préférences système__ s’ouvre et vous demande si vous souhaitez __Installer le « Profil de gestion » ?__ Cliquez sur __Installation__ pour continuer ou obtenez plus de détails en cliquant sur __Afficher le profil__.

 ![Installer le profil de gestion](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. Une fenêtre contextuelle macOS s’ouvre. Confirmez que vous souhaitez apporter des modifications en fournissant le __nom d’utilisateur__ et le __mot de passe__ de votre ordinateur, puis en cliquant sur __OK__. Cela installera le profil de gestion sur votre Mac.

 ![Fenêtre contextuelle d’installation de profil macOS](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. Des messages supplémentaires contenant plus de détails sur le profil ou vous demandant de confirmer __l’installation__ peuvent s’afficher sur votre Mac. Cliquez sur __Continuer__, puis sur __Installation__ via ces derniers pour continuer. Une fois l’installation terminée, vous pourrez voir votre__profil de gestion__ récemment installé dans la liste des __Profils d’appareils__.

 ![Profil macOS installé](./media/macOS_enroll_007_sysprefs_installed_profile.png)

Encore besoin d’aide ? Contactez votre administrateur informatique. Vous trouverez ses coordonnées sur le [site web du portail d’entreprise](http://portal.manage.microsoft.com).

