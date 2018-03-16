---
title: "Guide pratique pour affecter des applications à des groupes dans Microsoft Intune"
titlesuffix: 
description: "Une fois que vous avez ajouté une application à Microsoft Intune, vous pouvez l’affecter à des groupes d’utilisateurs ou d’appareils."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78a9e9f4af41cdb97efd017eec56e676eda82856
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Une fois que vous avez ajouté une application à Intune, vous pouvez l’affecter à des utilisateurs et des appareils.

Les applications peuvent être affectées aux appareils, qu’ils soient gérés par Intune ou non. Utilisez le tableau suivant pour vous aider à comprendre les différentes options pour attribuer des applications aux utilisateurs et aux appareils :

||||
|-|-|-|-|
|&nbsp;|Appareils inscrits avec Intune|Appareils non inscrits avec Intune|
|Attribuer aux utilisateurs|Oui|Oui|
|Attribuer aux appareils|Oui|Non|
|Attribuer des applications encapsulées ou incorporer le SDK Intune (pour les stratégies de protection d’application)|Oui|Oui|
|Attribuer des applications en tant qu’applications disponibles|Oui|Oui|
|Attribuer des applications en tant qu’applications requises|Oui|Non|
|Désinstallation d’applications|Oui|Non|
|Recevoir des mises à jour de l’application d’Intune|Oui|Non|
|Les utilisateurs finaux installent les applications disponibles à partir de l’application Portail d’entreprise|Oui|Non|
|Les utilisateurs finaux installent les applications disponibles à partir du portail d’entreprise web|Oui|Oui|

> [!NOTE]
> Actuellement, vous pouvez affecter des applications iOS et Android (applications métier ou achetées dans un Store) pour les appareils qui ne sont pas inscrits avec Intune.<br></br><br></br>
> Pour recevoir des mises à jour d’applications sur des appareils qui ne sont pas inscrits auprès d’Intune, les utilisateurs des appareils doivent accéder à leur portail d’entreprise et installer manuellement les mises à jour des applications.

## <a name="how-to-assign-an-app"></a>Comment affecter une application

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
1. Dans la charge de travail **Applications mobiles**, choisissez **Gérer** > **Applications**.
2. Dans la liste du panneau d’applications, cliquez sur l’application que vous souhaitez affecter.
3. Dans le panneau **Vue d’ensemble**, choisissez **Gérer** > **Affectations**.
4. Choisissez **Ajouter un groupe** puis, dans le panneau **Ajouter un groupe**, sélectionnez les groupes Azure AD à inclure ou à exclure de l’affectation de l’application.
5. Pour chaque application que vous choisissez, choisissez un **Type d’affectation** pour l’application :
    - **Disponible pour les appareils inscrits** : les utilisateurs installent l’application à partir de l’application ou du site web Portail d’entreprise.
    - **Disponible avec ou sans inscription** : affectez cette application à des groupes d’utilisateurs dont les appareils ne sont pas inscrits avec Intune.
    - **Requis** : l’application est installée sur les appareils dans les groupes sélectionnés.
    - **Désinstaller** : l’application est désinstallée des appareils dans les groupes sélectionnés.
6. **Pour les applications iOS uniquement** : si vous avez créé un profil VPN iOS qui contient des paramètres VPN par application, vous pouvez le sélectionner sous **VPN**. Quand l’application est exécutée, la connexion VPN est ouverte. Pour plus d’informations, consultez [Paramètres VPN pour les appareils iOS](vpn-settings-ios.md).
6. Une fois que vous avez terminé, choisissez **OK**, puis **Enregistrer**.

L’application est maintenant affectée aux groupes que vous avez sélectionnés.

## <a name="how-conflicts-between-app-intents-are-resolved"></a>Résolution des conflits entre les intentions d’application

Parfois, la même application est affectée à plusieurs groupes, mais avec des intentions différentes. Dans ces cas-là, utilisez le tableau ci-dessous pour comprendre l’intention résultante.

