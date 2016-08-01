---
title: "Planifier vos groupes d’utilisateurs et d’appareils | Microsoft Intune"
description: "Planifiez des groupes pour répondre aux besoins de votre organisation."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: bb3e96ad4276819ad46ab2a5e1a8deb931bd421a


---

# Planifier vos groupes d’utilisateurs et d’appareils
Les groupes dans Intune permettent de gérer les utilisateurs et les appareils avec une grande souplesse. Vous pouvez configurer des groupes en fonction des besoins de votre organisation en fonction :

- de l’emplacement géographique
- department
- des caractéristiques matérielles
- du système d'exploitation
- du propriétaire de l’appareil (l’utilisateur ou la société)


## Fonctionnement des groupes Intune


La vue par défaut du nœud Groupes dans la console d’administration Intune est la suivante :

![Capture d’écran de la vue par défaut du nœud Groupes dans la console Intune](/intune/media/Intune_Planning_Groups_Default_small.png)

Les stratégies étant déployées dans des groupes, la hiérarchie des groupes est l’une des principales considérations en matière de conception. Sachez également que vous ne pouvez plus modifier le groupe parent d’un groupe une fois que celui-ci a été créé. La conception de vos groupes est donc extrêmement importante dès le moment où vous commencez à utiliser le service Intune. Vous trouverez ci-dessous quelques-unes des pratiques recommandées pour la conception d’une hiérarchie de groupes basée sur les besoins de votre organisation.

## Règles d’appartenance au groupe

1. Un groupe peut contenir des utilisateurs ou des appareils, mais pas les deux.

    * **Groupes d’appareils** : ces groupes incluent à la fois les ordinateurs et les appareils mobiles. Pour pouvoir ajouter un ordinateur à un groupe, vous devez d'abord l'inscrire. Pour pouvoir ajouter un appareil mobile à un groupe, votre environnement doit d'abord être configuré pour prendre en charge des appareils mobiles et les appareils doivent être inscrits ou détectés à partir d'Exchange ActiveSync.

    * **Groupes d’utilisateurs** : un groupe peut contenir des utilisateurs issus de groupes de sécurité, lesquels sont des groupes qui se synchronisent à partir d’Active Directory. Si vous n'utilisez pas de synchronisation Active Directory, vous pouvez créer manuellement ces groupes.

2. Un appareil ou un utilisateur peut appartenir à plusieurs groupes.

3. Un groupe peut inclure et exclure des membres selon les règles d'appartenance suivantes :

    * **Critères d’appartenance** : règles dynamiques qu’Intune exécute pour inclure ou exclure des membres. Ces critères utilisent des **groupes de sécurité** et d'autres informations synchronisées à partir de votre annuaire Active Directory (AD) local. Lorsque le groupe de sécurité ou les données sont modifiés, l'appartenance au groupe change lorsque vous effectuez une synchronisation avec AD.

    * **Appartenance directe** : règles statiques qui permettent d’ajouter ou d’exclure explicitement des membres. La liste des membres est statique.

4. Les services de domaine Active Directory (AD DS) ne sont pas requis pour créer des groupes d'utilisateurs ou d'appareils comprenant des utilisateurs ou des ordinateurs, mais pour que les groupes d'appareils comprennent des appareils mobiles, votre environnement doit être configuré pour prendre en charge des appareils mobiles.

    En outre, les appareils doivent être découverts et ajoutés à Intune.

## Règles de relation de groupe

1. Chaque groupe que vous créez doit avoir un groupe parent et vous ne pouvez pas modifier le groupe parent d'un groupe après sa création.

2. Lorsque vous ajoutez des utilisateurs ou des appareils à un groupe enfant :

    * Les groupes enfants sont toujours des sous-ensembles du groupe parent.

    * Les nouveaux membres que vous ajoutez à un groupe enfant sont automatiquement ajoutés au groupe parent de ce groupe.

    * Vous ne pouvez pas ajouter un membre à un groupe enfant lorsque ce membre est exclu du groupe parent.

3. L'appartenance à un groupe parent définit l'appartenance possible du groupe enfant.

4. Lorsque vous supprimez un groupe parent, tous les groupes enfants sont supprimés.

5. Vous pouvez déployer du contenu et des stratégies sur un groupe parent tout en excluant leur déploiement sur des groupes enfants.

6. Vous pouvez ajouter un appareil ou un utilisateur spécifique à un groupe enfant qui n'est pas un membre du groupe parent. Si vous procédez ainsi, le nouveau membre du groupe est ajouté au groupe parent.

    Toutefois, vous ne pouvez pas ajouter un membre à un groupe enfant qui est exclu du groupe parent.

