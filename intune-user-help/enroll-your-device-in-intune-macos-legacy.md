---
title: "Inscrire un appareil macOS hérité sur Intune | Microsoft Docs"
description: Cette rubrique explique comment inscrire un appareil macOS sur Intune
keywords: "Mac OS X, macOS, OS X"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope: User help
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 115f32989cfbb991e097404c5297e7997f28f796
ms.sourcegitcommit: e692be57ec7044dfc224b70941affbfd7efba421
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2017
---
# <a name="enroll-your-legacy-macos-device-in-intune"></a>Inscrire un appareil macOS hérité sur Intune

Les instructions suivantes fonctionnent pour les appareils macOS sur OS X Yosemite 10.10 et versions antérieures. Vous trouverez des instructions pour l’inscription d’appareils macOS sur des versions plus récentes de macOS [ici](enroll-your-device-in-intune-macos-cp.md).

L’accès aux applications, aux données et aux ressources de votre organisation est essentiel pour que vous puissiez travailler. Si vous utilisez un appareil macOS au travail, cela signifie que vous devez installer un __profil de gestion__. Il s’agit simplement d’un fichier configuré par le support technique de votre entreprise, qui charge les paramètres et les informations d’accès sur votre Mac. Vous voulez en savoir plus ? Découvrez [ce qui se passe lorsque vous installez l’application Portail d’entreprise et que vous inscrivez votre appareil dans Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)

1. Sur votre __station d’accueil__, recherchez __Safari__ et ouvrez une nouvelle fenêtre, puis ouvrez le [site web du portail d’entreprise](https://portal.manage.microsoft.com).
2. Connectez-vous au site web du portail d’entreprise avec votre compte professionnel ou scolaire.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Une fois connecté, cliquez dans le **Menu** en haut à gauche de la page et sélectionnez **Mes appareils**.

 ![Capture d’écran de la page d’accueil du portail web avec le portail web indiquant qu’aucune application ne peut encore être installée, avec un bouton Mes appareils en dessous.](./media/macOS_enroll_001_landing_page.png)

4. Dans la page __Mes appareils__, une liste d’appareils inscrits ou simplement une bannière s’affiche. Cela dépend si un appareil, macOS ou autre, est déjà inscrit ou non. Pour inscrire un appareil qui n’est pas listé, sélectionnez la bannière qui indique __Si votre appareil est répertorié, appuyez ici pour l’identifier. Vous pouvez aussi appuyer ici pour inscrire votre appareil s’il n’est pas listé__. Si vous n’avez aucun appareil inscrit, la bannière indique **Vous n’avez aucun appareil inscrit. Inscrivez celui-ci en appuyant ici.**

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

Certains profils peuvent indiquer qu’ils sont **non vérifiés**. Du moment qu’ils appartiennent à votre entreprise, c’est normal.

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Vous trouverez ses coordonnées sur le [site web du portail d’entreprise](https://portal.manage.microsoft.com).
