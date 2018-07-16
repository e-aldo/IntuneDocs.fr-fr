---
title: Actions et message de non-conformité avec Microsoft Intune - Azure | Microsoft Docs
description: Créer un e-mail de notification à envoyer aux appareils non conformes. Ajoutez des actions après qu’un appareil a été marqué comme non conforme, par exemple ajoutez une période de grâce pour la conformité, ou créez une planification afin de bloquer l’accès jusqu’à ce que l’appareil soit conforme. Effectuez ces opérations à l’aide de Microsoft Intune dans Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3c8bc523f2796f8af7cb4801cdb13a60b7e2eb5d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905731"
---
# <a name="automate-email-and-add-actions-for-noncompliant-devices---intune"></a>Automatiser l’envoi d’un e-mail et ajouter des actions pour les appareils non conformes - Intune

Il existe une fonctionnalité **Actions en cas de non-conformité** qui configure une séquence ordonnée d’actions. Ces actions s’appliquent aux appareils qui ne satisfont pas à votre stratégie de conformité. 

## <a name="overview"></a>Vue d’ensemble
Par défaut, quand Intune détecte un appareil qui n’est pas conforme, il le marque immédiatement comme étant non conforme. L’[accès conditionnel](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) Azure Active Directory (AD) bloque alors l’appareil. Quand un appareil n’est pas conforme, les **actions en cas de non-conformité** offrent davantage de flexibilité pour décider de ce qu’il faut faire. Par exemple, ne pas bloquer immédiatement l’appareil et donner à l’utilisateur une période de grâce pendant laquelle il peut configurer la conformité de l’appareil.

Il existe deux types d’actions :

- **Notifier les utilisateurs finaux par e-mail** : personnalisez un e-mail de notification avant de l’envoyer à l’utilisateur final. Vous pouvez personnaliser les destinataires, l’objet et le corps du message, notamment le logo de l’entreprise et les informations de contact.

    Par ailleurs, Intune ajoute des informations sur l’appareil non conforme dans l’e-mail de notification.

- **Marquer l’appareil comme non conforme** : créez une planification, c’est-à-dire un nombre de jours au terme desquels l’appareil est marqué comme non conforme. Vous pouvez décider d’exécuter l’action immédiatement ou octroyer à l’utilisateur une période de grâce pour se mettre en conformité.

## <a name="before-you-begin"></a>Avant de commencer

- Pour définir des actions en cas de non-conformité, vous devez avoir au moins une stratégie de conformité de l’appareil. Pour créer une stratégie de conformité de l’appareil, consultez les plateformes suivantes :

  - [Android](compliance-policy-create-android.md)
  - [Profils professionnels Android](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [MacOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Quand vous utilisez des stratégies de conformité de l’appareil pour bloquer l’accès des appareils aux ressources de l’entreprise, l’accès conditionnel Azure AD doit être configuré. Pour obtenir des instructions, consultez [Configuration de l’accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).

- Vous devez créer un modèle de message de notification. Pour envoyer un e-mail à vos utilisateurs, ce modèle est utilisé pour créer des actions en cas de non-conformité.

## <a name="create-a-notification-message-template"></a>Créer un modèle de message de notification

1. Connectez-vous au [Portail Azure](https://portal.azure.com) avec vos informations d’identification Intune. 
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Conformité de l’appareil**, puis **Notifications**. 
4. Sélectionnez **Créer une notification**, puis entrez les informations suivantes :

   - Nom
   - Objet
   - Message
   - En-tête de l’e-mail - Inclure le logo de l’entreprise
   - Pied de page de l’e-mail - Inclure le nom de l’entreprise
   - Pied de page de l’e-mail - Inclure les informations de contact

   ![Exemple de message de notification de conformité dans Intune](./media/actionsfornoncompliance-1.PNG)

Une fois que vous avez terminé l’ajout des informations, choisissez **Créer**. Le modèle de message de notification est prêt à être utilisé.

> [!NOTE]
> Vous pouvez également modifier un modèle de notification créé précédemment.

## <a name="add-actions-for-noncompliance"></a>Ajouter des actions en cas de non-conformité

Par défaut, Intune crée automatiquement une action en cas de non-conformité. Quand un appareil ne satisfait pas à votre stratégie de conformité, cette action marque l’appareil comme non conforme. Vous pouvez personnaliser la durée pendant laquelle l’appareil est marqué comme non conforme. Cette action ne peut pas être supprimée.

Vous pouvez ajouter une action quand vous créez une stratégie de conformité, ou mettre à jour une stratégie de conformité existante. 

1. Dans le [portail Azure](https://portal.azure.com), ouvrez **Microsoft Intune**, puis sélectionnez **Conformité**.
2. Sélectionnez **Stratégies**, choisissez l’une de vos stratégies, puis sélectionnez **Propriétés**. 

  Vous n’avez pas encore de stratégie ? Créez une stratégie [Android](compliance-policy-create-android.md), [iOS](compliance-policy-create-ios.md), [Windows](compliance-policy-create-windows.md) ou une stratégie pour une autre plateforme.
  
  > [!NOTE]
  > Pour le moment, les appareils JAMF et les appareils ciblés avec des groupes d’appareils ne peuvent pas recevoir des actions de conformité.

3. Sélectionnez **Actions en cas de non-conformité**, puis sélectionnez **Ajouter** pour entrer les paramètres de l’action. Vous pouvez choisir le modèle de message créé précédemment, ajouter des destinataires supplémentaires et mettre à jour la planification de la période de grâce. Vous pouvez entrer le nombre de jours (de 0 à 365) sur la planification, puis appliquer les stratégies d’accès conditionnel. Si vous entrez **0** nombre de jours, l’accès conditionnel bloque **immédiatement** l’accès aux ressources de l’entreprise.

4. Quand vous avez terminé, sélectionnez **Ajouter** > **OK** pour enregistrer les modifications.

## <a name="next-steps"></a>Étapes suivantes
Surveiller l’activité de conformité de l’appareil en exécutant les rapports. [Guide pratique pour surveiller la conformité des appareils avec Intune](device-compliance-monitor.md) fournit quelques conseils.
