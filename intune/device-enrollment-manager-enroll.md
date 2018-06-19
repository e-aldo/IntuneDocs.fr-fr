---
title: Inscrire des appareils avec un compte de gestionnaire d’inscription d’appareil
titlesuffix: Microsoft Intune
description: Utilisez le compte de gestionnaire d’inscription d’appareil pour inscrire des appareils dans Intune. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a32eb1d65710bf09d61c0846a8d949d5cd99ed2
ms.sourcegitcommit: 91802e78cd5014d20a828ca25a54a381d452f0f8
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2018
ms.locfileid: "34216324"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Inscrire des appareils avec un compte de gestionnaire d’inscription d’appareil

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Les organisations peuvent utiliser Intune pour gérer un grand nombre d'appareils mobiles avec un seul compte d’utilisateur. Le compte du *gestionnaire d’inscription d’appareil* est un compte d’utilisateur spécial qui peut inscrire jusqu’à 1 000 appareils. Vous ajoutez des utilisateurs existants au compte de gestionnaire d’inscription d’appareil afin qu’ils puissent bénéficier des fonctionnalités associées. Chaque appareil inscrit utilise une seule licence. Nous vous recommandons d’utiliser des appareils inscrits par le biais de ce compte comme appareils partagés plutôt que comme appareils personnels (« BYOD »).  

