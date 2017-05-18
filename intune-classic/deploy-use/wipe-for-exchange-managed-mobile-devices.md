---
title: "Réinitialiser des appareils mobiles gérés par Exchange | Microsoft Docs"
description: "Microsoft Intune vous permet d’effacer ou de réinitialiser des appareils mobiles gérés à l&quot;aide d&quot;Exchange ActiveSync (EAS) avec Intune Exchange Connector"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 5f8da4e28f3b680d7b5b42c1c54fac4c9c43fbe2
ms.lasthandoff: 12/10/2016


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune vous permet d’effacer ou de réinitialiser des appareils mobiles gérés à l'aide d'Exchange ActiveSync (EAS) avec Intune Exchange Connector. Le tableau suivant décrit les fonctionnalités de réinitialisation disponibles via Exchange ActiveSync :

|Type de réinitialisation|Windows 8.1 et Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|réinitialisation complète|Supprime le compte de messagerie et le courrier mis en cache.|Réinitialiser XFactory.|Rétablir les paramètres d’usine.|
|Réinitialisation sélective/messagerie|Supprime le compte de messagerie.|Non pris en charge.|Non pris en charge.|
|Réinitialisation sélective/stratégies|Les stratégies appliquées sont supprimées, mais les paramètres ne sont pas modifiés.|XPolicy appliqué est supprimé, mais les paramètres ne sont pas modifiés.|Les stratégies appliquées sont supprimées, mais les paramètres sont inchangés.|

