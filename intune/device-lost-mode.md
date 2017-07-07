---
title: "Activer le mode Perdu d’iOS avec Intune"
titleSuffix: Intune on Azure
description: "Apprenez à utiliser Intune pour activer le mode Perdu sur les appareils iOS perdus ou volés."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a34d008ae76355578c6f24a932c9e1e501d5b46b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Activer le mode Perdu sur les appareils iOS


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

L’action d’appareil **Mode Perdu** vous permet d’activer le mode Perdu sur les appareils iOS perdus ou volés. Ce mode vous permet de spécifier un message et un numéro de téléphone qui s’affichent sur l’écran de verrouillage de l’appareil.

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
5. Dans la liste des appareils que vous gérez, choisissez un appareil iOS, puis choisissez l’action à distance **Mode perdu**.
6. Dans le panneau **Mode Perdu**, activez le mode Perdu, entrez le message qui s’affiche et éventuellement un numéro de téléphone de contact.
7. Cliquez sur **OK**.

Lorsque vous activez le mode Perdu, vous bloquez l’utilisation de l’appareil. L’utilisateur final ne peut pas accéder à l’appareil tant que vous n’avez pas désactivé le mode Perdu. Quand le mode Perdu est activé, vous pouvez utiliser l’action **Localiser l’appareil** pour rechercher l’emplacement de l’appareil.
Pour utiliser le mode Perdu, l’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé.

Pour connaître l’état de l’action que vous venez d’effectuer, allez dans le panneau **Appareils et groupes**, et choisissez **Actions d’appareil**.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informations de sécurité et de confidentialité pour le mode Perdu et actions Localiser l’appareil
- Aucune information d’emplacement de l’appareil n’est envoyée à Intune tant que vous n’activez pas cette action.
- Lorsque vous utilisez l’action Localiser l’appareil, les coordonnées de latitude et de longitude de l’appareil sont envoyées à Intune et affichées dans le portail Azure.
- Les données sont stockées pendant 24 heures avant d’être supprimées. Vous ne pouvez pas supprimer manuellement les données d’emplacement.
- Les données d’emplacement sont chiffrées aussi bien pendant leur stockage que leur transmission.
- Lorsque vous configurez le mode Perdu, nous vous recommandons de rédiger le message qui s’affiche sur l’écran de verrouillage de façon à ce qu’il inclue des informations qui permettent à quelqu’un de rendre l’appareil.

