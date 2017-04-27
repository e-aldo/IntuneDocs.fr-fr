---
title: "Rôles Intune (RBAC) pour Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez comment le contrôle d’accès en fonction du rôle (RBAC) vous permet de contrôler qui peut exécuter des actions et apporter des modifications."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: e60edd86289e0fca2aa03660d8ce782e373c0236
ms.lasthandoff: 03/15/2017


---

# <a name="intune-roles-rbac-for-microsoft-intune"></a>Rôles Intune (RBAC) pour Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

En d'autres termes, les **rôles** Intune (ou RBAC) vous permettent de contrôler les utilisateurs pouvant effectuer diverses actions Intune, et à qui ces actions s’appliquent. Vous pouvez utiliser les rôles intégrés, qui couvrent des scénarios courants dans Intune, ou vous pouvez créer vos propres rôles.

Un rôle est défini par :

- **Définition** : le nom d’un rôle et les autorisations qu’il configure.
- **Membres** : l’utilisateur ou groupe d’utilisateurs qui recevra ces autorisations.
- **Étendue** : les utilisateurs ou les appareils qu'une personne spécifique (le membre) peut gérer.
- **Affectation** : lors de la définition, les membres et l'étendue ont été configurés, le rôle est affecté.

## <a name="built-in-roles"></a>Rôles intégrés

Les rôles suivants sont intégrés dans Intune et vous pouvez personnaliser ces rôles, ou les affecter à des groupes sans configuration supplémentaire.

- **Administrateur Intune** : dispose d’autorisations complètes pour toutes les opérations Intune.
- **Gestionnaire d’applications** : gestion et déploiement d'applications et de profils.
- **Gestionnaire de stratégie de configuration** : gestion et déploiement de paramètres de configuration et de profils.
- **Opérateur de support technique** : exécution de tâches à distance et affichage d’informations sur l’utilisateur et l’appareil.
- **Opérateur en lecture seule** : affichage d'informations dans le portail Intune sans la possibilité d’apporter des modifications.


## <a name="custom-roles"></a>Rôles personnalisés

Si aucun des rôles intégrés ne correspond à vos besoins, vous pouvez créer votre propre rôle en sélectionnant des paramètres qui couvrent la plupart des fonctionnalités d’Intune. Vous pouvez voir une liste des paramètres disponibles plus loin dans cette rubrique.

### <a name="example"></a>Exemple

Vous engagez un nouvel administrateur informatique qui se chargera de déployer et gérer des applications pour les utilisateurs de votre bureau de Londres. Les utilisateurs sont dans un groupe Active Directory Azure nommé **London**. Vous souhaitez vous assurer de que l’administrateur informatique ne peut pas déployer des applications pour les utilisateurs de n’importe quel autre bureau. Vous prenez les mesures suivantes :

- Vous affectez le rôle intégré **Gestionnaire d'applications** avec les propriétés suivantes :
    - **Membres** : sélectionnez un groupe qui contient l’administrateur informatique qui déploie des applications
    - **Étendue** : sélectionnez le groupe Azure AD **London**.

    >[!IMPORTANT]
    >Pour créer, modifier ou affecter des rôles, votre compte doit posséder l'une des autorisations suivantes dans Azure AD :
    >- **Administrateur AAD général**
    >- **Administrateur de service Intune**

### <a name="how-to-create-a-custom-role"></a>Procédure de création d'un rôle personnalisé

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Rôles Intune**.
![Charge de travail de contrôle d’accès](./media/axxess-control.png)
1. Dans le panneau **Rôles** de la charge de travail **Contrôle d’accès**, choisissez **Ajouter un élément personnalisé**.
2. Dans le panneau **Ajouter un élément personnalisé**, entrez un nom et une description pour le nouveau rôle, puis cliquez sur **Autorisations**.
3. Dans le panneau **Autorisations**, sélectionnez les autorisations que vous souhaitez utiliser avec ce rôle. Utilisez la liste de référence des paramètres de rôles personnalisés plus loin dans cette rubrique pour vous aider.
4. Une fois terminé, cliquez sur **OK**.
5. Dans le panneau **Ajouter un rôle personnalisé**, cliquez sur **Créer**.

Le nouveau rôle s’affiche dans la liste sur le panneau **Rôles**.

## <a name="how-to-assign-a-role"></a>Affectation d’un rôle

