---
title: Voir les profils d’appareil avec Microsoft Intune - Azure | Microsoft Docs
description: Affichez et gérez les informations de profil de configuration d’appareil dans Microsoft Intune et consultez le graphique du nombre d’appareils attribués à un profil afin de savoir quels appareils ont des profils attribués ou déployés.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1c2eb08db58940ed575b3dea011395edd6711fc
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Suivre les profils d’appareil dans Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune inclut certaines fonctionnalités dans le portail Azure pour faciliter le monitoring et la gestion de vos profils de configuration d’appareil. Vous pouvez, par exemple, vérifier l’état d’un profil, consulter les appareils attribués et mettre à jour les propriétés d’un profil.

## <a name="view-existing-profiles"></a>Afficher les profils existants

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Configuration de l’appareil** > **Profils**.

Tous vos profils existants sont répertoriés et incluent des informations comme la plateforme, et si le profil est attribué à des appareils.

## <a name="view-details-on-a-profile"></a>Afficher les détails d’un profil

Une fois le profil d’appareil créé, Intune fournit des graphiques. Ces graphiques affichent l’état d’un profil, à savoir s’il a été attribué correctement à des appareils ou si le profil indique un conflit.

1. Sélectionnez un profil existant. Par exemple, sélectionnez un profil macOS.
2. Sélectionnez l’onglet **Vue d’ensemble**.

    Le graphique montre le nombre d’appareils attribués au profil d’appareil spécifique. Par exemple, si le profil d’appareil de la configuration s’applique aux appareils macOS, le graphique indique le nombre des appareils macOS.

    Il indique également le nombre d’appareils pour d’autres plateformes ayant le même profil d’appareil. Par exemple, il affiche le nombre d’appareils non macOS.

    ![Afficher le nombre d’appareils attribués au profil d’appareil](./media/device-configuration-profile-graphical-chart.png)

3. Sélectionnez le cercle dans le graphique. **État de l’appareil** s’ouvre.

    Les appareils attribués au profil sont répertoriés et il est indiqué si le profil est déployé avec succès. Notez également que seuls les appareils avec la plateforme spécifique sont répertoriés (par exemple, macOS).

    Fermez les informations sur l’état de l’appareil.

4. Dans les propriétés du profil (**Profils** > sélectionnez un profil spécifique), vous pouvez également modifier les propriétés existantes :
  - **Propriétés** : modifiez le nom, ou mettez à jour les paramètres existants.
  - **Affectations** : incluez ou excluez des appareils que la stratégie doit appliquer. Choisissez **Groupes sélectionnés** pour choisir des groupes spécifiques.
  - **État de l’appareil** : les appareils attribués au profil sont répertoriés et il est indiqué si le profil est déployé avec succès. Vous pouvez sélectionner un appareil spécifique pour obtenir davantage d’informations, notamment les applications installées.
  - **État de l’utilisateur** : répertorie les noms d’utilisateur avec des appareils concernés par ce profil, et indique si le profil est déployé avec succès. Vous pouvez sélectionner un utilisateur spécifique pour obtenir davantage d’informations.
  - **État par paramètre** : filtre la sortie en affichant les paramètres individuels au sein du profil, et indique si le paramètre est correctement appliqué.

## <a name="next-steps"></a>Étapes suivantes
[Attribuer des profils d’utilisateur et d’appareil](device-profile-assign.md)  
[Problèmes courants avec les profils d’appareil et résolutions](device-profile-troubleshoot.md)