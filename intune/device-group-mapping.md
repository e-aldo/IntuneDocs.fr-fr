---
title: "Guide pratique pour utiliser des catégories d’appareils dans Intune"
titleSuffix: Azure portal
description: "Découvrez comment utiliser les catégories d'appareils que les utilisateurs peuvent choisir lorsqu’ils inscrivent leurs appareils dans Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c100193c7db2be1a5655a1b77e1eec452a189d64
ms.sourcegitcommit: 5004b9564915712b41860df20324f39fac3dc27d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="map-device-groups"></a>Mappage de groupes d'appareils

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez les catégories d'appareils Microsoft Intune pour ajouter automatiquement des appareils à des groupes en fonction des catégories que vous définissez, afin de simplifier la gestion de ces appareils.

Les catégories d'appareils suivent le processus suivant :
1. Créez des catégories parmi lesquelles les utilisateurs effectuent leur choix quand ils inscrivent leurs appareils.
2. Quand des utilisateurs finaux d’appareils iOS et Android inscrivent leur appareil, ils doivent choisir une catégorie dans la liste des catégories que vous avez configurées. Pour affecter une catégorie à un appareil Windows, les utilisateurs finaux doivent utiliser le site web du portail d’entreprise (pour plus d’informations, voir **Après avoir configuré des groupes d’appareils** dans cet article).
3. Vous pouvez ensuite déployer des stratégies et des applications sur ces groupes.

Vous pouvez créer toute catégorie d’appareils souhaitée, par exemple :
- Appareil de point de vente
- Appareil de démonstration
- Ventes
- Gestion des comptes
- Manager

## <a name="how-to-configure-device-categories"></a>Comment configurer des catégories d'appareils

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Étape 1 : créer des catégories d'appareils dans le panneau Intune du portail Azure
1. Dans le portail Azure, choisissez **Autres services** > **Surveillance + gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Inscription de l’appareil**.
3. Dans le panneau **Inscription de l’appareil** choisissez **Catégories d’appareils**.
4. Sur la page **Catégories d’appareils**, choisissez **Créer** pour ajouter une nouvelle catégorie.
5. Dans le panneau suivant, entrez un **Nom** pour la nouvelle catégorie et éventuellement une **Description**.
6. Quand vous avez terminé, cliquez sur **Créer**. Vous pouvez voir la nouvelle catégorie dans la liste des catégories.

Vous utiliserez le nom de catégorie d’appareil quand vous créerez des groupes de sécurité Active Directory Azure à l’étape 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Étape 2 : Créer des groupes de sécurité Active Directory
Au cours de cette étape, vous allez créer des groupes dynamiques dans le portail Azure basés sur la catégorie d’appareil et le nom de la catégorie d’appareil.

Pour continuer, reportez-vous à l’article [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) dans la documentation d’Azure Active Directory.

Utilisez les informations de cette section pour créer un groupe d'appareils avec une règle avancée à l’aide de l’attribut **deviceCategory**. Par exemple, (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Une fois que vous configurez des groupes d'appareils et que les utilisateurs inscrivent leurs appareils, ces derniers peuvent voir une liste des catégories que vous avez configurées. Une fois qu’ils choisissent une catégorie et terminent l’inscription, leur appareil est ajouté au groupe de sécurité Active Directory qui correspond à la catégorie choisie.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Comment afficher les catégories d’appareils que vous gérez

1.  Dans le portail Azure, choisissez **Autres services** > **Surveillance + gestion** > **Intune**.

2. Dans le panneau Intune du portail Azure, choisissez **Appareils et groupes**.

3.  Sous **Gérer**, cliquez sur **Tous les appareils**.

4.  Dans la liste des appareils, examinez la colonne **Catégorie**.

Si la colonne **Catégorie** n’est pas affichée, cliquez sur **Colonnes**, choisissez **Catégorie** dans la liste, puis cliquez sur **Appliquer**.

### <a name="to-change-the-category-of-a-device"></a>Pour modifier la catégorie d’un appareil

1. Dans le portail Azure, choisissez **Autres services** > **Surveillance + gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Appareils et groupes**.
4. Dans le panneau **Appareils et groupes**, choisissez **Gérer** > **Tous les appareils**.
5. Dans la liste des appareils, cliquez sur l’appareil de votre choix, puis, dans le panneau de propriétés de l’appareil, choisissez **Gérer** > **Propriétés**.
6. Dans le panneau suivant, vous pouvez modifier la **Catégorie** de l’appareil sélectionné sur un des noms de catégorie que vous avez configurés précédemment.

## <a name="after-you-configure-device-groups"></a>Après avoir configuré des groupes d’appareils

Quand des utilisateurs finaux d’appareils iOS et Android inscrivent leur appareil, ils doivent choisir une catégorie dans la liste des catégories que vous avez configurées. Une fois qu’ils ont choisi une catégorie et terminé l’inscription, leur appareil est ajouté au groupe d’appareils Intune ou au groupe de sécurité Active Directory correspondant à la catégorie choisie.

Quelle que soit la plateforme, vos utilisateurs finaux peuvent toujours accéder à portal.manage.microsoft.com après avoir inscrit l’appareil. Invitez l’utilisateur à se rendre sur le site web Portail d’entreprise et à accéder à **Mes appareils**. Ils peuvent choisir un appareil inscrit répertorié à l’écran, puis sélectionner une catégorie.

Une fois le choix de catégorie effectué, l’appareil est ajouté automatiquement au groupe correspondant que vous avez créé. Si un appareil est déjà inscrit avant de configurer les catégories, l’utilisateur final verra une notification sur l’appareil sur le site web du portail d’entreprise, et il est invité à sélectionner une catégorie la prochaine fois qu’il accède à l’application de portail d’entreprise sur iOS ou Android.

## <a name="further-information"></a>Informations supplémentaires
- Vous pouvez modifier une catégorie d’appareil dans le portail Azure, mais vous devez manuellement mettre à jour tous les groupes de sécurité Azure Active Directory qui font référence à cette catégorie.

- Si vous supprimez une catégorie, les appareils qui lui ont été affectés affichent le nom de catégorie **Non affecté**.
