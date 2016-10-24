---
title: Migration vers des groupes Azure Active Directory | Microsoft Intune
description: "Comment vos groupes sont migrés d’Intune vers Azure AD"
keywords: 
author: nbigman
ms.author: nbigman
manager: angerobe
ms.date: 10/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 03b69afa-3548-4033-9039-191528f3fd99
translationtype: Human Translation
ms.sourcegitcommit: d92c9ffe42b36770a32c28941de3c402aec9dd68
ms.openlocfilehash: 08bcc258f64e6385ae6fa648ddb8f2b5fe68942e


---

## Nouvelle expérience d’administration pour les groupes
    
Suite à vos commentaires concernant le souhait d’avoir une expérience de regroupement et de ciblage unique dans Enterprise Mobility & Security, nous avons décidé de convertir les groupes Intune en groupes de sécurité basés sur Azure Active Directory. Cela permet d’unifier la gestion des groupes dans Intune et Azure Active Directory (Azure AD). La nouvelle expérience vous évitera d’avoir à dupliquer les groupes entre les services, et fournit une extensibilité à l’aide de PowerShell et Graph. 

### Quand et comment serai-je migré vers la nouvelle expérience de groupes ?
Les clients actuels seront migrés sur une période donnée, qui ne commencera pas avant décembre 2016. Vous recevrez un avis avant la migration de vos groupes. Si vous avez des questions concernant la migration, contactez notre équipe de migration à l’adresse [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).

### Quelles seront les nouvelles fonctionnalités à ma disposition ?
Voici les nouvelles fonctionnalités introduites : 
 
-    Les groupes de sécurité Azure AD seront pris en charge dans Intune pour tous les types de déploiements. 
-    Les groupes de sécurité Azure AD prendront en charge le regroupement d’appareils et d’utilisateurs.
-    Les groupes de sécurité Azure AD prendront en charge les groupes dynamiques avec des attributs d’appareils Intune. Par exemple, vous pourrez regrouper des appareils de manière dynamique en fonction de la plateforme (comme iOS). Ainsi, quand un nouvel appareil iOS sera inscrit dans votre organisation, il sera ajouté automatiquement au groupe d’appareils dynamique iOS.
-    Partage des expériences d’administration pour la gestion de groupe entre Azure AD et Intune.
- Le *rôle d’administrateur de Service Intune* sera ajouté à Azure AD pour permettre aux administrateurs de service dans Intune d’effectuer des tâches de gestion de groupe dans Azure AD.

 
### Quelles seront les fonctionnalités Intune qui ne seront pas disponibles ?
Malgré l’amélioration de l’expérience de groupe, certaines fonctionnalités Intune ne seront pas disponibles après la migration.

#### Fonctionnalité de gestion de groupe

