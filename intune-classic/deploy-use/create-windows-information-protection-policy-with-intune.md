---
title: "Créer et déployer une stratégie de protection d’application Protection des informations Windows (WIP) avec Intune"
description: "Créer et déployer des stratégies de protection d’application WIP avec Intune"
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 9/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 040ce88c47eb12bbe9b228189d90ca422e5185e7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Créer et déployer une stratégie de protection d’application Protection des informations Windows (WIP) avec Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

À compter d’Intune version 1704, vous pouvez utiliser des stratégies de protection d’application avec Windows 10 dans la gestion des applications mobiles (MAM) sans le scénario d’inscription.

## <a name="before-you-begin"></a>Avant de commencer

Examinons quelques concepts lors de l’ajout d’une stratégie WIP.

### <a name="list-of-allowed-and-exempt-apps"></a>Liste des applications autorisées et exemptes

-   **Applications autorisées** Il s’agit des applications qui doivent se conformer à cette stratégie.

-   **Applications exemptes** Ces applications sont exemptes de cette stratégie et peuvent accéder aux données d’entreprise sans restrictions.

### <a name="types-of-apps"></a>Types d’applications

-   **Applications recommandées :** liste préremplie d’applications (principalement Microsoft Office) que les administrateurs peuvent facilement importer dans la stratégie.

-   **Applications du Store :** l’administrateur peut ajouter n’importe quelle application du Windows Store à la stratégie.

-   **Applications de bureau Windows :** l’administrateur peut ajouter n’importe quelle application de bureau Windows traditionnelle à la stratégie (par exemple exe, dll, etc.)

## <a name="pre-requisites"></a>Conditions préalables

Vous devez configurer le fournisseur MAM avant de pouvoir créer une stratégie de protection d’application WIP.

-   En savoir plus sur la façon de [configurer le fournisseur MAM avec Intune](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10).

Les éléments suivants sont également requis :