1. Dans le panneau **Rôles** de la charge de travail **Contrôle d’accès**, choisissez le rôle intégré ou personnalisé que vous souhaitez affecter.
2. Dans le panneau <*Nom de rôle*> - **Propriétés**, choisissez **Gérer** > **Affectations**. Dans ce panneau, vous pouvez aussi modifier ou supprimer des rôles existants.
3. Dans le panneau suivant, choisissez **Affecter**.
4. Dans le panneau **Attributions de rôle**, entrez un **Nom** et éventuellement une **Description** pour l’attribution, puis choisissez les éléments suivants :
    - **Membres** : sélectionnez un groupe qui contient l’utilisateur auquel vous souhaitez accorder les autorisations.
    - **Étendue** : sélectionnez un groupe contenant les utilisateurs que le membre ci-dessus sera autorisé à gérer.
5. Une fois terminé, cliquez sur **OK**.

La nouvelle affectation s’affiche dans la liste des affectations.

## <a name="custom-role-settings-reference"></a>Référence des paramètres de rôle personnalisé

Lorsque vous créez un rôle personnalisé, vous pouvez configurer un ou plusieurs des paramètres suivants :

### <a name="device-configurations"></a>Configurations d'appareils

|||
|-|-|
|**Affecter**|Affecter des profils d’appareils.|
|**Créer**|Créer des profils d’appareils.|
|**Supprimer**|Supprimer des profils d’appareils.|
|**Lire**|Lire des profils d’appareils et leurs propriétés.|
|**Mettre à jour**|Mettre à jour les profils d’appareils existants.|

### <a name="managed-apps"></a>Applications gérées

|||
|-|-|
|**Affecter**|Affecter les applications managées à des groupes.|
|**Créer**|Ajouter de nouvelles applications managées à Intune.|
|**Supprimer**|Supprimer applications managées.|
|**Lire**|Lire des applications managées et leurs propriétés.|
|**Mettre à jour**|Mettre à jour des applications managées existantes.|
|**Réinitialisation**|Réinitialiser les applications managées des appareils.|

### <a name="managed-devices"></a>Appareils gérés

|||
|-|-|
|**Supprimer**|Supprimer les appareils gérés d’Intune.|
|**Lire**|Afficher des informations sur les appareils gérés dans le portail Intune.|
|**Mettre à jour**|Mettre à jour des informations sur les appareils gérés.|

### <a name="mobile-apps"></a>Applications mobiles

|||
|-|-|
|**Affecter**|Affecter des applications mobiles aux groupes.|
|**Créer**|Ajouter de nouvelles applications mobiles à Intune.|
|**Supprimer**|Supprimer des applications mobiles.|
|**Lire**|Lire des applications mobiles et leurs propriétés.|
|**Mettre à jour**|Mettre à jour les applications mobiles existantes.|

### <a name="organization"></a>Organisation

|||
|-|-|
|**Lire**|Lire les paramètres du locataire.|
|**Mettre à jour**|Mettre à jour les paramètres du locataire.|

### <a name="remote-tasks"></a>Tâches à distance

|||
|-|-|
|**Contourner le verrou d’activation**|Supprimer le verrou d'activation des appareils iOS sans avoir l'ID Apple et le mot de passe de l'utilisateur. |
|**Désactiver le mode de perte d'appareil**|Désactiver le mode de perte d'appareil. Le mode de perte de l'appareil vous permet de spécifier un message et un numéro de téléphone qui s’affichent sur l’écran de verrouillage de l’appareil.|
|**Activer le mode de perte d'appareil**|Activer le mode de perte d'appareil. Le mode de perte de l'appareil vous permet de spécifier un message et un numéro de téléphone qui s’affichent sur l’écran de verrouillage de l’appareil.|
|**Localiser l'appareil**|-|
|**Redémarrer maintenant**|Force le redémarrage de l’appareil.|
|**Verrouillage à distance**|Verrouille un appareil. Le propriétaire de l’appareil doit utiliser son code secret pour le déverrouiller.|
|**Réinitialiser le code secret**|Génère un nouveau code secret pour l'appareil qui sera affiché dans le panneau Vue d’ensemble de <device name>.|
|**Mettre hors service**|Supprime uniquement les données d’entreprise gérées par Intune. Cela ne supprime pas les données personnelles de l’appareil.|
|**Réinitialisation**|Réinitialise l’appareil à ses paramètres par défaut.|



### <a name="telecom-expenses"></a>Dépenses de télécommunications

|||
|-|-|
|**Lire**|Lire les paramètres de gestion des frais de télécommunication (TEM).|
|**Mettre à jour**|Mettre à jour les paramètres de gestion des frais de télécommunication (TEM).|

### <a name="terms-and-conditions"></a>conditions générales

|||
|-|-|
|**Affecter**|Affecter les conditions générales à des groupes.|
|**Créer**|Créer des paramètres de conditions générales.|
|**Supprimer**|Supprimer des paramètres de conditions générales.|
|**Lire**|Lire les paramètres des conditions générales dans le portail Intune.|
|**Mettre à jour**|Mettre à jour les paramètres des conditions générales.|
