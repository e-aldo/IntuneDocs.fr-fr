---
# required metadata

title: Résoudre des conflits de stratégie entre les objets de stratégie de groupe et Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Résoudre des conflits de stratégie entre les objets de stratégie de groupe (GPO) et Microsoft Intune
Intune utilise des stratégies qui vous aident à gérer les paramètres sur les ordinateurs que vous gérez. Par exemple, vous pouvez utiliser une stratégie pour contrôler les paramètres du Pare-feu Windows sur les ordinateurs. La majorité des paramètres Intune sont identiques aux paramètres que vous pouvez configurer avec la stratégie de groupe Windows. Toutefois, il est possible que, dans certains cas, les deux méthodes entrent en conflit l'une avec l'autre.

Lorsque les conflits se produisent, la stratégie de groupe au niveau du domaine est prioritaire sur la stratégie Intune, sauf si l’ordinateur ne peut pas ouvrir de session sur le domaine. Dans ce cas, la stratégie Intune est appliquée à l’ordinateur client.

## Que faire si vous utilisez la stratégie de groupe ?
Vérifiez que toutes les stratégies que vous appliquez ne sont pas gérées par la stratégie de groupe. Pour mieux éviter les conflits, vous pouvez employer une ou plusieurs des méthodes suivantes :

-   Déplacez vos ordinateurs vers une unité d’organisation Active Directory à laquelle les paramètres de la stratégie de groupe ne sont pas appliqués avant d’installer le client Intune. Vous pouvez également bloquer l’héritage de la stratégie de groupe sur les unités d’organisation contenant les ordinateurs inscrits dans Intune auxquels vous ne voulez pas appliquer les paramètres de la stratégie de groupe.

-   Utilisez un filtre WMI ou un filtre de sécurité pour restreindre les objets de stratégie de groupe aux seuls ordinateurs qui ne sont pas gérés par Intune. Pour obtenir des informations et des exemples sur la façon de procéder, consultez [Comment filtrer les objets de stratégie de groupe existants pour éviter les conflits avec la stratégie Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter) ci-après.

-   Désactivez ou supprimez les objets de stratégie de groupe en conflit avec les stratégies Intune.

Pour plus d'informations sur Active Directory et la stratégie de groupe Windows, consultez votre documentation Windows Server.

## Comment filtrer les objets de stratégie de groupe existants pour éviter les conflits avec la stratégie Intune
Si vous avez identifié des objets de stratégie de groupe dont les paramètres sont en conflit avec les stratégies Intune, vous pouvez utiliser l’une des méthodes de filtrage suivantes pour restreindre ces objets aux seuls ordinateurs qui ne sont pas gérés par Intune.

### Utiliser les filtres WMI
Les filtres WMI appliquent sélectivement les objets de stratégie de groupe aux ordinateurs répondant aux conditions d'une requête. Pour appliquer un filtre WMI, déployez une instance de classe WMI sur tous les ordinateurs de l’entreprise avant d’inscrire des ordinateurs dans le service Intune.

#### Application des filtres WMI à un GPO

1.  Créez un fichier objet de gestion en copiant et collant ce qui suit dans un fichier texte, puis enregistrez le fichier à un emplacement de votre choix sous le nom **WIT.mof**. Ce fichier contient l’instance de classe WMI que vous déployez aux ordinateurs à inscrire au service Intune.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Utilisez un script de démarrage ou une stratégie de groupe pour déployer le fichier. Ce qui suit est la commande de déploiement pour le script de démarrage. L’instance de classe WMI doit être déployée avant d’inscrire les ordinateurs clients au service Intune.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;chemin d’accès au fichier MOF&gt;\wit.mof**

3.  Exécutez l’une des deux commandes suivantes pour créer les filtres WMI selon que les objets de stratégie de groupe que vous voulez filtrer s’appliquent aux PC qui sont gérés avec Intune ou à ceux qui ne sont pas gérés à l’aide d’Intune.

    -   Pour les GPO s’appliquant aux ordinateurs non gérés à l’aide d’Intune, utilisez les éléments suivants :

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   Pour les GPO s’appliquant aux ordinateurs gérés à l’aide d’Intune, utilisez les éléments suivants :

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Modifiez le GPO dans la console de gestion des stratégies de groupe pour appliquer le filtre WMI que vous avez créé à l'étape précédente.

    -   Pour les GPO ne devant s’appliquer qu’aux ordinateurs que vous souhaitez gérer à l’aide d’Intune, appliquez le filtre **WindowsIntunePolicyEnabled=1**.

    -   Pour les GPO ne devant s’appliquer qu’aux ordinateurs que vous ne souhaitez pas gérer à l’aide d’Intune, appliquez le filtre **WindowsIntunePolicyEnabled=0**.

Pour plus d’informations sur l’application des filtres WMI dans la stratégie de groupe, consultez le billet de blog [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences (Filtrage de sécurité, filtrage WMI et ciblage au niveau de l’élément dans les préférences de la stratégie de groupe)](http://go.microsoft.com/fwlink/?LinkId=177883).

### Utiliser des filtres de groupe de sécurité
La stratégie de groupe vous permet d'appliquer des objets de stratégie de groupe (GPO) aux seuls groupes de sécurité spécifiés dans la zone **Filtrage de sécurité** de la console de gestion des stratégies de groupe d'un GPO sélectionné. Par défaut, les GPO s’appliquent aux **Utilisateurs authentifiés**.

-   Dans le composant logiciel enfichable **Utilisateurs et ordinateurs Active Directory**, créez un groupe de sécurité contenant les ordinateurs et les comptes d’utilisateur que vous ne souhaitez pas gérer avec Intune. Par exemple, vous pouvez nommer le groupe **Pas dans Microsoft Intune**.

-   Dans la console de gestion des stratégies de groupe, sous l’onglet **Délégation** pour le GPO sélectionné, cliquez avec le bouton droit de la souris sur le nouveau groupe de sécurité pour déléguer les autorisations **Lecture** et **Appliquer la stratégie de groupe** appropriées aux utilisateurs et aux ordinateurs dans le groupe de sécurité. (Les autorisations**Appliquer stratégie de groupe** sont disponibles dans la boîte de dialogue **Options avancées** ).

-   Ensuite, appliquez le nouveau filtre de groupe de sécurité à un GPO sélectionné et supprimez le filtre par défaut **Utilisateurs authentifiés** .

Le nouveau groupe de sécurité doit être maintenu comme inscription dans les modifications de service Intune.

### Voir aussi
[Gérer des PC Windows avec Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


