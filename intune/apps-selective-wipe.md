---
title: "Guide pratique pour effacer uniquement les données d’entreprise des applications"
titleSuffix: Intune on Azure
description: "Apprenez à effectuer une réinitialisation sélective des applications avec Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bfebc391997ac4e63466eb3a09044318cf807dbc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a>Guide pratique pour effacer uniquement les données d’entreprise des applications gérées par Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Lorsqu'un appareil est perdu ou volé, ou si l'employé quitte votre entreprise, vous devez vous assurer que les données de l'application d’entreprise sont supprimées de l'appareil. Mais vous ne voulez peut-être pas supprimer les données personnelles de l’appareil, en particulier si cet appareil appartient à un employé.

Pour supprimer des données d’application d’entreprise de manière sélective, créez une demande de réinitialisation en suivant les étapes indiquées dans cette rubrique. Une fois la demande terminée, les données d’entreprise sont supprimées de l’application dès sa prochaine exécution sur l’appareil.

>[!IMPORTANT]
> Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être réinitialisés. Actuellement, cela s’applique uniquement à l’application Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Créer une demande de réinitialisation

1.  Connectez-vous au [portail Azure](https://portal.azure.com).

2.  Choisissez **Plus de services**, saisissez **Intune** dans la zone de texte de filtre, puis sélectionnez **Intune**. Le panneau d’Intune s’ouvre. Choisissez le panneau **Gérer les applications**.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](./media/intune-azure-preview-blade.png)

3.  Dans le panneau **Mobile Apps**, choisissez **Nouvelle demande de réinitialisation**. Le panneau **Nouvelle demande de réinitialisation** s’ouvre.

4.  Choisissez **Nouvelle demande de réinitialisation**. Le panneau **Nouvelle demande de réinitialisation** s’ouvre.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  Choisissez **Utilisateur** pour ouvrir le panneau **Utilisateur** et sélectionnez l’utilisateur possédant les données des applications à réinitialiser.

6.  Choisissez **Appareil**. Cette opération ouvre le panneau **Appareil**, qui répertorie tous les appareils associés à l’utilisateur sélectionné et fournit également deux colonnes, le nom de l’appareil, qui est un nom convivial défini par l’utilisateur et le type d’appareil, à savoir sa plateforme. Sélectionnez l’appareil à réinitialiser.

7.  Vous voilà revenu dans le panneau **Nouvelle demande de réinitialisation**. Choisissez **Ok** pour effectuer une demande de réinitialisation. 

Le service crée une demande de réinitialisation distincte pour chaque application protégée sur l’appareil et l’utilisateur associé à la demande de réinitialisation, et en fait le suivi.

## <a name="monitor-your-wipe-requests"></a>Analyser vos demandes de réinitialisation

Vous pouvez obtenir un rapport de synthèse indique l’état global de la demande de réinitialisation et inclut le nombre de demandes en attente et d’échecs. Pour obtenir plus de détails, procédez comme suit :

1.  Le panneau **Applications mobiles - Réinitialisation en fonction des applications** affiche la liste de vos demandes regroupées par utilisateurs. Étant donné que le système crée une demande de réinitialisation pour chaque application protégée en cours d’exécution sur l’appareil, vous pouvez voir plusieurs demandes pour un même utilisateur. L’état de la demande de réinitialisation est indiquée : **en attente**, **échec**ou **réussite**.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](./media/wipe-request-status-1.png)

En outre, vous serez en mesure de voir le nom de l’appareil et son type, ce qui peut être utile lors de la lecture des rapports.

>[!IMPORTANT]
> L’utilisateur doit ouvrir l’application pour que la réinitialisation se produise. Cette opération peut prendre jusqu’à 30 minutes après l’envoi de la demande.

## <a name="delete-a-wipe-request"></a>Suppression d’une demande de réinitialisation

Les réinitialisations en attente sont affichées jusqu’à ce que vous les supprimiez manuellement.  Pour supprimer manuellement une demande de réinitialisation :

1.  Dans le panneau **Demande de réinitialisation**, choisissez la vignette **Demande de réinitialisation** pour ouvrir le panneau **Demande de réinitialisation**.

2.  Cliquez avec le bouton droit sur la demande de réinitialisation à supprimer, puis choisissez **Supprimer la demande de réinitialisation**.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](./media/delete-wipe-request.png)

3.  Vous êtes invité à confirmer la suppression. Choisissez **Oui** ou **Non**, puis cliquez sur **OK**.

### <a name="see-also"></a>Voir aussi
[Qu'est-ce qu'une stratégie de protection d’application](app-protection-policy.md)

[Qu’est-ce que la gestion des applications](app-management.md)