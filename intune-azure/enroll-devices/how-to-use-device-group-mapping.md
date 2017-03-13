---
title: "Guide pratique pour utiliser des catégories d’appareils dans Intune"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez comment utiliser les catégories d&quot;appareils que les utilisateurs peuvent choisir lorsqu’ils inscrivent leurs appareils dans Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: c635ced382074f7f45254fb219b58f54b56abb8e
ms.lasthandoff: 02/18/2017


---

# <a name="map-device-groups"></a>Mappage de groupes d'appareils


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez les catégories d'appareils Microsoft Intune pour ajouter automatiquement des appareils à des groupes en fonction des catégories que vous définissez, afin de simplifier la gestion de ces appareils.

Les catégories d'appareils suivent le processus suivant :
1.    Créez des catégories parmi lesquelles les utilisateurs effectuent leur choix quand ils inscrivent leurs appareils.
4.    Quand des utilisateurs finaux inscrivent leur appareil, ils doivent choisir une catégorie dans la liste des catégories que vous avez configurées. Si un appareil est déjà inscrit, l’utilisateur final est invité à sélectionner une catégorie la prochaine fois qu’il accède à l’application Portail d’entreprise.


Vous pouvez créer toute catégorie d’appareils souhaitée, par exemple :
- Appareil de point de vente
- Appareil de démonstration
- Ventes
- Gestion des comptes
- Manager

## <a name="how-to-configure-device-categories"></a>Comment configurer des catégories d'appareils

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Étape 1 : créer des catégories d'appareils dans le panneau Intune du portail Azure
1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscrire des appareils**.
3. Dans le panneau **Inscription** choisissez **Catégories**.
4. Sur la page **Catégories d’appareils**, choisissez **Créer** pour ajouter une nouvelle catégorie.
5. Dans le panneau suivant, entrez un **Nom** pour la nouvelle catégorie et éventuellement une **Description**.
6. Quand vous avez terminé, cliquez sur **Créer**. Vous verrez la catégorie que vous venez de créer dans la liste des catégories.

Vous utiliserez le nom de catégorie d’appareil quand vous créerez des groupes de sécurité Active Directory Azure à l’étape 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Étape 2 : Créer des groupes de sécurité Active Directory
Au cours de cette étape, vous allez créer des groupes dynamiques dans le portail Azure basés sur la catégorie d’appareil et le nom de la catégorie d’appareil.

Pour continuer, reportez-vous à la rubrique [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) dans la documentation d’Azure Active Directory. 

Utilisez les informations de cette section pour créer un groupe d'appareils avec une règle avancée à l’aide de l’attribut **deviceCategory**. Par exemple (**device.deviceCategory -eq** "*<the device category name you got from the Intune portal>*")

Une fois que vous configurez des groupes d'appareils et que les utilisateurs inscrivent leurs appareils, ces derniers peuvent voir une liste des catégories que vous avez configurées. Une fois qu’ils choisissent une catégorie et terminent l’inscription, leur appareil est ajouté au groupe de sécurité Active Directory qui correspond à la catégorie choisie.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Comment afficher les catégories d’appareils que vous gérez

1.    Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune du portail Azure, choisissez **Appareils et groupes**.

3.    Sous **Gérer**, cliquez sur **Tous les appareils**.

4.    Dans la liste des appareils, examinez la colonne **Catégorie**.

Si la colonne **Catégorie** n’est pas affichée, cliquez sur **Colonnes**, choisissez **Catégorie** dans la liste, puis cliquez sur **Appliquer**.

### <a name="to-change-the-category-of-a-device"></a>Pour modifier la catégorie d’un appareil

1. Dans le portail Azure, choisissez **Plus de services** > **Surveillance + gestion** > **Intune**.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils et groupes**.
4. Dans le panneau **Appareils et groupes**, choisissez **Gérer** > **Tous les appareils**.
5. Dans la liste des appareils, cliquez sur l’appareil de votre choix, puis, dans le panneau de propriétés de l’appareil, choisissez **Gérer** > **Propriétés**.
6. Dans le panneau suivant, vous pouvez modifier la **Catégorie** de l’appareil sélectionné sur un des noms de catégorie que vous avez configurés précédemment.



## <a name="further-information"></a>Informations supplémentaires
- Vous pouvez modifier une catégorie dans le portail Azure, mais si vous le faites, vous devrez manuellement mettre à jour tous les groupes de sécurité Azure Active Directory qui font référence à cette catégorie.

- Si vous supprimez une catégorie, tous les appareils qui lui ont été affectés afficheront alors le nom de catégorie **Non affecté**.



