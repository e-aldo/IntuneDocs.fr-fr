---
title: Collecter les journaux des appareils | Microsoft Intune
description: "Découvrez comment collecter des journaux à partir de vos appareils gérés."
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0c05b4e16f7b0a87215a0cd20f7d559cd8497296
ms.openlocfilehash: 0f175b1eb2d80a68c8b7864d21f5a9e585de458b


---

# <a name="device-logs"></a>Journaux des appareils

Dans le cadre de vos efforts de dépannage, vous pouvez collecter les journaux des appareils utilisateur. Les instructions permettant de collecter ces journaux sont décrites ici. En règle générale, vous devez accéder à l’appareil pour obtenir ces journaux ou demander à l’utilisateur de les collecter et de vous les envoyer.

### <a name="android-logs"></a>Journaux Android
Les journaux Android se trouvent dans *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.

Parfois, les fichiers n’apparaissent pas, surtout sur les appareils Android plus récents. Dans ce cas, demandez à vos utilisateurs d’ouvrir l’application Portail d’entreprise pour Android. Ils doivent ensuite sélectionner **Paramètres**>**Copier les journaux** et redémarrer leur appareil.

Pour plus d’informations sur la façon dont les utilisateurs peuvent vous envoyer des journaux de données, consultez les articles suivants :

- [Utiliser la journalisation détaillée pour aider votre administrateur informatique à résoudre les problèmes liés aux appareils](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android) : décrit comment les utilisateurs peuvent activer la journalisation détaillée pour vous envoyer automatiquement tous les journaux de données. La journalisation détaillée est activée par défaut.

- [Envoyer des journaux de données de diagnostic Android à votre administrateur informatique par e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)

- [Envoyer les journaux de données de diagnostic à votre administrateur informatique par câble USB](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>Journaux iOS

Les utilisateurs peuvent vous envoyer les erreurs d’inscription, comme décrit dans [Envoyer les erreurs d’inscription iOS à votre administrateur informatique](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Journaux Mac OS X

1. Ouvrez l’application **Console**.
2. Sous **FICHIERS**, choisissez **system.log**.
3. Dans la barre de menus en haut, choisissez **Fichier** > **Enregistrer une copie sous…**. Ensuite, enregistrez le fichier.

### <a name="windows-phone"></a>Windows Phone

Dans l’application Portail d’entreprise Windows Phone, les utilisateurs choisissent les trois points (**...**) pour accéder au menu, puis **Envoyer les journaux**. Cette option est disponible avant et après la connexion à l’application Portail d’entreprise.

### <a name="windows"></a>Windows

Pour le portail d’entreprise Windows, les journaux sont situés dans *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Nov16_HO5-->


