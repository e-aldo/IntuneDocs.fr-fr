---
title: Comment vos utilisateurs iOS obtiennent leurs applications
description: "Méthodes de mise à disposition des applications iOS pour les utilisateurs finaux"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72291be81df5e0358c9477a2749fb7d9d7cb8fdc
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2017
---
# <a name="how-your-ios-users-get-their-apps"></a>Comment vos utilisateurs iOS obtiennent leurs applications

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux obtiennent les applications que vous distribuez via Microsoft Intune.

**Applications requises** : applications requises par l’administrateur qui sont installées sur l’appareil avec une intervention minime de l’utilisateur, qui varie selon la plateforme.

**Applications disponibles** : applications fournies dans la liste de l’application Portail d’entreprise et qu’un utilisateur peut choisir d’installer.

**Applications gérées** : applications pouvant être gérées avec des stratégies et qui ont été « enveloppées » par Intune, ou qui ont été créées à l’aide du kit SDK d’application Intune. Ces applications peuvent être gérées par Intune et faire l’objet de stratégies de protection des applications.

**Applications non gérées** : applications pouvant être gérées avec des stratégies et qui n’ont pas été « enveloppées » par Intune, ou qui ne sont pas intégrées au kit SDK d’application Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

Les restrictions d’Apple n’autorisent pas l’affichage des applications métier et gérées de l’App Store dans l’application Portail d’entreprise. Pour contourner ce problème, les vignettes dans l’application Portail d’entreprise pour iOS dirigent les utilisateurs vers différentes vues dans un emplacement unique (à savoir le site web du Portail d’entreprise) pour toutes leurs applications.

Les utilisateurs inscrits obtiennent leurs applications en appuyant sur les vignettes suivantes dans l’écran Applications de l’application Portail d’entreprise :

- **Toutes les applications** pointent vers une liste de toutes les applications sous l’onglet TOUT du [site web Portail d’entreprise](https://portal.manage.microsoft.com).

- **Applications proposées** pointe vers l’onglet SÉLECTION du site web Portail d’entreprise.

- **Catégories** pointe vers l’onglet CATÉGORIES du site web Portail d’entreprise.


![Écran des applications du Portail d’entreprise iOS](./media/ios-cp-app-main-apps-screen.png)

Pour plus d’informations sur la façon d’ajouter des applications et de les placer dans ces vignettes, consultez [Ajouter des applications pour les appareils inscrits à Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Voir aussi
[Comment vos utilisateurs Android obtiennent leurs applications](end-user-apps-android.md)

[Comment vos utilisateurs Windows obtiennent leurs applications](end-user-apps-windows.md)
