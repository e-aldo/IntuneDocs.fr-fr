---
title: "Ajouter des paramètres personnalisés pour les appareils Android dans Microsoft Intunes - Azure | Microsoft Docs"
description: "Ajouter ou créer un profil personnalisé pour les appareils Android afin de créer un profil Wi-Fi avec une clé prépartagée, créer un profil VPN par application ou autoriser/bloquer des applications pour les appareils Samsung Knox Standard dans Microsoft Intune"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa105cc96cd0fa7d8c6beb32cdb80b7782d9828c
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2018
---
# <a name="custom-settings-for-android-devices---intune"></a>Paramètres personnalisés pour les appareils Android - Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les profils personnalisés utilisent des paramètres OMA-URI (Open Mobile Alliance Uniform Resource Identifier) pour configurer différentes fonctionnalités sur les appareils Android. Ces paramètres sont généralement utilisés par les fabricants d’appareils mobiles pour contrôler les fonctionnalités sur l’appareil.

Avec un profil personnalisé, vous pouvez configurer et attribuer les paramètres Android suivants. Ces paramètres ne sont pas intégrés aux stratégies Intune :

- [Créer un profil Wi-Fi avec une clé prépartagée](/intune/wi-fi-profile-shared-key)
- [Créer un profil VPN par application](/intune/android-pulse-secure-per-app-vpn)
- [Autoriser et bloquer des applications pour les appareils Samsung Knox Standard](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
> Seuls les paramètres répertoriés peuvent être configurés par ce type de profil. Les appareils Android n’exposent pas une liste complète des paramètres OMA-URI que vous pouvez configurer. Si vous souhaitez afficher davantage de paramètres, votez pour des paramètres supplémentaires sur le [site Intune Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas).

## <a name="custom-profile-settings-for-android-devices"></a>Paramètres de profil personnalisés pour les appareils Android

1. Connectez-vous au [portail Azure](https://portal.azure.com). 
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Créez un profil personnalisé à l’aide de la plateforme Android. Les étapes sont présentées dans [Configurer les paramètres d’appareils personnalisés dans Microsoft Intune](custom-settings-configure.md).
4. Dans **Paramètres OMA-URI personnalisés**, sélectionnez **Ajouter**, puis **Ajouter une ligne**.
5. Entrez les propriétés suivantes :

  - **Nom** : entrez un nom unique pour le paramètre OMA-URI afin de le retrouver facilement.
  - **Description** : entrez une description qui donne une vue d’ensemble du paramètre et tout autre détail important.
  - **Type de données** : entrez le type de données que vous utilisez pour ce paramètre OMA-URI. Choisissez **Chaîne**, **Chaîne (XML)**, **Date et heure**, **Entier**, **Virgule flottante** ou **Booléen**.
  - **OMA-URI** : entrez l’OMA-URI que vous souhaitez.
  - **Valeur** : entrez la valeur à associer à l’identificateur OMA-URI que vous avez entré.

6. Cliquez sur **OK** pour enregistrer vos modifications. Continuez à ajouter d’autres paramètres si besoin.

## <a name="next-steps"></a>Étapes suivantes

Une fois tous les paramètres ajoutés, le profil est créé et s’affiche dans la liste. Pour attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).
