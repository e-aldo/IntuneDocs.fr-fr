---
title: "Planifier vos groupes d’utilisateurs et d’appareils | Microsoft Docs"
description: "Planifiez des groupes pour répondre aux besoins de votre organisation."
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1e6727f633d2f74e1f1b018fad5f6765dfa4936b
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="plan-your-user-and-device-groups"></a>Planifier vos groupes d’utilisateurs et d’appareils

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les groupes créés dans Intune vous permettent de gérer vos utilisateurs et appareils avec une grande souplesse. Vous pouvez configurer des groupes en fonction des besoins de votre organisation en fonction :

- de l’emplacement géographique
- du service
- des caractéristiques matérielles
- du système d'exploitation
- du propriétaire de l’appareil (l’utilisateur ou la société)


## <a name="how-intune-groups-work"></a>Fonctionnement des groupes Intune


Voici la vue par défaut du nœud **Groupes** dans la console d’administration Intune :

![Capture d’écran de la vue par défaut du nœud Groupes dans la console Intune](../media/Intune_Planning_Groups_Default_small.png)

Les stratégies étant déployées sur des groupes, la hiérarchie des groupes est l’un des principaux points en matière de conception. Il est important de savoir que vous ne pouvez pas modifier le groupe parent d’un groupe une fois que vous avez créé le groupe. La façon dont vous créez vos groupes est extrêmement importante dès le moment où vous commencez à utiliser le service Intune. Vous trouverez ci-dessous des pratiques recommandées pour la conception d’une hiérarchie de groupes basée sur les besoins de votre organisation.

## <a name="group-membership-rules"></a>Règles d’appartenance au groupe

- Un groupe peut contenir des utilisateurs ou des appareils, mais pas les deux.

    * **Groupes d’appareils**. Ces groupes comprennent des ordinateurs et des appareils mobiles. Pour pouvoir ajouter un ordinateur à un groupe, vous devez d'abord l'inscrire. Pour pouvoir ajouter un appareil mobile à un groupe, vous devez configurer votre environnement pour qu’il prenne en charge les appareils mobiles et l’appareil doit être inscrit ou découvert dans Exchange ActiveSync.

    * **Groupes d’utilisateurs**. Un groupe peut avoir des utilisateurs de groupes de sécurité. Les groupes de sécurité sont synchronisés avec votre instance d’Active Directory. Si vous ne synchronisez pas avec Active Directory, vous pouvez créer ces groupes manuellement.

- Un appareil ou un utilisateur peut appartenir à plusieurs groupes.

- Un groupe peut inclure et exclure des membres selon les règles d'appartenance suivantes :

    * **Critères d’appartenance**. Il s’agit de règles dynamiques qu’Intune exécute pour inclure ou exclure des membres. Ces critères utilisent des groupes de sécurité et d’autres informations synchronisées avec votre instance locale d’Active Directory. Quand le groupe de sécurité ou les données sont modifiés, l’appartenance au groupe change quand vous effectuez une synchronisation avec Active Directory.

    * **Appartenance directe**. Il s'agit de règles statiques qui permettent d'ajouter ou d'exclure explicitement des membres. La liste des membres est statique.

-   Les services de domaine Active Directory (AD DS) ne sont pas nécessaires quand vous créez des groupes d’utilisateurs ou des groupes d’appareils comprenant des utilisateurs ou des ordinateurs. En revanche, pour que les groupes d’appareils puissent comprendre des appareils mobiles, votre environnement doit être configuré pour prendre en charge les appareils mobiles.

    En outre, les appareils doivent être découverts et ajoutés à Intune.

## <a name="group-relationship-rules"></a>Règles de relation de groupe

- Chaque groupe que vous créez doit avoir un groupe parent. Vous ne pouvez pas modifier le groupe parent d’un groupe une fois que vous avez créé le groupe.

- Lorsque vous ajoutez des utilisateurs ou des appareils à un groupe enfant :

    * Le groupe enfant est toujours un sous-ensemble du groupe parent.

    * Les nouveaux membres que vous ajoutez à un groupe enfant sont automatiquement ajoutés au groupe parent de ce groupe.

    * Vous ne pouvez pas ajouter un membre à un groupe enfant lorsque ce membre est exclu du groupe parent.

- L'appartenance à un groupe parent définit l'appartenance possible du groupe enfant.

- Lorsque vous supprimez un groupe parent, tous les groupes enfants sont supprimés.

- Vous pouvez déployer du contenu et des stratégies sur un groupe parent tout en excluant leur déploiement sur des groupes enfants.

- Vous pouvez ajouter un appareil ou un utilisateur spécifique à un groupe enfant si l’appareil ou l’utilisateur n’est pas membre du groupe parent. Dans ce cas, le nouveau membre du groupe enfant est ajouté au groupe parent.

    Toutefois, vous ne pouvez pas ajouter un membre à un groupe enfant si le membre est exclu du groupe parent.

