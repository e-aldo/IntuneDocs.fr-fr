---
title: "Envoyer des journaux à un administrateur informatique pour les appareils Windows 10 | Microsoft Docs"
description: "Inscrire un appareil Windows 10 1511 dans Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 038747fb-5b52-47c4-a2b6-f9218da4cfe1
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: be9976f03bf749222ca372040d4d936e6a8fd26b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="send-logs-to-your-it-admin-from-the-settings-app-for-windows-10"></a>Envoyer les journaux à un administrateur informatique à partir de l’application Paramètres pour Windows 10

Si vous obtenez une erreur pendant que vous utilisez l’appareil Windows 10 géré par votre entreprise, vous pouvez aider votre administrateur informatique à résoudre le problème en lui envoyant les informations par e-mail. Ces informations sont conservées sur votre appareil dans un document spécifique appelé _journal de diagnostic_.

1.  Pour ouvrir l’application **Paramètres** Windows, accédez au menu **Démarrer**, puis sélectionnez le bouton **Paramètres**. Vous pouvez également rechercher « paramètres » dans la barre de recherche.
2.  Accédez à **Comptes** > **Accès scolaire ou professionnel**.
3.  Sélectionnez « Exporter vos fichiers journaux de gestion ».

  ![Écran « Accès scolaire ou professionnel », qui montre l’option d’exportation sous le titre « Paramètres associés ».](./media/w10-export-logs.png)

4. Les journaux seront enregistrés sous **C:\Users\Public\Public Documents\MDMDiagnostics**. Deux fichiers seront créés : l’un est le journal proprement dit, et l’autre est un document spécial qui permet à votre administrateur de passer en revue les journaux dans différents programmes, par exemple Microsoft Excel. Joignez ces deux fichiers à un e-mail et envoyez cet e-mail à votre administrateur. Si vous effectuez cette opération plusieurs fois, choisissez simplement les fichiers créés le même jour que les journaux. 

Vous devrez peut-être envoyer également des [journaux à partir de l’application Portai d’entreprise](send-logs-to-your-it-admin-cp-windows.md) pour faciliter davantage la tâche à votre administrateur informatique, qui doit résoudre tous les problèmes éventuels. 

Encore besoin d’aide ? Contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).