||||
|-|-|-|
|Intention du groupe 1|Intention du groupe 2|Intention résultante|
|Utilisateur obligatoire|Utilisateur disponible|Obligatoire et disponible|
|Utilisateur obligatoire|Utilisateur non disponible|Obligatoire|
|Utilisateur obligatoire|Désinstallation utilisateur|Obligatoire|
|Utilisateur disponible|Utilisateur non disponible|Non disponible|
|Utilisateur disponible|Désinstallation utilisateur|Désinstaller|
|Utilisateur non disponible|Désinstallation utilisateur|Désinstaller
|Utilisateur obligatoire|Appareil obligatoire|Toutes deux existent, la passerelle traite Obligatoire 
|Utilisateur obligatoire|Désinstallation appareil|Toutes deux existent, la passerelle résout Obligatoire 
|Utilisateur disponible|Appareil obligatoire|Toutes deux existent, la passerelle résout Obligatoire (Obligatoire et Disponible)
|Utilisateur disponible|Désinstallation appareil|Toutes deux existent, la passerelle résout Disponible.<br>L’application apparaît dans le portail d’entreprise.<br>Dans le cas où l’application est déjà installée (en tant qu’application obligatoire avec intention précédente), elle est désinstallée.<br>Mais si l’utilisateur clique sur Installer dans le portail d’entreprise, l’application est installée et l’intention de désinstallation n’est pas honorée.|
|Utilisateur non disponible|Appareil obligatoire|Obligatoire|
|Utilisateur non disponible|Désinstallation appareil|Désinstaller|
|Désinstallation utilisateur|Appareil obligatoire|Toutes deux existent, la passerelle résout Obligatoire|
|Désinstallation utilisateur|Désinstallation appareil|Toutes deux existent, la passerelle résout Désinstallation|
|Appareil obligatoire|Désinstallation appareil|Obligatoire|
|Utilisateur obligatoire et disponible|Utilisateur disponible|Obligatoire et disponible|
|Utilisateur obligatoire et disponible|Désinstallation utilisateur|Obligatoire et disponible|
|Utilisateur obligatoire et disponible|Utilisateur non disponible|Obligatoire et disponible|
|Utilisateur obligatoire et disponible|Appareil obligatoire|Toutes deux existent Obligatoire et disponible
|Utilisateur obligatoire et disponible|Appareil non disponible|Obligatoire et disponible|
|Utilisateur obligatoire et disponible|Désinstallation appareil|Toutes deux existent, la passerelle résout Obligatoire. Obligatoire et disponible
|Utilisateur non disponible|Appareil non disponible|Non disponible|
|Utilisateur disponible|Appareil non disponible|Disponible|
|Utilisateur obligatoire|Appareil non disponible|Obligatoire|
|Utilisateur disponible sans inscription|Utilisateur obligatoire et disponible|Obligatoire et disponible
|Utilisateur disponible sans inscription|Utilisateur obligatoire|Obligatoire
|Utilisateur disponible sans inscription|Utilisateur non disponible|Non disponible
|Utilisateur disponible sans inscription|Utilisateur disponible|Disponible|
|Utilisateur disponible sans inscription|Appareil obligatoire|Obligatoire et disponible sans inscription|
|Utilisateur disponible sans inscription|Appareil non disponible|Disponible sans inscription|
|Utilisateur disponible sans inscription|Désinstallation appareil|Désinstaller et disponible sans inscription.<br>Si l’utilisateur n’a pas installé l’application à partir du portail d’entreprise, la désinstallation est honorée.<br>Si l’utilisateur installe l’application à partir du portail d’entreprise, l’installation est prioritaire par rapport à la désinstallation.|

>[!NOTE]
>Pour les applications de l’App Store iOS gérées uniquement, quand vous les ajoutez à Intune et que vous les affectez comme Obligatoire, elles sont créées automatiquement avec des intentions Obligatoire et Disponible.

## <a name="next-steps"></a>Étapes suivantes

Consultez la page [Guide pratique pour surveiller des applications](apps-monitor.md) pour plus d’informations pour vous aider à contrôler les affectations de l’application.
