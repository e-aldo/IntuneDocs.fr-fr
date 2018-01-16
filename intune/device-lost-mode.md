---
title: "Activer le mode Perdu d’iOS avec Intune"
titlesuffix: Azure portal
description: "Apprenez à utiliser Intune pour activer le mode Perdu sur les appareils iOS perdus ou volés."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 54c298e751f2cb63e8c9fd60aa14ed626ab9a0b1
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2018
---
# <a name="activate-lost-mode-on-ios-devices"></a>Activer le mode Perdu sur les appareils iOS


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Mode Perdu** vous permet d’activer le mode Perdu sur les appareils iOS perdus ou volés. Ce mode vous permet de spécifier un message et un numéro de téléphone qui s’affichent sur l’écran de verrouillage de l’appareil.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Windows - Non prise en charge
- Windows Phone - Non prise en charge
- iOS - Prise en charge d’iOS 9.3 et ultérieur, en mode supervisé et appartenant à l’entreprise
- macOS - Non prise en charge
- Android - Non prise en charge

## <a name="how-to-activate-lost-mode"></a>Comment activer le mode Perdu

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil iOS, puis choisissez l’action à distance **Mode perdu**.
6. Dans le panneau **Mode Perdu**, activez le mode Perdu. Entrez ensuite le message à afficher et, si vous le souhaitez, le numéro de téléphone du contact.
7. Cliquez sur **OK**.

Lorsque vous activez le mode Perdu, vous bloquez l’utilisation de l’appareil. L’utilisateur final ne peut pas accéder à l’appareil tant que vous n’avez pas désactivé le mode Perdu. Quand le mode Perdu est activé, vous pouvez utiliser l’action **Localiser l’appareil** pour rechercher l’emplacement de l’appareil.
Pour utiliser le mode Perdu, l’appareil doit être un appareil iOS en mode supervisé.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informations de sécurité et de confidentialité pour le mode Perdu et actions Localiser l’appareil
- Aucune information sur l’emplacement de l’appareil n’est envoyée à Intune tant que vous n’activez pas cette action.
- Lorsque vous utilisez l’action Localiser l’appareil, les coordonnées de latitude et de longitude de l’appareil sont envoyées à Intune et affichées dans le portail Azure.
- Les données sont stockées pendant 24 heures avant d’être supprimées. Vous ne pouvez pas supprimer manuellement les données d’emplacement.
- Les données d’emplacement sont chiffrées aussi bien pendant leur stockage que leur transmission.
- Nous vous recommandons de rédiger le message qui s’affiche sur l’écran de verrouillage de façon à ce qu’il inclue des informations qui permettent à quelqu’un de rendre l’appareil.

## <a name="next-steps"></a>Étapes suivantes

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.