7. L'appartenance au groupe est récursive. Exemple :

    * **Patrice** est membre d'un seul groupe, le groupe de sécurité **Utilisateurs d'ordinateurs portables** .

    * Le groupe **Utilisateurs d'ordinateurs portables** est membre du groupe de sécurité **Utilisateurs approuvés** .

    * Vous créez un groupe dans Intune qui utilise une requête d'appartenance dynamique qui permet d'inclure les membres du groupe **Utilisateurs approuvés**. Le résultat est que votre groupe d'utilisateurs Intune inclut **Patrice**.

> [!TIP]
> Quand vous créez vos groupes, réfléchissez à la manière dont vous allez appliquer la stratégie. Par exemple, vous pouvez définir des stratégies spécifiques aux systèmes d'exploitation de vos appareils et d'autres spécifiques aux différents rôles de votre organisation ou aux unités d'organisation vous avez déjà définies dans Active Directory. Certains estiment qu'il est utile d'avoir des groupes d'appareils spécifiques pour iOS, Android et Windows, ainsi que des groupes d'utilisateurs pour chaque rôle organisationnel.

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your company. Then create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful naming your policies so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy you'll want to communicate it to your users, so after you create the more general groups and policies pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## Groupes intégrés
Intune fournit neuf groupes prédéfinis que vous ne pouvez pas modifier ni supprimer : <!--maybe a screen shot would be best?-->

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
> Votre devise : *garder les choses simples*. Si votre organisation n’a pas de besoins spécifiques, tels que ceux décrits ci-dessous, faites au plus simple et adoptez la structure de groupes et les stratégies par défaut pour faciliter à long terme la gestion du service. La maintenance sera plus facile si vous pouvez traiter vos utilisateurs de manière égale. Moins il y aura de différenciation entre les groupes, moins vous aurez à gérer de stratégies.


### Tous les utilisateurs et appareils de votre organisation
Définissez un groupe parent pour tous les utilisateurs et appareils de votre organisation, car vous aurez sans doute des stratégies qui s’appliqueront à tous. Vous pouvez utiliser pour cela les groupes par défaut **Tous les utilisateurs** et **Tous les appareils** dans Intune. Les sous-groupes qui organisent les appareils par caractéristiques, comme par exemple un groupe pour le BYOD (bring your own device) et un autre pour les appareils d’entreprise, peuvent être les enfants des groupes parents **Tous les utilisateurs** et **Tous les appareils**.

## Personnalisation des groupes de votre organisation.

### Appareils appartenant à l’entreprise et BYOD
Si votre organisation permet aux employés d’utiliser leurs propres appareils au travail (BYOD), fournit des appareils d’entreprise (CO), ou combine les deux, nous vous recommandons d’appliquer des stratégies en fonction de ces deux catégories d’appareils.

Dans le cas du BYOD ou d’une combinaison, veillez à planifier les stratégies de manière à ce qu’elles ne transgressent pas des règles de confidentialité locales. Créez un groupe parent pour tous les utilisateurs qui utiliseront leurs propres appareils. Vous pouvez ensuite utiliser ce groupe pour appliquer des stratégies applicables à tous les utilisateurs de cette catégorie.

![Capture d’écran de la création d’un groupe parent BYOD](/intune/media/Intune_Planning_Groups_BYOD_small.png)

De même, vous pouvez créer un groupe pour les utilisateurs d’appareils d’entreprise dans votre organisation :

