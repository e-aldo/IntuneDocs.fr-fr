---
title: "Créer une stratégie de conformité des appareils macOS dans Microsoft Intune"
titleSuffix: 
description: "Créez une stratégie de conformité de l’appareil Microsoft Intune pour les appareils macOS afin de pouvoir spécifier des exigences qu’un appareil doit respecter pour être conforme."
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7703b8ea26d6ce53b82e806a78c788d14ae05b4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>Créer une stratégie de conformité pour les appareils macOS avec Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Une stratégie de conformité de l’appareil Intune pour macOS spécifie les règles et les paramètres que les appareils macOS doivent satisfaire pour être considérés comme conformes. Vous pouvez utiliser ces stratégies avec l’accès conditionnel pour autoriser ou bloquer l’accès aux ressources de l’entreprise, et vous pouvez générer des rapports sur les appareils et prendre des mesures en cas de non-conformité. Vous créez des stratégies de conformité de l’appareil pour chaque plateforme dans le portail Intune Azure.

## <a name="before-you-begin"></a>Avant de commencer

Avant de créer et d’affecter une stratégie de conformité des appareils, passez en revue les concepts liés à ce type de stratégie dans Intune.

- Pour en savoir plus sur les stratégies de conformité des appareils, consultez [Bien démarrer avec les stratégies de conformité des appareils](device-compliance.md).

> [!IMPORTANT]
> Vous devez créer des stratégies de conformité des appareils pour chaque plateforme. Les paramètres de stratégie de conformité des appareils Intune dépendent des fonctionnalités de plateforme, c’est-à-dire des paramètres exposés via le protocole MDM.

Le tableau suivant décrit la gestion des paramètres non conformes quand une stratégie de conformité est utilisée avec une stratégie d’accès conditionnel :


| Paramètre de stratégie | macOS 10.11 et ultérieur |
| --- | --- |
| **Configuration d’un code confidentiel ou mot de passe** | Corrigé |   
| **Chiffrement de l’appareil** | Corrigé (en définissant le code confidentiel) |
| **Profil de messagerie** | En quarantaine |
|**Version minimale du système d’exploitation** | En quarantaine |
| **Version maximale du système d’exploitation** | En quarantaine |  


**Corrigé** : le système d’exploitation de l’appareil applique la conformité. (Par exemple, l’utilisateur est obligé de définir un code confidentiel.)

**En quarantaine** : le système d’exploitation de l’appareil n’applique pas la conformité. (Par exemple, les appareils Android n’obligent pas l’utilisateur à chiffrer l’appareil.) Quand l’appareil n’est pas conforme, les actions suivantes se produisent :

- L’appareil est bloqué si une stratégie d’accès conditionnel s’applique à l’utilisateur.
- Le portail d’entreprise informe l’utilisateur des problèmes de conformité.

## <a name="macos-compliance-policy-settings"></a>Paramètres de stratégie de conformité macOS

Quand vous créez une stratégie de conformité des appareils avec Intune, vous avez le choix entre plusieurs catégories avec différents paramètres :

- Intégrité de l’appareil

- Propriétés de l’appareil

- Sécurité système

### <a name="device-health"></a>Intégrité de l’appareil

- **Exiger la protection de l’intégrité du système** : Choisissez **Exiger** pour vérifier si la protection de l’intégrité du système est activée sur vos appareils macOS.

### <a name="device-properties"></a>Propriétés des appareils

- **Version minimale du système d’exploitation** : Quand un appareil ne répond pas à la condition de version minimale du système d’exploitation, il est signalé comme non conforme. Un lien avec des informations sur la mise à niveau apparaît. L’utilisateur peut choisir de mettre à niveau son appareil. Ensuite, il peut accéder aux ressources de l’entreprise.

- **Version maximale du système d’exploitation** : Quand un appareil utilise une version de système d’exploitation ultérieure à celle spécifiée dans la règle, l’accès aux ressources d’entreprise est bloqué et l’utilisateur est invité à contacter son administrateur informatique. Jusqu’à ce qu’il y ait une modification de la règle pour autoriser la version du système d’exploitation, cet appareil ne peut pas être utilisé pour accéder aux ressources de l’entreprise.

### <a name="system-security-settings"></a>Paramètres de sécurité système

#### <a name="password"></a>Mot de passe

- **Exiger un mot de passe pour déverrouiller les appareils mobiles** : Choisissez **Exiger** pour obliger les utilisateurs à entrer un mot de passe pour accéder à leur appareil.

