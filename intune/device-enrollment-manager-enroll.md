---
title: Inscrire des appareils - Gestionnaire d'inscription d'appareil
titlesuffix: Azure portal
description: "Utilisez le compte de gestionnaire d’inscription d’appareil pour inscrire des appareils dans Intune. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eda4ad57f1365a7fe27d58ad8f40399b1582b4b6
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="enroll-devices-using-device-enrollment-manager"></a>Inscrire des appareils avec le gestionnaire d’inscription d’appareil

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Les organisations peuvent utiliser Intune pour gérer un grand nombre d'appareils mobiles avec un seul compte d'utilisateur. Le compte du *gestionnaire d’inscription d’appareil* est un compte d’utilisateur spécial qui peut inscrire jusqu’à 1 000 appareils. Vous ajoutez des utilisateurs existants au compte de gestionnaire d’inscription d’appareil afin qu’ils puissent bénéficier des fonctionnalités associées. Chaque appareil inscrit utilise une seule licence. Nous vous recommandons d’utiliser des appareils inscrits par le biais de ce compte comme appareils partagés plutôt que comme appareils personnels (« BYOD »).  

Les utilisateurs doivent figurer dans le portail Azure pour être ajoutés comme gestionnaires d’inscription d’appareil. Pour une sécurité optimale, l’utilisateur du gestionnaire d’inscription d’appareil ne doit pas être également un administrateur Intune.

>[!NOTE]
>La méthode d’inscription DEM ne peut pas être utilisée avec ces autres méthodes d’inscription : [Apple Configurator avec l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator avec l’inscription directe](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) ou le [Programme d’inscription des appareils (DEP)](device-enrollment-program-enroll-ios.md). Il ne peut pas être utilisé pour inscrire des appareils macOS. 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemple d’un scénario faisant intervenir un gestionnaire d’inscription d’appareil

Un restaurant souhaite fournir 50 tablettes à son personnel de service et des moniteurs de commande à son personnel de cuisine. Les employés n’ont jamais besoin d’accéder aux données de l’entreprise ou de se connecter comme utilisateurs. L’administrateur Intune crée un compte de gestionnaire d’inscription d’appareil et lui ajoute un superviseur de restaurant, ce qui a pour effet d’attribuer à ce superviseur les fonctionnalités associées. Le superviseur peut désormais inscrire les 50 tablettes en utilisant les informations d’identification du gestionnaire d’inscription d’appareil.

Seuls les utilisateurs existants dans le portail Azure peuvent être gestionnaires d'inscription d'appareil. Le gestionnaire d’inscription d’appareil ne peut pas être administrateur Intune.

L’utilisateur du gestionnaire d’inscription d’appareil peut :

-   Inscrire jusqu’à 1 000 appareils dans Intune
-   Se connecter au Portail d’entreprise pour obtenir des applications d’entreprise
-   Configurer l’accès aux données de l’entreprise en déployant des applications spécifiques aux rôles sur les tablettes

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitations des appareils qui sont inscrits avec un compte de gestionnaire d’inscription d’appareil