Les utilisateurs doivent exister dans le [portail Azure](https://portal.azure.com) pour pouvoir être ajoutés comme gestionnaires d’inscription d’appareil. Pour une sécurité optimale, l’utilisateur du gestionnaire d’inscription d’appareil ne doit pas être également un administrateur Intune.

>[!NOTE]
>La méthode d’inscription DEM ne peut pas être utilisée avec ces autres méthodes d’inscription : [Apple Configurator avec l’Assistant Configuration](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator avec l’inscription directe](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) ou le [Programme d’inscription des appareils (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Exemple d’un scénario faisant intervenir un gestionnaire d’inscription d’appareil

Un restaurant souhaite fournir 50 tablettes à son personnel de service et des moniteurs de commande à son personnel de cuisine. Les employés n’ont jamais besoin d’accéder aux données de l’entreprise ou de se connecter comme utilisateurs. L’administrateur Intune crée un compte de gestionnaire d’inscription des appareils et ajoute un superviseur de restaurant au compte DEM. Le superviseur a maintenant des fonctionnalités DEM. Le superviseur peut désormais inscrire les 50 tablettes en utilisant les informations d’identification du gestionnaire d’inscription d’appareil.

Seuls les utilisateurs existant dans le [portail Azure](https://portal.azure.com) peuvent être gestionnaires d’inscription d’appareil. Le gestionnaire d’inscription d’appareil ne peut pas être administrateur Intune.

L’utilisateur du gestionnaire d’inscription d’appareil peut :

-   Inscrire jusqu’à 1 000 appareils dans Intune
-   Se connecter au Portail d’entreprise pour obtenir des applications d’entreprise
-   Configurer l’accès aux données de l’entreprise en déployant des applications spécifiques aux rôles sur les tablettes

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Limitations des appareils qui sont inscrits avec un compte de gestionnaire d’inscription d’appareil

Les appareils inscrits avec un compte de gestionnaire d’inscription d’appareil ont les limitations suivantes :

  - Pas d’accès par utilisateur. Étant donné qu’aucun utilisateur n’est affecté aux appareils, l’appareil n’a pas accès à la messagerie ou aux données d’entreprise. Les configurations VPN, par exemple, peuvent toujours être utilisées pour fournir aux applications d’appareil un accès aux données.
  - L’utilisateur du gestionnaire d’inscription d’appareil ne peut pas annuler l’inscription des appareils inscrits auprès du gestionnaire d’inscription d’appareil sur l’appareil lui-même à l’aide du portail d’entreprise. L’administrateur Intune peut annuler l’inscription.
  - Seul l’appareil local s’affiche dans l’application Portail d’entreprise ou le site web.
  - Les utilisateurs ne peuvent pas utiliser les applications du programme d’achat en volume (VPP) Apple avec des licences utilisateur en raison des critères des identifiants Apple par utilisateur pour la gestion des applications.
  - (iOS uniquement) Si vous utilisez le gestionnaire d’inscription d’appareil pour inscrire des appareils iOS, vous ne pouvez pas utiliser Apple Configurator, Apple School Manager (ASM) ou le programme d’inscription des appareils Apple pour inscrire des appareils.
  - (Android uniquement) Il existe une limite quant à la quantité d’appareils Android for Work qui peuvent être inscrits avec un seul compte DEM. Vous pouvez inscrire un maximum de 10 appareils de profil professionnel Android par compte DEM. Cette limitation ne s’applique pas à l’inscription Android héritée.
  - Les appareils peuvent installer des applications VPP s’ils ont des licences d’appareil.
  - Chaque appareil nécessite une licence d’appareil. Apprenez-en davantage sur les [licences utilisateur et d’appareil](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Vous pouvez déployer des applications d’entreprise sur des appareils gérés par le Gestionnaire d’inscription des appareils. Déployez l’application Portail d’entreprise comme une **Installation requise** au compte d’utilisateur du Gestionnaire de l’inscription des appareils.
> Pour améliorer les performances, l’affichage de l’application Portail d’entreprise sur un appareil de gestionnaire d’inscription d’appareil affiche uniquement les appareils locaux. La gestion à distance d’autres appareils DEM est possible uniquement à partir de la console d’administration Intune.


## <a name="add-a-device-enrollment-manager"></a>Ajouter un gestionnaire d’inscription d’appareil

1.  Dans le [portail Azure d’Intune](https://aka.ms/intuneportal), choisissez **Inscription d’appareil** > **Gestionnaires d’inscription d’appareil**.

2.  Sélectionnez **Ajouter**.

3.  Dans le panneau **Ajouter un utilisateur**, entrez le nom d’utilisateur principal de l’utilisateur DEM, puis sélectionnez **Ajouter**. L’utilisateur DEM est ajouté à la liste des utilisateurs DEM.

## <a name="permissions-for-dem"></a>Autorisations pour DEM

Les rôles d’administrateur de service Intune ou global d’Azure AD sont nécessaires pour effectuer les tâches liées à l’inscription DEM dans le portail d’administration. Ces rôles sont également requis pour afficher tous les utilisateurs DEM même si les autorisations RBAC sont répertoriées et disponibles sous le rôle Utilisateur personnalisé. Un utilisateur sans le rôle Administrateur global ou Administrateur du service Intune, mais disposant des autorisations en lecture pour le rôle Gestionnaires d’inscription d’appareil, peut voir seulement les utilisateurs DEM qu’il a créés. La prise en charge des rôles RBAC pour ces fonctionnalités sera annoncée ultérieurement.

Si un utilisateur n’a pas le rôle Administrateur global ou Administrateur du service Intune, mais qu’il dispose des autorisations en lecture pour le rôle Gestionnaires d’inscription des appareils, il peut voir seulement les utilisateurs DEM qu’il a créés.

## <a name="remove-a-device-enrollment-manager"></a>Supprimer un gestionnaire d’inscription d’appareil

La suppression d’un gestionnaire d’inscription d’appareil n’affecte pas les appareils inscrits. Quand un gestionnaire d’inscription d’appareil est supprimé :

-   Les appareils inscrits ne sont pas affectés et continuent à être entièrement gérés.
-   Les informations d’identification du compte du gestionnaire d’inscription d’appareil supprimé restent valides.
-   Le gestionnaire d’inscription d’appareil supprimé ne peut pas réinitialiser ni mettre hors service des appareils.
-   Le gestionnaire d’inscription d’appareil supprimé peut inscrire uniquement un certain nombre d’appareils jusqu'à la limite par utilisateur configurée par l’administrateur d’Intune.

**Pour supprimer un gestionnaire d’inscription d’appareil**

1. Dans le [portail Azure](https://aka.ms/intuneportal), choisissez **Inscription des appareils**, puis choisissez **Gestionnaires d’inscription des appareils**.
2. Dans le panneau **Gestionnaires d’inscription d’appareil**, sélectionnez l’utilisateur gestionnaire d’inscription d’appareil, puis sélectionnez **Supprimer**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Afficher les propriétés d’un gestionnaire d’inscription d’appareil

1. Dans le [portail Azure](https://portal.azure.com), choisissez **Inscription de l’appareil**, puis choisissez **Gestionnaires d’inscription d’appareil**.
2. Dans le panneau **Gestionnaires d’inscription d’appareil**, cliquez avec le bouton droit sur l’utilisateur gestionnaire d’inscription d’appareil, puis sélectionnez **Propriétés**.
