---
title: "Définir l’autorité de gestion des appareils mobiles"
titleSuffix: Intune on Azure
description: "Découvrez comment définir l’autorité de gestion des appareils mobiles dans Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 97dede1ac393a434342f62d1f8488389dcb28d44
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="set-the-mobile-device-management-authority"></a>Définir l’autorité de gestion des appareils mobiles

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Le paramètre d’autorité de gestion des appareils mobiles (MDM) détermine la façon dont vous gérez vos appareils. En tant qu’administrateur informatique, vous devez définir une autorité de gestion des appareils mobiles (MDM) avant que les utilisateurs puissent inscrire des appareils pour la gestion.

Les configurations possibles sont les suivantes :

- **Intune autonome** : gestion cloud uniquement, que vous configurez à l’aide du portail Azure. Inclut l’ensemble complet de fonctionnalités d’Intune. [Configurez l’autorité MDM dans la console Intune](#set-mdm-authority-to-intune).

- **Intune hybride** : intégration de la solution cloud Intune à System Center Configuration Manager. Vous configurez Intune à l’aide de la console Configuration Manager. [Configurez l’autorité MDM dans Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).

- **Gestion des appareils mobiles pour Office 365** : intégration d’Office 365 à la solution cloud Intune. Vous configurez Intune à partir de votre Centre d’administration Office 365. Comprend un sous-ensemble des fonctionnalités disponibles avec Intune autonome. Configurez l’autorité MDM dans le Centre d'administration Office 365.

>[!IMPORTANT]    
Dans Configuration Manager 1610 ou version ultérieure et Microsoft Intune version 1705, vous modifiez l’autorité de gestion des appareils mobiles sans avoir à contacter le Support Microsoft et sans avoir à annuler l’inscription et à réinscrire vos appareils gérés existants. Pour plus de détails, consultez [Que faire si vous choisissez le paramètre d’autorité MDM incorrect](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).

## <a name="set-mdm-authority-to-intune"></a>Définir l'autorité MDM sur Intune

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.
  ![Capture d’écran de la charge de travail Dépannage d’Intune avec le lien Sélectionner utilisateur](media/set-mdm-auth.png)
2. Dans le panneau Intune, choisissez **Inscription de l’appareil**, puis choisissez **Vue d’ensemble**.

3. Dans le panneau **Démarrer la gestion des appareils**, choisissez **Définir l’autorité MDM sur Intune**. Un message indique que vous avez défini Intune comme autorité de gestion des appareils mobiles.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Nettoyage de l’appareil mobile après expiration du certificat MDM

Le certificat MDM est renouvelé automatiquement lorsque les appareils mobiles communiquent avec le service Intune. Si des appareils mobiles sont réinitialisés ou ne parviennent pas à communiquer avec le service Intune pendant un certain temps, le certificat MDM n’est pas renouvelé. L’appareil est supprimé du portail Azure 180 jours après l’expiration du certificat MDM.
