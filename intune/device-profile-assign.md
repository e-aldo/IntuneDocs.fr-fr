---
title: "Guide pratique pour attribuer des profils d’appareils avec Intune"
titlesuffix: Azure portal
description: "Une fois que vous avez créé un profil d’appareil Intune, apprenez à l’attribuer à des appareils dans cette rubrique."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef03eeab32050559d34d3d7d580c06c21f5ffb05
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Guide pratique pour attribuer des profils d’appareil Microsoft Intune

## <a name="assign-a-device-profile"></a>Attribuer un profil d’appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
1. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
2. Dans le panneau de la liste des profils, sélectionnez le profil à gérer, puis, dans le panneau <*nom du profil*> **Rapports**, choisissez **Gérer** > **Attributions**.
3. Dans le panneau suivant, choisissez **Inclure** (pour inclure des groupes) ou **Exclure** (pour exclure des groupes), puis **Sélectionner des groupes**.
![Inclure et exclure des groupes dans une attribution de profil.](./media/group-include-exclude.png)
4. Dans le panneau **Sélectionner des groupes**, choisissez les groupes Azure Active Directory que vous souhaitez inclure ou exclure dans l’attribution. Vous pouvez maintenir la touche **CTRL** enfoncée pour sélectionner plusieurs groupes.
4. Lorsque vous avez terminé, dans le panneau **Sélectionner des groupes**, choisissez **Sélectionner**.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Comment exclure des groupes d’une attribution de profil d’appareil

Les profils de configuration d’appareil Intune vous permettent d’exclure des groupes de l’attribution de stratégie. Par exemple, vous pouvez attribuer un profil d’appareil au groupe de **tous les utilisateurs de l’entreprise**, mais exclure des membres du groupe des **cadres supérieurs**.

Quand vous excluez des groupes d’une attribution, excluez uniquement les groupes d’utilisateurs ou les groupes d’appareils, mais pas un mélange des deux groupes. Intune ne prend pas en compte l’association entre utilisateurs et appareils lors de l’exclusion de groupes. L’inclusion de groupes d’utilisateurs tout en excluant des groupes d’appareils n’aboutira vraisemblablement pas aux résultats voulus. En cas d’utilisation de groupes mixtes, ou en présence d’autres conflits, l’inclusion est prioritaire sur l’exclusion.

Par exemple, vous souhaitez attribuer un profil d’appareil à tous les appareils de votre organisation, à l’exception des bornes. Vous incluez le groupe **Tous les utilisateurs**, mais excluez le groupe **Tous les appareils**.

Dans ce cas, tous les utilisateurs et leurs appareils obtiennent la stratégie, même si l’appareil de l’utilisateur fait partie du groupe **Tous les appareils**. 

L’exclusion évalue uniquement les membres directs des groupes et n’inclut pas les appareils qui sont associés à un utilisateur. Toutefois, les appareils qui n’ont pas d’utilisateur n’obtiennent pas la stratégie, car ils ne sont pas associés au groupe **Tous les utilisateurs**. 

Si vous incluez **Tous les appareils**, mais excluez **Tous les utilisateurs**, tous les appareils reçoivent la stratégie. Dans ce cas, l’intention est d’exclure les appareils associés à un utilisateur de cette stratégie. Toutefois, rien ne se produit, car la fonctionnalité d’exclusion ne compare que les membres directs des groupes. 

>[!Tip]
>Les exclusions ne sont actuellement pas disponibles pour l’attribution d’applications ni les stratégies de conformité. Pour exclure des membres d’une attribution, vous pouvez utiliser les intentions d’attribution Disponible et Non applicable. Par exemple, vous attribuez une application à **tous les utilisateurs de l’entreprise** avec l’intention **Disponible** et aux **cadres supérieurs** avec l’intention **Non applicable**. L’application est attribuée à tous les utilisateurs *sauf* les utilisateurs du groupe des **cadres supérieurs**. Si vous attribuez l’application à **tous les utilisateurs de l’entreprise** avec l’intention **Obligatoire**, les utilisateurs du groupe des **cadres supérieurs** ne sont pas exclus.
 
    
## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur la surveillance des attributions de profils d’appareils, consultez [Guide pratique pour surveiller des profils d’appareils](device-profile-monitor.md).
