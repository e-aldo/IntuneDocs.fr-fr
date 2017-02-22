---
title: "Gestion des appareils avec Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment afficher les appareils que vous gérez avec Intune et effectuer diverses opérations dessus."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 040c4e18d87110ab7380a64540d08127574a7c46
ms.openlocfilehash: 5a967cc1be387f83f95591186f786db61d3debcd


---

# <a name="what-is-device-management"></a>Qu’est-ce que la gestion des appareils ? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

La charge de travail **Appareils et groupes** vous des informations sur les appareils que vous gérez et vous permet de procéder à des tâches à distance sur ces appareils. Pour accéder à la charge de travail :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Analyse + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils et groupes**.

    ![Charge de travail Appareils et groupes](./media/devices-and-groups-workload.png)

Maintenant, choisissez l’une des options suivantes :

- **Vue d’ensemble** : obtenez des informations sur les appareils inscrits, et les systèmes d’exploitation que chaque appareil s’exécute.
- **Gérer** : choisissez **Tous les appareils** pour afficher la liste de tous les appareils que vous gérez.
    Sélectionnez un de ces appareils dans la liste pour ouvrir le panneau <*Nom de l’appareil*> **Vue d’ensemble** où vous pouvez sélectionner un des éléments suivants :
    - **Vue d’ensemble** : consultez des informations générales sur l’appareil, notamment des informations sur son nom, son propriétaire, s’il s’agit d’un appareil BYOD, son dernier archivage et bien plus encore. En outre, vous pouvez effectuer les actions suivantes à distance sur l’appareil (toutes les actions ne sont pas prises en charge par toutes les plateformes d’appareils) :
        - **Supprimer les données d’entreprise** : supprime uniquement les données d’entreprise gérées par Intune. Cela ne supprime pas les données personnelles de l’appareil. L’appareil ne sera plus géré par Intune et ne sera plus en mesure d’accéder aux ressources d’entreprise (non pris en charge pour les appareils Windows joints à Azure Active Directory).
        - **Réinitialisation aux paramètres d’usine** : réinitialise l’appareil à ses paramètres par défaut. L’appareil ne sera plus géré par Intune et les données personnelles et d’entreprise seront supprimées. Vous ne pouvez pas annuler cette action.
        - **Verrouillage à distance** : verrouille l’appareil. Le propriétaire de l’appareil doit utiliser son mot de passe pour le déverrouiller. Vous pouvez verrouiller à distance uniquement les appareils avec un code confidentiel ou un mot de passe défini.
        - **Réinitialiser le code secret** : génère un nouveau code pour l’appareil qui sera affiché dans le panneau <*Nom de l’appareil*> **Vue d’ensemble**.
        - **Contourner le verrou d’activation** : cela vous permet de supprimer le verrou d'activation des appareils iOS sans avoir l'ID Apple et le mot de passe de l'utilisateur. Une fois que vous contournez le verrou d’activation, l’appareil l’active à nouveau au démarrage de l’application Trouver mon iPhone. Contournez le verrou d’activation uniquement si vous avez un accès physique à l’appareil.
        - **Mode perdu** : si un appareil a été volé, vous pouvez activer le mode perdu. Cela vous permet de spécifier un message et un numéro de téléphone qui s’affichent sur l’écran de verrouillage de l’appareil.
        - **Redémarrer** : force l’appareil à redémarrer. Le propriétaire de l’appareil n’est pas automatiquement informé du redémarrage, et peut ainsi perdre son travail.
        ![Vue d’ensemble de l’appareil](http://i.imgur.com/4Rx4VXm.png)
        
    - **Matériel** : plus d’informations sur l’appareil, y compris son espace de stockage libre, son modèle et le fabricant, et bien plus encore.
    ![Inventaire matériel des appareils gérés](./media/hardware-inventory.png)
    - **Applications détectées** : affiche une liste de toutes les applications qu’Intune trouve installées sur l’appareil.
    ![Nœud Applications détectées](./media/detected-applications.png)
- **Moniteur** : choisissez **Actions d’appareil** pour afficher une liste d’actions d’appareil qui ont été effectuées sur les appareils que vous gérez et l’état actuel de ces actions.
![Surveiller les actions des appareils](./media/monitor-device-actions.png)



<!--HONumber=Feb17_HO1-->


