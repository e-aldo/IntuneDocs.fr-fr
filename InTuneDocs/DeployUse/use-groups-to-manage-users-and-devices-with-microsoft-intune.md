---
title: "Utiliser des groupes pour gérer les utilisateurs et les appareils | Microsoft Intune"
description: "Créez et gérez des groupes à l’aide de l’espace de travail Groupes."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 06/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb9b01ce-9b9b-4c2a-bf99-3879c0bdaba5
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7c680c43b8c9120755ec3c652cf7ec1cbcc3472
ms.openlocfilehash: b13e2ff2f4822d71ef8cff9d835e32b99cb3e4ab


---
# Utiliser des groupes pour gérer les utilisateurs et les appareils dans Microsoft Intune

Cette rubrique explique comment créer des groupes dans Intune. Elle fournit également des informations sur l’évolution de la gestion des groupes dans mois à venir. Pour en savoir plus sur l’approche *actuelle* de la gestion des groupes, consultez la section [Créer des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](#Create-groups-to-manage-users-and-devices-with-Microsoft-Intune) dans cette rubrique.

## Notice concernant les prochaines améliorations apportées à l’expérience d’administration pour les groupes

Suite à vos commentaires concernant le souhait d’avoir une expérience de regroupement et de ciblage unique dans Enterprise Mobility + Security, nous avons décidé de convertir les groupes Intune en groupes de sécurité basés sur Azure Active Directory. Cela permet d’unifier la gestion des groupes dans Intune et Azure Active Directory (Azure AD). La nouvelle expérience vous évitera d’avoir à dupliquer les groupes entre les services, et fournit une extensibilité à l’aide de PowerShell et Graph. 

### Comment cela m’affecte-t-il aujourd’hui ?
Cette modification ne vous affecte pas aujourd’hui, mais nous pouvons vous indiquer les nouveautés à venir :

-   En septembre, les nouveaux comptes approvisionnés après la publication de service mensuelle utiliseront les groupes de sécurité Active Directory Azure plutôt que les groupes d’utilisateurs Intune.   
-   En octobre, les nouveaux comptes approvisionnés après la publication de service mensuelle gèreront les groupes d’utilisateurs et d’appareils dans le portail Azure AD. Aucun impact sur les clients existants
-   En novembre, l’équipe de produit Intune commencera la migration des clients existants vers la nouvelle expérience de gestion de groupe basée sur Azure AD. Tous les groupes d’utilisateurs et d’appareils qui sont aujourd’hui dans Intune seront migrés vers les groupes de sécurité Azure AD. La migration se fera par lots à partir du mois de novembre. Nous ne démarrerons pas la migration tant que nous ne serons pas sûrs de pouvoir minimiser l’impact sur votre travail quotidien et garantir qu’il n’y aura aucun impact sur les utilisateurs finaux. Nous vous fournirons également un avis avant la migration de votre compte.


### Quand et comment serai-je migré vers la nouvelle expérience de groupes ?
Les clients actuels seront migrés sur une période donnée. Nous finalisons actuellement la planification de cette migration et mettrons à jour cette rubrique dans quelques semaines pour vous fournir plus de détails. Vous recevrez un avis avant la migration. Si vous avez des questions concernant la migration, contactez notre équipe de migration à l’adresse [intunegrps@microsoft.com](intunegrps@microsoft.com).

### Qu’arrivera-t-il à mes groupes d’utilisateurs et d’appareils existants ?
 Les groupes d’utilisateurs et d’appareils que vous avez créés seront migrés vers des groupes de sécurité Azure AD. Les groupes Intune par défaut, comme le groupe Tous les utilisateurs, seront migrés uniquement si vous les utilisez dans des déploiements au moment de la migration. Il est possible que la migration soit plus complexe pour certains groupes. Nous vous avertirons si des étapes supplémentaires sont nécessaires pour la migration.

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

-   Vous ne pourrez pas exclure des membres ou des groupes lors de la création d’un groupe. Toutefois, les groupes dynamiques Azure AD vous permettront d’utiliser des attributs pour créer des règles avancées pour exclure les membres en fonction de critères.
-   Les groupes **Utilisateurs non groupés** et **Appareils non groupés** ne seront pas pris en charge. Ces groupes ne seront pas migrés.


#### Fonctionnalités dépendantes de groupe

-   Le rôle Administrateur de service n’aura pas les autorisations **Gérer les groupes**.
-   Vous ne pourrez pas regrouper d’appareils Exchange ActiveSync.  Votre groupe **Tous les appareils gérés par EAS** sera converti de groupe en affichage de rapport.
-  Le glissement des groupes dans les rapports ne sera pas disponible.
-  Le ciblage de groupe personnalisé des règles de notification ne sera pas disponible.

### Que dois-je faire pour me préparer à cette modification ?
 Voici quelques recommandations qui vous aideront à effectuer cette transition :

- Nettoyez les groupes Intune dont vous n’avez plus besoin avant la migration.
- Évaluez votre utilisation de l’exclusion dans les groupes et modifiez la conception de vos groupes pour ne plus avoir besoin d’utiliser d’exclusion.
-  Si certains de vos administrateurs n’ont pas l’autorisation de créer des groupes dans Azure AD, demandez à votre administrateur Azure AD de les ajouter au rôle Azure AD **Administrateur de service Intune**.


## Créer des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune

Cette section décrit comment créer des groupes Intune dans la console d’administration Intune.

Pour créer et gérer des groupes, utilisez l’espace de travail **Groupes** dans la console d’administration Microsoft Intune. La page **Vue d'ensemble des groupes** contient des récapitulatifs des états qui vous aident à identifier et hiérarchiser les problèmes qui requièrent votre attention :

-   Alertes
-   Mises à jour logicielles
-   Endpoint Protection
-   Stratégie
-   Gestion des logiciels

En outre, votre hiérarchie de groupe s’affiche avec des récapitulatifs d’état pour vous aider à identifier et à résoudre les problèmes des membres d’un groupe sélectionné.


> [!TIP]
> Quand vous créez vos groupes, tenez compte de la façon dont vous allez appliquer la stratégie. Par exemple, vous pouvez définir des stratégies spécifiques aux systèmes d'exploitation de vos appareils et d'autres spécifiques aux différents rôles de votre organisation ou aux unités d'organisation vous avez déjà définies dans Active Directory. Certains estiment qu'il est utile d'avoir des groupes d'appareils spécifiques pour iOS, Android et Windows, ainsi que des groupes d'utilisateurs pour chaque rôle organisationnel.
>
> Vous souhaiterez probablement créer une stratégie par défaut qui s'applique à l'ensemble des groupes et des appareils pour établir les exigences de base de votre entreprise en matière de conformité. Créez ensuite des stratégies plus spécifiques pour les catégories d'utilisateurs et d'appareils les plus étendues, par exemple des stratégies de messagerie pour chacun des systèmes d'exploitation de vos appareils.
>
> Veillez à affecter des noms explicites à vos stratégies pour pouvoir facilement les identifier par la suite. Voici un exemple de nom de stratégie descriptif : **Stratégie de messagerie WP pour toute l'entreprise**.
>
> Il est souhaitable de communiquer chaque stratégie de restriction que vous créez à vos utilisateurs. Par conséquent, au terme de la création des groupes et des stratégies d'ordre général, prêtez attention à la façon dont vous créez les groupes de plus petit taille pour réduire les communications inutiles.


## Créer un groupe d'appareils

1.  Dans la console d’administration Intune, choisissez **Groupes** &gt; **Vue d’ensemble** &gt; **Créer un groupe**.

2.  Spécifiez un nom et une éventuelle description pour le groupe, sélectionnez un groupe d’appareils en tant que groupe parent. Choisissez **Suivant**.

3.  Dans la page **Définir les critères d'appartenance**, sélectionnez le type des appareils que le groupe va inclure. Les options supplémentaires pour configurer le groupe varient selon le type des appareils que vous sélectionnez :

    -   **Ordinateur** : indiquez si vous souhaitez inclure tous les membres du groupe parent, et spécifiez les unités d’organisation (UO) et les domaines que vous voulez inclure ou exclure. Les informations sur les unités d'organisation et les domaines d'un ordinateur sont obtenues à partir de l'inventaire.

    -   **Mobile** : indiquez si vous souhaitez inclure uniquement les appareils mobiles gérés par Intune, ceux gérés par Exchange ActiveSync ou les deux à la fois.

    -   **Tous les appareils** : cette option permet d’inclure tous les appareils sans exclusions basées sur des critères.

4.  Dans la page **Définir l'appartenance directe**, incluez et excluez les appareils individuels que vous spécifiez en cliquant sur **Parcourir**. Si vous utilisez l'option pour sélectionner des appareils qui ne sont pas dans le groupe parent que vous avez spécifié, ces appareils sont automatiquement ajoutés au groupe parent.


5.  Sur la page **Résumé**, passez en revue les actions à entreprendre. Choisissez **Terminer**.

Le groupe récemment créé est disponible dans la liste **Groupes**, dans l’espace de travail **Groupes**, sous le groupe parent. À ce stade, vous pouvez également modifier ou supprimer le groupe.

## Créer un groupe d'utilisateurs

1.  Dans la console d’administration Intune, choisissez **Groupes** &gt; **Vue d’ensemble** &gt; **Créer un groupe**.

2.  Spécifiez un nom et une éventuelle description pour le groupe, sélectionnez un groupe d’utilisateurs en tant que groupe parent. Choisissez **Suivant**.

3.  Dans la page **Définir les critères d'appartenance**, indiquez si vous souhaitez inclure tous les membres du groupe parent ou démarrer avec un groupe vide.  Vous pouvez alors inclure ou exclure des membres en fonction des **groupes de sécurité** d’utilisateurs que vous configurez manuellement dans le [Centre d’administration Office 365](http://go.microsoft.com/fwlink/?LinkId=698854) ou qui se synchronisent à partir de votre annuaire Active Directory local. Si l'appartenance à un groupe de sécurité change, l'appartenance des groupes d'utilisateurs en fonction de ce groupe de sécurité peut également changer.

    > [!IMPORTANT]
    > À l’heure actuelle, si votre groupe inclut des membres issus de groupes de sécurité ou de responsables spécifiques et que vous excluez aussi des membres de groupes spécifiques, les membres que vous avez inclus au départ sont supprimés. Pour créer un groupe comprenant à la fois des membres inclus et des membres exclus, nous vous recommandons de créer d’abord un groupe parent contenant les membres inclus, puis de créer un enfant de ce groupe dans lequel vous répertorierez les membres exclus. Vous pourrez dès lors utiliser ce groupe enfant selon les besoins pour les stratégies et profils Intune et la distribution d’applications.

    > [!NOTE]
    > Dans le portail de gestion Azure, vous pouvez créer un groupe basé sur le responsable des utilisateurs. Le groupe sera dynamique, changeant à mesure que des employés sont ajoutés ou supprimés dans l’équipe du responsable dans Azure Active Directory. La procédure à suivre pour créer un groupe Azure basé sur un responsable est décrite à la page [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/en-us/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/) dans la section intitulée **Pour configurer un groupe en tant que groupe « Responsable »**.


4.  Dans la page **Définir l'appartenance directe**, incluez et excluez les utilisateurs individuels que vous spécifiez en cliquant sur **Parcourir**. Si vous utilisez l'option pour sélectionner des utilisateurs qui ne sont pas dans le groupe parent que vous avez spécifié, ces appareils sont automatiquement ajoutés au groupe parent. En bas de la boîte de dialogue **Sélectionner les membres**, vous trouverez l’option pour ajouter un utilisateur manuellement. Cela est utile si vous souhaitez ajouter un utilisateur qui ne dispose pas encore d’un appareil inscrit.


5.  Sur la page **Résumé**, passez en revue les actions à entreprendre. Choisissez **Terminer**.

Le groupe récemment créé est disponible dans la liste **Groupes**, dans l’espace de travail **Groupes**, sous le groupe parent. À ce stade, vous pouvez également modifier ou supprimer le groupe.

> [!TIP]
> Les groupes de sécurité constituent un bon point de départ pour remplir les groupes d'utilisateurs. Dans la mesure où vos groupes de sécurité définissent qui a accès aux ressources, vous pouvez très bien en faire des groupes d’utilisateurs Intune. Les groupes de sécurité synchronisés entre Active Directory et Azure Active Directory, ou créés directement dans Azure Active Directory par le biais du Centre d’administration Office 365 ou du portail d’administration Azure, sont tous disponibles pour créer des groupes d’utilisateurs dans Intune.

## Personnaliser les vues pour les rôles d’administrateur
Les vues de groupes filtrées vous permettent de personnaliser la vue que les administrateurs peuvent voir en fonction de leur rôle et de limiter les groupes que chaque administrateur informatique peut gérer. Elles peuvent être utiles quand :

-   vos administrateurs informatiques doivent uniquement pouvoir déployer des éléments pour des utilisateurs et des appareils spécifiques ;

-   vous souhaitez afficher uniquement les groupes appropriés à chaque administrateur informatique.

Vous pouvez configurer des vues de groupes filtrées pour les administrateurs de service dans la console d’administration Intune. Pour plus d’informations, consultez [Informations à connaître avant de commencer à utiliser Microsoft Intune](/intune/get-started/what-to-know-before-you-start-microsoft-intune).

Une fois que vous avez configuré des vues de groupes filtrées pour un administrateur de service, celui-ci :

-   peut afficher et sélectionner uniquement les groupes que vous avez spécifiés lors du déploiement de logiciels ou de stratégies ou lors de l'utilisation de rapports ;

-   ne reçoit pas d'informations d'état dans les pages suivantes de la console d'administration :

    -   **Présentation du système**

    -   **Vue d'ensemble des groupes**

    -   **Vue d'ensemble de Endpoint Protection**

    -   **Vue d'ensemble des alertes**

    -   **Vue d'ensemble du logiciel**

    -   **Vue d'ensemble de la stratégie**

### Configurer des vues de groupes filtrées

1.  Dans la console d’administration Intune, choisissez **Administration** &gt; **Gestion des administrateurs** &gt; **Administrateurs de service**.

2.  Sélectionnez l'administrateur de service pour lequel vous souhaitez filtrer des groupes, puis cliquez sur **Gérer les groupes**.

3.  Dans la boîte de dialogue **Sélectionner les groupes qui seront visibles pour cet administrateur de service**, ajoutez les groupes auxquels l'administrateur de service sélectionné pourra accéder, puis cliquez sur **OK**.

Une fois les vues de groupes filtrées configurées, l'administrateur informatique pourra afficher et sélectionner uniquement les groupes que vous avez sélectionnés.

## Gérer vos groupes
Une fois vos groupes créés, vous devez les gérer en fonction des besoins de votre organisation.

Vous pouvez modifier votre groupe pour modifier son nom et sa description ainsi que les membres de ce groupe.

Vous pouvez supprimer un groupe qui ne répond plus aux besoins de votre organisation. Le fait de supprimer un groupe ne supprime pas les utilisateurs appartenant à ce groupe.

## Étapes suivantes

### Vérifiez votre conception
Après avoir configuré vos groupes et stratégies, vérifiez les implications pratiques de votre conception en consultant la **Valeur prévue** et l’**État**.

1. Sélectionnez un appareil dans un groupe d'appareils et parcourez les catégories d'informations en haut de l'écran.
2. Sélectionnez **Stratégie** . Voici une capture d'écran des paramètres de stratégie d'un appareil Android qui illustre les informations affichées à l'écran.

![Exemple de stratégie de paramètres iOS](../media/Intune-Device-Policy-v.2.jpg)

Chaque stratégie contient une **Valeur prévue** et un **État**. La valeur prévue est la valeur que vous souhaitez obtenir lors de l'attribution de la stratégie. L’état est ce vous obtenez au bout du compte quand toutes les stratégies qui s’appliquent à l’appareil, ainsi que les restrictions et les conditions requises du matériel et du système d’exploitation, sont regroupées.  La capture d'écran illustre clairement ce point à travers deux exemples :

-   **Autoriser les mots de passe simples** est défini avec la valeur **Oui**, comme indiqué dans la colonne **Valeur prévue**, mais son **État** a la valeur **Non applicable**. Cela est dû au fait que les mots de passe simples ne sont pas pris en charge par les appareils Android.

-   De même, l’élément de stratégie développé **Paramètres de messagerie pour les appareils iOS** n’est pas appliqué à cet appareil, car il s’agit d’un appareil Android.

> [!NOTE]
> N’oubliez pas que quand deux stratégies avec différents niveaux de restriction s’appliquent au même appareil ou utilisateur, la stratégie la plus restrictive prévaut dans la pratique.



<!--HONumber=Aug16_HO4-->


