---
# required metadata

title: Réinitialiser des appareils mobiles gérés par Exchange | Microsoft Intune
description:
keywords:
author: nathbarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Wipe for Exchange-managed mobile devices
Microsoft Intune vous permet d’effacer ou de réinitialiser des appareils mobiles gérés à l'aide d'Exchange ActiveSync (EAS) avec Intune Exchange Connector. Le tableau suivant décrit les fonctionnalités de mise hors service/réinitialisation disponibles via Exchange ActiveSync :

|Type de réinitialisation|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Réinitialisation complète|Supprime le compte de messagerie et le courrier mis en cache|Supprime le compte de messagerie et le courrier mis en cache|Rétablir les paramètres d'usine|Rétablir les paramètres d'usine|Rétablir les paramètres d'usine|
|Réinitialisation sélective/Messagerie|Supprime le compte de messagerie.|Supprime le compte de messagerie.|Non pris en charge|Non pris en charge|Non pris en charge|
|Réinitialisation sélective/Stratégies|Les stratégies appliquées sont supprimées, mais les paramètres ne sont pas modifiés.|Les stratégies appliquées sont supprimées, mais les paramètres ne sont pas modifiés.|Les stratégies appliquées sont supprimées, mais les paramètres ne sont pas modifiés.|Les stratégies appliquées sont supprimées, mais les paramètres sont inchangés.|Les stratégies appliquées sont supprimées, mais les paramètres ne sont pas modifiés.|


<!--HONumber=May16_HO1-->


