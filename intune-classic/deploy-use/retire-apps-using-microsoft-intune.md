---
title: Mettre hors service des applications
description: "Découvrez comment supprimer ou désinstaller des applications à l’aide d’Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 15e90a2fea2ec3b4f020a0e14c40da2cb65aecab
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
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