Les appareils inscrits avec un compte de gestionnaire d’inscription d’appareil ont les limitations suivantes :

  - Pas d’accès par utilisateur. Étant donné qu’aucun utilisateur n’est affecté aux appareils, l’appareil n’a pas accès à la messagerie ou aux données d’entreprise. Les configurations VPN, par exemple, peuvent toujours être utilisées pour fournir aux applications d’appareil un accès aux données.
  - Aucun accès conditionnel car il s’agit de scénarios par utilisateur.
  - L’utilisateur du gestionnaire d’inscription d’appareil ne peut pas annuler l’inscription des appareils inscrits auprès du gestionnaire d’inscription d’appareil sur l’appareil lui-même à l’aide du portail d’entreprise. L’administrateur Intune peut faire cela, mais pas l’utilisateur du gestionnaire d’inscription d’appareil.
  - Seul l’appareil local s’affiche dans l’application Portail d’entreprise ou le site web.
  - Les utilisateurs ne peuvent pas utiliser les applications du programme d’achat en volume (VPP) Apple en raison des critères des identifiants Apple par utilisateur pour la gestion des applications.
  - (iOS uniquement) Si vous utilisez le gestionnaire d’inscription d’appareil pour inscrire des appareils iOS, vous ne pouvez pas utiliser Apple Configurator, Apple School Manager (ASM) ou le programme d’inscription des appareils Apple pour inscrire des appareils.
  - (Android uniquement) Il existe une limite quant à la quantité d’appareils Android for Work qui peuvent être inscrits avec un seul compte DEM. Vous pouvez inscrire un maximum de dix appareils de profil professionnel Android par compte DEM. Cette limitation ne s’applique pas à l’inscription Android héritée.
  - Chaque appareil nécessite une licence d’appareil. Apprenez-en davantage sur les [licences utilisateur et d’appareil](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Pour déployer des applications d’entreprise sur des appareils gérés par le gestionnaire d’inscription d’appareil, déployez l’application Portail d’entreprise comme **Installation requise** sur le compte d’utilisateur du gestionnaire d’inscription d’appareil.
> Pour améliorer les performances, l’affichage de l’application Portail d’entreprise sur un appareil de gestionnaire d’inscription d’appareil affiche uniquement les appareils locaux. La gestion à distance d’autres appareils DEM est possible uniquement à partir de la console d’administration Intune.


## <a name="add-a-device-enrollment-manager"></a>Ajouter un gestionnaire d’inscription d’appareil

1.  Dans le portail Azure, choisissez **Autres services** > **Surveillance + gestion** > **Intune**.

2.  Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Gestionnaires d’inscription d’appareil**.

3.  Sélectionnez **Ajouter**.

4.  Dans le panneau **Ajouter un utilisateur**, entrez le nom d’utilisateur principal de l’utilisateur DEM, puis sélectionnez **Ajouter**. L’utilisateur DEM est ajouté à la liste des utilisateurs DEM.

## <a name="permissions-for-dem"></a>Autorisations pour DEM

Les rôles d’administrateur de service Intune ou global d’Azure AD sont requis pour effectuer les tâches d’inscription à la gestion de l’inscription des appareils (DEM). Ces rôles sont également requis pour afficher tous les utilisateurs DEM même si les autorisations RBAC sont répertoriées et disponibles sous le rôle Utilisateur personnalisé. Un utilisateur sans rôle d’administrateur de service Intune ou global affecté mais disposant des autorisations en lecture pour le rôle Gestionnaires d’inscription d’appareil peut voir uniquement les utilisateurs DEM qu’il a créés. La prise en charge des rôles RBAC pour ces fonctionnalités sera annoncée ultérieurement.

Si un utilisateur n’a pas de rôle d’administrateur de service Intune ou global affecté à ceux-ci, mais dispose des autorisations en lecture pour le rôle Gestionnaires d’inscription d’appareil, il pourra uniquement voir les utilisateurs DEM qu’il a créés.

## <a name="remove-a-device-enrollment-manager"></a>Supprimer un gestionnaire d’inscription d’appareil

La suppression d’un gestionnaire d’inscription d’appareil n’affecte pas les appareils inscrits. Quand un gestionnaire d’inscription d’appareil est supprimé :

-   Les appareils inscrits ne sont pas affectés et continuent à être entièrement gérés.
-   Les informations d’identification du compte du gestionnaire d’inscription d’appareil supprimé restent valides.
-   Le gestionnaire d’inscription d’appareil supprimé ne peut pas réinitialiser ni mettre hors service des appareils.
-   Le gestionnaire d’inscription d’appareil supprimé peut inscrire uniquement un certain nombre d’appareils jusqu'à la limite par utilisateur configurée par l’administrateur d’Intune.

**Pour supprimer un gestionnaire d’inscription d’appareil**

1. Dans le portail Azure, choisissez **Autres services** > **Surveillance + gestion** > **Intune**.
2. Dans le panneau Intune, choisissez **Inscrire des appareils**, puis choisissez **Gestionnaires d’inscription d’appareil**.
3. Dans le panneau **Gestionnaires d’inscription d’appareil**, cliquez avec le bouton droit sur l’utilisateur DEM, puis sélectionnez **Supprimer**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Afficher les propriétés d’un gestionnaire d’inscription d’appareil

1. Dans le portail Azure, choisissez **Inscription de l’appareil**, puis choisissez **Gestionnaires d’inscription d’appareil**.
2. Dans le panneau **Gestionnaires d’inscription d’appareil**, cliquez avec le bouton droit sur l’utilisateur DEM, puis sélectionnez **Propriétés**.
