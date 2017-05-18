---
title: "Réinitialiser les données d’applications d’entreprise gérées | Microsoft Docs"
description: "Découvrez comment sélectivement supprimer des données de votre entreprise à partir d’appareils à distance."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8a3e8634769b05e6639f7efb6394b7333d998f06
ms.openlocfilehash: 5d5cde748aa8fa464526d0dc2b2ef9ee460fff9d


---

# <a name="wipe-company-app-data-with-intune-mam"></a>Réinitialiser les données d’application d’entreprise avec Intune MAM

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Lorsqu'un appareil est perdu ou volé, ou si l'employé quitte votre entreprise, vous devez vous assurer que les données de l'application d’entreprise sont supprimées de l'appareil. Mais vous ne voulez peut-être pas supprimer les données personnelles de l’appareil, en particulier si cet appareil appartient à un employé.

Pour supprimer des données d’application d’entreprise de manière sélective, créez une demande de réinitialisation en suivant les étapes indiquées dans cette rubrique. Une fois la demande terminée, les données d’entreprise sont supprimées de l’application dès sa prochaine exécution sur l’appareil.

>[!IMPORTANT]
> Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être effacés. Actuellement, cela s’applique uniquement à l’application Microsoft Outlook.

## <a name="create-a-wipe-request"></a>Créer une demande de réinitialisation

1.  Connectez-vous au [portail Azure](https://portal.azure.com).

2.  Choisissez **Plus de services**, saisissez **Intune** dans la zone de texte de filtre, puis sélectionnez **Protection d’application Intune**. Le panneau Gestion des applications mobiles Intune s’ouvre.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  Dans le panneau **Paramètres**, choisissez **Demandes de réinitialisation**.

3.  Choisissez **Nouvelle demande de réinitialisation**. Le panneau **Nouvelle demande de réinitialisation** s’ouvre.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  Choisissez **Utilisateur** pour ouvrir le panneau **Utilisateur** et sélectionnez l’utilisateur possédant les données des applications à réinitialiser.

5.  Choisissez **Appareil**. Cette opération ouvre le panneau **Appareil**, qui répertorie tous les appareils associés à l’utilisateur sélectionné et fournit également deux colonnes, le nom de l’appareil, qui est un nom convivial défini par l’utilisateur et le type d’appareil, à savoir sa plateforme. Sélectionnez l’appareil à réinitialiser.

6.  Vous voilà revenu dans le panneau **Nouvelle demande de réinitialisation**. Choisissez **Ok** pour effectuer une demande de réinitialisation. 

Le service crée une demande de réinitialisation distincte pour chaque application protégée sur l’appareil et l’utilisateur associé à la demande de réinitialisation, et en fait le suivi.

>[!NOTE]
> Vous pouvez également créer des **Demandes de réinitialisation** en cliquant sur la **Vignette Demande de réinitialisation** dans le panneau de gestion des applications mobiles Intune.

## <a name="monitor-your-wipe-requests"></a>Analyser vos demandes de réinitialisation

Vous pouvez obtenir un rapport de synthèse indique l’état global de la demande de réinitialisation et inclut le nombre de demandes en attente et d’échecs. Pour obtenir plus de détails, procédez comme suit :

1.  Dans le panneau Gestion des applications mobiles Intune , cliquez sur la vignette **Demandes de réinitialisation**.

2.  Dans le panneau **Demande de réinitialisation**, choisissez la vignette **Demande de réinitialisation** pour ouvrir le panneau **Demande de réinitialisation**.

3.  Le panneau **Demande de réinitialisation** affiche la liste de vos demandes regroupées par utilisateurs. Étant donné que le système crée une demande de réinitialisation pour chaque application protégée en cours d’exécution sur l’appareil, vous pouvez voir plusieurs demandes pour un même utilisateur. L’état de la demande de réinitialisation est indiquée : **en attente**, **échec**ou **réussite**.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](../media/AppManagement/wipe-request-status-1.png)

En outre, vous serez en mesure de voir le nom de l’appareil et son type, ce qui peut être utile lors de la lecture des rapports.

>[!IMPORTANT]
> L’utilisateur doit ouvrir l’application pour que la réinitialisation se produise. Cette opération peut prendre jusqu’à 30 minutes après l’envoi de la demande.

## <a name="delete-a-wipe-request"></a>Suppression d’une demande de réinitialisation

Les réinitialisations en attente sont affichées jusqu’à ce que vous les supprimiez manuellement.  Pour supprimer manuellement une demande de réinitialisation

1.  Dans le panneau Gestion des applications mobiles Intune , cliquez sur la vignette **Demandes de réinitialisation**.

2.  Dans le panneau **Demande de réinitialisation**, choisissez la vignette **Demande de réinitialisation** pour ouvrir le panneau **Demande de réinitialisation**.

3.  Cliquez avec le bouton droit sur la demande de réinitialisation à supprimer, puis choisissez **Supprimer la demande de réinitialisation**.

    ![Capture d'écran du panneau Nouvelle demande de réinitialisation](../media/AppManagement/delete-wipe-request.png)

4.  Vous êtes invité à confirmer la suppression. Choisissez **Oui** ou **Non**, puis cliquez sur **OK**.


### <a name="see-also"></a>Voir aussi
[Protéger les données d’application à l’aide des stratégies de gestion des applications mobiles](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Utilisation du portail Azure](azure-portal-for-microsoft-intune-mam-policies.md)



<!--HONumber=Feb17_HO1-->


