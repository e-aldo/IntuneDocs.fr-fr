---
title: Guide pratique pour effacer uniquement les données d’entreprise des applications
titleSuffix: Microsoft Intune
description: Apprenez à effectuer une réinitialisation sélective des applications avec Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6284786213661b737cb912c2b7e0dd1a1f433d8d
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Guide pratique pour effacer uniquement les données d’entreprise des applications gérées par Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Lorsqu'un appareil est perdu ou volé, ou si l'employé quitte votre entreprise, vous devez vous assurer que les données de l'application d’entreprise sont supprimées de l'appareil. Mais vous ne souhaitez peut-être pas supprimer les données personnelles contenues dans l’appareil, en particulier si celui-ci appartient à un employé.

>[!NOTE]
> Les plateformes iOS et Android sont les deux plateformes prises en charge actuellement pour le nettoyage des données d’entreprise à partir d’applications gérées par Intune.

Pour supprimer des données d’application d’entreprise de manière sélective, créez une demande de réinitialisation en suivant les étapes indiquées dans cette rubrique. Une fois la demande terminée, les données d’entreprise sont supprimées de l’application dès sa prochaine exécution sur l’appareil.

>[!IMPORTANT]
> Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être réinitialisés. Actuellement, cela s’applique uniquement à l’application Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Créer une demande de réinitialisation

1.  Connectez-vous au [portail Azure](https://portal.azure.com).

2.  Choisissez **Tous les services**, saisissez **Intune** dans la zone de texte de filtre, puis sélectionnez **Intune**. Le volet Intune s’ouvre, choisissez le volet **Applications mobiles**.

    ![Capture d’écran du volet Microsoft Intune](./media/apps-selective-wipe01.png)

3.  Dans le **volet Applications mobiles**, choisissez **Réinitialisation sélective des applications**.

4.  Choisissez **Nouvelle demande de réinitialisation**. Le volet **Nouvelle demande de réinitialisation** s’ouvre.

    ![Capture d’écran du panneau Nouvelle demande de réinitialisation](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Choisissez un utilisateur, puis choisissez **Sélectionnez** pour sélectionner l’utilisateur dont vous souhaitez réinitialiser les données d’application.

6.  Ensuite, choisissez **Appareil** dans le volet **Nouvelle demande de réinitialisation**. Cette opération ouvre le volet **Sélectionner un appareil**, qui répertorie tous les appareils associés à l’utilisateur sélectionné et fournit également deux colonnes : le nom de l’appareil, qui est un nom convivial défini par l’utilisateur et le type d’appareil, à savoir sa plateforme. Sélectionnez l’appareil à réinitialiser.

7.  Vous voilà revenu dans le volet **Nouvelle demande de réinitialisation**. Choisissez **Ok** pour effectuer une demande de réinitialisation.

Le service crée une demande de réinitialisation distincte pour chaque application protégée sur l’appareil et l’utilisateur associé à la demande de réinitialisation, et en fait le suivi.

## <a name="monitor-your-wipe-requests"></a>Analyser vos demandes de réinitialisation

Vous pouvez obtenir un rapport de synthèse indique l’état global de la demande de réinitialisation et inclut le nombre de demandes en attente et d’échecs. Pour obtenir plus de détails, procédez comme suit :

1.  Le volet **Applications mobiles - Réinitialisation sélective des applications** affiche la liste de vos demandes regroupées par utilisateur. Étant donné que le système crée une demande de réinitialisation pour chaque application protégée en cours d’exécution sur l’appareil, vous pouvez voir plusieurs demandes pour un même utilisateur. L’état de la demande de réinitialisation est indiquée : **en attente**, **échec**ou **réussite**.

    ![Capture d’écran de l’état de demande de réinitialisation dans le volet Réinitialisation sélective des applications](./media/wipe-request-status-1.png)

En outre, vous pouvez voir le nom de l’appareil et son type, ce qui peut être utile lors de la lecture des rapports.

>[!IMPORTANT]
> L’utilisateur doit ouvrir l’application pour que la réinitialisation se produise. Cette opération peut prendre jusqu’à 30 minutes après l’envoi de la demande.

## <a name="delete-a-wipe-request"></a>Suppression d’une demande de réinitialisation

Les réinitialisations en attente sont affichées jusqu’à ce que vous les supprimiez manuellement. Pour supprimer manuellement une demande de réinitialisation :

1.  Dans le volet **Applications mobiles -Réinitialisation sélective des applications**.

2.  Dans la liste, cliquez avec le bouton droit sur la demande de réinitialisation à supprimer, puis choisissez **Supprimer la demande de réinitialisation**.

    ![Capture d’écran de la liste de demandes de réinitialisation dans le volet Réinitialisation sélective des applications](./media/delete-wipe-request.png)

3.  Vous êtes invité à confirmer la suppression. Choisissez **Oui** ou **Non**, puis cliquez sur **OK**.

### <a name="see-also"></a>Voir aussi
[Qu'est-ce qu'une stratégie de protection d’application](app-protection-policy.md)

[Qu’est-ce que la gestion des applications](app-management.md)
