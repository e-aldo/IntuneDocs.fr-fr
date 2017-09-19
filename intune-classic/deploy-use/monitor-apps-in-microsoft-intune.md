---
title: "Déploiements d’applications de surveillance"
description: "Découvrez comment surveiller les applications déployées avec Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c93ff280e57bcfc1970d9c3f7b56b1c8fc4746a5
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="monitor-app-deployments-in-microsoft-intune"></a>Surveillance de déploiements d’applications dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="monitor-an-app-deployment"></a>Surveillance d’un déploiement d’application
Vous pouvez voir les applications que vous gérez et l’état de tous les déploiements dans la console d’administration Intune. <!---App status is displayed in real-time. You don't have to wait for the device to check-in before you can see this.--->

### <a name="to-view-apps-that-you-manage-and-their-status"></a>Pour afficher les applications que vous gérez ainsi que leur statut
Dans l’espace de travail **Applications** , choisissez le nœud **Applications**, puis choisissez **Applications**.

La liste des applications que vous gérez apparaît. Vous pouvez choisir n’importe quelle application pour afficher l’état de l’installation dans le volet inférieur de la fenêtre de console. Choisissez cet état pour afficher plus de détails. Par exemple, si l’état indique **1 utilisateur dispose de ce logiciel**, vous pouvez cliquer sur le message afin d’afficher le nom de l’utilisateur.

> [!TIP]
> Vous pouvez utiliser la liste déroulante **Filtres** pour afficher uniquement les applications qui répondent aux critères que vous spécifiez, telles que les applications dont l’installation a échoué ou les applications qui ont été déployées avec succès.
>
> ![Exemple de filtres d’application](./media/app-filters.png)

En outre, l’espace de travail **Tableau de bord** présente une vue d’ensemble de l’état de vos applications. Si vous cliquez n'importe où dans la vue d'ensemble, vous serez dirigé vers la liste des applications.

## <a name="to-view-more-detailed-information-about-an-app"></a>Pour afficher plus d'informations détaillées sur une application
Dans la liste des applications, choisissez n’importe quelle application, puis cliquez sur **Afficher les propriétés**.

Dans la page **Propriétés du logiciel** de l’application, choisissez l’un des onglets suivants : **Général** - affiche des informations générales sur l’application et l’état de son installation, **Appareils** - affiche les appareils ayant installé avec succès un déploiement ciblé de l’application, **Utilisateurs** - affiche les utilisateurs dont les appareils ont correctement installé un déploiement ciblé de l’application.

Comme auparavant, vous pouvez utiliser la liste déroulante **Filtres** pour configurer les valeurs affichées sous les onglets.
