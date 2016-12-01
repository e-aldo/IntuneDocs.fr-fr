---
title: Inscrire un appareil macOS dans Intune | Microsoft Intune
description: Cette rubrique explique comment inscrire un appareil macOS dans Intune
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 162d176c5f272f5f19ba18cdd07fe815ac1bcce7
ms.openlocfilehash: fc0efceb8a0c3e1323f7d94625bc5f618d35bfd6


---

# <a name="enroll-your-macos-device-in-intune"></a>Inscrire votre appareil macOS dans Intune

L’accès aux applications, aux données et aux ressources de votre organisation est essentiel pour que vous puissiez travailler. Si vous utilisez un appareil macOS au travail, cela signifie que vous devez installer un __profil de gestion__. Il s’agit simplement d’un fichier configuré par votre administrateur informatique qui charge les paramètres et les informations d’accès sur votre Mac. Vous voulez en savoir plus ? Découvrez [ce qui se passe lorsque vous installez l’application Portail d’entreprise et que vous inscrivez votre appareil dans Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).

  > [!NOTE]
  > Si vous essayez d’inscrire un appareil iOS, tel qu’un iPhone ou un iPad, [suivez plutôt ces instructions](enroll-your-device-in-intune-ios.md).

1. Sur votre __station d’accueil__, recherchez __Safari__ et ouvrez une nouvelle fenêtre, puis ouvrez le [site web du portail d’entreprise](http://portal.manage.microsoft.com).
2. Connectez-vous au site web du portail d’entreprise avec votre compte professionnel ou scolaire.

  [!INCLUDE[wit_nextref](../includes/end-user-password-guidance.md)]

3. Lorsque vous vous connectez, vous verrez toutes les __applications__ disponibles, __Mes appareils__ et toutes les __coordonnées__ de votre équipe informatique. En haut de la page, vous verrez une remarque indiquant que **cet appareil n’est pas inscrit, ou que le portail d’entreprise ne peut pas l’identifier. <u>Appuyez ici</u> pour sélectionner un autre appareil.** Cliquez sur __Appuyer ici__.

 ![Page d’accueil macOS du portail d’entreprise](./media/macOS_enroll_001_landing_page.png)

4. Une fenêtre contextuelle s’affiche avec une brève description de la raison pour laquelle vous vous apprêtez à __identifier ou inscrire cet appareil__. Passez en revue ces informations, puis cliquez sur __Inscription__ pour continuer.

 ![Identifier ou inscrire cet appareil macOS](./media/macOS_enroll_002_IDenroll_popup.png)

5. Une deuxième fenêtre contextuelle s’affiche avec une brève description de ce qui se produit lorsque vous __inscrivez cet appareil__. Passez en revue ces informations, puis cliquez sur __Installation__ pour continuer.

 ![Inscrire cet appareil macOS](./media/macOS_enroll_003_enroll_popup.png)

  > [!NOTE]
  > Intune doit avoir accès à votre ordinateur pour vérifier que votre appareil est suffisamment sécurisé pour accéder aux ressources de votre organisation. Découvrez [ce qui se produit lorsque vous inscrivez votre appareil dans Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios).

6. __Préférences système__ s’ouvre et vous demande si vous souhaitez __Installer le « Profil de gestion » ?__ Cliquez sur __Installation__ pour continuer ou obtenez plus de détails en cliquant sur __Afficher le profil__.

 ![Installer le profil de gestion](./media/macOS_enroll_004_sysprefs_mgmt_profile.png)

7. Une fenêtre contextuelle macOS s’ouvre. Confirmez que vous souhaitez apporter des modifications en fournissant le __nom d’utilisateur__ et le __mot de passe__ de votre ordinateur, puis en cliquant sur __OK__. Cela installera le profil de gestion sur votre Mac.

 ![Fenêtre contextuelle d’installation de profil macOS](./media/macOS_enroll_005_sysprefs_admin_login.png)

8. Des messages supplémentaires contenant plus de détails sur le profil ou vous demandant de confirmer __l’installation__ peuvent s’afficher sur votre Mac. Cliquez sur __Continuer__, puis sur __Installation__ via ces derniers pour continuer. Une fois l’installation terminée, vous pourrez voir votre__profil de gestion__ récemment installé dans la liste des __Profils d’appareils__.

 ![Profil macOS installé](./media/macOS_enroll_006_sysprefs_installed_profile.png)

Encore besoin d’aide ? Contactez votre administrateur informatique. Vous trouverez ses coordonnées sur le [site web du portail d’entreprise](http://portal.manage.microsoft.com).



<!--HONumber=Nov16_HO4-->


