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
ms.sourcegitcommit: 9f1946c02c6267a22844106e8f72555ec5e9cabb
ms.openlocfilehash: 212dcd31697180dae61569dda13b56704a079bf4


---


# Comment vos utilisateurs iOS obtiennent leurs applications

Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux obtiennent les applications que vous distribuez via Microsoft Intune.

**Applications requises** : applications requises par l’administrateur qui sont installées sur l’appareil avec une intervention minime de l’utilisateur, qui varie selon la plateforme.

**Applications disponibles** : applications fournies dans la liste de l’application Portail d’entreprise et qu’un utilisateur peut choisir d’installer.

**Applications gérées** : applications gérables par l’intermédiaire de stratégies et qui ont été « encapsulées » par Intune ou qui ont été créées à l’aide du Kit SDK de gestion des applications mobiles Intune. Ces applications peuvent être gérées par Intune et faire l'objet de stratégies d'application.

**Applications non gérées** : applications gérables par l’intermédiaire de stratégies et qui n’ont pas été encapsulées par Intune ou qui n’intègrent pas le Kit SDK de gestion des applications mobiles Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

Les restrictions d’Apple n’autorisent pas les applications métier et gérées de l’App store à être répertoriées dans l’application Portail d’entreprise, ce qui signifie que les utilisateurs doivent accéder à différentes vues pour rechercher toutes leurs applications. Les applications pour chaque mosaïque affichée à la page d’applications du Portail d’entreprise sont disponibles comme suit :

- La mosaïque **Applications d’entreprise** pointe vers une liste de toutes les applications dans l’onglet **TOUT** du [site Web Portail d’entreprise](http://portal.manage.microsoft.com).

- La mosaïque **Autres applications** pointe actuellement vers une vue située à l’intérieur de l’application Portail d’entreprise, qui répertorie toutes les applications que le Portail d’entreprise est autorisé à afficher par Apple. Cela inclut toutes les applications à l’exception des applications métier et gérées de l’App store.

- La mosaïque **Catégories** pointe actuellement vers une vue située à l’intérieur de l’application Portail d’entreprise, qui répertorie les catégories d’applications.

    ![ios-how-to-sync-device-with-intune](./media/ios-sync-comp-portal-apps.png)


###Voir aussi
[Comment vos utilisateurs Android obtiennent leurs applications](how-your-android-users-get-their-apps.md)</br>
[Comment vos utilisateurs Windows obtiennent leurs applications](how-your-windows-users-get-their-apps.md)



<!--HONumber=Aug16_HO4-->


