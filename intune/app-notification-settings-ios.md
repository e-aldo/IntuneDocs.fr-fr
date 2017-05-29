---
title: "Paramètres de notification des applications Intune pour les appareils iOS"
titleSuffix: Intune Azure preview
description: "Intune Azure en version préliminaire : découvrez les paramètres que vous pouvez utiliser pour contrôler les notifications envoyées par des applications sur des appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c64167275a2628c6a3a4e899e00c25df4c10b06b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="intune-app-notifications-settings-for-ios-devices"></a>Paramètres de notification des applications Intune pour les appareils iOS

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Apprenez à configurer l’envoi de notifications par des applications installées sur un appareil. Ce paramètre prend en charge les appareils supervisés exécutant iOS 9.3 et versions ultérieures.

## <a name="configure-settings"></a>Configurer les paramètres

1. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **Notifications de l’application (mode supervisé uniquement)**.
2. Dans le panneau **Notifications de l’application**, choisissez **Ajouter**, puis configurez les valeurs suivantes :
    - **ID d’ensemble d’applications** : entrez **l’ID d’ensemble d’applications** de l’application que vous souhaitez configurer. Pour obtenir de l’aide, consultez la section **Référence à un ID d’ensemble pour les applications iOS intégrées** de cette rubrique.
    - **Nom de l’application** : entrez le nom de l’application que vous souhaitez configurer. Ce nom ne s’affiche pas sur l’appareil et est utilisé pour vous aider à identifier l’application dans la liste.
    - **Éditeur :** indiquez l’éditeur de l’application que vous souhaitez configurer. Ce nom ne s’affiche pas sur l’appareil et est utilisé pour vous aider à identifier l’application dans la liste.
    - **Notifications** : permet d’activer ou désactiver l’envoi de notifications entre l’application et l’appareil. Si vous désactivez ce paramètre, les paramètres suivants sont également désactivés.
        - **Afficher dans le centre de notifications** : activez cette option pour permettre à l’application d’afficher des notifications dans le centre de notifications de l’appareil.
        - **Afficher dans l’écran de verrouillage** : activez cette option pour afficher les notifications de l’application sur l’écran de verrouillage de l’appareil.
        - **Type d’alerte** : sélectionnez le type de notification que vous voulez afficher lorsque l’appareil est déverrouillé. Plusieurs options sont possibles :
            - **Aucune** : aucune notification n’est affichée.
            - **Bannière** : une bannière s’affiche brièvement pour montrer la notification.
            - **Modal** : la notification s’affiche et l’utilisateur doit la fermer manuellement pour pouvoir continuer à utiliser l’appareil.
        - **Badge sur l’icône de l’application** : activez cette option pour ajouter un badge à l’icône de l’application afin d’indiquer que l’application a envoyé une notification.
        - **Sons** : activez cette option pour émettre un son lorsqu’une notification est envoyée.
3. Continuez à ajouter autant d’applications que nécessaire. Quand vous avez terminé, cliquez sur **OK**.
4. Cliquez sur **OK** jusqu’à ce que vous reveniez au panneau **Créer un profil**, puis cliquez sur **Créer**. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Référence à un ID d’ensemble pour les applications iOS intégrées

Cette liste affiche l’ID d’ensemble de quelques applications iOS intégrées parmi les plus courantes. Pour rechercher l’ID d’ensemble d’autres applications, contactez votre éditeur de logiciels. 

|||
|-|-|
|Nom de l’application|ID d’ensemble|
|App Store|com.apple.AppStore|
|Calculatrice|com.apple.calculator|
|Calendrier|com.apple.mobilecal|
|Appareil photo|com.apple.camera|
|Horloge|com.apple.mobiletimer|
|Boussole|com.apple.compass|
|Contacts|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Trouver des amis|com.apple.mobileme.fmf1|
|Trouver un iPhone|com.apple.mobileme.fmip1|
|Centre de jeux|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Intégrité|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Mappages|com.apple.Maps|
|Messages|com.apple.MobileSMS|
|Musique|com.apple.Music|
|Actualités|com.apple.news|
|Remarques|com.apple.mobilenotes|
|Nombres|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Photo|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Rappels|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Paramètres|com.apple.Preferences|
|Bourse|com.apple.stocks|
|Conseils|com.apple.tips|
|Vidéos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Portefeuille|com.apple.Passbook|
|Regardez|com.apple.Bridge|
|Météo|com.apple.weather|
