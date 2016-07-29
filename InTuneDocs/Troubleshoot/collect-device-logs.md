---
title: Collecter les journaux des appareils | Microsoft Intune
description: 
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9915b275101e287498217c4f35e1c0e56d2425c2
ms.openlocfilehash: 46579569c33b50f4b19a62d83c1db5e0e304621b


---

# Journaux des appareils

Dans le cadre de vos efforts de dépannage, vous pouvez collecter les journaux des appareils utilisateur. Les instructions permettant de collecter ces journaux sont décrites ici. En règle générale, vous devrez peut-être accéder à l’appareil ou demander à l’utilisateur qu’il collecte les journaux et vous les envoie.

### Emplacement des journaux Android
Les journaux Android se trouvent dans *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. L’utilisateur peut également vous envoyer les fichiers journaux par e-mail, comme décrit dans [Send Android diagnostic data logs to your IT administrator using email](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) (Envoyer les journaux de données de diagnostic Android à votre administrateur informatique par e-mail).

### Journaux iOS

L’utilisateur peut vous envoyer les erreurs d’inscription comme décrit dans [Send iOS enrollment errors to your IT administrator](/intune/enduser/send-errors-to-your-it-admin-ios) (Envoyer les erreurs d’inscription iOS à votre administrateur informatique).

### Appareils Mac OS X

1. Ouvrez l’application **Console**.
2. Sous **FICHIERS**, choisissez **system.log**.
3. Dans la barre de menus en haut, choisissez **Fichier** > **Enregistrer une copie sous…** et enregistrez le fichier.

### Windows Phone

Sur le **portail d’entreprise Windows Phone**, l’utilisateur devra choisir **...** pour accéder au menu, puis choisir **Envoyer les journaux**. Cette option est disponible avant et après la connexion au portail.

### Windows

Pour le portail d’entreprise Windows, les journaux sont situés dans *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Jul16_HO4-->


