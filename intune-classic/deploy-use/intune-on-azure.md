---
title: Considérations relatives à la gestion d’appareils Windows avec Intune dans Azure
description: Considérations relatives à l’utilisation d’Intune dans Azure pour gérer les appareils Windows de votre organisation.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 71effb587bfb82ecae18afda67b05fffd2127052
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a>Intune dans la console Azure et PC client Intune hérité

Intune a récemment migré vers une architecture de services d’application SaaS basée sur Azure. Azure inclut des améliorations significatives en termes de mise à l’échelle, de capacité et de performances. Cette transition offre également une expérience améliorée d’administration Intune et un workflow optimisé dans le portail Azure. 

Lors de l’utilisation d’Intune dans Azure pour gérer les appareils Windows de votre organisation, tenez compte des points suivants :

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Les fonctionnalités du PC client hérité sont uniquement disponibles dans la console Silverlight

Les workflows de gestion du PC client Intune utilisent la [Console d’administration Intune basée sur Silverlight](https://manage.microsoft.com/), ce qui implique les exigences suivantes :

- Pour toutes les tâches de gestion non groupées à l’aide du PC client Intune, vous devez utiliser la console Silverlight.
- Lors de la gestion de groupes, vous devez utiliser [Intune dans le portail Azure](https://portal.azure.com/). Cette exigence s’explique par le fait qu’Intune utilise désormais les groupes Azure AD au lieu des groupes Intune hérités. 

Suite à ce passage aux groupes Azure AD, le filtrage « basé sur les groupes » dans les affichages du tableau de bord de la console Silverlight a légèrement changé. Pour effectuer un filtrage dans l’interface utilisateur de Silverlight mise à jour, procédez comme suit :

1. Sélectionnez un affichage.
2. Dans la zone **Filtres**, entrez le nom du groupe à filtrer et appuyez sur la touche Entrée. La liste ainsi filtrée affichera uniquement les appareils appartenant à ce groupe.

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a>Gérer les appareils Windows 10 via GPM

Nous vous recommandons d’utiliser la [gestion des périphériques mobiles (GPM) pour gérer vos appareils Windows 10](https://docs.microsoft.com/intune/device-restrictions-windows-10) au lieu d’utiliser le PC client Intune hérité. La capacité à gérer Windows 10 via GPM est disponible dans Intune sur le portail Azure. La GPM sous Windows 10 fournit un grand nombre de nouvelles fonctions de gestion et de sécurité qui ne sont pas disponibles via le PC client Intune hérité.

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a>Continuer à gérer Windows 7 via le PC client Intune

Pour Windows 7, qui ne peut pas être géré via GPM, nous continuerons à prendre en charge les fonctions du PC client Intune existantes uniquement dans la console de Silverlight. Nous vous conseillons d’envisager de passer à la gestion GPM lors de votre mise à niveau vers Windows 10.

## <a name="mdm-capabilities"></a>Fonctions GPM

Pour obtenir une comparaison détaillée entre les fonctions du PC client et les fonctions GPM, consultez [Comparer la gestion des PC Windows en tant qu’ordinateurs ou appareils mobiles](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison). Les mises à jour GPM continueront à introduire de nouvelles fonctions de gestion pour les appareils Windows 10 inscrits auprès de la GPM, notamment des options d’évaluation pour les applications Win 32. Consultez [Nouveautés](https://docs.microsoft.com/intune/whats-new) pour connaître les derniers ajouts de version à ce service.

## <a name="switch-from-pc-client-to-mdm"></a>Passer du PC client à la GPM

Pour passer de la gestion des appareils Windows 10 via le PC client Intune à la gestion via GPM, procédez comme suit :

1. Dans la console de Silverlight, effectuez une **réinitialisation sélective** pour désinscrire l’appareil du PC client.
  ![](media/intune_on_azure/image02.png)
2. Réinscrivez l’appareil à l’aide de la [GPM (et/ou Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll). 

## <a name="next-steps"></a>Étapes suivantes
[Inscrire des appareils Windows](https://docs.microsoft.com/intune/windows-enroll)

 
