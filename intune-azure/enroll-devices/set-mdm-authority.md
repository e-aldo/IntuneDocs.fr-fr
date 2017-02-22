---
title: "Définir l’autorité de gestion des appareils mobiles | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Appareil : découvrez comment configurer l’autorité de gestion d’appareils mobiles dans Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 3c0de501c172484f036aa2d812f0c40fcfa1d93f

---

# <a name="set-the-mobile-device-management-authority"></a>Définir l’autorité de gestion des appareils mobiles 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Le paramètre d’autorité de gestion des appareils mobiles détermine la façon dont vous gérez vos appareils. Les configurations possibles sont :

- **Intune autonome** : gestion cloud uniquement, que vous configurez à l’aide du portail Azure. Inclut l’ensemble complet de fonctionnalités d’Intune.

- **Intune hybride** : intégration de la solution cloud Intune avec System Center Configuration Manager. Vous pouvez configurer Intune en utilisant la console Configuration Manager.

- **Gestion des appareils mobiles pour Office 365** : intégration d’Office 365 avec la solution cloud Intune. Vous configurez Intune depuis votre centre d’administration Office 365. Comprend un sous-ensemble des fonctionnalités disponibles avec Intune autonome.

>[!IMPORTANT]
>Une fois que vous définissez l’autorité de gestion des appareils mobiles, vous devez contacter le [Support Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) pour la modifier, par conséquent, faites votre choix avec soin.

**Pour définir l'autorité de gestion des appareils mobiles :**

1. Dans le portail Azure, choisissez **Plus de services**, entrez **Intune** dans la zone de texte, puis choisissez **Autres** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Vue d’ensemble**.

3. Dans le panneau **Démarrer la gestion des appareils**, choisissez **Définir l’autorité MDM sur Intune**. Un message indique que vous avez défini correctement votre autorité de MDM sur Intune.



<!--HONumber=Feb17_HO1-->


