---
title: Résoudre les problèmes d’installation d’applications
titlesuffix: Microsoft Intune
description: Utilisez le volet de résolution des problèmes de Microsoft Intune pour vous aider à résoudre les problèmes d’installation d’applications.
keywords: ''
author: ErikRe
ms.author: erikre
manager: dougeby
ms.date: 07/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: b613f364-0150-401f-b9b8-2b09470b34f4
ms.reviewer: mghadial
ms.custom: intune-azure
ms.openlocfilehash: c1c2a37103f8fedc09a70b4387aae3f472dfb636
ms.sourcegitcommit: dc8b6f802cca7895a19ec38bec283d4b3150d213
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39138677"
---
# <a name="troubleshoot-app-installation-issues"></a>Résoudre les problèmes d’installation d’applications

Sur les appareils gérés par MDM Microsoft Intune, les installations d’applications peuvent parfois échouer. Quand ces installations d’applications échouent, il peut être difficile de comprendre la raison de l’échec ou de résoudre le problème. Microsoft Intune fournit des détails sur l’échec de l’installation d’applications qui permettent aux opérateurs du support technique et aux administrateurs Intune d’afficher des informations sur l’application pour répondre aux demandes d’assistance des utilisateurs. Le volet de résolution des problèmes dans Intune fournit des détails sur l’échec, notamment des détails sur les applications managées sur l’appareil d’un utilisateur. Des informations détaillées sur le cycle de vie de bout en bout d’une application sont fournies sous chaque appareil individuel dans le volet **Applications managées**. Vous pouvez afficher les problèmes d’installation, par exemple quand l’application a été créée, modifiée, ciblée et remise à un appareil. 

## <a name="to-review-app-troubleshooting-details"></a>Pour examiner les informations de résolution des problèmes d’une application

Intune fournit des informations de résolution des problèmes d’une application en fonction des applications installées sur l’appareil d’un utilisateur spécifique.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le volet **Intune**, choisissez **Dépanner**.
4. Cliquez sur **Sélectionner un utilisateur** pour sélectionner un utilisateur à aider. Le volet **Sélectionner les utilisateurs** s’affiche.
5. Sélectionnez un utilisateur en tapant son nom ou son adresse e-mail. Cliquez sur **Sélectionner** en bas du volet. Les informations sur la résolution des problèmes pour l’utilisateur s’affichent dans le volet **Résoudre les problèmes**. 
6. Sélectionnez dans la liste **Appareils** l’appareil sur lequel exécuter la résolution des problèmes.
    ![Volet de résolution des problèmes de Microsoft Intune.](media/troubleshoot-app-install-01.png)
7. Sélectionnez **Applications managées** dans le volet de l’appareil sélectionné. Une liste des applications managées s’affiche.
    ![Détails d’un appareil spécifique managé par Intune.](media/troubleshoot-app-install-02.png)
8. Sélectionnez une application dans la liste où **l’état d’installation** indique un échec.
    ![Une application sélectionnée qui affiche les détails d’un échec d’installation.](media/troubleshoot-app-install-03.png)

    > [!Note]  
    > La même application peut être attribuée à plusieurs groupes, mais avec différentes actions prévues (intentions) pour l’application. Par exemple, une intention résolue pour une application affichera **exclue** si l’application est exclue pour un utilisateur lors de l’attribution de l’application. Pour plus d’informations, consultez [Résolution des conflits entre les intentions d’application](apps-deploy.md#how-conflicts-between-app-intents-are-resolved).<br><br>
    > Actuellement, Intune ne filtre pas les applications en fonction de la plateforme du système d’exploitation.

Les détails de l’erreur d’installation de l’application indiquent le problème. Vous pouvez utiliser ces informations pour déterminer la meilleure action à prendre pour résoudre le problème. Pour plus d’informations sur la résolution des problèmes d’installation d’une application, consultez [Codes d’erreur pour la résolution des problèmes d’installation d’une application](https://blogs.technet.microsoft.com/intunesupport/2018/05/15/error-codes-for-troubleshooting-app-installation-issues).

> [!Note]  
> Vous pouvez également accéder au volet **Dépannage** en pointant votre navigateur sur [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="next-steps"></a>Étapes suivantes

- Pour plus d’informations de résolution des problèmes Intune, consultez [Utiliser le portail de résolution des problèmes pour aider les utilisateurs dans votre entreprise](help-desk-operators.md). 
- Découvrez plus d’informations sur les problèmes connus de Microsoft Intune. Pour plus d’informations, consultez [Problèmes connus dans Microsoft Intune](known-issues.md).
- Besoin d’aide supplémentaire ? Consultez [Guide pratique pour obtenir un support technique pour Microsoft Intune](get-support.md).
