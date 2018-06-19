---
title: Wipe for Exchange-managed mobile devices
description: Microsoft Intune vous permet d’effacer ou de réinitialiser des appareils mobiles gérés à l'aide d'Exchange ActiveSync (EAS) avec Intune Exchange Connector
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31016082"
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune vous permet d’effacer ou de réinitialiser des appareils mobiles gérés à l'aide d'Exchange ActiveSync (EAS) avec Intune Exchange Connector. Le tableau suivant décrit les fonctionnalités de réinitialisation disponibles via Exchange ActiveSync :


|      Type de réinitialisation       |              Windows 8.1 et Windows RT 8.1              |                            iOS                             |                          Android                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        réinitialisation complète        |          Supprime le compte de messagerie et le courrier mis en cache.           |                      Réinitialiser XFactory.                       |                      Rétablir les paramètres d’usine.                       |
|  Réinitialisation sélective/messagerie   |                  Supprime le compte de messagerie.                  |                       Non pris en charge.                       |                      Non pris en charge.                       |
| Réinitialisation sélective/stratégies | Les stratégies appliquées sont supprimées, mais les paramètres ne sont pas modifiés. | XPolicy appliqué est supprimé, mais les paramètres ne sont pas modifiés. | Les stratégies appliquées sont supprimées, mais les paramètres sont inchangés. |

