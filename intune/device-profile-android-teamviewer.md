---
title: "Administrer à distance des appareils dans Microsoft Intune - Azure | Microsoft Docs"
description: "Afficher les rôles nécessaires pour utiliser TeamViewer, découvrir comment installer le connecteur TeamViewer et obtenir des instructions pas à pas pour administrer à distance des appareils à l’aide de Microsoft Intune dans le portail Azure"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 64f6dd6bf787a6f590655f03ac8f04312836e0b5
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="use-teamviewer-to-remotely-administer-intune-devices"></a>Utiliser TeamViewer pour administrer à distance des appareils Intune

Il est possible d’administrer à distance des appareils gérés par Intune à l’aide de [TeamViewer](https://www.teamviewer.com). TeamViewer est un programme tiers que vous achetez séparément. Cette rubrique vous montre comment configurer TeamViewer dans Intune et comment administrer à distance un appareil. 

## <a name="prerequisites"></a>Prérequis

- Utilisez un appareil pris en charge. Les appareils Android et Windows gérés par Intune prennent en charge l’administration à distance. TeamViewer peut ne pas prendre en charge Windows Holographique (HoloLens), Windows Collaboration (Surface Hub) ou Windows 10 S. Pour obtenir les dernières informations sur la prise en charge, visitez [TeamViewer](https://www.teamviewer.com).

- L’administrateur Intune dans le portail Azure doit avoir les [rôles Intune](role-based-access-control.md) suivants :  

    - **Mettre à jour l’assistance à distance** : permet aux administrateurs de modifier les paramètres du connecteur TeamViewer.
    - **Demander une assistance à distance** : permet aux administrateurs de démarrer une nouvelle session d’assistance à distance pour n’importe quel utilisateur. Les utilisateurs ayant ce rôle ne sont pas limités par un rôle Intune dans une étendue. Par ailleurs, les groupes d’utilisateurs ou d’appareils affectés à un rôle Intune dans une étendue peuvent demander une assistance à distance. 

- Un compte [TeamViewer](https://www.teamviewer.com) avec les informations d’identification de connexion.

En utilisant TeamViewer, vous autorisez le connecteur TeamViewer pour Intune à créer des sessions TeamViewer, lire les données Active Directory et enregistrer le jeton d’accès de compte TeamViewer.

## <a name="configure-the-teamviewer-connector"></a>Configurer le connecteur TeamViewer

Pour fournir une assistance à distance sur des appareils, configurez le connecteur TeamViewer Intune à l’aide des étapes suivantes :

1. Dans le [portail Azure](https://portal.azure.com), sélectionnez **Tous les services**, puis recherchez **Microsoft Intune**.
2. Dans **Microsoft Intune**, sélectionnez **Appareils**, puis **Connecteur TeamViewer**.
3. Sélectionnez **Connexion**, puis acceptez le contrat de licence.
4. Sélectionnez **Se connecter à TeamViewer pour autoriser**.
5. Une page web s’ouvre sur le site TeamViewer. Entrez les informations d’identification de votre licence TeamViewer, puis cliquez sur **Connexion**.

## <a name="remotely-administer-a-device"></a>Administrer un appareil à distance

Après avoir configuré le connecteur, vous êtes prêt à administrer à distance un appareil. Procédez comme suit : 

1. Dans le [portail Azure](https://portal.azure.com), sélectionnez **Tous les services**, puis recherchez **Microsoft Intune**.
2. Dans **Microsoft Intune**, sélectionnez **Appareils**, puis **Tous les appareils**.
3. Dans la liste, sélectionnez l’appareil à administrer à distance. Dans les propriétés de l’appareil, sélectionnez **Nouvelle session d’assistance à distance**.
4. Une fois Intune connecté au service TeamViewer, des informations sur l’appareil s’affichent. **Connectez-vous** pour démarrer la session à distance.

![Utiliser TeamViewer pour administrer à distance un appareil Android (exemple)](./media/android-teamviewer.png)

Quand vous démarrez une session à distance, un utilisateur final voit un indicateur de notification sur l’icône de l’application Portail d’entreprise sur son appareil. Une notification s’affiche également quand l’application s’ouvre. L’utilisateur peut alors accepter la demande d’assistance à distance.

Dans TeamViewer, vous pouvez effectuer diverses actions sur l’appareil, notamment prendre son contrôle. Pour tout savoir sur ce que vous pouvez faire, consultez [l’aide de TeamViewer](https://www.teamviewer.com/support/documents/).

Une fois que vous avez terminé, fermez la fenêtre TeamViewer.