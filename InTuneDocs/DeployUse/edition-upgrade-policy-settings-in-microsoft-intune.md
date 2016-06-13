---
# required metadata

title: Paramètres de la stratégie de mise à niveau d’édition Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie de mise à niveau d’édition Windows dans Microsoft Intune
La **stratégie de mise à niveau d’édition** Microsoft Intune vous permet de mettre automatiquement à niveau les appareils qui exécutent l’une des versions suivantes de Windows 10 vers une édition plus récente :
* Windows 10 Desktop
* Windows 10 Holographique

## Avant de commencer
Avant de commencer à mettre à niveau des appareils vers la dernière version, vous avez besoin d’un des éléments suivants :
* Une clé de produit valide pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Desktop).
* Un fichier de licence de Microsoft, qui contient les informations de licence pour installer la nouvelle version de Windows sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Mobile et Windows 10 Holographique).
* Les appareils Windows 10 que vous ciblez doivent être inscrits dans Microsoft Intune.

## Paramètres de stratégie de mise à niveau d’édition

|Nom du paramètre|Détails|
|-|-|
|**Nom**|Entrez un nom pour la stratégie de mise à niveau d’édition.|
|**Description**|Si vous le souhaitez, entrez une description pour la stratégie qui vous permet de l’identifier dans la console Intune.
|**Édition vers laquelle mettre à niveau**|Dans la liste déroulante, sélectionnez la version de Windows 10 Desktop, Windows 10 Holographique ou Windows 10 Mobile vers laquelle vous voulez mettre à niveau les appareils ciblés.
|**Clé du produit**|Spécifiez la clé de produit fournie par Microsoft, que vous pouvez utiliser pour mettre à niveau tous les appareils Windows 10 Desktop ciblés.<br>Une fois que vous avez créé une stratégie contenant une clé de produit, vous ne pouvez plus modifier la clé de produit. La raison en est que la clé est masquée pour des raisons de sécurité. Pour changer la clé de produit, vous devez entrer à nouveau toute la clé.
|**Fichier de licence**|Cliquez sur **Parcourir** pour sélectionner le fichier de licence fournie par Microsoft qui contient des informations de licence pour l’édition Windows Holographique ou Windows 10 Mobile vers laquelle vous souhaitez mettre à niveau les appareils ciblés.

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

<!--HONumber=Jun16_HO1-->


