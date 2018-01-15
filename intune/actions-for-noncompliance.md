---
title: "Actions en cas de non-conformité avec Intune"
titleSuffix: Intune on Azure
description: "Découvrez comment créer des actions en cas de non-conformité avec Intune"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 01/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9747835e01dd2cf033ff4df7cba33ffd24660d61
ms.sourcegitcommit: bd4c4b53312407548600053ab99672cb2d08bb63
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2018
---
# <a name="automate-actions-for-noncompliance"></a>Automatiser des actions en cas de non-conformité

Les **actions en cas de non-conformité** vous permettent de configurer une séquence ordonnée d’actions appliquées aux appareils qui ne répondent pas aux critères de la stratégie de conformité. Par défaut, quand un appareil ne répond pas aux critères de la stratégie de conformité, Intune le marque immédiatement comme étant non conforme, puis l’accès conditionnel Azure AD bloque l’appareil. Les **actions en cas de non-conformité** offrent plus de flexibilité pour décider ce qu’il faut faire si un appareil n’est pas conforme. Par exemple, vous pouvez décider de ne pas bloquer immédiatement l’appareil et donner à l’utilisateur une période de grâce pendant laquelle il peut configurer la conformité de l’appareil.

Il existe deux types d’actions :

-   **Notifier les utilisateurs finaux par e-mail** : vous pouvez personnaliser votre notification par e-mail avant de l’envoyer à l’utilisateur final. Intune permet la personnalisation des destinataires, de l’objet et du corps du message, notamment le logo de l’entreprise et les informations de contact.
-   **Marquer l’appareil comme non conforme** : vous pouvez déterminer une planification du nombre de jours au terme desquels l’appareil est marqué comme non conforme. Vous pouvez décider d’exécuter l’action immédiatement ou octroyer à l’utilisateur une période de grâce pour se mettre en conformité avez vos stratégies de conformité des appareils.

## <a name="before-you-begin"></a>Avant de commencer

- Vous devez avoir au moins une stratégie de conformité d’appareil créée pour définir des actions de non-conformité. Découvrez comment créer une stratégie de conformité des appareils pour les plateformes suivantes :

    -   [Android](compliance-policy-create-android.md)
    -   [Android for Work](compliance-policy-create-android-for-work.md)
    -   [iOS](compliance-policy-create-ios.md)
    -   [MacOS](compliance-policy-create-mac-os.md)
    -   [Windows](compliance-policy-create-windows.md)

- Vous devez avoir configuré l’accès conditionnel Azure AD si vous prévoyez d’utiliser des stratégies de conformité d’appareils pour empêcher les appareils d’utiliser les ressources de l’entreprise. Découvrez [comment configurer l’accès conditionnel EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

- Vous devez disposer d’un modèle de message de notification déjà créé. Le modèle de message de notification est utilisé ultérieurement lors de la création d’actions de non-conformité pour envoyer un e-mail à vos utilisateurs.

- Vous devez configurer Exchange Online pour accepter les e-mails provenant de  *IntuneNotificationService@microsoft.com*  pour permettre à Intune d’envoyer la notification par e-mail. Pour plus d’informations, consultez [Configurer des restrictions de remise de message pour une boîte aux lettres](https://technet.microsoft.com/library/bb397214(v=exchg.160).aspx).

### <a name="to-create-a-notification-message-template"></a>Pour créer un modèle de message de notification

1. Accédez à [Intune sur le portail Azure](https://portal.azure.com) et connectez-vous avec vos informations d’identification Intune.
2. Choisissez **Autres services** dans le menu de gauche, puis tapez **Intune** dans le filtre de zone de texte.
3. Choisissez **Intune**
4. Choisissez **Conformité de l’appareil**, puis choisissez **Notifications** dans la section **Gérer**.
5. Choisissez **Créer une notification**, puis entrez les informations suivantes :
    - Nom
    - Objet
    - Message
    - En-tête de l’e-mail - Inclure le logo de l’entreprise
    - Pied de page de l’e-mail - Inclure le nom de l’entreprise
    - Pied de page de l’e-mail - Inclure les informations de contact

   ![Exemple de modèle de message de notification](./media/actionsfornoncompliance-1.PNG)

Une fois que vous avez terminé l’ajout des informations, choisissez **Créer**. Le modèle de message de notification est prêt à être utilisé.

> [!NOTE] 
> Vous pouvez également modifier un modèle de notification créé précédemment.

## <a name="to-create-actions-for-non-compliance"></a>Pour créer des actions en cas de non-conformité

> [!TIP]
> Par défaut, Intune fournit une action prédéfinie dans les actions de la section Non-conformité. Cette action marque l’appareil comme non conforme après avoir été détecté comme ne répondant pas aux critères de votre stratégie de conformité des appareils. Vous pouvez personnaliser le délai après lequel l’appareil est marqué non conforme. L’action ne peut pas être annulée.

Vous pouvez ajouter une action lorsque vous créez une stratégie de conformité d’appareils ou modifiez une stratégie de conformité d’appareils existante.

1.  Dans la charge de travail Intune, dans le panneau **Stratégies de conformité des appareils**, choisissez **Stratégies** sous la section **Gérer**.
2.  Choisissez une stratégie de conformité des appareils en cliquant sur celle-ci, puis choisissez **Propriétés** sous la section **Gérer**.
3.  Dans le panneau **Propriétés de stratégie de conformité d’appareil**, choisissez **Actions en cas de non-conformité**.
4.  Dans le panneau **Actions en cas de non-conformité**, choisissez **Ajouter** pour spécifier les paramètres d’action. Vous pouvez choisir le modèle de message créé précédemment, des destinataires supplémentaires et la planification de la période de grâce. Vous pouvez spécifier le nombre de jours (de 0 à 365) sur la planification, puis appliquer les stratégies d’accès conditionnel. Si vous spécifiez **0** pour le nombre de jours, l’accès conditionnel bloque **immédiatement** l’accès aux ressources de l’entreprise quand les appareils sont non conformes aux stratégies de conformité des appareils.
5.  Une fois que vous avez terminé l’ajout des informations, choisissez **Ajouter**, puis **OK**.

## <a name="next-steps"></a>Étapes suivantes
Vous pouvez surveiller l’activité de conformité d’appareils en exécutant les rapports disponibles dans le panneau de conformité des appareils. Pour plus d’informations, consultez [Guide pratique pour surveiller la conformité des appareils](device-compliance-monitor.md).

