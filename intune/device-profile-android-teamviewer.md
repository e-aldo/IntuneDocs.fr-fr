---
title: "Guide d’administration à distance des appareils Android à l’aide de TeamViewer"
titlesuffix: Azure portal
description: "Apprenez à administrer à distance des appareils Android à l’aide de TeamViewer."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a6286760e1e49cdb090736e9444fe8ce18ddeb7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2017
---
# <a name="provide-remote-assistance-for-intune-managed-android-devices"></a>Fournir une assistance à distance pour les appareils Android gérés par Intune

Intune peut utiliser le logiciel [TeamViewer](https://www.teamviewer.com), vendu séparément, pour vous permettre de fournir une assistance à distance aux utilisateurs d’appareils Android. Utilisez les informations de cette rubrique pour commencer.

## <a name="before-you-start"></a>Avant de commencer

### <a name="required-permissions"></a>Autorisations requises

Assurez-vous que l’utilisateur du portail Azure dispose des autorisations suivantes affectées à en tant que [rôle Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) :
- Pour permettre à l’administrateur de modifier les paramètres du connecteur TeamViewer, accordez l’autorisation **Mettre à jour l’assistance à distance**.
- Pour permettre à l’administrateur de lancer une nouvelle demande d’assistance à distance, accordez l’autorisation **Demander une assistance à distance**. Les utilisateurs disposant de l’autorisation **Demander une assistance à distance** peuvent demander de lancer une session pour n’importe quel utilisateur. Ils ne sont limités par aucune étendue d’attribution de rôle Intune. Les étendues d’affectation de rôle Intune ne limitent pas les appareils ou utilisateurs dont les demandes d’assistance à distance peuvent être lancées.

>[!NOTE]
>En activant TeamViewer, vous autorisez le connecteur TeamViewer pour Intune à créer des sessions TeamViewer, lire les données Active Directory et enregistrer le jeton d’accès de compte TeamViewer.

### <a name="configure-the-intune-teamviewer-connector"></a>Configurer le connecteur TeamViewer Intune

Avant de pouvoir fournir une assistance à distance sur des appareils Android, vous devez configurer le connecteur TeamViewer Intune. Pour cela, effectuez les étapes suivantes :


1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils et groupes**, choisissez **Configuration** > **Connecteur TeamViewer**.
5. Dans le panneau **Connecteur TeamViewer**, cliquez sur **Activer**, puis affichez et acceptez le contrat de licence de service TeamViewer.
6. Choisissez **Se connecter à TeamViewer & autoriser**.
7. Une page web s’ouvre sur le site TeamViewer. Saisissez les informations d’identification de votre licence TeamViewer, puis cliquez sur **Connexion**.


## <a name="how-to-remotely-administer-an-android-device"></a>Comment administrer un appareil Android

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.
4. Dans le panneau **Appareils**, choisissez **Gérer** > **Tous les appareils**.
5. Sélectionnez l’appareil que vous souhaitez administrer à distance, puis, dans le panneau Propriétés de l’appareil, choisissez **Plus** > **Nouvelle session d’assistance à distance**.
6. Une fois qu’Intune se connecte au service TeamViewer, vous voyez des informations sur l’appareil Android. Choisissez **Connexion** pour démarrer la session à distance.

![Android TeamViewer Windows](./media/android-teamviewer.png)

Dans la fenêtre de TeamViewer, vous pouvez effectuer une série d’actions à distance sur l’appareil Android, y compris le contrôle à distance de l’appareil. Pour obtenir des informations complètes sur les actions que vous pouvez effectuer, consultez la [documentation de TeamViewer](https://www.teamviewer.com/support/documents/).

Une fois que vous avez terminé, fermez la fenêtre TeamViewer.

## <a name="end-user-notifications"></a>Notifications à l’utilisateur final

Un utilisateur final voit un indicateur de notification sur l’icône de l’application Portail d’entreprise sur son appareil, ainsi qu’une notification quand il ouvre l’application. Il peut alors accepter la demande d’assistance à distance.

