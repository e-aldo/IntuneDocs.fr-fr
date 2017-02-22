---
title: "Bien démarrer avec les groupes dans la version préliminaire du portail Intune Azure | Microsoft Docs"
description: "Découvrez les nouveautés concernant les groupes dans la version préliminaire du portail Intune Azure"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: 27a9c9d8269b302fa9735972056d38e7919f42b5


---

# <a name="get-started-with-groups"></a>Bien démarrer avec les groupes

[!INCLUDE[azure preview](../includes/azure_preview.md)]

Nous avons tenu compte de vos commentaires et apporté des modifications à l’utilisation des groupes dans Microsoft Intune.
Si vous utilisez Intune à partir du portail Azure, vos groupes Intune ont été migrés vers des groupes de sécurité Azure Active Directory.

Vous pourrez ainsi utiliser la même expérience de groupes dans l’ensemble des applications Enterprise Mobility + Security et Azure AD. En outre, vous pourrez utiliser PowerShell et l’API Graph pour étendre et personnaliser cette nouvelle fonctionnalité.

Les groupes de sécurité Azure AD prennent en charge tous les types de déploiements Intune pour les utilisateurs et les appareils. En outre, vous pouvez utiliser des groupes dynamiques Azure AD qui se mettent automatiquement à jour en fonction des attributs que vous fournissez. Par exemple, vous pouvez créer un groupe d'appareils exécutant iOS 9. Chaque fois qu’un nouvel appareil fonctionnant sous iOS 9 est inscrit, il sera automatiquement ajouté au groupe dynamique.

## <a name="what-is-not-available"></a>Qu’est-ce qui n’est pas disponible ?

Certaines des fonctionnalités relatives aux groupes Intune que vous utilisiez peut-être auparavant ne sont pas disponibles dans Azure AD :

- Les groupes Intune **Utilisateurs non groupés** et **Appareils non groupés** ne sont plus disponibles.
- L’option permettant **d’exclure des membres spécifiques** d’un groupe n’existe pas dans le portail Azure. Toutefois, vous pouvez utiliser un groupe de sécurité Azure AD avec des règles avancées pour répliquer ce comportement. Par exemple, vous pouvez créer une règle avancée qui inclut toutes les personnes de votre service Ventes dans un groupe de sécurité, mais pas celles qui contiennent le mot « Assistant » dans le titre de leur fonction, en utilisant cette règle avancée : `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Le groupe **Tous les appareils gérés par Exchange ActiveSync** intégré à la console Intune n’a pas été migré vers Azure AD. Toutefois, vous pouvez toujours accéder aux informations sur les appareils EAS gérés à partir du portail Azure.


## <a name="how-to-get-started"></a>Commencer

- Lisez les rubriques Azure AD suivantes pour en savoir plus sur les groupes de sécurité Azure AD et leur fonctionnement :
    -  [Gestion de l’accès aux ressources avec les groupes Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Gestion des groupes dans Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Assurez-vous que les administrateurs qui ont besoin de créer des groupes sont ajoutés au rôle Azure AD **Administrateur de service Intune**. Notez que le rôle d’administrateur de service Azure AD n’a pas d'autorisations **Gérer des groupes**.
-  Si vous utilisiez des groupes avec l’option **Exclure des membres spécifiques**, vous pouvez modifier ces groupes afin qu’ils n’aient pas besoin d’exclusions, ou utiliser des règles avancées dans votre requête Azure AD afin d’obtenir le même résultat.


## <a name="what-happened-to-intune-groups"></a>Qu’est-il advenu aux groupes Intune ?

| Groupes dans Intune|Groupe dans Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Groupe d’utilisateurs statique|Groupe de sécurité Azure AD statique|
|Groupe d’utilisateurs dynamique|Groupes de sécurité Azure AD statiques avec une hiérarchie de groupes de sécurité Azure AD|
|Groupe d'appareils statique|Groupe de sécurité Azure AD statique|
|Groupe d'appareils dynamique|Groupe de sécurité Azure AD dynamique|
|Groupe avec une condition d’inclusion|Groupe de sécurité Azure AD statique contenant des membres statiques ou dynamiques de la condition d’inclusion dans Intune|
|Un groupe avec une condition d’exclusion|Non migré|
|Les groupes intégrés **Tous les utilisateurs**, **Utilisateurs non groupés**, **Tous les appareils**, **Appareils non groupés**, **Tous les ordinateurs**, **Tous les appareils mobiles**, **Tous les appareils gérés par la gestion des appareils mobiles** et **Tous les appareils gérés par EAS**|Groupes de sécurité Azure AD|

Dans Intune, tous les groupes doivent avoir un groupe parent. Les groupes peuvent contenir uniquement des membres de leur groupe parent. Dans Azure AD, les groupes enfants peuvent contenir des membres qui n'appartiennent pas au groupe parent.

Les attributs sont des propriétés d’appareils qui peuvent être utilisés dans la définition de groupes. Ce tableau décrit comment ces critères sont migrés vers les groupes de sécurité Azure AD.

| Attribut dans Intune|Attribut dans Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Attribut d’unité d’organisation pour les groupes d’appareils|Attribut d’unité d’organisation pour les groupes dynamiques.|
|Attribut de nom de domaine pour les groupes d’appareils|Attribut de nom de domaine pour les groupes dynamiques.|
|Groupe de sécurité comme attribut pour les groupes d’utilisateurs|Les groupes ne peuvent pas être des attributs dans les requêtes dynamiques Azure AD. Les groupes dynamiques peuvent contenir seulement des attributs spécifiques à des utilisateurs ou à des appareils.|
|Attribut de gestionnaire pour les groupes d’utilisateurs|Règle avancée pour l’attribut *gestionnaire* dans les groupes dynamiques|
|Tous les utilisateurs du groupe d’utilisateurs parent|Groupe statique avec ce groupe comme membre|
|Tous les appareils mobiles du groupe d’appareils parent|Groupe statique avec ce groupe comme membre|
|Tous les appareils mobiles gérés par Intune|Attribut de type de gestion avec « MDM » comme valeur pour le groupe dynamique|
|Groupes imbriqués dans des groupes statiques |Groupes imbriqués dans des groupes statiques|
|Groupes imbriqués dans des groupes dynamiques|Groupe dynamique avec un seul niveau d’imbrication|

## <a name="what-happens-to-policies-and-apps-you-previously-deployed"></a>Que se passe-t-il pour les stratégies et les applications que vous aviez déployées ?

Les applications et les stratégies continuent d'être déployées sur les groupes, comme avant. Toutefois, vous devrez désormais gérer ces groupes à partir du portail Azure au lieu de la console Intune classique.



<!--HONumber=Feb17_HO1-->


