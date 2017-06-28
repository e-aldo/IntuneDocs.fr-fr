---
title: Mettre hors service des applications
description: "Découvrez comment supprimer ou désinstaller des applications à l’aide d’Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 1851fa03d36ffe42a49fd557cdd0c2c6250726f4
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017


---

# <a name="retire-apps-using-microsoft-intune"></a>Mettre hors service des applications à l’aide de Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour mettre une application hors service, il vous suffit de la désinstaller. Quand vous déployez et gérez des applications avec Intune, le processus de désinstallation d’application est identique pour les PC Windows et les appareils mobiles. Pour que cette procédure réussisse, l’application doit prendre en charge le processus de désinstallation.

## <a name="uninstall-an-app"></a>Désinstaller une application

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Applications** &gt; **Applications**.

2.  Sélectionnez l’application à désinstaller (une application ayant été déployée précédemment), puis choisissez **Gérer le déploiement**.

3.  Dans la page **Action de déploiement** , sélectionnez **Désinstaller** dans la colonne **Approbation** .

L'application sera désinstallée la prochaine fois que l'appareil ou l'ordinateur vérifiera les applications.

### <a name="see-also"></a>Voir aussi
[Ajouter des applications dans Microsoft Intune](add-apps.md)

