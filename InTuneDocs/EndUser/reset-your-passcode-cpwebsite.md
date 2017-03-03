---
title: "Guide pratique pour réinitialiser votre code secret à partir du site web du Portail d’entreprise | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- Company Portal
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mamoriss
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: f293901d3865f0b10ed876e83b151cf59a046cba
ms.openlocfilehash: 68725bb63ae2750e89a03c16027f8b4fd9111255
ms.lasthandoff: 02/24/2017


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Guide pratique pour réinitialiser le code secret de votre appareil à partir du site web du portail d’entreprise

Si vous perdez le code confidentiel ou le mot de passe d’un appareil que vous avez inscrit dans Intune, vous pouvez utiliser le [site web du portail d’entreprise](http://portal.manage.microsoft.com) pour le réinitialiser. Vous pouvez utiliser le site web du portail d’entreprise pour gérer les ordinateurs et appareils que vous avez inscrits dans Intune et effectuer pour la majeure partie les mêmes tâches qu’avec l’application de votre portail d’entreprise.

> [!NOTE]
> Il est possible que le bouton **Réinitialiser le code secret** ne soit pas visible sur le site web du portail d’entreprise. Dans ce cas, vous devez contacter votre administrateur informatique pour obtenir de l’aide via le site web du portail d’entreprise.

Pour réinitialiser votre code d’accès

1.    Sur le [site web Portail d’entreprise](http://portal.manage.microsoft.com), cliquez sur le bouton de __menu__ ![Petite image du bouton de menu, représentant trois barres horizontales empilées les unes sur les autres.](/Intune/whats-new/media/CP_hamburger_menu.png), puis sélectionnez __Mes appareils__.

2. Dans la page __Mes appareils__, sélectionnez le nom de l’appareil dont vous voulez réinitialiser le code secret.

  ![Capture d’écran de la page Mes appareils, avec quelques appareils non identifiés au-dessus de la bannière invitant à inscrire les appareils non listés ou à identifier ceux qui ne le sont pas.](./media/macOS_enroll_002_tap_here_banner.png)

3.    L’appareil s’ouvre dans une fenêtre contextuelle. Sélectionnez le bouton **Réinitialiser le code secret**.

    ![Toutes les options disponibles pour un appareil sélectionné sur le site web Portail d’entreprise, notamment Renommer, Supprimer, Réinitialiser l’appareil, Réinitialiser le code secret et Verrouillage à distance. ](./media/iwp-screen-with-all-options.png)

4.  Une bannière s’affiche, vous demandant de confirmer que vous voulez réinitialiser votre code secret, après quoi votre appareil vous déconnecte. Vous devez alors attendre 5 minutes avant de vous reconnecter.

  ![Bannière de réinitialisation du code secret avec son avertissement concernant la réinitialisation du code secret et la façon dont l’utilisateur sera déconnecté. Les boutons disponibles pour l’utilisateur sont Se déconnecter et Annuler.](./media/iwp-reset-passcode-popup.png)

4.  Sélectionnez **Se déconnecter**. Un dernier message s’affiche, vous informant de la suppression du code secret de l’appareil. Si vous n’avez pas l’appareil avec vous, ne supprimez pas le code secret, car quiconque ayant un accès physique à l’appareil pourra accéder à la plupart des informations (personnelles ou professionnelles) contenues dans ce dernier.

  ![Deuxième bannière de réinitialisation du code secret avec son avertissement concernant la réinitialisation du code secret et la façon dont ce dernier sera supprimé de l’appareil. Elle indique également la façon recommandée de définir un nouveau code secret en accédant aux paramètres de l’appareil.](./media/iwp-reset-passcode-2nd-popup.png)


Les types de codes secrets varient en fonction des appareils. Pour déterminer comment la réinitialisation de votre code secret peut affecter votre appareil spécifique, consultez le tableau ci-dessous. 

    |Type d'appareil|Ce qui se produit lors de la réinitialisation|
    |------------|-----------|
    |Android|Supprime le code secret existant et crée un code secret temporaire avec des lettres et des chiffres|
    |iOS|Supprime le code secret existant et ne crée pas de code secret temporaire. Si vous utilisez le scanneur d’empreinte digitale Touch ID pour ouvrir votre appareil ou effectuer des achats, vous devrez le reconfigurer.|
    |Windows 10 Mobile|Supprime le code secret existant et crée un code secret temporaire avec des lettres et des chiffres. Si vous utilisez la reconnaissance faciale Windows Hello pour vous connecter, elle sera toujours prise en charge.|
    |Windows Phone 8.1|Supprime le code secret existant et crée un code secret temporaire avec des chiffres.|

    5.  Déverrouillez votre appareil et définissez un nouveau code secret, ou modifiez le code secret temporaire en accédant à **Paramètres** sur votre appareil.

    Pour afficher une notification confirmant que votre code d’accès a été réinitialisé avec succès, cliquez sur l’indicateur de notification en haut à droite du site web du portail d’entreprise.

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).

