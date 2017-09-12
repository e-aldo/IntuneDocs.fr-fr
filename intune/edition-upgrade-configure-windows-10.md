---
title: "Configurer des mises à niveau Windows 10 avec Intune"
titlesuffix: Azure portal
description: "Apprenez à utiliser Intune pour mettre à niveau vers une version différente les appareils Windows 10 que vous gérez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f6bd4c4af168bc64acabc05fdaad93558ddd10a
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Guide pratique pour configurer des mises à niveau de l’édition Windows 10 dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez les informations de cette rubrique pour découvrir comment configurer un profil de mise à niveau Windows 10. Ce profil vous permet de mettre à niveau automatiquement les appareils qui exécutent les versions suivantes de Windows 10 vers une version différente :

- Windows 10 Famille
- Windows 10 Holographique
- Windows 10 Mobile


Les chemins de mise à niveau pris en charge sont les suivants :

- De Windows 10 Professionnel vers Windows 10 Entreprise
- De Windows 10 Famille vers Windows 10 Éducation
- De Windows 10 Mobile vers Windows 10 Mobile Entreprise
- De Windows 10 Holographique Professionnel vers Windows 10 Holographique Entreprise


## <a name="before-you-start"></a>Avant de commencer
Avant de commencer à mettre à niveau des appareils vers la dernière version, vous avez besoin d’un des éléments suivants :

- Une clé de produit valide pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Desktop). Vous pouvez utiliser des clés MAK (Multiple Activation Key) ou KMS (Key Management Server) ou Un fichier de licence de Microsoft qui contient les informations de licence permettant d’installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Mobile et Windows 10 Holographique).
- Les appareils Windows 10 auxquels vous attribuez la stratégie doivent être inscrits dans Microsoft Intune. Vous ne pouvez pas utiliser la stratégie de mise à niveau d’édition avec des PC qui exécutent le logiciel client PC Intune.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Création d’un profil d'appareil contenant des paramètres de restriction d'appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de Services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de mise à niveau d’édition.
5. À partir de la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. À partir de la liste déroulante **Type de profil**, sélectionnez **Mise à niveau d’édition**.
7. Dans le panneau **Mise à niveau d’édition**, configurez les paramètres suivants :
    - **Édition depuis laquelle mettre à niveau** : dans la liste déroulante, sélectionnez la version de Windows 10 que vous souhaitez mettre à niveau sur les appareils.
    - **Édition vers laquelle mettre à niveau** : dans la liste déroulante, sélectionnez la version de Windows 10 (bureau), Windows 10 Holographique ou Windows 10 Mobile que vous souhaitez mettre à niveau pour les appareils ciblés.
    - **Clé de produit** : spécifiez la clé de produit que vous avez obtenue auprès de Microsoft pouvant être utilisée pour mettre à niveau tous les appareils de bureau Windows 10 ciblés.<br>.Après avoir créé une stratégie qui contient une clé de produit, vous ne pouvez pas modifier la clé de produit ultérieurement. La raison en est que la clé est masquée pour des raisons de sécurité. Pour changer la clé de produit, vous devez la réentrer en entier.
    - **Fichier de licence** : choisissez **Parcourir** pour sélectionner le fichier de licence que vous avez obtenu auprès de Microsoft contenant les informations de licence pour la version de Windows Holographique ou Windows 10 Mobile que vous souhaitez mettre à niveau sur les appareils ciblés.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="next-steps"></a>Étapes suivantes

Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareils](device-profile-assign.md).

>[!NOTE]
>Si vous supprimez par la suite l’affectation de stratégie, la version de Windows sur l’appareil n’est pas annulée et continue de fonctionner normalement.

