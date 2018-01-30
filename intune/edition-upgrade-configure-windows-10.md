---
title: "Configurer des mises à niveau Windows 10 avec Intune"
titlesuffix: Azure portal
description: "Apprenez à utiliser Intune pour mettre à niveau vers une version différente les appareils Windows 10 que vous gérez."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 12/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8581aea9db4c04efda5fe9f3281be95330bcd2e2
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Guide pratique pour configurer des mises à niveau de l’édition Windows 10 dans Microsoft Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez les informations de cet article pour découvrir comment configurer un profil de mise à niveau Windows 10. Ce profil vous permet de mettre à niveau automatiquement les appareils qui exécutent Windows 10 vers une version différente. 

## <a name="before-you-start"></a>Avant de commencer
Avant de commencer à mettre à niveau des appareils vers la dernière version, vous avez besoin d’un des éléments suivants :

- Une clé de produit valide pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Desktop). Vous pouvez utiliser des clés MAK (Multiple Activation Key) ou KMS (Key Management Server) ou Un fichier de licence de Microsoft qui contient les informations de licence permettant d’installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Mobile et Windows 10 Holographique).
- Les appareils Windows 10 auxquels vous attribuez la stratégie doivent être inscrits dans Microsoft Intune. Vous ne pouvez pas utiliser la stratégie de mise à niveau d’édition avec des PC qui exécutent le logiciel client PC Intune.

## <a name="supported-upgrade-paths-for-the-windows-10-edition-upgrade-profile"></a>Chemins de mise à niveau pris en charge pour le profil de mise à niveau de l’édition Windows 10
Les listes suivantes indiquent les chemins de mise à niveau pris en charge pour le profil de mise à niveau de l’édition Windows 10. L’édition Windows 10 à mettre à niveau est affichée en gras, suivie de la liste des éditions prises en charge à partir desquelles vous pouvez effectuer la mise à niveau :

**Windows 10 Éducation**
- Windows 10 Professionnel
- Windows 10 Pro Éducation
- Windows 10 Cloud
- Windows 10 Entreprise
- Windows 10 Core
    
**Windows 10 Éducation N**    
- Windows 10 Professionnel N
- Windows 10 Pro Éducation N
- Windows 10 Cloud N
- Windows 10 Édition Entreprise N
- Windows 10 Core N
    
**Windows 10 Enterprise**
- Windows 10 Professionnel
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Édition Entreprise N**
- Windows 10 Professionnel N
- Windows 10 Cloud N
- Windows 10 Core N
    
**Windows 10 Professionnel**
- Windows 10 Cloud
    
**Windows 10 Professionnel N**
- Windows 10 Cloud N
    
**Windows 10 Pro Éducation**
- Windows 10 Professionnel
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Éducation N**
- Windows 10 Professionnel N
- Windows 10 Cloud N
- Windows 10 Core N

**Windows 10 Holographique pour entreprises**
- Windows 10 Holographique

**Windows 10 Mobile Entreprise**
- Windows 10 Mobile

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Créer un profil d’appareil contenant des paramètres de restriction de l’appareil
1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de mise à niveau d’édition.
5. À partir de la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. À partir de la liste déroulante **Type de profil**, sélectionnez **Mise à niveau d’édition**.
7. Dans le panneau **Mise à niveau d’édition**, configurez les paramètres suivants :
    - **Édition vers laquelle mettre à niveau** : dans la liste déroulante, sélectionnez la version de Windows 10 (bureau), Windows 10 Holographique ou Windows 10 Mobile que vous souhaitez mettre à niveau pour les appareils ciblés.
    - **Clé de produit** : spécifiez la clé de produit que vous avez obtenue auprès de Microsoft pouvant être utilisée pour mettre à niveau tous les appareils de bureau Windows 10 ciblés.<br>.Après avoir créé une stratégie qui contient une clé de produit, vous ne pouvez pas modifier la clé de produit ultérieurement. La raison en est que la clé est masquée pour des raisons de sécurité. Pour changer la clé de produit, vous devez la réentrer en entier.
    - **Fichier de licence** : choisissez **Parcourir** pour sélectionner le fichier de licence que vous avez obtenu auprès de Microsoft contenant les informations de licence pour la version de Windows Holographique ou Windows 10 Mobile vers laquelle vous souhaitez mettre à niveau les appareils ciblés.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="next-steps"></a>Étapes suivantes

Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](device-profile-assign.md).

>[!NOTE]
>Si vous supprimez par la suite l’affectation de stratégie, la version de Windows sur l’appareil n’est pas annulée et continue de fonctionner normalement.