-   Vous ne pourrez pas exclure des membres ou des groupes lors de la création d’un groupe. Cependant, les groupes dynamiques Azure AD vous permettent d’utiliser des attributs pour créer des règles avancées permettant d’exclure les membres en fonction de critères. Par exemple, vous pouvez créer une règle avancée qui inclut toutes les personnes de votre service Ventes dans un groupe de sécurité, mais pas celles qui contiennent le mot « Assistant » dans le titre de leur fonction, avec cette règle avancée : `(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`. Pour plus d’informations, consultez [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-   Les groupes **Utilisateurs non groupés** et **Appareils non groupés** ne seront pas pris en charge. Ces groupes ne seront pas migrés.

#### Fonctionnalités dépendantes de groupe

-   Le rôle Administrateur de service n’aura pas les autorisations **Gérer les groupes**.
-   Vous ne pourrez pas regrouper d’appareils Exchange ActiveSync.  Votre groupe **Tous les appareils gérés par EAS** sera converti de groupe en affichage de rapport.
-  Le glissement des groupes dans les rapports ne sera pas disponible.
-  Le ciblage de groupe personnalisé des règles de notification ne sera pas disponible.

### Que dois-je faire pour me préparer à cette modification ?
 Voici quelques recommandations qui vous aideront à effectuer cette transition :
 
- Nettoyez les groupes Intune dont vous n’avez plus besoin avant la migration.
- Évaluez votre utilisation de l’exclusion dans les groupes et pensez à reconcevoir vos groupes pour ne plus avoir besoin d’utiliser l’exclusion ou pour pouvoir utiliser des règles avancées pour atteindre le même objectif.
-  Si certains de vos administrateurs n’ont pas l’autorisation de créer des groupes dans Azure AD, demandez à votre administrateur Azure AD de les ajouter au rôle Azure AD **Administrateur de service Intune**.

Vous pouvez également en savoir plus sur les groupes de sécurité Azure AD :
-  Pour une vue d’ensemble, lisez [Gestion de l’accès aux ressources avec les groupes Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/).
-  Pour plus d’informations sur la façon de créer et de gérer des groupes Azure AD, consultez [Gestion des groupes dans Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/).
-  Pour plus d’informations sur les règles avancées des groupes de sécurité, consultez [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).

> [!NOTE]
Vous remarquerez peut-être que la documentation sur les groupes de sécurité Azure AD ne traite pas de la création de groupes pour les appareils. Cette fonctionnalité sera activée dans Azure AD avant le début de la migration des groupes Intune.

## Informations détaillées sur la migration
Voici les informations détaillées sur la façon dont vos groupes Intune seront migrés vers des groupes de sécurité Azure AD.

### Migration des groupes existants

| Le groupe Intune devient...|...groupe de sécurité Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Groupes d’utilisateurs statiques ciblés par la stratégie Intune|Groupes de sécurité Azure AD statiques contenant les mêmes utilisateurs|
|Groupes d’utilisateurs dynamiques ciblés par la stratégie Intune|Groupes de sécurité Azure AD statiques avec une hiérarchie de groupes de sécurité Azure AD|
|Groupes d’appareils statiques ciblés par la stratégie Intune|Groupes de sécurité Azure AD statiques avec des appareils|
|Groupes d’appareils dynamiques avec des attributs d’appareils, qui sont ciblés par la stratégie Intune|Groupes de sécurité Azure AD dynamiques avec des attributs d’appareils|
|Groupe avec une condition d’inclusion|Groupe de sécurité Azure AD statique distinct qui contient un groupe + tous les membres statiques/dynamiques que la condition d’inclusion avait autorisés dans Intune|
|Un groupe avec une condition d’exclusion|...ne sera pas migré. Les conditions d’exclusion ne sont pas prises en charge lors de la création de groupes statiques dans Azure AD. Une condition d’exclusion peut être utilisée lors de la création d’un groupe dynamique dans Azure AD.|
|Groupes par défaut **Tous les utilisateurs**, **Utilisateurs non groupés**, **Tous les appareils**, **Appareils non groupés**, **Tous les ordinateurs**, **Tous les appareils mobiles**, **Tous les appareils gérés par la gestion des appareils mobiles** et **Tous les appareils gérés par EAS**, que vous utilisez dans la stratégie Intune  |Groupes de sécurité Azure AD. Les groupes par défaut qui ne sont pas utilisés doivent être créés par le client quand ils sont nécessaires, en utilisant des groupes dynamiques.|

### Modifications dans les vues hiérarchiques
Vue hiérarchique des groupes dans Intune : une relation parent-enfant dans Intune était une relation de sur-ensemble – sous-ensemble, alors que ce n’est pas le cas dans Azure AD. Un enfant peut avoir des membres que n’avait pas le parent. Les groupes peuvent également être cycliques par nature dans Azure AD : un groupe parent peut être un enfant d’un groupe enfant.

### Conversion des attributs lors de la migration
Les attributs sont des propriétés d’appareils qui peuvent être utilisés dans la définition de groupes. Ce tableau décrit comment ces critères sont migrés vers les groupes de sécurité Azure AD.

| Attribut Intune|Attribut Azure AD|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|Attribut d’unité d’organisation pour les groupes d’appareils|Attribut d’unité d’organisation pour les groupes dynamiques. Valeurs d’attributs mises à la disposition de l’administrateur appartenant à chaque locataire en l’ajoutant comme un des composants du locataire pour affichage.|
|Attribut de nom de domaine pour les groupes d’appareils|Attribut de nom de domaine pour les groupes dynamiques. Valeurs d’attributs mises à la disposition de l’administrateur appartenant à chaque locataire en l’ajoutant comme un des composants du locataire pour affichage|
|Groupe de sécurité comme attribut pour les groupes d’utilisateurs|Les groupes ne peuvent pas être des attributs dans les requêtes dynamiques Azure AD. Les groupes dynamiques peuvent contenir seulement des attributs spécifiques à des utilisateurs ou à des appareils.|
|Attribut de gestionnaire pour les groupes d’utilisateurs|Règle avancée pour l’attribut *gestionnaire* dans les groupes dynamiques|
|Tous les utilisateurs du groupe d’utilisateurs parent|Groupe statique avec ce groupe comme membre|
|Tous les appareils mobiles du groupe d’appareils parent|Groupe statique avec ce groupe comme membre|
|Tous les appareils mobiles gérés par Microsoft Intune Direct Management|Attribut de type de gestion avec « MDM » comme valeur pour le groupe dynamique|
|Tous les appareils mobiles gérés par EAS|Les appareils EAS ne peuvent pas être regroupés dans Azure AD. Votre groupe **Tous les appareils gérés par EAS** sera converti de groupe en affichage de rapport.|
|Groupes imbriqués dans des groupes statiques |Groupes imbriqués dans des groupes statiques|
|Groupes imbriqués dans des groupes dynamiques|Groupe dynamique avec un seul niveau d’imbrication|


## Migration des stratégies
Pendant la migration des groupes, vous continuez à gérer vos stratégies dans la console Intune. Dans la console Intune, un lien vous dirige vers votre console de gestion Azure, où vous allez gérer vos groupes. Vos stratégies continuent d’être déployées sur les groupes de sécurité Azure AD qui existent parallèlement à vos anciens groupes Intune.

Une fois toutes les fonctionnalités Intune migrées vers le portail de gestion Azure (autour du premier trimestre 2017), vous pourrez y gérer les stratégies et les groupes.

     
### Voir aussi
[Gestion de l’accès aux ressources avec les groupes Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-manage-groups/)

[Gestion des groupes dans Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-manage-groups/)

[Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/)



<!--HONumber=Oct16_HO2-->