- **Mots de passe simples** : Choisissez **Bloquer** pour empêcher l’utilisateur de créer un mot de passe simple comme **1234** ou **1111**.

- **Longueur minimale du mot de passe** : Spécifie le nombre minimal de chiffres ou de caractères du mot de passe.

- **Type de mot de passe** : Indiquez si l’utilisateur doit créer un mot de passe **Alphanumérique** ou **Numérique**.

- **Nombre de caractères non alphanumériques dans le mot de passe** : Si vous définissez **Type de mot de passe obligatoire** sur **Alphanumérique**, ce paramètre spécifie le nombre minimal de jeux de caractères que le mot de passe doit avoir. 

    > [!NOTE]
    > Si vous définissez un nombre plus élevé, l’utilisateur doit créer un mot de passe plus complexe.

    > [!IMPORTANT]
    > Pour les appareils macOS, ce paramètre indique le nombre de caractères spéciaux (par exemple, **!** , **#**, **&amp;**) qui doivent être inclus dans le mot de passe.

- **Nombre maximal de minutes d’inactivité avant demande du mot de passe** : Spécifiez la durée d’inactivité après laquelle l’utilisateur doit rentrer son mot de passe.

- **Expiration du mot de passe (jours)** : Sélectionnez le nombre de jours (entre 1 et 250) avant expiration du mot de passe et création d’un nouveau.

- **Nombre de mots de passe précédents avant d’autoriser leur réutilisation** : Spécifiez le nombre de mots de passe précédents qui ne peuvent pas être réutilisés.

    > [!IMPORTANT]
    > Quand les exigences de mot de passe sont changées sur un appareil macOS, elles n’entrent pas en vigueur tant que l’utilisateur ne change pas son mot de passe. Par exemple, si vous définissez une limite de longueur de mot de passe à huit chiffres et que l’appareil macOS a actuellement un mot de passe à 6 chiffres, l’appareil reste conforme tant que l’utilisateur n’a pas mis à jour son mot de passe sur l’appareil.

## <a name="to-create-a-device-compliance-policy"></a>Pour créer une stratégie de conformité de l’appareil

1. Accédez au [portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification Intune.

2. Une fois que vous êtes correctement connecté, le **tableau de bord Azure** apparaît.

3. Choisissez **Tous les services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.

4. Choisissez **Intune** pour afficher le **tableau de bord Intune**.

5. Choisissez **Conformité de l’appareil**, puis choisissez **Stratégies** sous **Gérer**.

6. Choisissez **Créer une stratégie**.

7. Tapez un nom et une description, puis choisissez la plateforme à laquelle vous souhaitez appliquer cette stratégie.

8. Le volet **Stratégie de conformité Mac** s’ouvre. Choisissez les catégories de paramètres de conformité des appareils (**Sécurité du système**, **Intégrité de l’appareil** et **Propriétés de l’appareil**) pour spécifier vos paramètres.

10. Une fois que vous avez choisi vos paramètres, choisissez **OK** sous chaque catégorie de paramètres de conformité des appareils.

11. Choisissez **OK**, puis **Créer**.

## <a name="assign-user-groups"></a>Affectation de groupes d’utilisateurs

Pour attribuer une stratégie de conformité à des utilisateurs, choisissez une stratégie que vous avez configurée. Vous trouverez les stratégies existantes dans le volet **Conformité de l’appareil - Stratégies**.

1. Choisissez la stratégie de conformité des appareils à affecter aux utilisateurs, puis **Affectations**. Cette opération ouvre le volet dans lequel vous pouvez sélectionner des **groupes de sécurité Azure Active Directory** que vous affectez à la stratégie.

2. Choisissez **Groupes sélectionnés** pour ouvrir la page qui affiche les groupes de sécurité Azure AD.

3. Choisissez **Enregistrer** pour affecter la stratégie de conformité des appareils aux groupes de sécurité Azure AD.

4. Une fois que vous avez terminé d’affecter la stratégie de conformité des appareils à vos groupes, vous pouvez fermer le volet **Affectations**.

    > [!TIP]
    > Par défaut, les appareils vérifient la conformité toutes les huit heures, mais les utilisateurs peuvent forcer ce processus dans l’application Portail d’entreprise Intune.

## <a name="next-steps"></a>Étapes suivantes

[Guide pratique pour surveiller les stratégies de conformité des appareils](compliance-policy-monitor.md)
