---
title: "Guide pratique pour surveiller la conformité des appareils"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez comment surveiller la conformité des appareils."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b6c245d60c661c04b4c4d29c9bdcdd752254d978
ms.openlocfilehash: 6932e75fd002661245baa7754824ec6cfe500a22
ms.lasthandoff: 03/15/2017


---
# <a name="how-to-monitor-device-compliance-in-intune-azure-preview"></a>Surveiller la conformité des appareils dans Intune Azure en préversion

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vous pouvez afficher le résumé de l’état de vos **profils de conformité** dans le panneau **Vue d'ensemble**.
Vous pouvez cliquer de manière interactive sur les graphiques pour explorer les détails. Si vous avez configuré plusieurs profils de conformité, vous pouvez également afficher l’état de chaque stratégie en accédant à son volet et en choisissant **Rapports** dans la section **Gérer**.  Vous trouverez ci-dessous les détails des rapports disponibles dans la préversion.

##  <a name="device-compliance"></a>Conformité de l’appareil

La vue résumée du rapport de conformité de l'appareil commence par afficher les informations agrégées sur le nombre d'appareils qui communiquent avec l'un des états suivants :

- **Conforme**: l'appareil a été évalué comme conforme avec les paramètres de profil de conformité spécifiés.
- **Non conforme**: l’appareil a été évalué comme non conforme.  Si une période de grâce a été définie dans le profil, elle a expiré et l'appareil passe dans un état non conforme.
- **Période de grâce**: l’appareil a été évalué comme non conforme. Toutefois, la période de grâce s’applique toujours avant que l'appareil ne soit vraiment marqué comme non conforme.

Vous pouvez rechercher dans chaque section pour afficher plus de détails sur les appareils et utilisateurs individuels.

## <a name="setting-compliance"></a>Configuration de la conformité

Le rapport de conformité de configuration fournit des détails pour chaque paramètre de conformité, notamment les éléments suivants :

- Le nombre d'appareils non compatibles avec le paramètre.
- La plateforme à laquelle le paramètre est appliqué.

Vous pouvez rechercher dans chaque paramètre pour afficher plus d’informations sur les profils dans lesquels ces paramètres ont été activés, ainsi que la valeur du paramètre configurée.

