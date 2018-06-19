---
title: Mettre à niveau des appareils Windows 10 avec Microsoft Intune - Azure | Microsoft Docs
description: Créez un profil d’appareil dans Microsoft Intune pour mettre à niveau des appareils Windows 10 avec des versions plus récentes. Découvrez également les chemins de mise à niveau pris en charge pour Windows 10 Professionnel, Édition N, Éducation, Cloud, Entreprise, Standard, Holographique et Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 994ab8e7d955d18b293e4d9e9661e0c44baaaa1f
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025431"
---
# <a name="configure-windows-10-edition-upgrade-profile-in-intune"></a>Configurer un profil de mise à niveau d’édition Windows 10 dans Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configurez un profil de mise à niveau dans Intune pour mettre à niveau automatiquement les appareils qui exécutent Windows 10 vers une version différente. Découvrez également les chemins de mise à niveau pris en charge.

## <a name="before-you-begin"></a>Avant de commencer
Avant de mettre à niveau des appareils vers la dernière version, vous avez besoin de l’un des éléments suivants :

- Une clé de produit valide pour installer la version de Windows mise à jour sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Desktop). Vous pouvez utiliser des clés MAK (Multiple Activation Key) ou KMS (Key Management Server) ou un fichier de licence Microsoft qui contient les informations de licence permettant d’installer la version de Windows mise à jour sur tous les appareils que vous ciblez avec la stratégie (pour les éditions Windows 10 Mobile et Windows 10 Holographique).
- Les appareils Windows 10 auxquels vous affectez la stratégie sont inscrits dans Microsoft Intune. Vous ne pouvez pas utiliser la stratégie de mise à niveau d’édition avec des PC qui exécutent le logiciel client PC Intune.

## <a name="supported-upgrade-paths"></a>Chemins de mise à niveau pris en charge
Le tableau suivant indique les chemins de mise à niveau pris en charge pour le profil de mise à niveau de l’édition Windows 10.

| Mise à niveau à partir de | Mise à niveau vers |
|---|---|
| Windows 10 Professionnel | Windows 10 Éducation <br/>Windows 10 Entreprise <br/>Windows 10 Pro Éducation |
| Windows 10 Professionnel N | Windows 10 Éducation N <br/>Windows 10 Édition Entreprise N <br/>Windows 10 Pro Éducation N | 
| Windows 10 Pro Éducation | Windows 10 Éducation | 
| Windows 10 Pro Éducation N | Windows 10 Éducation N |
| Windows 10 Cloud | Windows 10 Éducation <br/>Windows 10 Entreprise <br/>Windows 10 Professionnel <br/>Windows 10 Pro Éducation | 
| Windows 10 Cloud N | Windows 10 Éducation N <br/>Windows 10 Édition Entreprise N <br/>Windows 10 Professionnel N <br/>Windows 10 Pro Éducation N | 
| Windows 10 Entreprise | Windows 10 Éducation | 
| Windows 10 Édition Entreprise N | Windows 10 Éducation N | 
| Windows 10 Core | Windows 10 Éducation <br/>Windows 10 Entreprise <br/>Windows 10 Pro Éducation | 
| Windows 10 Core N | Windows 10 Éducation N <br/>Windows 10 Édition Entreprise N <br/>Windows 10 Pro Éducation N | 
| Windows 10 Holographique | Windows 10 Holographique pour entreprises |
| Windows 10 Mobile | Windows 10 Mobile Entreprise |


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

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
1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Configuration de l’appareil**, **Profils**, puis **Créer un profil**.
4. Entrez un **Nom** et une **Description** pour le profil de mise à niveau d’édition.
5. À partir de la liste déroulante **Plateforme**, sélectionnez **Windows 10 et versions ultérieures**.
6. À partir de la liste déroulante **Type de profil**, sélectionnez **Mise à niveau d’édition**.
7. Dans les propriétés **Mise à niveau d’édition**, entrez les paramètres suivants :
   - **Édition vers laquelle mettre à niveau** : dans la liste déroulante, sélectionnez la version de Windows 10 Desktop, Windows 10 Holographique ou Windows 10 Mobile vers laquelle vous mettez à niveau les appareils ciblés.
   - **Clé de produit** : entrez la clé de produit fournie par Microsoft pouvant être utilisée pour mettre à niveau tous les appareils Windows 10 Desktop ciblés. 
    Une fois que vous avez créé une stratégie qui contient une clé de produit, la clé ne peut plus être mise à jour et est masquée pour des raisons de sécurité. Pour changer la clé de produit, retapez-la en entier.
   - **Fichier de licence** : choisissez **Parcourir** pour sélectionner le fichier de licence fourni par Microsoft. Ce fichier de licence contient des informations de licence pour l’édition Windows Holographique ou Windows 10 Mobile vers laquelle vous mettez à niveau les appareils ciblés.
8. Une fois que vous avez terminé, sélectionnez **Créer** pour enregistrer les modifications.

Le profil est créé et apparaît dans la liste des profils.

## <a name="next-steps"></a>Étapes suivantes

Pour attribuer ce profil à des groupes, consultez [Guide pratique pour attribuer des profils d’appareil](device-profile-assign.md).

>[!NOTE]
>Si vous supprimez par la suite l’affectation de stratégie, la version de Windows sur l’appareil n’est pas annulée et continue de fonctionner normalement.