---
title: "Paramètres de la stratégie de mise à niveau d’édition Windows | Microsoft Docs"
description: "Découvrez comment utiliser Intune pour mettre à niveau automatiquement vos appareils Windows 10 vers une autre version."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 81061f032ef2079695f45e54e99cbb6479252bed
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie de mise à niveau d’édition Windows dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

La **stratégie de mise à niveau d’édition** Microsoft Intune vous permet de mettre automatiquement à niveau les appareils qui exécutent l’une des versions suivantes de Windows 10 vers une édition différente :
* Windows 10 Desktop
* Windows 10 Holographique
* Windows 10 Mobile

Les chemins de mise à niveau pris en charge sont les suivants :
- De Windows 10 Professionnel vers Windows 10 Entreprise
- De Windows 10 Famille vers Windows 10 Éducation
- De Windows 10 Mobile vers Windows 10 Mobile Entreprise
- De Windows 10 Holographique Professionnel vers Windows 10 Holographique Entreprise

## <a name="before-you-start"></a>Avant de commencer
Avant de commencer à mettre à niveau des appareils vers la dernière version, vous avez besoin d’un des éléments suivants :
* Une clé de produit valide pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Desktop). Vous pouvez utiliser les touches Clés d’activation multiple (MAK) ou Serveur gestionnaire de clés (KMS).
**ou** Un fichier de licence de Microsoft qui contient les informations de licence permettant d’installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Mobile et Windows 10 Holographique).
* Les appareils Windows 10 que vous ciblez doivent être inscrits dans Microsoft Intune. Vous ne pouvez pas utiliser la stratégie de mise à niveau d’édition avec des PC qui exécutent le logiciel client PC Intune.

## <a name="edition-upgrade-policy-settings"></a>Paramètres de stratégie de mise à niveau d’édition

|Nom du paramètre|Détails|
|-|-|
|**Nom**|Entrez un nom pour la stratégie de mise à niveau d’édition.|
|**Description**|Si vous le souhaitez, entrez une description pour la stratégie qui vous permet de l’identifier dans la console Intune.
|**Édition vers laquelle mettre à niveau**|Dans la liste déroulante, sélectionnez la version de Windows 10 Desktop, Windows 10 Holographique ou Windows 10 Mobile vers laquelle vous voulez mettre à niveau les appareils ciblés.
|**Clé de produit**|Spécifiez la clé de produit fournie par Microsoft, que vous pouvez utiliser pour mettre à niveau tous les appareils Windows 10 Desktop ciblés.<br>Une fois que vous avez créé une stratégie qui contient une clé de produit, vous ne pouvez plus modifier la clé de produit. La raison en est que la clé est masquée pour des raisons de sécurité. Pour changer la clé de produit, vous devez la réentrer en entier.
|**Fichier de licence**|Choisissez **Parcourir** pour sélectionner le fichier de licence fournie par Microsoft qui contient des informations de licence pour l’édition Windows Holographique ou Windows 10 Mobile vers laquelle vous souhaitez mettre à niveau les appareils ciblés.

### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

