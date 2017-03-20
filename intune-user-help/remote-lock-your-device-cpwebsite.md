---
title: "Verrouiller votre appareil dans le Portail d’entreprise | Microsoft Docs"
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
ms.assetid: adc6af23-b22f-42e5-955a-4dffbdb8b42b
searchScope:
- User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 10c7bc5461c746ab50e83c2ffc590b89efe75e5f
ms.openlocfilehash: 6910fd7b67fcd934b35a81cdbd372b2069fb3493
ms.lasthandoff: 03/13/2017


---

# <a name="remotely-lock-your-device-from-the-company-portal-website"></a>Verrouiller à distance un appareil à partir du site web du portail d’entreprise

Des accidents se produisent et des appareils peuvent parfois disparaître. Si votre appareil a été perdu ou volé, vous devez d’abord vous demander si les informations qu’il contient sont accessibles à n’importe qui, quel que soit l’endroit où se trouve votre appareil.

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

Pour plus de sécurité, vous pouvez le verrouiller en utilisant l’option Verrouillage à distance sur le [site web du portail d’entreprise](http://portal.manage.microsoft.com). L’option Verrouillage à distance fonctionne pour :

* Android
* iOS
* macOS
* Windows 10 Mobile (si un code secret avait déjà été défini sur l’appareil)
* Windows Phone 8.1 (si un code secret avait déjà été défini sur l’appareil)

## <a name="to-use-remote-lock-to-lock-your-device"></a>Pour utiliser l’option Verrouillage à distance pour verrouiller votre appareil

1.    Sur le [site web Portail d’entreprise](http://portal.manage.microsoft.com), cliquez sur le bouton de __menu__ ![Petite image du bouton de menu, représentant trois barres horizontales empilées les unes sur les autres.](/Intune/whats-new/media/CP_hamburger_menu.png), puis sélectionnez __Mes appareils__.

  ![Image du site web Portail d’entreprise avec un menu latéral développé sur le côté gauche de l’écran, contenant les boutons Accueil, Toutes les applications, Mes appareils, Support technique et Déconnexion.](/media/iwp-expanded-sidebar.png)

2. Dans la page __Mes appareils__, sélectionnez le nom de l’appareil à verrouiller.

  ![Capture d’écran de la page Mes appareils, avec quelques appareils non identifiés au-dessus de la bannière invitant à inscrire les appareils non listés ou à identifier ceux qui ne le sont pas.](./media/macOS_enroll_002_tap_here_banner.png)

3.    L’appareil s’ouvre dans une fenêtre contextuelle. Appuyez sur le bouton **Verrouillage à distance**.

    ![Toutes les options disponibles pour un appareil sélectionné sur le site web Portail d’entreprise, notamment Renommer, Supprimer, Réinitialiser l’appareil, Réinitialiser le code secret et Verrouillage à distance. ](./media/iwp-screen-with-all-options.png)

4.    Une notification s’affiche pour vous informer que vous êtes sur le point de verrouiller votre appareil. Appuyez sur **Verrouillage à distance** et le site web du portail d’entreprise tente de verrouiller votre appareil.

    Une fois que vous avez sélectionné **Verrouillage à distance**, le message « Verrouillage à distance en attente » s’affiche.  Si le verrouillage à distance aboutit, l’état passe à « Verrouillage à distance réussi ».

    L’état Verrouillage à distance s’affiche à trois emplacements :

    * La zone de notification du site web.
    * La page **Détails** de l’appareil.
    * La vignette qui affiche le nom de l’appareil dans la section **Mes appareils** de la page.

> [!Note]
> Si vous voyez une notification « Échec du verrouillage à distance », attendez quelques minutes et essayez à nouveau de verrouiller votre appareil. Dès le début de la nouvelle tentative, l’état passe à « Verrouillage à distance en attente ». Si la nouvelle tentative ne fonctionne pas, vous devez contacter votre administrateur informatique.

Si vous retrouvez votre appareil et que vous souhaitez le déverrouiller après avoir utilisé le verrouillage à distance, il vous suffit d’entrer votre code secret.

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).