- L'appartenance au groupe est récursive. Exemple :

    * **Patrice** est membre d'un seul groupe, le groupe de sécurité **Utilisateurs d'ordinateurs portables** .

    * Le groupe **Utilisateurs d'ordinateurs portables** est membre du groupe de sécurité **Utilisateurs approuvés** .

    * Vous créez un groupe dans Intune qui utilise une requête d'appartenance dynamique qui permet d'inclure les membres du groupe **Utilisateurs approuvés**. Le résultat est que votre groupe d'utilisateurs Intune inclut **Patrice**.

> [!TIP]
> Quand vous créez des groupes, réfléchissez à la manière dont vous allez appliquer la stratégie. Par exemple, vous pouvez définir des stratégies propres aux systèmes d’exploitation de vos appareils, ou des stratégies propres aux différents rôles ou unités d’organisation que vous avez déjà définis dans votre service Active Directory. Certains administrateurs trouvent utiles de créer des groupes d’appareils propres à iOS, Android et Windows, outre la création de groupes d’utilisateurs pour chaque rôle dans l’organisation.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a>Groupes intégrés
Intune fournit neuf groupes prédéfinis que vous ne pouvez ni modifier ni supprimer : <!--maybe a screen shot would be best?-->

-   **Tous les utilisateurs**
    -   Utilisateurs non groupés
-   **Tous les appareils**
    -   Tous les ordinateurs
    -   Tous les appareils mobiles
        -   Tous les appareils gérés par gestion directe
        -   Tous les appareils gérés par Exchange ActiveSync
    -   Tous les appareils d'entreprise
    -   Appareils non groupés

> [!NOTE]
> Votre devise : *garder les choses simples*. Si votre organisation n’a pas de besoins spécifiques, tels que ceux décrits dans les sections suivantes, faites au plus simple et adoptez la structure de groupes et les stratégies par défaut. Le service sera ainsi plus facile à gérer à long terme. La maintenance sera plus simple si vous pouvez traiter vos utilisateurs de manière uniforme. Avec peu de différenciation par groupe, vous aurez moins de stratégies à tenir à jour.


### <a name="all-users-and-devices-in-your-organization"></a>Tous les utilisateurs et appareils de votre organisation
Définissez un groupe parent pour tous les utilisateurs et appareils de votre organisation. Vous aurez sans doute des stratégies qui s’appliqueront à tous. Vous pouvez utiliser pour cela les groupes par défaut Intune **Tous les utilisateurs** et **Tous les appareils**. Les sous-groupes qui organisent les appareils par caractéristiques, comme par exemple un groupe pour les appareils BYOD et un autre pour les appareils d’entreprise, peuvent être les enfants des groupes parents **Tous les utilisateurs** et **Tous les appareils**.

## <a name="customize-groups-for-your-organization"></a>Personnaliser les groupes de votre organisation

### <a name="byod-and-corporate-owned-devices"></a>Appareils appartenant à l’entreprise et BYOD
Si votre organisation permet aux employés d’utiliser leurs propres appareils, fournit des appareils d’entreprise ou combine les deux, nous vous recommandons d’appliquer des stratégies distinctes pour ces catégories d’appareils.

Dans le cas du BYOD ou d’une combinaison, veillez à planifier les stratégies de manière à ce qu’elles ne transgressent pas des règles de confidentialité locales. Créez un groupe parent pour tous les utilisateurs qui utiliseront leurs propres appareils. Vous pouvez utiliser ce groupe pour appliquer des stratégies applicables à tous les utilisateurs de cette catégorie.

![Création d’un groupe parent BYOD](../media/Intune_Planning_Groups_BYOD_small.png)

De même, vous pouvez créer un groupe pour les utilisateurs d’appareils d’entreprise dans votre organisation :

