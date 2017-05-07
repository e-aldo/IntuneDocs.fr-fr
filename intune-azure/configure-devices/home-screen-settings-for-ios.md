---
title: "Paramètres de disposition de l’écran d’accueil Intune pour les appareils iOS"
titleSuffix: Intune Azure preview
description: "Intune Azure en version préliminaire : découvrez les paramètres que vous pouvez utiliser pour personnaliser l’écran d’accueil et l’écran d’ancrage sur des appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 72bfde93389a060ed52062be0f2692b8bc35543a
ms.lasthandoff: 04/19/2017


---

# <a name="intune-home-screen-layout-settings-for-ios-devices"></a>Paramètres de disposition de l’écran d’accueil Intune pour les appareils iOS

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez ces paramètres pour configurer la disposition des applications, des dossiers et des éléments web sur l’écran d’ancrage et l’écran d’accueil de tous les appareils iOS auxquels vous affectez la stratégie.

Les appareils iOS auxquels vous affectez le profil doivent être en mode supervisé et exécuter iOS 9.3 ou version ultérieure.

1. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **Disposition de l’écran d’accueil (supervisé uniquement)**.
2. Dans le panneau **Disposition de l’écran d’accueil (supervisé uniquement)**, choisissez si vous voulez configurer les dispositions **Ancrer** ou **Pages**.

## <a name="add-items-to-the-dock"></a>Ajouter des éléments à l’écran d’ancrage

Dans le panneau **Ancrer**, vous pouvez ajouter jusqu’à 6 éléments ou dossiers à l’espace d’ancrage se trouvant en bas de l’écran iOS. De nombreux appareils prennent cependant en charge moins d’éléments (par exemple, les appareils iPhone acceptent un maximum de 4 éléments). Dans ce cas, seuls les quatre premiers éléments que vous avez configurés s’afficheront sur l’appareil.

1. Choisissez **Ajouter** pour ajouter un élément à l’écran d’ancrage.
2. Dans le panneau **Ajouter une ligne**, indiquez si vous souhaitez ajouter une **Application** ou un **Dossier**.
3. En utilisant les informations fournies dans les sections **Comment ajouter une application à la liste** et **Comment ajouter un dossier à la liste** de cette rubrique, configurez les applications et les dossiers que vous souhaitez voir apparaître dans l’écran d’ancrage.
4. Continuez à ajouter des éléments. Lorsque vous avez terminé, cliquez sur **OK** jusqu’à ce que vous reveniez au panneau **Créer un profil**. Choisissez **Créer**.

>[!TIP]
> Vous pouvez faire glisser et déplacer des éléments dans l’écran d’accueil et dans les listes de pages pour les réorganiser. 

### <a name="example"></a>Exemple

Dans cet exemple, vous avez configuré l’écran d’ancrage pour afficher uniquement les applications Safari, Messagerie et Bourse. Dans l’image suivante, l’application Messagerie est sélectionnée pour illustrer ses propriétés :

![Exemples de paramètres d’ancrage iOS](http://i.imgur.com/FfFiUcP.png)

Lorsque vous affectez la stratégie à un iPhone, vous obtenez un ancrage semblable à ce qui suit :

![Exemple de disposition d’ancrage iOS sur iPhone](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a>Ajouter des pages à l’écran d’accueil

Ajoutez les pages que vous souhaitez afficher sur l’écran d’accueil pour faire apparaître les applications sur chaque page. Les applications que vous ajoutez à une page sont organisées de gauche à droite, dans l’ordre selon lequel elles sont spécifiées dans la liste. Si vous ajoutez plus d’applications que la page ne peut en contenir, les applications seront déplacées vers une page suivante.


1. Dans le panneau **Pages**, choisissez **Ajouter**.
2. Dans le panneau **Ajouter une ligne**, entrez un **nom de page**. Ce nom est utilisé à titre de référence dans le portail Intune, mais il *n’est pas affiché* sur l’appareil iOS.
3. Cliquez sur **Ajouter** et indiquez si vous souhaitez ajouter une **Application** ou un **Dossier** à la page.
4. En utilisant les informations fournies dans les sections **Comment ajouter une application à la liste** et **Comment ajouter un dossier à la liste** de cette rubrique, configurez les applications et les dossiers que vous souhaitez voir apparaître sur la page.

### <a name="example"></a>Exemple

Dans cet exemple, vous avez configuré une page nommée **Contoso**. La page affiche uniquement les applications Trouver des amis et Réglages. Dans l’image suivante, l’application Réglages est sélectionnée pour illustrer ses propriétés :

![Exemple de paramètres d’écran d’accueil iOS](http://i.imgur.com/Jc2OxyX.png)

Lorsque vous affectez la stratégie à un iPhone, vous obtenez une page semblable à ce qui suit :

![Appareil iOS avec écran d’accueil modifié](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a>Comment ajouter une application à la liste

1. Entrez le **Nom de l’application**. Ce nom est utilisé à titre de référence dans le portail Intune, mais il *n’est pas affiché* sur l’appareil iOS.
2. Entrez **l’ID d’ensemble d’applications** de l’application que vous souhaitez déployer. Pour obtenir de l’aide, consultez la section **Référence à un ID d’ensemble pour les applications iOS intégrées** de cette rubrique.
3. Cliquez sur **OK**, puis continuer à ajouter des éléments, sans dépasser **6** éléments pour l’ancrage et **60** éléments pour une page de l’appareil.
4. Lorsque vous avez terminé, cliquez sur **OK**.

## <a name="how-to-add-a-folder-to-the-list"></a>Comment ajouter un dossier à la liste

Les applications que vous ajoutez à une page dans un dossier sont organisées de gauche à droite, dans l’ordre selon lequel elles sont spécifiées dans la liste. Si vous ajoutez plus d’applications que la page ne peut en contenir, les applications seront déplacées vers une page suivante.

1. Entrez le **Nom du dossier**. Ce nom apparaîtra aux utilisateurs sur leur appareil.
2. Cliquez sur **Ajouter** pour créer une page dans le dossier. Vous pouvez ajouter jusqu’à 20 pages.
3. Dans le panneau **Ajouter une ligne**, entrez un nom de page. Ce nom est utilisé à titre de référence dans le portail Intune, mais il *n’est pas affiché* sur l’appareil iOS.
3. Entrez le **Nom de l’application**. Ce nom est utilisé à titre de référence dans le portail Intune, mais il *n’est pas affiché* sur l’appareil iOS.
2. Entrez **l’ID d’ensemble d’applications** de l’application que vous souhaitez déployer. Consultez la section **Comment ajouter une application à la liste** pour plus d’informations.
3. Choisissez **Ajouter**. Vous pouvez ajouter jusqu’à 60 éléments.
4. Lorsque vous avez terminé, cliquez sur **OK**.


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


