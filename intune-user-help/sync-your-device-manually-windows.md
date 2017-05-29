---
title: "Synchroniser manuellement votre appareil Windows | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 443c6de7-5187-4dc4-b844-6085a0c659bd
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 05b290345c761372850fb501a3707dbd53a3ef07
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="sync-your-windows-device-manually"></a>Synchroniser votre appareil Windows manuellement

Parfois, une tentative d’installation d’une application sur votre appareil Windows peut durer plus longtemps que prévu. Dans ce cas, vous pouvez tenter de synchroniser manuellement votre appareil Windows. La synchronisation peut accélérer l’installation.

> [!Note]
> L’installation d’applications peut prendre du temps si vous êtes sur un réseau avec des vitesses plus lentes ou des quantités plus élevées d’appareils téléchargeant du contenu en même temps.

Les versions suivantes de Windows peuvent être synchronisées manuellement. Malheureusement, si votre appareil utilise une autre version de Windows, vous ne pouvez pas lancer une synchronisation manuelle.

* [Synchronisation de Windows 10 Desktop](#windows-10-desktop)
* [Synchronisation de Windows 10 Mobile](#windows-10-mobile)
* [Synchronisation de Windows Phone 8.1](#windows-phone-81)

## <a name="windows-10-desktop"></a>Windows 10 Desktop
Comme il existe plusieurs versions de Windows 10, il y a deux procédures. Pour connaître la procédure à exécuter, examinez les captures d’écran, puis suivez les étapes qui ressemblent à ce que vous voyez sur votre appareil.

1. Choisissez le bouton **Démarrer**, puis choisissez **Paramètres**.

    ![Bouton Démarrer](./media/win10pc-sync-1-start-button.png)

2. Dans la page **Paramètres**, choisissez **Comptes**.

    ![Choix de Comptes dans la page Paramètres](./media/win10pc-sync-2-settings-accounts.png)

3. Examinez les deux écrans suivants et déterminez celui qui ressemble à celui qui s’affiche sur votre appareil. Suivez les étapes correspondant à l’écran qui s’affiche sur votre appareil.

    Si cet écran s’affiche, qui indique « Accès Professionnel ou Scolaire », suivez les instructions indiquées dans la section [Étapes à suivre si vous voyez Accès scolaire ou professionnel](#steps-to-follow-if-you-see-access-work-or-school).

    ![Étapes de synchronisation à suivre si vous voyez Accès Professionnel ou Scolaire](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Si vous voyez cet écran, qui indique « Accès professionnel », consultez les [étapes à suivre si vous voyez Accès professionnel](#steps-to-follow-if-you-see-work-access).

    ![Choix d’accès professionnel comme type de compte](./media/win10pc-sync-3-work-access.png)

### <a name="steps-to-follow-if-you-see-access-work-or-school"></a>Étapes à suivre si vous voyez Accès scolaire ou professionnel

1. Dans la page **Comptes**, choisissez **Accès Professionnel ou Scolaire**.

    ![Choisir Accès Professionnel ou Scolaire](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2. Choisissez votre compte professionnel ou scolaire. Selon la configuration effectuée par votre administrateur informatique, vous pouvez voir deux comptes similaires à l’exemple ci-dessous. Un compte est accompagné d’un porte-documents, l’autre du logo Microsoft.

    - Si vous voyez le compte avec le porte-documents, sélectionnez-le, puis recherchez un bouton **Info** sous celui-ci.
    - Si vous voyez uniquement le compte avec le logo Microsoft, sélectionnez le compte, puis recherchez un bouton **Info** sous celui-ci.

    ![Choisissez votre nom de compte en regard du porte-documents ou du logo Microsoft](./media/win10pc-rs1-sync-info-button.png)

3. Choisissez le bouton **Info**. Une boîte de dialogue s’ouvre, similaire à l’exemple ci-dessous.

    ![Choisissez votre nom de compte en regard du porte-documents ou du logo Microsoft](./media/win10pc-rs1-sync-button.png)

4. Choisissez le bouton **Synchroniser**. Votre appareil est synchronisé avec Intune.

### <a name="steps-to-follow-if-you-see-work-access"></a>Étapes à suivre si vous voyez Accès professionnel

1. Dans la page **Comptes**, choisissez **Accès professionnel**.

    ![Choix d’accès professionnel comme type de compte](./media/win10pc-sync-3-work-access.png)

2. Dans la section **Inscription à la gestion des appareils**, choisissez le nom de votre entreprise.

    ![Choix du nom de l’entreprise pour la gestion des appareils](./media/win10pc-sync-4-tap-com-name.png)

3. Choisissez le bouton **Synchroniser**.

    ![Choix du bouton Synchroniser](./media/win10pc-sync-5-tap-sync.png)

   Le bouton est grisé jusqu’à ce que la synchronisation se termine.

### <a name="windows-10-mobile"></a>Windows 10 Mobile
Pour synchroniser manuellement votre appareil mobile Windows 10 pour accélérer l’installation d’une application :

   1. Accédez à **Toutes les applications** > **Paramètres** > **Comptes**.

       ![Choix de Comptes dans l’écran Paramètres](./media/win10m-sync-1-settings-accounts.png)

   2. Choisissez **Accès professionnel**.

       ![Choix d’accès professionnel comme type de compte](./media/win10m-sync-2-work-access.png)

   3. Sous **Inscription à la gestion des appareils**, choisissez le nom de votre entreprise.

       ![Choix du nom de l’entreprise pour la gestion des appareils](./media/win10m-sync-3-tap-comp-name.png)

   4. Choisissez l’icône **Synchroniser**.

       ![Choix de l’icône Synchroniser](./media/win10m-sync-4-tap-sync.png)

       Le message « Nous synchronisons votre compte » apparaît en haut de l’écran. Le bouton **Synchroniser** est grisé tant que la synchronisation n’est pas terminée sur votre appareil.

## <a name="windows-phone-81"></a>Windows Phone 8.1
Pour synchroniser manuellement votre appareil Windows Phone 8.1 pour accélérer l’installation d’une application :

1. Accédez à **Toutes les applications** > **Paramètres** > **espace de travail**.

    ![Liste des paramètres](./media/wp81-1-sync-settings-workplace.png)

2. Choisissez le nom de votre société.

    ![Choix du nom de la société pour le compte de l’espace de travail](./media/wp81-2-sync-tap-compname.png)

3. Choisissez l’icône **Synchroniser**.

    ![Choix de l’icône Synchroniser](./media/wp81-3-sync-tap-sync-button.png)

   Le message « Nous synchronisons votre compte » apparaît en haut de l’écran jusqu’à la fin de la synchronisation de votre appareil.

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).

