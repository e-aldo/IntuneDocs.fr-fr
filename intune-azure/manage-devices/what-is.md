---
title: "Gérer des appareils avec Intune"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : découvrez comment afficher les appareils que vous gérez avec Intune et effectuer diverses opérations dessus."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 8a43e1646476696b978a7f8a3e92f920606a698b
ms.lasthandoff: 03/17/2017


---

# <a name="what-is-microsoft-intune-device-management"></a>Qu’est-ce que la gestion des appareils Microsoft Intune ? 


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

La charge de travail **Appareils** vous donne des informations sur les appareils que vous gérez et vous permet de procéder à des tâches à distance sur ces appareils. Pour accéder à la charge de travail :

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils**.

Maintenant, choisissez l’une des options suivantes :

- **Vue d’ensemble** : obtenez des informations sur les appareils inscrits, et les systèmes d’exploitation que chaque appareil s’exécute.
- **Gérer** : choisissez **Tous les appareils** pour afficher la liste de tous les appareils que vous gérez.
    Sélectionnez un de ces appareils dans la liste pour ouvrir le panneau <*Nom de l’appareil*> **Vue d’ensemble** où vous pouvez sélectionner un des éléments suivants :
    - **Vue d’ensemble** : consultez des informations générales sur l’appareil, notamment des informations sur son nom, son propriétaire, s’il s’agit d’un appareil BYOD, son dernier archivage et bien plus encore. 
                
    - **Matériel** : plus d’informations sur l’appareil, y compris son espace de stockage libre, son modèle et le fabricant, et bien plus encore.
    ![Inventaire matériel des appareils gérés](./media/hardware-inventory.png)
    - **Applications détectées** : affiche une liste de toutes les applications qu’Intune trouve installées sur l’appareil.
    ![Nœud Applications détectées](./media/detected-applications.png)
- **Moniteur** : choisissez **Actions d’appareil** pour afficher une liste d’actions d’appareil qui ont été effectuées sur les appareils que vous gérez et l’état actuel de ces actions.
![Surveiller les actions des appareils](./media/monitor-device-actions.png)
- **Aide et support** : affiche les liens vers la documentation sur la résolution des problèmes et le support technique.

## <a name="available-device-actions"></a>Actions d’appareils disponibles

En outre, vous pouvez effectuer les actions suivantes à distance sur l’appareil (toutes les actions ne sont pas prises en charge par toutes les plateformes d’appareils) :

### <a name="remove-company-data"></a>**Supprimer les données d’entreprise**
Supprime uniquement les données d’entreprise gérées par Intune. Cela ne supprime pas les données personnelles de l’appareil. L’appareil ne sera plus géré par Intune et ne sera plus en mesure d’accéder aux ressources d’entreprise (non pris en charge pour les appareils Windows joints à Azure Active Directory).

### <a name="factory-reset"></a>**Réinitialisation aux paramètres d’usine**
Réinitialise l’appareil à ses paramètres par défaut. L’appareil ne sera plus géré par Intune et les données personnelles et d’entreprise seront supprimées. Vous ne pouvez pas annuler cette action.

### <a name="remote-lock"></a>**Verrouillage à distance**
Verrouille l’appareil. Le propriétaire de l’appareil doit utiliser son mot de passe pour le déverrouiller. Vous pouvez verrouiller à distance uniquement les appareils avec un code confidentiel ou un mot de passe défini.

### <a name="reset-passcode"></a>**Réinitialiser le code secret**
Génère un nouveau code pour l’appareil qui sera affiché dans le panneau <*Nom de l’appareil*> **Vue d’ensemble**.

### <a name="bypass-activation-lock"></a>**Contourner le verrou d’activation**
Cela supprime le verrou d’activation des appareils iOS sans qu’il soit nécessaire d’avoir l’ID Apple et le mot de passe de l’utilisateur. Une fois que vous contournez le verrou d’activation, l’appareil l’active à nouveau au démarrage de l’application Trouver mon iPhone. Contournez le verrou d’activation uniquement si vous avez un accès physique à l’appareil.

### <a name="lost-mode"></a>**Mode Perdu**
Si un appareil iOS a été volé ou perdu, vous pouvez activer le mode Perdu. Cela vous permet de spécifier un message et un numéro de téléphone qui s’affichent sur l’écran de verrouillage de l’appareil. Pour cela :
1.    Dans le volet Propriétés d’un appareil iOS, choisissez **Plus** > **Mode Perdu**.
2.    Dans le panneau **Mode Perdu**, activez le mode Perdu, entrez le message qui s’affiche et éventuellement un numéro de téléphone de contact.
3.    Cliquez sur **OK**.
Lorsque vous activez le mode Perdu, vous bloquez l’utilisation de l’appareil. L’utilisateur final ne peut pas accéder à l’appareil tant que vous n’avez pas désactivé le mode Perdu. Quand le mode Perdu est activé, vous pouvez utiliser l’action **Localiser l’appareil** pour rechercher l’emplacement de l’appareil.
Pour utiliser le mode Perdu, l’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé.

### <a name="locate-device"></a>**Localiser l’appareil**
Utilisez cette action à distance pour afficher l’emplacement d’un appareil iOS perdu ou volé sur une carte. L’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé. Avant que vous puissiez utiliser cette action, l’appareil doit être configuré en mode Perdu.
1.    Dans le volet Propriétés d’un appareil iOS, choisissez **Plus** > **Localiser l’appareil**.
2.    Une fois que l’appareil a été localisé, son emplacement s’affiche dans le panneau **Localiser l’appareil**. 
    ![Panneau Localiser l’appareil](./media/locate-device.png)

### <a name="restart"></a>**Redémarrer**
Force le redémarrage de l’appareil. Le propriétaire de l’appareil n’est pas automatiquement informé du redémarrage, et peut ainsi perdre son travail.


## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Informations de sécurité et de confidentialité pour le mode Perdu et actions Localiser l’appareil
- Aucune information d’emplacement de l’appareil n’est envoyée à Intune tant que vous n’activez pas cette action.
- Lorsque vous utilisez l’action Localiser l’appareil, les coordonnées de latitude et de longitude de l’appareil sont envoyées à Intune et affichées dans le portail Azure.
- Les données sont stockées pendant 24 heures avant d’être supprimées. Vous ne pouvez pas supprimer manuellement les données d’emplacement.
- Les données d’emplacement sont chiffrées aussi bien pendant leur stockage que leur transmission.
- Lorsque vous configurez le mode Perdu, nous vous recommandons de rédiger le message qui s’affiche sur l’écran de verrouillage de façon à ce qu’il inclue des informations qui permettent de déterminer l’emplacement de l’appareil.

