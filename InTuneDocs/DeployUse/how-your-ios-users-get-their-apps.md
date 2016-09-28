---
title: Comment vos utilisateurs iOS obtiennent leurs applications | Microsoft Intune
description: "Méthodes de mise à disposition des applications iOS pour les utilisateurs finaux"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 52b9e786fe22b04081441db88a3629062fc85668
ms.openlocfilehash: a215d547507dcc460e83009cc6a04baf3fd8f4a4


---


# Comment vos utilisateurs iOS obtiennent leurs applications

Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux obtiennent les applications que vous distribuez via Microsoft Intune.

**Applications requises** : applications requises par l’administrateur qui sont installées sur l’appareil avec une intervention minime de l’utilisateur, qui varie selon la plateforme.

**Applications disponibles** : applications fournies dans la liste de l’application Portail d’entreprise et qu’un utilisateur peut choisir d’installer.

**Applications gérées** : applications gérables par l’intermédiaire de stratégies et qui ont été « encapsulées » par Intune ou qui ont été créées à l’aide du Kit SDK de gestion des applications mobiles Intune. Ces applications peuvent être gérées par Intune et faire l'objet de stratégies d'application.

**Applications non gérées** : applications gérables par l’intermédiaire de stratégies et qui n’ont pas été encapsulées par Intune ou qui n’intègrent pas le Kit SDK de gestion des applications mobiles Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

Les restrictions d’Apple n’autorisent pas l’affichage des applications métier et gérées de l’App Store dans l’application Portail d’entreprise. Pour contourner ce problème, les vignettes d’applications dans l’application Portail d’entreprise pour iOS dirigent les utilisateurs vers différentes vues dans un emplacement unique (à savoir le site web du Portail d’entreprise) pour toutes leurs applications, comme expliqué ci-après :

- La vignette **Applications d’entreprise** pointait auparavant vers une liste de toutes les applications dans l’onglet TOUT du [site web du Portail d’entreprise](http://portal.manage.microsoft.com). Elle a toujours le même comportement, mais son nom a été remplacé par **Toutes les applications**.

- La vignette **Autres applications** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les applications dont l’affichage dans le Portail d’entreprise était autorisé par Apple. Cette vignette s’appelle maintenant **Applications proposées**. Quand l’utilisateur appuie dessus, il accède à l’onglet SÉLECTION du site web du Portail d’entreprise.

-  La vignette **Catégories** pointait auparavant vers une vue, dans l’application Portail d’entreprise, qui répertoriait toutes les catégories d’applications. Son nom n’a pas changé, mais la vignette pointe maintenant vers l’onglet CATÉGORIES du site web du Portail d’entreprise.
Vous trouverez des captures d’écran mises à jour [ici](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).



###Voir aussi
[Comment vos utilisateurs Android obtiennent leurs applications](how-your-android-users-get-their-apps.md)</br>
[Comment vos utilisateurs Windows obtiennent leurs applications](how-your-windows-users-get-their-apps.md)



<!--HONumber=Sep16_HO3-->


