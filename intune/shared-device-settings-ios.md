---
title: "Paramètres de configuration des appareils Intune partagés pour iOS"
titlesuffix: Azure portal
description: "Découvrez les paramètres Intune que vous pouvez utiliser pour afficher des informations sur l’écran de verrouillage des appareils iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c5473a280551ab74f781a2de682d7e5922491e98
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Paramètres de configuration des appareils partagés permettant d’afficher des messages sur l’écran de verrouillage d’un appareil iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les paramètres de configuration des appareils partagés vous permettent de spécifier le texte facultatif affiché sur la fenêtre de connexion et l’écran de verrouillage, par exemple un message de type « Si perdu, renvoyez à » et des informations d’étiquette d’inventaire. 

>[!IMPORTANT]
> Cette fonctionnalité est prise en charge sur les appareils supervisés exécutant iOS 9.3 et ultérieur.

## <a name="create-shared-device-settings"></a>Créer des paramètres d’appareils partagés

1. Dans le panneau **Fonctionnalités de l’appareil**, sélectionnez **Configuration des appareils partagés (mode supervisé uniquement)**.
2. Dans le panneau **Configuration des appareils partagés (mode supervisé uniquement)**, configurez les paramètres suivants :
    - **Informations de l’étiquette d’inventaire** : entrez des informations sur l’étiquette d’inventaire de l’appareil. Par exemple : **Appartient à Contoso Corp**. Les informations que vous entrez sont appliquées à tous les appareils auxquels vous affectez ce profil.
    - **Note de l’écran de verrouillage** : entrez une note qui pourrait vous aider à récupérer l’appareil en cas de perte ou de vol. Par exemple : **Si vous trouvez cet appareil, appelez le « numéro »**.
3. Lorsque vous avez terminé, cliquez sur **OK** jusqu’à ce que vous reveniez au panneau **Créer un profil**, puis cliquez sur **Créer**. 


## <a name="next-steps"></a>Étapes suivantes

Vous pouvez maintenant affecter le profil d’appareil aux groupes que vous choisissez. Pour plus d’informations, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).