![Groupes d’utilisateurs frères pour les appareils BYOD et d’entreprise](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a>Groupes pour des régions géographiques
Si votre organisation a besoin de stratégies pour des régions spécifiques, vous pouvez créer des groupes basés sur la région géographique. Vous pouvez les baser sur des groupes régionaux déjà créés dans votre instance d’Active Directory et les synchroniser avec votre service Azure Active Directory. Vous pouvez également créer des groupes régionaux directement dans Azure Active Directory.

Les captures d’écran suivantes montrent comment créer des groupes Intune basés sur des groupes synchronisés avec votre instance locale d’Active Directory. Ces exemples partent du principe que vous avez un groupe de sécurité Active Directory nommé **US Users Group**.

Tout d’abord, fournissez les informations générales.

![Capture d’écran de la zone Modifier le groupe](../media/Intune_Planning_Groups_AD_General_small.png)

Sous **Critères d’appartenance**, sélectionnez **US Users Group**, synchronisé avec Active Directory, comme groupe de sécurité à utiliser sous Règles d’adhésion.

![Capture d’écran de la boîte de dialogue Modifier le groupe](../media/Intune_Planning_Groups_AD_Criteria_small.png)

Passez en revue vos entrées, puis choisissez **Terminer** pour créer le groupe.

![Capture d’écran de la boîte de dialogue Modifier le groupe](../media/Intune_Planning_Groups_AD_Summary_small.png)

Dans notre exemple, nous avons également créé un groupe nommé **MEA** pour le Moyen-Orient et l’Asie.

> [!NOTE]
> Si l’appartenance au groupe n’est pas remplie d’après l’appartenance au groupe de sécurité, vérifiez que vous avez affecté des licences Intune aux membres du groupe.

### <a name="groups-for-specific-hardware"></a>Groupes pour du matériel spécifique
Si votre organisation impose d’avoir des stratégies applicables à des types de matériel spécifiques, vous pouvez créer des groupes sur la base de cette exigence. Vous pouvez baser les stratégies sur des groupes spécifiques déjà créés dans votre instance locale d’Active Directory, puis les synchroniser avec Azure Active Directory. Vous pouvez également créer des groupes directement dans Azure Active Directory. Dans cet exemple, nous utilisons **US Users Group** comme parent du groupe **Laptop Users**.

![Boîte de dialogue Sélectionner un groupe de sécurité](../media/Intune_Planning_Groups_Laptop_small.png)

À ce stade, la hiérarchie de votre groupe doit ressembler à la capture d’écran suivante. Comme vous le voyez, le groupe Intune **Laptop Users** contient maintenant des membres. Les stratégies appliquées à ce groupe seront appliquées aux utilisateurs d’ordinateurs portables BYOD de la région U.S.

![Affichage du groupe d’utilisateurs d’ordinateurs portables](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a>Groupes pour des systèmes d’exploitation spécifiques
Si votre organisation impose d’avoir des stratégies applicables à des systèmes d’exploitation spécifiques comme Android, iOS ou Windows, vous pouvez créer des groupes en conséquence. Comme dans les exemples précédents, vous pouvez les baser sur des groupes propres aux systèmes d’exploitation déjà créés dans votre instance locale d’Active Directory et les synchroniser avec Azure Active Directory. Vous pouvez également les créer directement dans votre instance d’Azure Active Directory.

En utilisant la même méthode que pour les exemples précédents, vous pouvez créer des groupes basés sur les utilisateurs <!--devices?--> qui utilisent des plateformes de système d’exploitation spécifiques.

> [!NOTE]
> Si certains de vos utilisateurs emploient plusieurs systèmes d’exploitation/plateformes mobiles et que vous n’avez pas de moyen automatisé pour classer les utilisateurs comme utilisateurs Android, iOS ou Windows, vous pouvez appliquer des stratégies au niveau de l’appareil. Vous disposerez ainsi d’une meilleure flexibilité dans l’application de stratégies propres au système d’exploitation.
>
> Vous ne pouvez pas approvisionner des groupes de manière dynamique en fonction du système d’exploitation de l’appareil. Vous devez pour cela utiliser des groupes de sécurité Active Directory ou Azure Active Directory.

![Groupe d’utilisateurs d’ordinateurs portables](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

Une fois que tous les groupes d’utilisateurs sont remplis en fonction des exigences de votre organisation, la hiérarchie de vos groupes doit ressembler à ceci :

![Vue de la hiérarchie de groupes](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Vous pouvez utiliser cette hiérarchie pour appliquer les stratégies de l’organisation.

### <a name="device-groups"></a>Groupes d'appareils
Vous pouvez également créer des groupes similaires pour les appareils, comme indiqué ici, en commençant par un groupe qui comprend tous les appareils appartenant aux employés (pour le scénario BYOD).

![Boîte de dialogue Créer un groupe](../media/Intune_Planning_Groups_Device_General_small.png)

Veillez à sélectionner **Tous les appareils (ordinateurs et appareils mobiles)** pour que le groupe comprenne tous les appareils BYOD :

![Définir les critères d'appartenance](../media/Intune_Planning_Groups_Device_Criteria_small.png)

Passez en revue vos entrées, puis choisissez **Terminer** pour créer le groupe BYOD.

![Boîte de dialogue Créer un groupe](../media/Intune_Planning_Groups_Device_Summary_small.png)

Continuez à créer des groupes d’appareils jusqu’à ce que la hiérarchie de groupes d’appareils ressemble à la hiérarchie de groupes d’utilisateurs. Votre nœud de groupes dans la console Intune doit maintenant ressembler à ceci :

![Vue de la hiérarchie de groupes Intune](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a>Hiérarchies de groupes et conventions d’affectation des noms
Pour simplifier la gestion des stratégies, nous vous recommandons de nommer chaque stratégie d’après la fonction, la plateforme et l’étendue auxquels elle s’applique. Utilisez un standard de nommage qui suit la structure de groupe que vous avez créée quand vous avez préparé l’application de vos stratégies.

Par exemple, pour une stratégie Android qui s’applique à tous les appareils mobiles Android de l’entreprise au niveau régional des États-Unis, vous pouvez nommer la stratégie **CO_US_Mob_Android_General**.

![Créer des stratégies pour Android](../media/Intune_planning_policy_android_small.png)

Le fait de nommer les stratégies de cette façon vous permet d’identifier rapidement les stratégies, leur utilisation et leur étendue dans le nœud **Stratégies**, comme indiqué ci-dessous :

![Liste de stratégies Intune](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a>Étapes suivantes
[Créer des groupes](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

