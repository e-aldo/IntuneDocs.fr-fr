---
title: Guide pratique pour réinitialiser votre code secret à partir du site web du Portail d’entreprise | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 45b087b9617b783517f8296f1726891392764d5f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31019328"
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Guide pratique pour réinitialiser le code secret de votre appareil à partir du site web du portail d’entreprise

Si vous perdez le code confidentiel ou le mot de passe d’un appareil que vous avez inscrit dans Intune, vous pouvez utiliser le [site web du portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog) pour le réinitialiser. Vous pouvez utiliser le site web du portail d’entreprise pour gérer les ordinateurs et appareils que vous avez inscrits dans Intune et effectuer pour la majeure partie les mêmes tâches qu’avec l’application de votre portail d’entreprise.

> [!NOTE]
> Le bouton Réinitialiser le code secret ne sera peut-être pas visible sur le site web du portail d’entreprise si vous utilisez un appareil d’entreprise inscrit. Si ce n’est pas le cas, vous devez contacter le support de votre entreprise pour réinitialiser le code secret.

Pour réinitialiser votre code secret

1. Sur le [site web Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog), cliquez sur le bouton de __menu__ ![Petite image du bouton de menu, représentant trois barres horizontales empilées les unes sur les autres.](/intune/media/CP_hamburger_menu.png), puis sélectionnez __Mes appareils__.

2. Dans la page __Mes appareils__, sélectionnez le nom de l’appareil dont vous voulez réinitialiser le code secret.

   ![Capture d’écran de la page Mes appareils, avec quelques appareils non identifiés au-dessus de la bannière invitant à inscrire les appareils non listés ou à identifier ceux qui ne le sont pas.](./media/macOS_enroll_002_tap_here_banner.png)

3. L’appareil s’ouvre dans une fenêtre contextuelle. Sélectionnez le bouton **Réinitialiser le code secret**.

   ![Toutes les options disponibles pour un appareil sélectionné sur le site web Portail d’entreprise, notamment Renommer, Supprimer, Réinitialiser l’appareil, Réinitialiser le code secret et Verrouillage à distance. ](./media/iwp-screen-with-all-options.png)

4. Une bannière s’affiche, vous demandant de confirmer que vous voulez réinitialiser votre code secret, après quoi votre appareil vous déconnecte. Vous devez alors attendre 5 minutes avant de vous reconnecter.

   ![Bannière de réinitialisation du code secret avec son avertissement concernant la réinitialisation du code secret et la façon dont l’utilisateur sera déconnecté. Les boutons disponibles pour l’utilisateur sont Se déconnecter et Annuler.](./media/iwp-reset-passcode-popup.png)

5. Sélectionnez **Se déconnecter**. Un dernier message s’affiche, vous informant de la suppression du code secret de l’appareil. Si vous n’avez pas l’appareil avec vous, ne supprimez pas le code secret, car quiconque ayant un accès physique à l’appareil pourra accéder à la plupart des informations (personnelles ou professionnelles) contenues dans ce dernier. 

   ![Deuxième bannière de réinitialisation du code secret avec son avertissement concernant la réinitialisation du code secret et la façon dont ce dernier sera supprimé de l’appareil. Elle indique également la façon recommandée de définir un nouveau code secret en accédant aux paramètres de l’appareil.](./media/iwp-reset-passcode-2nd-popup.png)

   Les différents appareils ont différents types de code secret.

   **Android** : supprime le code secret existant et crée un code secret temporaire avec des lettres et des chiffres. 
  
   > [!NOTE]
   > Vous ne pouvez pas réinitialiser le code secret pour les appareils Android 7.0 et versions ultérieures. Si vous oubliez votre code secret, vous devez réinitialiser ces appareils avec les paramètres d’usine.

   **iOS** : supprime le code secret existant et ne crée pas de code secret temporaire. Si vous utilisez le scanneur d’empreinte digitale Touch ID pour ouvrir votre appareil ou effectuer des achats, vous devez le reconfigurer.

   **Windows 10 Mobile** : supprime le code secret existant et crée un code secret temporaire avec des lettres et des chiffres. Si vous utilisez la reconnaissance faciale Windows Hello pour vous connecter, elle sera toujours prise en charge.
    
   **Windows Phone 8.1** : supprime le code secret existant et crée un code secret temporaire avec des chiffres.

   Pour les appareils Android et Windows, le mot de passe temporaire s’affiche dans le **Détails de l’appareil**. 

6. Déverrouillez votre appareil et définissez un nouveau code secret, ou modifiez le code secret temporaire en accédant à **Paramètres** sur votre appareil.

Pour afficher une notification confirmant que votre code d’accès a été réinitialisé avec succès, cliquez sur l’indicateur de notification en haut à droite du site web du portail d’entreprise.

Encore besoin d’aide ? Contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).
