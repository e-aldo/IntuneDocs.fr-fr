---
title: "Guide pratique d’affectation d’applications aux groupes"
titleSuffix: Intune Azure preview
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
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b372d4ee505ca39a4739069e5798918ecde134ea
ms.openlocfilehash: abf45b835d13ef5fe4acb769194542611448504e
ms.lasthandoff: 02/18/2017

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

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Modifications apportées à la façon dont vous affectez des applications à des groupes dans la préversion d’Intune

Dans la préversion d’Intune Azure, vous n’utilisez plus des groupes Intune pour affecter des applications ; vous utilisez maintenant des groupes de sécurité Azure Active Directory (Azure AD). Pour cette raison, vous devez vous familiariser avec certaines modifications qui ont été apportées au fonctionnement des affectations d’applications, en particulier quand vous avez affecté des applications à des groupes enfants Intune.
Le plus important à noter est que le concept de groupes enfants n’existe pas dans Azure AD. Toutefois, certains groupes peuvent contenir les mêmes membres. Dans ce cas, le comportement entre Intune classique et la préversion d’Intune Azure est différent. Ceci est illustré dans le tableau suivant :

||||||
|-|-|-|-|-|
|**Intune classique (avant la migration du locataire)**|-|**Intune Azure (une fois la migration du locataire terminée)**|-|**Plus d’informations**|
|**Intention de déploiement de groupe parent**|**Intention de déploiement de groupe enfant**|**Intention d’affectation résultante pour les membres communs des groupes parents et enfants précédents**|**Action intentionnelle d’affectation résultante pour les membres du groupe parent**|-|    
|Disponible|Obligatoire|Obligatoire et disponible|Disponible|Obligatoire et disponible signifie que les applications affectées en fonction des besoins peuvent également être visibles dans l’application Portail d’entreprise.
|Non applicable|Disponible|Non applicable|Non applicable|Solution de contournement : Supprimez l’intention de déploiement « Non Applicable » du groupe parent Intune.
|Obligatoire|Disponible|Obligatoire et disponible|Obligatoire|-|
|Obligatoire et disponible<sup>1</sup>|Disponible|Obligatoire et disponible|Obligatoire et disponible|-|    
|Obligatoire|Non applicable|Obligatoire|Obligatoire|-|    
|Obligatoire et disponible|Non applicable|Obligatoire et disponible|Obligatoire et disponible|-|    
|Obligatoire|Désinstaller|Obligatoire|Obligatoire|-|    
|Obligatoire et disponible|Désinstaller|Obligatoire et disponible|Obligatoire et disponible|-|
<sup>1</sup> Pour les applications du Windows store iOS managées uniquement, quand vous les ajoutez à Intune et que vous les déployez en fonction des besoins, elles sont créées automatiquement avec des intentions Obligatoire et Disponible.

Vous pouvez effectuer les actions suivantes pour éviter les conflits de déploiement :

1.    Si vous avez déployé précédemment des applications dans des groupes parents et enfants Intune associés, il peut être préférable de supprimer ces déploiements avant de commencer la migration de votre locataire.
2.    Supprimez les groupes enfants des groupes parents et créez un groupe contenant les membres de l’ancien groupe enfant. Vous pouvez ensuite créer un déploiement d’application pour ce groupe.
Remarques : Si le groupe parent précédent était « Tous les utilisateurs », vous devez créer un groupe dynamique qui ne contient pas de membre du groupe enfant.
Vous devez apporter des modifications aux groupes dans le [Portail Azure](https://portal.azure.com/) pour les groupes d’utilisateurs et d’appareils. Le [Portail classique Azure](https://manage.windowsazure.com/) vous permet uniquement de modifier des groupes d’utilisateurs.


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

