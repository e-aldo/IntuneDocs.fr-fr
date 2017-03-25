---
title: "Actions en cas de non-conformité"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : apprenez à créer des actions pour les appareils non conformes"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Créer des actions en cas de non-conformité

Les **actions en cas de non-conformité** vous permettent de configurer une séquence ordonnée d’actions qui sont appliquées aux appareils non conformes. Par exemple, vous pouvez informer les utilisateurs des appareils non conformes par e-mail ou empêcher ces appareils d’accéder aux ressources de l’entreprise au moyen de l’accès conditionnel.

## <a name="use-case-scenario"></a>Cas d’utilisation

Par défaut, une fois qu’un appareil est signalé comme non conforme par une stratégie de conformité d’appareils Intune, l’accès conditionnel le bloque immédiatement et l’utilisateur reçoit un e-mail contenant des instructions à suivre pour rendre l’appareil conforme. Les **actions en cas de non-conformité** offrent plus de flexibilité lorsqu’il s’agit de décider quoi faire si un appareil est non conforme. Par exemple, vous pouvez décider de ne pas bloquer immédiatement l’appareil et donner à l’utilisateur une période de grâce pendant laquelle il peut configurer la conformité de l’appareil.

Il existe deux types d’actions :

-   Informer l’utilisateur par e-mail

-   Bloquer l’accès aux ressources de l’entreprise au moyen de l’accès conditionnel

## <a name="notify-the-user-via-email"></a>Informer l’utilisateur par e-mail

Vous pouvez choisir parmi les modèles d’e-mail par défaut créés au préalable ou créer une notification par e-mail personnalisée. Nous fournissons une personnalisation de l’objet, du corps du message, y compris le logo de l’entreprise, les coordonnées et les destinataires supplémentaires.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Bloquer l’accès aux ressources de l’entreprise au moyen de l’accès conditionnel

Vous pouvez définir une planification du nombre de jours pendant lequel l’appareil ne peut plus accéder aux ressources de l’entreprise. Ce blocage peut être immédiat ou vous pouvez décider de ne pas bloquer immédiatement l’appareil et d’octroyer à l’utilisateur une période de grâce pendant laquelle il peut assurer la conformité aux stratégies de conformité d’appareil.

## <a name="before-you-begin"></a>Avant de commencer

Vous devez avoir au moins une stratégie de conformité d’appareil créée pour définir des actions de non-conformité.

-   Découvrez comment créer une stratégie de conformité des appareils pour :

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

Vous devez avoir configuré l’accès conditionnel EMS lorsque vous prévoyez d’utiliser des stratégies de conformité d’appareils pour empêcher les appareils d’utiliser les ressources de l’entreprise.

- Découvrez [comment configurer l’accès conditionnel EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

En outre, vous devez disposer d’un modèle de message de notification déjà créé. Le modèle de message de notification est utilisé ultérieurement lors de la création d’actions de non-conformité pour envoyer un e-mail à vos utilisateurs.

### <a name="to-add-a-notification-message-template"></a>Pour ajouter un modèle de message de notification

Dans le panneau **Stratégies de conformité d’appareils** :

1.  Sous **Gérer**, choisissez **Notifications**. Le volet de modèles de message de notification s’ouvre.

    ![Ajouter un modèle de notification](../media/afnc-1.png)

2.  Choisissez **Ajouter**, puis définissez les éléments suivants :

    a.  Description

    b.  Du

    c.  Objet

    d.  Message

    e.  En-tête de l’e-mail - Inclure le logo de l’entreprise

    f.  Pied de page de l’e-mail - Inclure le nom de l’entreprise

    g.  Pied de page de l’e-mail - Inclure les informations de contact

     ![Modèle de message de notification](../media/afnc-2.png)

Une fois que vous avez ajouté les informations requises, cliquez sur **Créer**. Le modèle de message de notification est prêt à être utilisé.

> [!NOTE] 
> Vous pouvez également modifier un modèle de notification créé précédemment.

## <a name="to-create-actions-for-non-compliance"></a>Pour créer des actions en cas de non-conformité

Vous pouvez ajouter une action au moment où vous créez une stratégie de conformité d’appareils ou en modifiant une stratégie de conformité d’appareils existante.

1.  Dans le panneau **Device compliance policies (Stratégies de conformité d’appareils)**, sous **Gérer**, choisissez **Stratégies**.

2.  Choisissez une stratégie de conformité d’appareils en cliquant dessus.

    ![Stratégies de conformité](../media/afnc-3.png)

3.  Dans le panneau **device compliance policy properties (Propriétés de stratégie de conformité d’appareil)**, choisissez **Actions en cas de non-conformité**.

4.  Le panneau Actions en cas de non-conformité s’ouvre. Choisissez **Ajouter** pour spécifier les paramètres d’action.

    ![Panneau Actions en cas de non-conformité](../media/afnc-4.png)

Voici les actions en cas de non-conformité :

-   **Marquer comme non conforme**

-   **Notification**

### <a name="enforce-conditional-access-policy"></a>Marquer comme non conforme

Pour ajouter cette action en cas de non-conformité :

1.  À partir du panneau **Actions en cas de non-conformité**, choisissez **Ajouter**.

2.  Dans le panneau **Paramètres d’action**, sélectionnez **Marquer comme non conforme** dans la liste déroulante des actions.

3.  Dans **Planification**, vous pouvez spécifier le nombre de jours (de 0 à 255) pendant lesquels appliquer la stratégie d’accès conditionnel. Si vous spécifiez **0**, cela signifie que l’accès conditionnel doit **immédiatement** bloquer l’accès aux ressources de l’entreprise dès que les appareils sont non conformes aux stratégies de conformité d’appareils.

    ![Planifier les actions en cas de non-conformité](../media/afnc-5.png)

4.  Choisissez **Ajouter**, puis **OK** à partir du panneau **Actions**.

5.  À partir du panneau **Propriétés de stratégie de conformité de l’appareil (Propriétés de stratégie de conformité d’appareil)**, choisissez **Enregistrer**.

### <a name="send-e-mail-to-end-user"></a>Notification

Vous pouvez utiliser un modèle d’e-mail à envoyer aux utilisateurs non conformes. Ces e-mails aident à garantir la conformité des appareils dans toute l’organisation.

Pour ajouter cette action en cas de non-conformité :

1.  À partir du panneau **Actions en cas de non-conformité**, choisissez **Ajouter**.

2.  Dans le panneau **Paramètres d’action**, sélectionnez **Notification** dans la liste déroulante des actions.

3.  Choisissez un modèle de message créé précédemment en cliquant sur **Modèle de message**. Pour afficher le contenu du modèle de message, choisissez **Sélectionner**.

    ![Modèle de message](../media/afnc-6.png)

> [!NOTE] 
> Vous pouvez afficher le modèle de message, mais vous ne pouvez pas le modifier. Si vous souhaitez modifier le modèle de message, vous devez revenir au panneau **Notifications**.

1.  Dans **Planification**, entrez le nombre de jours qui doivent s’écouler avant que l’e-mail soit envoyé aux utilisateurs non conformes. Si vous spécifiez **0** comme nombre de jours, cela signifie que l’e-mail est envoyé **immédiatement**.

2.  Choisissez **Ajouter**, puis **OK** à partir du panneau **Actions**.

3.  À partir du panneau **Propriétés de stratégie de conformité de l’appareil (Propriétés de stratégie de conformité d’appareil)**, choisissez **Enregistrer**.

