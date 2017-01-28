---
title: "Guide pratique pour réinitialiser le code secret de votre appareil à partir du site web du portail d’entreprise | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/03/2017
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
translationtype: Human Translation
ms.sourcegitcommit: beba9603ffb43d025132d2d86f0996ff505a9019
ms.openlocfilehash: f9d66fe07173245ff831f204dd120598ad7564db


---

# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>Guide pratique pour réinitialiser le code secret de votre appareil à partir du site web du portail d’entreprise

Si vous perdez le code confidentiel ou le mot de passe d’un appareil que vous avez inscrit dans Intune, vous pouvez utiliser le [site web du portail d’entreprise](http://portal.manage.microsoft.com) pour le réinitialiser. Vous pouvez utiliser le site web du portail d’entreprise pour gérer les ordinateurs et appareils que vous avez inscrits dans Intune et effectuer pour la majeure partie les mêmes tâches qu’avec l’application de votre portail d’entreprise.

> [!NOTE]
> Il est possible que le bouton **Réinitialiser le code secret** ne soit pas visible sur le site web du portail d’entreprise. Dans ce cas, vous devez contacter votre administrateur informatique pour obtenir de l’aide via le site web du portail d’entreprise.

Pour réinitialiser votre code d’accès

1.  Ouvrez le [site web du portail d’entreprise](http://portal.manage.microsoft.com) sur l’appareil dont vous souhaitez réinitialiser le code d’accès.

2.  Choisissez **Réinitialiser le code d’accès**.

    ![Détails de l’appareil avec le bouton Réinitialiser le code d’accès](./media/iwp-screen-with-all-options.png)

3.  Choisissez **Déconnexion**, puis reconnectez-vous avec vos informations d’identification professionnelles ou scolaires. Vous devez vous reconnecter dans les cinq minutes.

    ![Message de réinitialisation avec bouton de déconnexion](./media/iwp-2-sign-out.png)

4.  Choisissez **Réinitialiser le code d’accès**.

    ![Message qui explique ce qui se passe quand vous réinitialisez le code d’accès](./media/iwp-3-tap-reset-passcode-after-signin.png)

    Pour savoir comment la **réinitialisation du code d’accès** fonctionne sur votre appareil, consultez le tableau.

    |Type d'appareil|Ce qui se produit lors de la réinitialisation|
    |------------|-----------|
    |Android|Supprime le code secret existant et crée un code secret temporaire avec des lettres et des chiffres|
    |iOS|Supprime le code secret existant et ne crée pas de code secret temporaire. Si vous utilisez le scanneur d’empreinte digitale Touch ID pour ouvrir votre appareil ou effectuer des achats, vous devrez le reconfigurer.|
    |Windows 10 Mobile|Supprime le code secret existant et crée un code secret temporaire avec des lettres et des chiffres. Si vous utilisez la reconnaissance faciale Windows Hello pour vous connecter, elle sera toujours prise en charge.|
    |Windows Phone 8.1|Supprime le code secret existant et crée un code secret temporaire avec des chiffres.|

    5.  Déverrouillez votre appareil et définissez un nouveau code secret, ou modifiez le code secret temporaire en accédant à **Paramètres** sur votre appareil.

    Pour afficher une notification confirmant que votre code d’accès a été réinitialisé avec succès, cliquez sur l’indicateur de notification en haut à droite du site web du portail d’entreprise.

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).



<!--HONumber=Jan17_HO1-->