-   Licence [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP ne prend pas en charge les identités multiples, une seule identité gérée peut exister à la fois.

## <a name="to-add-a-wip-policy"></a>Pour ajouter une stratégie WIP

Une fois que vous avez configuré Intune dans votre organisation, vous pouvez créer une stratégie propre à WIP via le [portail Azure](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).

1.  Allez dans le **Tableau de bord Gestion des applications mobiles Intune**, choisissez **Tous les paramètres**, puis **Stratégie d’application**.

2.  Dans le panneau **Stratégie d’application**, choisissez **Ajouter une stratégie**, puis entrez les valeurs suivantes :

    a.  **Nom :** tapez un nom (obligatoire) pour votre nouvelle stratégie.

    b.  **Description :** Tapez une description facultative.

    c.  **Plateforme :** choisissez **Windows 10** comme plateforme prise en charge pour votre stratégie de protection d’application.

    d.  **État d’inscription :** choisissez **Sans inscription** en tant qu’état d’inscription de votre stratégie.

3.  Choisissez **Créer**. La stratégie est créée et apparaît dans le tableau du panneau **Stratégie d’application**.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>Pour ajouter les applications recommandées à votre liste d’applications autorisées

1.  À partir du panneau **Stratégie d’application**, cliquez sur le nom de votre stratégie, puis cliquez sur **Applications autorisées** à partir du panneau **Ajouter une stratégie**. Le panneau **Applications autorisées** s’ouvre et affiche toutes les applications qui sont déjà incluses dans la liste pour cette stratégie de protection d’application.

2.  À partir du panneau **Applications autorisées**, choisissez **Ajouter des applications**. Le panneau **Ajouter des applications** s’ouvre pour afficher toutes les applications qui font partie de cette liste.

3.  Sélectionnez chaque application devant accéder à vos données d’entreprise, puis choisissez **OK**. Le panneau **Applications autorisées** est mis à jour et vous montre les applications sélectionnées.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Ajout d’une application du Windows Store à votre liste d’applications autorisées

**Pour ajouter une application du Windows Store**

1.  À partir du panneau **Stratégie d’application**, cliquez sur le nom de votre stratégie, puis choisissez **Applications autorisées** dans le menu qui s’affiche avec toutes les applications qui sont déjà incluses dans la liste pour cette stratégie de protection d’application.

2.  À partir du panneau **Applications autorisées**, choisissez **Ajouter des applications**.

3.  Dans le panneau **Ajouter des applications**, choisissez **Applications du Windows Store** dans la liste déroulante. Le panneau change pour afficher des zones vous permettant d’ajouter un **éditeur** et un **nom** d’application.

4.  Tapez le nom de l’application et le nom de son éditeur, puis choisissez **OK**.

    > [!TIP]
    > Voici un exemple d’application, où **l’éditeur** est *CN = Microsoft Corporation, O = Microsoft Corporation, L = Redmond, S = Washington, C = US* et le **nom** du produit est *Microsoft.MicrosoftAppForWindows*.

5.  Une fois que vous avez entré les informations dans les champs, choisissez **OK** pour ajouter l’application à votre liste **Applications autorisées**.

> [!NOTE]
> Pour ajouter plusieurs applications du Windows Store en même temps, vous pouvez cliquer sur le menu **(...) ** à la fin de la ligne de l’application, puis continuer à ajouter des applications. Quand vous avez terminé, choisissez **OK**.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Ajout d’une application de bureau à votre liste d’applications autorisées

**Pour ajouter une application de bureau**

1.  À partir du panneau **Stratégie d’application**, cliquez sur le nom de votre stratégie, puis cliquez sur **Applications autorisées.** Le panneau **Applications autorisées** s’ouvre et affiche toutes les applications qui sont déjà incluses dans la liste pour cette stratégie de protection d’application.

2.  À partir du panneau **Applications autorisées**, choisissez **Ajouter des applications**.

3.  Dans le panneau **Ajouter des applications**, choisissez **Applications de bureau** dans la liste déroulante.

4.  Une fois que vous avez entré les informations dans les champs, choisissez **OK** pour ajouter l’application à votre liste **Applications autorisées**.

> [!NOTE]
> Pour ajouter plusieurs **applications de bureau** en même temps, vous pouvez cliquer sur le menu **(...)** à la fin de la ligne de l’application, puis continuer à ajouter des applications. Quand vous avez terminé, choisissez **OK**.

## <a name="windows-information-protection-wip-learning"></a>Windows Information Protection (WIP) Learning

Après avoir ajouté les applications que vous souhaitez protéger avec WIP, vous devez appliquer un mode de protection à l’aide de **WIP Learning**.

### <a name="before-you-begin"></a>Avant de commencer

Windows Information Protection (WIP) Learning est un rapport qui permet aux administrateurs de surveiller leurs applications WIP inconnues. Les applications inconnues sont celles non déployées par le département informatique de votre organisation. L’administrateur peut exporter ces applications à partir du rapport et les ajouter aux stratégies WIP pour éviter une perturbation de la productivité avant l’application de WIP en mode « Masquer les substitutions ».

Nous vous recommandons de commencer avec **Silencieux** ou **Autoriser les substitutions** lors de la vérification avec un petit groupe que vous avez les bonnes applications dans votre liste d’applications autorisées. Une fois cela fait, vous pouvez passer sur votre stratégie d’application finale, **Masquer les substitutions**.

#### <a name="what-the-protection-modes-are"></a>Que sont les modes de protection ?

- **Masquer les substitutions :**
    - WIP recherche des pratiques de partage de données inappropriées et empêche l’utilisateur de terminer l’action.
    - Cela peut inclure le partage d’informations entre des applications non protégées pas votre entreprise, ou le partage de données d’entreprise entre des personnes et appareils en dehors de votre organisation.
<br></br>

- **Autoriser les substitutions :**
    - WIP recherche les partages de données inappropriés, et avertit les utilisateurs s’ils font quelque chose de potentiellement dangereux.
    - Toutefois, ce mode permet à l’utilisateur de remplacer la stratégie et de partager les données. L’action est alors consignée dans votre journal d’audit.
<br></br>
- **Silencieux :**
    - WIP s’exécute en mode silencieux, en consignant les partages de données inappropriés, sans bloquer l’utilisateur avec les invites qui s’afficheraient pour le mode Autoriser la substitution.
    - Les actions non autorisées d’applications, comme les tentatives d’accès inappropriées à une ressource réseau ou à des données protégées par WIP sont toujours arrêtées.
<br></br>
- **Désactivé (Non recommandé) :**
    - WIP est désactivé et ne permet pas de protéger ou vérifier vos données.
    - Après avoir désactivé WIP, une tentative est effectuée pour déchiffrer les fichiers marqués par WIP sur les disques connectés localement. N’oubliez pas que vos informations de déchiffrement et de stratégie précédentes ne sont pas réappliquées automatiquement si vous réactivez la protection WIP.

### <a name="to-add-a-protection-mode"></a>Pour ajouter un mode de protection

1.  À partir du panneau **Stratégie d’application**, cliquez sur le nom de votre stratégie, puis cliquez sur **Paramètres requis** à partir du panneau **Ajouter une stratégie**.

    ![Capture d’écran du mode d’apprentissage](../media/AppManagement/learning-mode-sc1.png)

1.  Choisissez **Enregistrer**.

### <a name="to-use-wip-learning"></a>Pour utiliser WIP Learning

1. Accédez au tableau de bord Azure.

2. Choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

3. Choisissez **Intune**, le **tableau de bord Intune** s’affiche, sélectionnez alors **Applications mobiles**.

4. Choisissez **WIP Learning** sous la section **Surveiller**. Les applications inconnues consignées par WIP Learning s’affichent.

> [!IMPORTANT]
> Une fois que les applications s’affichent dans le rapport de journalisation WIP Learning, vous pouvez ajouter à vos stratégies de protection d’application.

## <a name="to-deploy-your-wip-app-protection-policy"></a>Pour déployer votre stratégie de protection d’application WIP

> [!IMPORTANT]
> Cela s’applique à WIP avec la gestion des applications mobiles (MAM) sans le scénario d’inscription.

Une fois que vous avez créé votre stratégie de protection d’application WIP, vous devez la déployer dans votre organisation à l’aide de MAM.

1.  Dans le panneau **Stratégie d’application**, choisissez votre nouvelle stratégie de protection d’application, puis **Groupes d’utilisateurs** et **Ajouter un groupe d’utilisateurs**.

    Une liste de groupes d’utilisateurs, composée de tous les groupes de sécurité figurant dans Azure Active Directory, s’ouvre dans le panneau **Ajouter un groupe d’utilisateurs**.

1.  Choisissez le groupe auquel vous souhaitez appliquer votre stratégie, puis cliquez sur **Sélectionner** pour déployer la stratégie.
