---
title: "Guide pratique pour attribuer des applications à des groupes | Préversion Intune Azure | Microsoft Docs"
description: "Préversion Intune Azure : Une fois que vous avez ajouté une application à Intune, vous souhaiterez l’attribuer à des groupes d’utilisateurs ou d’appareils."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 638ad0d87c19c9e40e96b42d18e5c4342f40a156
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Guide pratique pour attribuer des applications à des groupes avec Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Lorsque vous ajoutez une application à Intune, vous souhaitez probablement la mettre à disposition des utilisateurs et des appareils. Pour cela, affectez-la.

Les applications peuvent être affectées aux appareils, qu’ils soient gérés par Intune ou non. Utilisez le tableau suivant pour vous aider à comprendre les différentes options pour attribuer des applications aux utilisateurs et aux appareils :

||||
|-|-|-|-|
|&nbsp;|Appareils inscrits avec Intune|Appareils non inscrits avec Intune|
|Attribuer aux utilisateurs|Oui|Oui|
|Attribuer aux appareils|Oui|Non|
|Attribuer des applications encapsulées ou incorporer le SDK Intune (pour les stratégies de protection d’application)|Oui|Oui|
|Attribuer des applications en tant qu’applications disponibles|Oui|Oui|
|Attribuer des applications en tant qu’applications requises|Oui|Non|
|Désinstallation d’applications|Oui|Oui|
|Les utilisateurs finaux installent les applications disponibles à partir de l’application de portail d’entreprise|Oui|Non|
|Les utilisateurs finaux installent les applications disponibles à partir du portail d’entreprise web|Oui|Oui|

> [!NOTE]
> Actuellement, vous pouvez affecter des applications iOS et Android (applications métier ou achetées sur une boutique) pour les appareils qui ne sont pas inscrits avec Intune.

## <a name="how-to-assign-an-app"></a>Comment affecter une application

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Gérer les applications**.
1. Dans la charge de travail **Gérer les applications**, choisissez **Gérer** > **Applications**.
2. Dans la liste du panneau d’applications, cliquez sur l’application que vous souhaitez affecter.
3. Dans le panneau <*Nom de l’application*> - **Vue d’ensemble**, choisissez **Gérer** > **Affectations**.
4. Choisissez **Sélectionner des groupes** puis, dans le panneau **Sélectionner des groupes**, sélectionnez les groupes Azure AD auxquels vous souhaitez affecter l’application.
5. Pour chaque application que vous choisissez, choisissez un **Type d’affectation** pour l’application :
    - **Disponible** : les utilisateurs effectuent l’installation de l’application à la demande à partir de l’application ou du site web de portail d’entreprise.
    - **Non applicable** : l’application n’est pas installée ni affichée dans le portail d’entreprise.
    - **Requis** : l’application est installée sur les appareils dans les groupes sélectionnés.
    - **Désinstaller** : l’application est désinstallée des appareils dans les groupes sélectionnés.
    - **Disponible avec ou sans inscription** : affectez cette application à des groupes d’utilisateurs dont les appareils ne sont pas inscrits avec Intune. Consultez le tableau ci-dessus pour l’aide.
6. Une fois que vous avez terminé, choisissez **Enregistrer**.

L’application est maintenant affectée au groupe que vous avez choisi.

Consultez la page [Guide pratique pour surveiller des applications](monitor-apps.md) pour plus d’informations pour vous aider à contrôler les affectations de l’application.

