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
ms.sourcegitcommit: 37841027c7ae040163440a19f9e163fb4eb87233
ms.openlocfilehash: ad780fb3403f6caaee1218d785a5cad326c18df5


---


# Comment vos utilisateurs iOS obtiennent leurs applications

Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux obtiennent les applications que vous distribuez via Microsoft Intune.

**Applications requises** : applications requises par l’administrateur qui sont installées sur l’appareil avec une intervention minime de l’utilisateur, qui varie selon la plateforme.

**Applications disponibles** : applications fournies dans la liste de l’application Portail d’entreprise et qu’un utilisateur peut choisir d’installer.

**Applications gérées** : applications gérables par l’intermédiaire de stratégies et qui ont été « encapsulées » par Intune ou qui ont été créées à l’aide du SDK de gestion des applications mobiles Intune. Ces applications peuvent être gérées par Intune et faire l'objet de stratégies d'application.

**Applications non gérées** : applications gérables par l’intermédiaire de stratégies et qui n’ont pas été encapsulées par Intune ou qui n’intègrent pas le SDK de gestion des applications mobiles Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

Les restrictions d’Apple n’autorisent pas l’affichage des applications métier et gérées de l’App Store dans l’application Portail d’entreprise. Pour contourner ce problème, les vignettes dans l’application Portail d’entreprise pour iOS dirigent les utilisateurs vers différentes vues dans un emplacement unique (à savoir le site web du Portail d’entreprise) pour toutes leurs applications.

- **Applications d’entreprise** pointait vers une liste de toutes les applications sous l’onglet TOUT du [site web du Portail d’entreprise](http://portal.manage.microsoft.com). Elle a toujours le même comportement, mais son nom a été remplacé par **Toutes les applications**.

- **Autres applications** pointait vers une vue dans l’application Portail d’entreprise qui répertorie toutes les applications dont l’affichage dans le Portail d’entreprise était autorisé par Apple. Cette vignette s’appelle maintenant **Applications proposées**. Quand l’utilisateur appuie dessus, il accède à l’onglet SÉLECTION du site web du Portail d’entreprise.

-  **Catégories** pointait vers une vue dans l’application Portail d’entreprise qui répertorie toutes les catégories d’applications. Son nom n’a pas changé, mais la vignette pointe maintenant vers l’onglet CATÉGORIES du site web du Portail d’entreprise.
Des captures d’écran mises à jour sont disponibles dans [Améliorations apportées à l’accès des utilisateurs finaux iOS à leurs applications](https://gallery.technet.microsoft.com/Improvements-in-how-iOS-d1104186).



### Voir aussi
[Comment vos utilisateurs Android obtiennent leurs applications](how-your-android-users-get-their-apps.md)

[Comment vos utilisateurs Windows obtiennent leurs applications](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


