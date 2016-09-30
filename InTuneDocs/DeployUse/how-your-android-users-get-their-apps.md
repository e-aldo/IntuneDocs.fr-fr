---
title: Comment vos utilisateurs Android obtiennent leurs applications | Microsoft Intune
description: "Méthodes de mise à disposition des applications Android pour les utilisateurs finaux"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a3db9269bf4f93021d16d8ea23a2a13b87b43677
ms.openlocfilehash: d3d37b9bcf8cc5833b4e11185b49902e26a625dc


---


# Comment vos utilisateurs Android obtiennent leurs applications
Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux Android obtiennent les applications que vous distribuez via Microsoft Intune. Les informations peuvent être différentes pour les appareils Android natifs et les appareils Samsung Knox.

## Appareils Android natifs (ne s’applique pas aux appareils Samsung Knox)

| Type d’application | Applications métier | Applications Play Store  |
| ------------- |-------------| -----|
| Applications disponibles      | Sur le site Portail d’entreprise, les utilisateurs appuient sur **Installer**. Une notification s’affiche, sur laquelle les utilisateurs appuient pour démarrer l’installation. Une fois l’installation effectuée, la notification disparaît. | Sur le site Portail d’entreprise, les utilisateurs appuient sur l’application et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation.|
| Applications requises      | Les utilisateurs reçoivent une notification qu’ils ne peuvent pas masquer et qui leur indique qu’ils doivent installer une application. Les utilisateurs appuient sur la notification pour démarrer l’installation. Une fois l’installation effectuée, la notification disparaît.    | Les utilisateurs reçoivent une notification qu’ils ne peuvent pas masquer et qui leur indique qu’ils doivent installer une application. Les utilisateurs appuient sur la notification et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation. Une fois l’installation effectuée, la notification disparaît. |

## Appareils Android Samsung Knox

| Type d’application | Applications métier | Applications Play Store  |
| ------------- |-------------| -----|
| Applications disponibles      | Sur le site Portail d’entreprise, les utilisateurs appuient sur **Installer**. L’application est installée sans autre intervention de l’utilisateur. | Sur le site Portail d’entreprise, les utilisateurs appuient sur l’application et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation.|
| Applications requises      | L’application est installée sans intervention de l’utilisateur.    | Les utilisateurs reçoivent une notification qu’ils ne peuvent pas masquer et qui leur indique qu’ils doivent installer une application. Les utilisateurs appuient sur la notification et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation. Une fois l’installation effectuée, la notification disparaît. |

Les applications peuvent être gérées ou non gérées, comme décrit ci-dessous. Le processus de fabrication d’applications gérées est le même pour tous les types d’appareil Android.

**Applications gérées** : applications gérables par l’intermédiaire de stratégies et qui ont été « encapsulées » par Intune ou qui ont été créées à l’aide du Kit SDK de gestion des applications mobiles Intune. Ces applications peuvent être gérées par Intune et faire l'objet de stratégies d'application.

**Applications non gérées** : applications gérables par l’intermédiaire de stratégies et qui n’ont pas été encapsulées par Intune ou qui n’intègrent pas le Kit SDK de gestion des applications mobiles Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

### Voir aussi
[Ajouter des applications avec Microsoft Intune](/intune/deploy-use/add-apps)

[Comment vos utilisateurs iOS obtiennent leurs applications](how-your-ios-users-get-their-apps.md)

[Comment vos utilisateurs Windows obtiennent leurs applications](how-your-windows-users-get-their-apps.md)



<!--HONumber=Sep16_HO5-->


