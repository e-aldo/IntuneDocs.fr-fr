---
title: Réinitialiser des appareils Windows 10 avec Microsoft Intune - Azure | Microsoft Docs
description: Utilisez Redémarrage à zéro pour supprimer ou désinstaller des applications sur des PC Windows 10 à l’aide de Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5658bf2e1ee250ef9fd405b3f7ec1772b166f338
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020994"
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Utiliser Fresh Start pour réinitialiser les appareils Windows 10 avec Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

L’action de l’appareil **Redémarrage à zéro** supprime toutes les applications installées sur un PC Windows 10 exécutant Creators Update. Elle met alors automatiquement à jour le PC vers la dernière version de Windows.

Cette action permet de supprimer les applications préinstallées (OEM) qui sont généralement installées avec un nouveau PC. Pour conserver le contenu du dossier de base de l’utilisateur et supprimer uniquement les applications et les paramètres, utilisez le paramètre `if user data is retained`.

> [!IMPORTANT]
> Le Redémarrage à zéro désinscrit l’appareil d’Intune, mais l’appareil est toujours joint dans Azure Active Directory.

## <a name="use-fresh-start"></a>Utiliser le Redémarrage à zéro

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils**, puis **Tous les appareils**.
4. Dans la liste des appareils que vous gérez, choisissez un appareil de bureau Windows 10, puis sélectionnez **Redémarrage à zéro**.

## <a name="next-steps"></a>Étapes suivantes

Pour consulter l’état de cette action, sélectionnez**Actions de l’appareil** (**Microsoft Intune** > **Appareils**).