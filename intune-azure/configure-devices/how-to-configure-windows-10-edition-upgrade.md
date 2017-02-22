---
title: "Configuration des mises à niveau vers l’édition Windows 10 avec Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : apprenez à utiliser Intune pour mettre à niveau les appareils Windows 10 que vous gérez."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 9ce16ea61da87aa5087fafeb5c1eaf743fef4a14


---

# <a name="how-to-configure-windows-10-edition-upgrades"></a>Guide pratique de configuration des mises à niveau Windows 10 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez les informations de cette rubrique pour découvrir comment configurer un profil de mise à niveau Windows 10. Ce profil vous permet de mettre à niveau automatiquement les appareils qui exécutent les versions suivantes de Windows 10 vers une version plus récente :

- Windows 10 Desktop
- Windows 10 Holographique
- Windows 10 Mobile

Les chemins de mise à niveau pris en charge sont les suivants :

- De Windows 10 Professionnel vers Windows 10 Entreprise
- De Windows 10 Famille vers Windows 10 Éducation
- De Windows 10 Mobile vers Windows 10 Mobile Entreprise
- De Windows 10 Holographique Professionnel vers Windows 10 Holographique Entreprise

## <a name="before-you-start"></a>Avant de commencer
Avant de commencer à mettre à niveau des appareils vers la dernière version, vous avez besoin d’un des éléments suivants :

- Une clé de produit valide pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Desktop). Vous pouvez utiliser les touches Clés d’activation multiple (MAK) ou Serveur gestionnaire de clés (KMS). ou un fichier de licence de Microsoft qui contient les informations de licence pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions de Windows 10 Mobile et Windows 10 Holographique).
- Les appareils Windows 10 que vous ciblez doivent être inscrits dans Microsoft Intune. Vous ne pouvez pas utiliser la stratégie de mise à niveau d’édition avec des PC qui exécutent le logiciel client PC Intune.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Création d’un profil d'appareil contenant des paramètres de restriction d'appareil

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de mise à niveau d’édition.
5. À partir de la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. À partir de la liste déroulante **Type de profil**, sélectionnez **Mise à niveau d’édition**.
7. Dans le panneau **Mise à niveau d’édition**, configurez les éléments suivants :
    - **Édition depuis laquelle mettre à niveau** : dans la liste déroulante, sélectionnez la version de Windows 10 que vous souhaitez mettre à niveau sur les appareils.
    - **Édition vers laquelle mettre à niveau** : dans la liste déroulante, sélectionnez la version de Windows 10 (bureau), Windows 10 Holographique ou Windows 10 Mobile que vous souhaitez mettre à niveau pour les appareils ciblés.
    - **Clé de produit** : spécifiez la clé de produit que vous avez obtenue auprès de Microsoft pouvant être utilisée pour mettre à niveau tous les appareils de bureau Windows 10 ciblés.<br>.Après avoir créé une stratégie qui contient une clé de produit, vous ne pouvez pas modifier la clé de produit ultérieurement. La raison en est que la clé est masquée pour des raisons de sécurité. Pour changer la clé de produit, vous devez la réentrer en entier.
    - **Fichier de licence** : choisissez **Parcourir** pour sélectionner le fichier de licence que vous avez obtenu auprès de Microsoft contenant les informations de licence pour la version de Windows Holographique ou Windows 10 Mobile que vous souhaitez mettre à niveau sur les appareils ciblés.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le volet de la liste des profils.
Si vous souhaitez continuer et affecter ce profil à des groupes, consultez [Guide pratique d’affectation des profils d'appareil](how-to-assign-device-profiles.md).




<!--HONumber=Feb17_HO1-->

