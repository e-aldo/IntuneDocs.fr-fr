---
title: Configurer une page d’état d’inscription
titleSuffix: Microsoft Intune
description: Affichez un message d’accueil aux utilisateurs qui inscrivent des appareils Windows 10.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 5/17/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c6604c35cebdad4341f27a51db1a4c735f9a9818
ms.sourcegitcommit: 6bd5867c41fb5288fde114dbfcc127dd206f7148
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235614"
---
# <a name="set-up-an-enrollment-status-page"></a>Configurer une page d’état d’inscription
 
[!INCLUDE [azure_portal](./includes/azure_portal.md)]
 
Pendant la configuration de l’appareil, la page d’état d’inscription affiche des informations d’état de l’installation sur l’appareil de l’utilisateur final. Des applications, des profils et des certificats risquent de ne pas être installés complètement au moment où un utilisateur est inscrit. La page d’état peut aider les utilisateurs à comprendre l’état de leur appareil pendant et après l’inscription. Vous pouvez activer la page d’état pour tous vos utilisateurs, et aussi les empêcher d’utiliser l’appareil jusqu’à ce que toutes les applications et tous les profils affectés soient installés.
 
Pour activer la page d’état d’inscription pour tous vos utilisateurs finaux, suivez les étapes ci-dessous.
 
1.  Dans [Intune](https://aka.ms/intuneportal), choisissez **Inscription de l’appareil** > **Inscription Windows** > **Page d’état d’inscription (préversion)**.
2.  Dans le panneau **Page d’état d’inscription**, choisissez **Par défaut** > **Paramètres**.
3.  Pour **Afficher la progression de l’installation des profils et des applications**, choisissez **Oui**.
4.  Choisissez les autres paramètres que vous voulez activer, puis choisissez **Enregistrer**.
 
## <a name="enrollment-status-page-tracking-information"></a>Informations de suivi de la page d’état d’inscription

La page d’état montre le suivi des informations de préparation de l’appareil, de configuration de l’appareil et de configuration du compte.

### <a name="device-preparation"></a>Préparation de l’appareil

Pour la préparation de l’appareil, la page d’état d’inscription montre le suivi des attestations de clé du Module de plateforme sécurisée (TPM) (le cas échéant), ainsi que la progression de la jonction à Azure Active Directory et de l’inscription dans Intune.

### <a name="device-setup"></a>Configuration de l’appareil

Pour la configuration de l’appareil, la page d’état d’inscription montre le suivi des éléments suivants s’ils sont affectés à Tous les appareils :
- Stratégies de sécurité
    - Un fournisseur de services de configuration pour toutes les inscriptions.
    - Les fournisseurs de services de configuration réels configurés par Intune ne sont pas suivis ici.
- Applications
    - Applications MSI métier par machine.
    - Applications du Store métier avec contexte d’installation = Appareil.
    - Applications du Store métier et du Store hors connexion avec contexte d’installation = Appareil.
- Les profils de connectivité (VPN et Wi-Fi) ne sont pas encore suivis : ils indiquent donc toujours « 0 sur 0 ».
- Les certificats ne sont pas encore suivis : ils indiquent donc toujours « 0 sur 0 ».

### <a name="account-setup"></a>Configuration du compte
Pour la configuration du compte, la page d’état d’inscription montre le suivi des éléments suivants :
- Stratégies de sécurité
    - Un seul fournisseur de services de configuration pour toutes les inscriptions.
    - Les fournisseurs de services de configuration réels configurés par Intune ne sont pas suivis ici.
- Applications
    - Applications MSI métier par utilisateur qui sont affectées à Tous les appareils, à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil.
    - Applications MSI métier par machine qui sont affectées à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil.
    - Applications du Store métier qui sont affectées à Tous les appareils, à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil, avec contexte d’installation = Utilisateur.
    - Applications du Store en ligne qui sont affectées à Tous les appareils, à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil, avec contexte d’installation = Utilisateur.
    - Applications du Store hors connexion qui sont affectées à Tous les appareils, à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil, avec contexte d’installation = Utilisateur.
- Profils de connectivité
    - Profils VPN ou Wi-Fi qui sont affectés à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil.
- Certificats
    - Profils de certificat qui sont affectés à Tous les utilisateurs ou à un groupe d’utilisateurs dont est membre l’utilisateur inscrivant l’appareil.

## <a name="next-steps"></a>Étapes suivantes
Après avoir configuré les pages d’inscription Windows, découvrez comment gérer les appareils Windows. Pour plus d’informations, consultez [Qu’est-ce que la gestion des appareils Microsoft Intune ?](https://docs.microsoft.com/intune/device-management)