---
title: "Paramètres de configuration des appareils Intune partagés pour iOS"
titleSuffix: Intune Azure preview
description: "Intune Azure en version préliminaire : découvrez les paramètres Intune que vous pouvez utiliser pour afficher des informations sur l’écran de verrouillage des appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 4/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: 2bc107054f438d5ed72de87dec85900f871c0acc
ms.lasthandoff: 04/19/2017


---

# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Paramètres de configuration des appareils partagés permettant d’afficher des messages sur l’écran de verrouillage d’un appareil iOS

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Les paramètres de configuration des appareils partagés vous permettent de spécifier le texte facultatif affiché sur la fenêtre de connexion et l’écran de verrouillage (par exemple un message de type « Si perdu, renvoyez à » et des informations d’étiquette d’inventaire). 

>[!IMPORTANT]
> Cette fonctionnalité est prise en charge sur les périphériques supervisés exécutant iOS 9.3 et versions ultérieures.

1. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **Configuration des appareils partagés (mode supervisé uniquement)**.
2. Sur le panneau **Configuration des appareils partagés (mode supervisé uniquement**, configurez les éléments suivants :
    - **Informations de l’étiquette d’inventaire** : entrez des informations sur l’étiquette d’inventaire de l’appareil. Par exemple : **Appartient à Contoso Corp**. Les informations que vous entrez seront appliquées à tous les appareils que vous affectez à ce profil.
    - **Note de l’écran de verrouillage** : entrez une note qui pourrait vous aider à récupérer l’appareil en cas de perte ou de vol. Par exemple : **Si vous le trouvez, appelez le « numéro »**.
3. Lorsque vous avez terminé, cliquez sur **OK** jusqu’à ce que vous reveniez au panneau **Créer un profil**, puis cliquez sur **Créer**. 

