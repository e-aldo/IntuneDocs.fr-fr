---
title: Inscrire des appareils - Gestionnaire d&quot;inscription d&quot;appareil
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : utilisez le compte de gestionnaire d’inscription d’appareil pour inscrire des appareils dans Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: b4629d98f935ab2fac95144940e2a58a1b1e7c5c
ms.lasthandoff: 02/18/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Inscrire des appareils avec le gestionnaire d’inscription d’appareil

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Les organisations peuvent utiliser Intune pour gérer un grand nombre d'appareils mobiles avec un seul compte d’utilisateur. Le compte du *gestionnaire d’inscription d’appareil* est un compte d’utilisateur spécial qui peut inscrire jusqu’à 1 000 appareils. Vous ajoutez des utilisateurs existants au compte de gestionnaire d’inscription d’appareil afin qu’ils puissent bénéficier des fonctionnalités associées. Chaque appareil inscrit utilise une seule licence. Nous vous recommandons d’utiliser des appareils inscrits par le biais de ce compte comme appareils partagés plutôt que comme appareils personnels (« BYOD »).  

Les utilisateurs doivent figurer dans le portail Azure pour être ajoutés comme gestionnaires d’inscription d’appareil. Pour une sécurité optimale, l’utilisateur du gestionnaire d’inscription d’appareil ne doit pas être également un administrateur Intune.

>[!NOTE]
>La méthode d’inscription DEM ne peut pas être utilisée avec ces autres méthodes d’inscription : [Apple Configurator avec l’Assistant Configuration](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md), [Apple Configurator avec l’inscription directe](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md) ou le [Programme d’inscription des appareils](enroll-ios-devices-using-device-enrollment-program.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemple d’un scénario faisant intervenir un gestionnaire d’inscription d’appareil

Un restaurant souhaite fournir 50 tablettes à son personnel de service et des moniteurs de commande à son personnel de cuisine. Les employés n’ont jamais besoin d’accéder aux données de l’entreprise ou de se connecter comme utilisateurs. L’administrateur Intune crée un compte de gestionnaire d’inscription d’appareil et lui ajoute un superviseur de restaurant, ce qui a pour effet d’attribuer à ce superviseur les fonctionnalités associées. Le superviseur peut désormais inscrire les 50 tablettes en utilisant les informations d’identification du gestionnaire d’inscription d’appareil.

Seuls les utilisateurs existants dans la console Intune peuvent être gestionnaires d'inscription d'appareil. Le gestionnaire d’inscription d’appareil ne peut pas être administrateur Intune.

L’utilisateur du gestionnaire d’inscription d’appareil peut :

-   Inscrire jusqu’à 1 000 appareils dans Intune.
-   Se connecter au Portail d’entreprise pour obtenir des applications d’entreprise
-   Configurer l’accès aux données de l’entreprise en déployant des applications spécifiques aux rôles sur les tablettes.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitations des appareils qui sont inscrits avec un compte de gestionnaire d’inscription d’appareil

Les appareils inscrits avec un compte de gestionnaire d’inscription d’appareil ont les limitations suivantes :

  - Il n’existe aucun « utilisateur » propre à l’appareil. Par conséquent, aucun accès aux données d’entreprise ou à la messagerie n’est possible. Toutefois, le VPN, par exemple, peut toujours être utilisé pour fournir aux applications d’appareil un accès aux données.

  - Il n’y a pas d’accès conditionnel, car il s’agit de scénarios par utilisateur.

  - L’utilisateur du gestionnaire d’inscription d’appareil ne peut pas annuler l’inscription des appareils inscrits auprès du gestionnaire d’inscription d’appareil sur l’appareil lui-même à l’aide du portail d’entreprise. L’administrateur Intune a cette capacité, mais pas l’utilisateur du gestionnaire d’inscription d’appareil.

  - Seul l’appareil local s’affiche dans l’application Portail d’entreprise ou le site web.
 
  - Les utilisateurs ne peuvent pas utiliser les applications du programme d’achat en volume (VPP) Apple en raison des critères des identifiants Apple par utilisateur pour la gestion des applications.
 
  - (iOS uniquement) Si vous utilisez le gestionnaire d’inscription d’appareil pour inscrire des appareils iOS, vous ne pouvez pas utiliser Apple Configurator ni le programme d’inscription des appareils Apple pour inscrire des appareils.


> [!NOTE]
> Pour déployer des applications d’entreprise sur des appareils gérés par le gestionnaire d’inscription d’appareil, déployez l’application Portail d’entreprise comme **Installation requise** sur le compte d’utilisateur du gestionnaire d’inscription d’appareil.
> Pour améliorer les performances, l’affichage de l’application Portail d’entreprise sur un appareil de gestionnaire d’inscription d’appareil affiche uniquement les appareils locaux. La gestion à distance d’autres appareils DEM est possible uniquement à partir de la console d’administration Intune.


## <a name="add-a-device-enrollment-manager"></a>Ajouter un gestionnaire d’inscription d’appareil

1.  Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2.  Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Gestionnaires d’inscription d’appareil**.

3.  Sélectionnez **Ajouter**.

4.  Dans le panneau **Ajouter un utilisateur**, entrez le nom d’utilisateur principal de l’utilisateur DEM, puis sélectionnez **Ajouter**. L’utilisateur DEM est ajouté à la liste des utilisateurs DEM.

## <a name="remove-a-device-enrollment-manager"></a>Supprimer un gestionnaire d’inscription d’appareil

La suppression d’un gestionnaire d’inscription d’appareil n’affecte pas les appareils inscrits. Quand un gestionnaire d’inscription d’appareil est supprimé :

-   La suppression d’un utilisateur de la liste des utilisateurs DEM n’affecte pas les appareils inscrits. Ceux-ci continuent à être entièrement gérés.

-   Les informations d’identification du compte du gestionnaire d’inscription d’appareil supprimé restent valides.

-   Le gestionnaire d’inscription d’appareil supprimé ne peut pas réinitialiser ni mettre hors service des appareils.

-   Le gestionnaire d’inscription d’appareil supprimé ne peut pas inscrire d’autres appareils, sauf si la limite par appareil, configurée par l’administrateur Intune, n’a pas été atteinte.

**Pour supprimer un gestionnaire d’inscription d’appareil**

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Gestionnaires d’inscription d’appareil**.

3. Dans le panneau **Gestionnaires d’inscription d’appareil**, cliquez avec le bouton droit sur l’utilisateur DEM, puis sélectionnez **Supprimer**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Afficher les propriétés d’un gestionnaire d’inscription d’appareil

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Gestionnaires d’inscription d’appareil**.

3. Dans le panneau **Gestionnaires d’inscription d’appareil**, cliquez avec le bouton droit sur l’utilisateur DEM, puis sélectionnez **Propriétés**.

