---
title: "Stratégies de configuration d’applications pour Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Découvrez comment utiliser des stratégies de configuration des applications pour Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 406d0faa1e03a41d20c1b584d2d37f9810ddbf32
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/09/2017
---
# <a name="app-configuration-policies-for-intune"></a>Stratégies de configuration d’applications pour Intune

Fournissez des paramètres quand les utilisateurs exécutent une application iOS ou Android avec des stratégies de configuration d’applications dans Microsoft Intune. Par exemple, une application peut exiger que les utilisateurs spécifient les paramètres suivants :

- Un numéro de port personnalisé.
- Des paramètres de langue.
- Des paramètres de sécurité.
- Des paramètres de personnalisation comme le logo de l’entreprise.

Si les utilisateurs n’entrent pas correctement ces paramètres, cela peut occasionner plus de travail à votre assistance technique et ralentir l’adoption des nouvelles applications.

Les stratégies de configuration des applications peuvent vous aider à éliminer ces problèmes en vous permettant d’affecter ces paramètres dans une stratégie avant que les utilisateurs exécutent l’application. Les paramètres sont alors fournis automatiquement, les utilisateurs n’ont aucune action à effectuer.

Vous n’affectez pas ces stratégies directement sur les appareils et utilisateurs. Vous associez plutôt une stratégie à une application que vous affectez ensuite. Les paramètres de stratégie sont utilisés chaque fois que l’application les vérifie (en général, lors de sa première exécution).

Vous disposez de deux options pour indiquer la façon dont vous souhaitez utiliser des configurations d’applications avec Intune :
 - **Appareils gérés**  
   L’appareil est géré par Intune en tant que fournisseur de gestion des appareils mobiles (MDM).
 - **Applications gérées**  
   Une application est gérée sans inscription de l’appareil.

## <a name="apps-that-support-app-configuration"></a>Applications qui prennent en charge la configuration d’application

Vous pouvez utiliser des stratégies de configuration d’applications pour les applications qui les prennent en charge. Pour que la configuration d’application soit prise en charge dans Intune, les applications doivent avoir été écrites afin de prendre en charge l’utilisation des configurations d’applications. Pour plus de détails, consultez l’éditeur de l’application.

Vous pouvez préparer votre application métier en incorporant le SDK d’application Intune dans l’application ou en enveloppant (wrap) l’application une fois qu’elle a été développée. Le kit SDK d’application Intune, disponible pour iOS et Android, permet d’appliquer des stratégies de protection des applications Intune sur votre application. Il s’efforce de minimiser la quantité de modifications du code pour les développeurs d’applications. Pour plus d’informations, consultez [Vue d’ensemble du SDK d’application Intune](app-sdk.md).

## <a name="graph-api-support-for-app-configuration"></a>Prise en charge de l’API Graph pour la configuration d’application

En outre, vous pouvez utiliser l’API Graph pour accomplir des tâches de configuration d’application. Pour plus d’informations, consultez [Configuration ciblée de gestion des applications mobiles de référence pour API Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).

## <a name="next-steps"></a>Étapes suivantes

### <a name="managed-devices"></a>Appareils gérés

 - Découvrez comment utiliser la configuration d’application avec vos appareils iOS.  Consultez [Ajouter des stratégies de configuration d’applications pour les appareils iOS gérés](app-configuration-policies-use-ios.md).
 - Découvrez comment utiliser la configuration d’application avec vos appareils Android.  Consultez [Ajouter des stratégies de configuration d’applications pour les appareils Android gérés](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Applications gérées

 - Découvrez comment utiliser la configuration d’application avec des applications gérées. Consultez [Ajouter des stratégies de configuration pour les applications gérées sans inscription d’appareil](app-configuration-policies-managed-app.md).