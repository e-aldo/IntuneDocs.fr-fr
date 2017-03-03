---
title: Migration vers des groupes Azure Active Directory | Microsoft Docs
description: "Comment vos groupes sont migrés d’Intune vers Azure AD"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: dd4c8f1d810338912b4926be8419ccf9a52ae722
ms.openlocfilehash: 8d3900da91c89700b97d8774f893d82d3a74ea83
ms.lasthandoff: 12/22/2016


---

# <a name="a-new-way-of-using-groups-in-intune"></a>Une nouvelle façon d’utiliser les groupes dans Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Nous avez tenu compte de vos commentaires et apporté des modifications à l’utilisation des groupes dans Microsoft Intune.
Nous migrons actuellement tous les groupes Intune de nos clients vers des groupes de sécurité Azure Active Directory.

Vous pourrez ainsi utiliser la même expérience de groupes dans l’ensemble des applications Enterprise Mobility + Security et Azure AD. En outre, vous pourrez utiliser PowerShell et l’API Graph pour étendre et personnaliser cette nouvelle fonctionnalité.

Les groupes de sécurité Azure AD prennent en charge tous les types de déploiements Intune pour les utilisateurs et les appareils. En outre, vous pouvez utiliser des groupes dynamiques Azure AD qui se mettent automatiquement à jour en fonction des attributs que vous fournissez. Par exemple, vous pouvez créer un groupe d'appareils exécutant iOS 9. Chaque fois qu’un nouvel appareil fonctionnant sous iOS 9 est inscrit, il sera automatiquement ajouté au groupe dynamique.

## <a name="when-is-this-happening"></a>Quand cela se passe-t-il ?

Le processus de migration est en cours d’exécution en ce moment même. Vous serez averti quand votre tour viendra.
Si votre migration a déjà eu lieu, vous verrez un message ressemblant à ceci lorsque vous essayez d’accéder à des groupes à partir de la console Intune classique :

![Message indiquant que les groupes ont été migrés.](http://i.imgur.com/72KRaXj.png)

## <a name="what-wont-be-available"></a>Qu'est-ce qui ne sera plus disponible ?

Certaines fonctionnalités existantes des groupes Intune ne sont pas disponibles dans Azure AD :

- Les groupes Intune **Utilisateurs non groupés** et **Appareils non groupés** ne seront pas pris migrés.
- L’option permettant d'**exclure des membres spécifiques** d’un groupe existant dans la console Intune n’existe pas dans le portail Azure. Toutefois, vous pouvez utiliser un groupe de sécurité Azure AD avec des règles avancées pour répliquer ce comportement. Par exemple, vous pouvez créer une règle avancée qui inclut toutes les personnes de votre service Ventes dans un groupe de sécurité, mais pas celles qui contiennent le mot « Assistant » dans le titre de leur fonction, en utilisant cette règle avancée : `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.
- Le groupe **Tous les appareils gérés par Exchange ActiveSync** intégré à la console Intune ne sera pas migré vers Azure AD. Toutefois, vous pouvez toujours accéder aux informations sur les appareils EAS gérés à partir du portail Azure.
- Vous ne pourrez pas filtrer les rapports par groupes dans la console Intune classique.
<!--- - Custom group targeting of notification rules will not be available. ROB I took this out as I couldn't replicate the behavior. --->

## <a name="how-to-get-ready"></a>Mise en route

- Lisez les rubriques Azure AD suivantes pour en savoir plus sur les groupes de sécurité Azure AD et leur fonctionnement :
    -  [Gestion de l’accès aux ressources avec les groupes Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
    -  [Gestion des groupes dans Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
- Vous pouvez supprimer les groupes Intune que vous n’utilisez plus avant de migrer.
-  Assurez-vous que les administrateurs qui ont besoin de créer des groupes sont ajoutés au rôle Azure AD **Administrateur de service Intune**. Notez que le rôle d’administrateur de service Azure AD n’a pas d'autorisations **Gérer des groupes**.
-  Si vous utilisez des groupes avec l’option **Exclure des membres spécifiques**, vous pouvez modifier ces groupes afin qu'ils n'aient pas besoin d'exclusions, ou utiliser des règles avancées dans votre requête Azure AD afin d'obtenir le même résultat.


## <a name="what-happens-to-intune-groups"></a>Qu'advient-il aux groupes Intune ?

| Groupes dans Intune|Groupe dans Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Groupe d’utilisateurs statique|Groupe de sécurité Azure AD statique|
|Groupe d’utilisateurs dynamique|Groupes de sécurité Azure AD statiques avec une hiérarchie de groupes de sécurité Azure AD|
|Groupe d'appareils statique|Groupe de sécurité Azure AD statique|
|Groupe d'appareils dynamique|Groupe de sécurité Azure AD dynamique|
|Groupe avec une condition d’inclusion|Groupe de sécurité Azure AD statique contenant des membres statiques ou dynamiques de la condition d'inclusion dans Intune.|
|Un groupe avec une condition d’exclusion|Non migré|
|Les groupes intégrés **Tous les utilisateurs**, **Utilisateurs non groupés**, **Tous les appareils**, **Appareils non groupés**, **Tous les ordinateurs**, **Tous les appareils mobiles**, **Tous les appareils gérés par la gestion des appareils mobiles** et **Tous les appareils gérés par EAS**|Groupes de sécurité Azure AD.|

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

## <a name="what-happens-to-policies-and-apps-youve-already-deployed"></a>Que se passe-t-il pour les stratégies et les applications que vous avez déjà déployées ?

Les applications et les stratégies continuent d'être déployées sur les groupes, comme avant. Toutefois, vous devrez désormais gérer ces groupes à partir du portail Azure au lieu de la console Intune classique.


## <a name="how-to-get-more-information"></a>Comment obtenir plus d'informations

Contacter notre équipe migration : [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).    
     


