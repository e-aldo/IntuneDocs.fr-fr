---
# required metadata

title: Mettre hors service des applications | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Mettre hors service des applications à l’aide de Microsoft Intune

Pour mettre une application hors service, il vous suffit de la désinstaller. Quand vous déployez et gérez des applications avec Intune, le processus de désinstallation d’application est identique pour les PC Windows et les appareils mobiles. Pour que cette procédure réussisse, l'application doit prendre en charge la désinstallation.

## Désinstaller une application

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), sélectionnez **Applications** &gt; **Applications**.

2.  Sélectionnez l’application que vous souhaitez désinstaller (que vous avez déployée auparavant), puis sélectionnez **Gérer le déploiement**.

3.  Dans la page **Action de déploiement** , sélectionnez **Désinstaller** dans la colonne **Approbation** .

L'application sera désinstallée la prochaine fois que l'appareil ou l'ordinateur vérifiera les applications.

### Voir aussi
[Ajouter des applications dans Microsoft Intune](add-apps.md)


<!--HONumber=May16_HO1-->


