---
title: Comment vos utilisateurs Android obtiennent leurs applications | Microsoft Docs
description: "Méthodes de mise à disposition des applications Android pour les utilisateurs finaux"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 370dd5d4a96253f0b7d208ef85659beeace18739
ms.lasthandoff: 12/10/2016


---


# <a name="how-your-android-users-get-their-apps"></a>Comment vos utilisateurs Android obtiennent leurs applications

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez ces informations pour comprendre comment et où vos utilisateurs finaux Android obtiennent les applications que vous distribuez via Microsoft Intune. Les informations peuvent différer selon le type d’appareil (appareils Android natifs ou appareils Samsung Knox Standard).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Appareils Android (non-Samsung Knox Standard) natifs

| Type d’application | Applications métier | Applications Play Store  |
| ------------- |-------------| -----|
| Applications disponibles      | Sur le site Portail d’entreprise, les utilisateurs appuient sur **Installer**. Une notification s’affiche, sur laquelle les utilisateurs appuient pour démarrer l’installation. Une fois l’installation effectuée, la notification disparaît. | Sur le site Portail d’entreprise, les utilisateurs appuient sur l’application et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation.|
| Applications requises      | Les utilisateurs reçoivent une notification qu’ils ne peuvent pas masquer et qui leur indique qu’ils doivent installer une application. Les utilisateurs appuient sur la notification pour démarrer l’installation. Une fois l’installation effectuée, la notification disparaît.    | Les utilisateurs reçoivent une notification qu’ils ne peuvent pas masquer et qui leur indique qu’ils doivent installer une application. Les utilisateurs appuient sur la notification et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation. Une fois l’installation effectuée, la notification disparaît. |

## <a name="samsung-knox-standard-android-devices"></a>Appareils Android Samsung Knox Standard

| Type d’application | Applications métier | Applications Play Store  |
| ------------- |-------------| -----|
| Applications disponibles      | Sur le site Portail d’entreprise, les utilisateurs appuient sur **Installer**. L’application est installée sans autre intervention de l’utilisateur. | Sur le site Portail d’entreprise, les utilisateurs appuient sur l’application et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation.|
| Applications requises      | L’application est installée sans intervention de l’utilisateur.    | Les utilisateurs reçoivent une notification qu’ils ne peuvent pas masquer et qui leur indique qu’ils doivent installer une application. Les utilisateurs appuient sur la notification et accèdent à une page d’application dans le Play Store, où ils peuvent démarrer l’installation. Une fois l’installation effectuée, la notification disparaît. |

Les applications peuvent être gérées ou non gérées, comme décrit ci-dessous. Le processus de fabrication d’applications gérées est le même pour tous les types d’appareil Android.

**Applications gérées** - Il s’agit d’applications gérables par l’intermédiaire de stratégies. Elles ont été « encapsulées » par Intune ou ont été créées à l’aide du SDK Intune Mobile Application Management (MAM). Ces applications peuvent être gérées par Intune et faire l'objet de stratégies d'application.

**Applications non gérées** - Il s’agit d’applications qui ne sont pas gérables par l’intermédiaire de stratégies. Elles n’ont pas été encapsulées par Intune ou n’intègrent pas le SDK MAM Intune. Vous ne pouvez pas appliquer de stratégies d'application à ces applications.

### <a name="see-also"></a>Voir aussi
[Ajouter des applications avec Microsoft Intune](/intune/deploy-use/add-apps)

[Comment vos utilisateurs iOS obtiennent leurs applications](how-your-ios-users-get-their-apps.md)

[Comment vos utilisateurs Windows obtiennent leurs applications](how-your-windows-users-get-their-apps.md)

