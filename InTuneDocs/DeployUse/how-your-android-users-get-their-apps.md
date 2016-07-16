---
title: Comment vos utilisateurs Android obtiennent leurs applications | Microsoft Intune
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3bcf89636f9da8fd8bfa5cc52391742a9ce9f92
ms.openlocfilehash: 25571ce1b214c927f3dc2ea3968d00970621e474


---


# Comment vos utilisateurs Android obtiennent leurs applications
Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux obtiennent les applications que vous distribuez via Microsoft Intune. 

**Applications requises** : applications requises par l’administrateur qui sont installées sur l’appareil avec une intervention minime de l’utilisateur, qui varie selon la plateforme.
 
- **Appareils Samsung Knox** : si vous déployez une application requise sur les appareils Samsung Knox, elle est installée automatiquement et sans assistance sur l’appareil de l’utilisateur.
- **Natif (appareils non-Samsung Knox)** : si vous déployez une application requise sur les appareils non-Samsung Knox, elle n’est pas installée automatiquement sur l’appareil de l’utilisateur. Dans ce cas, l’utilisateur est invité à installer l’application. Une fois qu’il a accepté les invites, l’application est téléchargée et il reçoit une notification indiquant qu’il doit l’installer. 

**Applications disponibles** : applications fournies dans la liste de l’application Portail d’entreprise et qu’un utilisateur peut choisir d’installer.

**Applications gérées** : applications gérables par l’intermédiaire de stratégies et qui ont été « encapsulées » par Intune ou qui ont été créées à l’aide du Kit SDK de gestion des applications mobiles Intune. Ces applications peuvent être gérées par Intune et faire l'objet de stratégies d'application.

**Applications non gérées** : applications gérables par l’intermédiaire de stratégies et qui n’ont pas été encapsulées par Intune ou qui n’intègrent pas le Kit SDK de gestion des applications mobiles Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

###Voir aussi
[Ajouter des applications avec Microsoft Intune](/intune/deploy-use/add-apps)
[Comment vos utilisateurs iOS obtiennent leurs applications](how-your-ios-users-get-their-apps.md)
[Comment vos utilisateurs Windows obtiennent leurs applications](how-your-windows-users-get-their-apps.md)


<!--HONumber=Jul16_HO1-->


