---
title: "Inscrire un appareil macOS dans Intune avec l’application Portail d’entreprise | Microsoft Docs"
description: "Explique comment inscrire un appareil macOS dans Intune avec l’application Portail d’entreprise"
keywords: "Mac OS X, macOS, OS X"
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope:
- User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 4f01a5aa9567ea914da2c36756e8c3f12f55c58d
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a>Inscrire votre appareil macOS dans Intune avec l’application Portail d’entreprise

L’accès aux applications, aux données et aux ressources de votre organisation vous permet de travailler plus facilement. Votre organisation utilise Intune pour [gérer l’accès à ces ressources](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md). De ce fait, vous devez télécharger l’application Portail d’entreprise pour macOS. Les instructions suivantes fonctionnent pour les appareils macOS sur OS X El Capitan 10.11+.

> [!NOTE]
> Vous trouverez des instructions pour l’inscription d’appareils macOS sur des versions plus antérieures de macOS [ici](enroll-your-device-in-intune-macos-legacy.md).

1. Sur votre __station d’accueil__, recherchez __Safari__ et ouvrez une nouvelle fenêtre, puis ouvrez le [site web du portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).

2. Connectez-vous au site web du portail d’entreprise avec votre compte professionnel ou scolaire.

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. Une fois connecté, cliquez dans le **Menu** en haut à gauche de la page et sélectionnez **Mes appareils**.

   ![Capture d’écran de la page d’accueil du portail web avec le portail web indiquant qu’aucune application ne peut encore être installée, avec un bouton Mes appareils en dessous.](./media/macOS_enroll_001_landing_page.png)

4. Dans la page __Mes appareils__, une liste d’appareils inscrits ou simplement une bannière s’affiche. Cela dépend si un appareil, macOS ou autre, est déjà inscrit ou non. Pour inscrire un appareil qui n’est pas listé, sélectionnez la bannière qui indique __Si votre appareil est répertorié, appuyez ici pour l’identifier. Vous pouvez aussi appuyer ici pour inscrire votre appareil s’il n’est pas listé__. Si vous n’avez aucun appareil inscrit, la bannière indique **Vous n’avez aucun appareil inscrit. Inscrivez celui-ci en appuyant ici.**

    ![Capture d’écran de la page Mes appareils, avec quelques appareils non identifiés au-dessus de la bannière invitant à inscrire les appareils non listés ou à identifier ceux qui ne le sont pas.](./media/macOS_enroll_002_tap_here_banner.png)

5. Téléchargez l’application Portail d’entreprise sur votre appareil macOS pour poursuivre l’inscription.

    ![Notification qui invite un utilisateur à télécharger l’application Portail d’entreprise macOS. Cette notification contient le texte mentionné à l’étape, au-dessus d’un bouton intitulé « Télécharger » en bas à droite.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. Votre Mac vérifie que le téléchargement de **CompanyPortal.pkg** peut être ouvert sans risque. Ouvrez le programme d’installation et effectuez le processus d’installation.

7. Quand le programme d’installation a terminé, ouvrez votre dossier **Applications** ou **Launchpad**, puis ouvrez **Portail d’entreprise**.

8. Votre Mac affiche alors un message indiquant que **« Portail d’entreprise » est une application téléchargée à partir d’Internet. Voulez-vous vraiment l’ouvrir ?** Cliquez sur **Ouvrir**.

  > [!NOTE]
  > Intune doit avoir accès à votre ordinateur pour vérifier que votre appareil est suffisamment sécurisé pour accéder aux ressources de votre organisation. Si votre ordinateur refuse d’ouvrir l’application Portail d’entreprise, essayez de [désactiver Gatekeeper](https://support.apple.com/HT202491), puis d’ouvrir l’application.

9. Le premier écran qui s’affiche dans l’application Portail d’entreprise vous invite à vous **Connecter** avec le même compte professionnel ou scolaire que celui que vous avez utilisé pour vous connecter au site web Portail d’entreprise.

10. Le portail d’entreprise vérifie vos informations de compte, puis vous montre vos états **Inscription de l’appareil** et **Conformité de l’appareil**. Des triangles jaunes vous informent que vous devez effectuer des actions pour vérifier que votre Mac peut être utilisé en toute sécurité au travail. Cliquez sur **Commencer** pour commencer l’[inscription de votre appareil pour la gestion](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).

11. Votre Mac commence l’inscription pour la gestion. Vous pouvez être invité à fournir les informations de connexion de votre ordinateur pendant cette opération. L’inscription peut prendre quelques minutes. Pendant ce temps, vous pouvez effectuer d’autres tâches sur votre ordinateur. Un message s’affiche une fois la configuration de l’application Portail d’entreprise terminée pour vous informer que vous avez terminé.

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Vous trouverez ses coordonnées sur le [site web du portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).