![Capture d’écran des groupes d’utilisateurs frères pour le BYOD et les appareils d’entreprise](/intune/media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### Groupes pour des régions géographiques
Si votre organisation a besoin de stratégies pour des régions spécifiques, vous pouvez créer des groupes en fonction de la région géographique. Vous pouvez les baser sur les groupes régionaux que vous avez déjà créés dans Active Directory (AD) et de les synchroniser sur Azure AD. Vous pouvez également les créer directement dans Azure AD.

Ces captures d’écran montrent comment créer des groupes Intune basés sur des groupes synchronisés à partir de votre annuaire Active Directory local. Cet exemple part du principe que vous avez un groupe de sécurité AD nommé **US Users Group**.

1. Tout d’abord, fournissez les informations générales.

![Capture d’écran de la zone Modifier le groupe](/intune/media/Intune_Planning_Groups_AD_General_small.png)

Sous Critères d’appartenance, sélectionnez **US Users Group**, synchronisé à partir d’Active Directory, comme groupe de sécurité à utiliser sous Règles d’adhésion.

![Boîte de dialogue Modifier le groupe](/intune/media/Intune_Planning_Groups_AD_Criteria_small.png)

Vérifiez si tout est correct, puis cliquez sur **Terminer** pour terminer la création du groupe.

![Boîte de dialogue Modifier le groupe](/intune/media/Intune_Planning_Groups_AD_Summary_small.png)

Dans notre exemple, nous avons également créé un groupe Middle East and Asia, MEA.

> [!NOTE]
> Si l’appartenance au groupe n’est pas remplie d’après l’appartenance au groupe de sécurité, vérifiez que vous avez affecté des licences Intune à ces membres.

### Groupes pour du matériel spécifique
Si votre organisation impose d’avoir des stratégies applicables à des types de matériel spécifiques, vous pouvez créer des groupes sur la base de cette exigence. Vous pouvez les baser sur des groupes spécifiques que vous avez déjà créés dans votre AD local et les synchroniser sur Azure AD. Vous pouvez également les créer directement dans Azure AD. Dans cet exemple, nous utilisons **US Users Group** comme parent du groupe **Laptop Users**.

![Sélectionnez la boîte de dialogue Groupe de sécurité](/intune/media/Intune_Planning_Groups_Laptop_small.png)

À ce stade, la hiérarchie des groupes doit ressembler à ce qui suit. Comme vous le voyez, le groupe Intune **Laptop Users** contient maintenant des membres. Les stratégies appliquées à ce groupe sont désormais appliquées aux utilisateurs d’ordinateurs portables BYOD de la région US.

![Affichage du groupe d’utilisateurs d’ordinateurs portables](/intune/media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### Groupes pour des systèmes d’exploitation spécifiques
Si votre organisation impose d’avoir des stratégies applicables à des systèmes d’exploitation spécifiques comme Android, iOS ou Windows, vous pouvez créer des groupes en conséquence. Comme dans les exemples précédents, vous pouvez les baser sur des groupes de système d’exploitation spécifiques que vous avez déjà créés dans votre AD local et les synchroniser sur Azure AD. Vous pouvez également les créer directement dans Azure AD.

En suivant la même méthode que dans les exemples précédents, nous pouvons créer des groupes basés sur les utilisateurs <!--devices?--> avec des plateformes de système d’exploitation spécifiques.

> [!NOTE]
> Si certains de vos utilisateurs utilisent plusieurs systèmes d’exploitation/plateformes mobiles et que vous n’avez pas de moyen automatisé pour classer les utilisateurs en tant qu’utilisateurs Android, iOS ou Windows, vous pouvez appliquer des stratégies au niveau de l’appareil pour disposer d’une meilleure flexibilité dans l’application de stratégies propres au système d’exploitation.
>
> Vous ne pouvez pas approvisionner des groupes de manière dynamique en fonction du système d’exploitation de l’appareil. Vous devez pour cela utiliser des groupes de sécurité AD ou AAD.

![Affichage du groupe d’utilisateurs d’ordinateurs portables](/intune/media/Intune_Planning_Groups_OS_Hierachy_small.png)

Une fois que tous les groupes d’utilisateurs sont remplis en fonction de ces exigences organisationnelles, votre hiérarchie de groupes doit ressembler à ceci :

![Vue de la hiérarchie de groupes](/intune/media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

Vous pouvez utiliser cette hiérarchie pour appliquer les stratégies de l’organisation de manière appropriée.

### Groupes d'appareils
Vous pouvez également créer des groupes similaires pour les appareils, comme indiqué ci-dessous, en commençant par un groupe qui comprend tous les appareils appartenant aux employés (pour le scénario BYOD) :

![Boîte de dialogue Créer un groupe](/intune/media/Intune_Planning_Groups_Device_General_small.png)

Veillez à sélectionner **Tous les appareils (ordinateurs et appareils mobiles)** pour que le groupe comprenne tous les appareils BYOD :

![Définir les critères d'appartenance](/intune/media/Intune_Planning_Groups_Device_Criteria_small.png)

Vérifiez que tout est correct, puis cliquez sur **Terminer** pour créer le groupe BYOD.

![Boîte de dialogue Créer un groupe](/intune/media/Intune_Planning_Groups_Device_Summary_small.png)

Continuez à créer des groupes d’appareils jusqu’à ce que la hiérarchie de groupes d’appareils ressemble à la hiérarchie de groupes d’utilisateurs. Votre nœud de groupes dans la console Intune doit maintenant ressembler à ceci :

![Vue de la hiérarchie de groupes Intune](/intune/media/Intune_Groups_Hierarchy_Final_Small.png)

## Hiérarchies de groupes et conventions d’affectation des noms
Pour simplifier la gestion des stratégies, nous vous recommandons de nommer chaque stratégie selon la fonction, la plateforme et l’étendue auxquels elle s’applique. Cette norme de nommage doit suivre la structure des groupes que vous avez créée en vue de l’application de vos stratégies.

Par exemple, pour une stratégie Android appliquée à tous les appareils mobiles Android de l’entreprise au niveau régional des États-Unis, la stratégie peut se nommer **CO_US_Mob_Android_General**.

![Créer des stratégies pour Android](/intune/media/Intune_planning_policy_android_small.png)

Le fait de nommer les stratégies de cette façon vous permet d’identifier rapidement les stratégies, leur utilisation et leur étendue prévues à partir du nœud des stratégies de la console, comme indiqué ci-dessous :

![Liste de stratégies Intune](/intune/media/Intune_planning_policy_view_small.png)

## Étapes suivantes
[Créer des groupes](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


