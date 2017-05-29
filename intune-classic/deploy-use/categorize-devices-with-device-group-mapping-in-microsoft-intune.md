---
title: "Catégoriser les appareils avec le mappage de groupe d’appareils | Microsoft Docs"
description: "Le mappage de groupe d’appareils dans Microsoft Intune vous permet de regrouper des appareils dans des catégories que vous définissez afin d’en faciliter la gestion."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 618827ed6baf7a9dec6aef804f19bcbca08ed39f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017

---

# <a name="categorize-devices-with-device-group-mapping-in-microsoft-intune"></a>Catégoriser les appareils avec le mappage de groupe d’appareils dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Le **mappage de groupe d’appareils** dans Microsoft Intune vous permet d’ajouter automatiquement des appareils à des groupes basés sur des catégories que vous définissez afin d’en faciliter la gestion. 

Le mappage de groupe d’appareils utilise le flux de travail suivant :
1. Créez des catégories parmi lesquelles les utilisateurs effectuent leur choix quand ils inscrivent leurs appareils.
2. Vous créez des groupes ou utilisez des groupes existants pour chaque catégorie que vous souhaitez utiliser. Selon la version d’Intune que vous utilisez, il s’agit de groupes Intune ou de groupes de sécurité Azure Active Directory.
2. Vous configurez des règles qui mappent la catégorie choisie au groupe d’appareils que vous avez créé.
3. Quand des utilisateurs finaux inscrivent leur appareil, ils doivent choisir une catégorie dans la liste des catégories que vous avez configurées. Une fois ce choix effectué, leur appareil est ajouté automatiquement au groupe correspondant que vous avez créé. Si un appareil est déjà inscrit, l’utilisateur final est invité à sélectionner une catégorie la prochaine fois qu’il accède à l’application Portail d’entreprise.
4. Vous pouvez ensuite déployer des stratégies et des applications sur ces groupes.

Vous pouvez créer toute catégorie d’appareils souhaitée, par exemple :
* Appareil de point de vente
* Appareil de démonstration
* Ventes
* Gestion des comptes
* Manager

## <a name="important-information-about-a-change-in-group-management-for-intune"></a>Informations importantes sur une modification dans la gestion de groupe pour Intune

Sur la base de vos commentaires, nous sommes en train d’unifier l’expérience de regroupement et de ciblage dans Enterprise Mobility + Security. Ainsi, nous convertirons bientôt les groupes Intune en groupes de sécurité Azure Active Directory. Après cette modification, vous ne créerez plus de groupes à l’aide d’Intune. Au lieu de cela, vous les créerez dans le portail Azure. Cette modification sera progressive ; vous pouvez découvrir ses caractéristiques et sa chronologie dans [cette rubrique](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

### <a name="which-procedure-in-this-topic-should-you-use-to-configure-device-group-mapping"></a>Quelle procédure dans cette rubrique devez-vous suivre pour configurer le mappage de groupe d’appareils ?

En raison de l’implémentation progressive des groupes de sécurité Azure Active Directory, vous devez ouvrir l’espace de travail **Groupes** dans la [console d’administration Intune](https://manage.microsoft.com) pour identifier la procédure à utiliser :

-  Si vous voyez un lien vers le portail Azure, vous n’utilisez plus de groupes Intune. Suivez la procédure [Comment configurer le mappage de groupe d’appareils pour des groupes Azure Active Directory](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-azure-active-directory-groups) ci-dessous.
-  Si vous ne voyez pas de lien vers le portail Azure, vous utilisez toujours des groupes Intune. Suivez la procédure [Comment configurer le mappage de groupe d’appareils pour des groupes Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune#how-to-configure-device-group-mapping-for-intune-groups) ci-dessous.

## <a name="how-to-configure-device-group-mapping-for-intune-groups"></a>Comment configurer le mappage de groupe d’appareils pour des groupes Intune
1. Pour chaque catégorie que vous souhaitez utiliser, créez un groupe d’appareils Intune ou identifiez un groupe existant. Pour plus d’informations sur la création de groupes, consultez [Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration**
3. Dans l’espace de travail **Administration**, développez **Gestion des appareils mobiles**, puis choisissez **Mappage de groupe d’appareils**.
4. Dans la page **Mappage de groupe d’appareils**, activez le mappage de groupe d’appareils.
5. Choisissez **Ajouter** pour créer une règle de mappage.
6. Dans la boîte de dialogue **Ajouter une règle de mappage de groupe d’appareils**, entrez le nom de la catégorie que vous souhaitez créer puis, dans la liste déroulante, choisissez le regroupement d’appareils auquel vous souhaitez mapper cette catégorie. Choisissez **Ajouter** quand vous avez terminé.
7. Une fois que vous avez fini d’ajouter des catégories et des groupes, Choisissez **Enregistrer**.



## <a name="how-to-configure-device-group-mapping-for-azure-active-directory-groups"></a>Comment configurer le mappage de groupe d’appareils pour des groupes Azure Active Directory

### <a name="step-1---create-device-categories-in-the-intune-administration-console"></a>Étape 1 : Créer des catégories d’appareils dans la console d’administration Intune
1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration**
3. Dans l’espace de travail **Administration**, développez **Gestion des appareils mobiles**, puis choisissez **Catégories d’appareil**.
4. Dans la page **Catégories d’appareil** apparaît une liste où vous pouvez configurer les catégories d’appareils : 
- Vous pouvez entrer un nom, puis cliquer sur **Ajouter** pour l’ajouter comme nouvelle catégorie d’appareil.
- Vous pouvez aussi sélectionner une catégorie, puis la **Supprimer**.

Vous utiliserez le nom de catégorie d’appareil quand vous créerez des groupes de sécurité Active Directory Azure à l’étape 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Étape 2 : Créer des groupes de sécurité Active Directory

Au cours de cette étape, vous allez créer des groupes dynamiques dans le portail Azure basés sur la catégorie d’appareil et le nom de la catégorie d’appareil.

Pour continuer, reportez-vous à la rubrique [Utilisation d’attributs pour créer des règles avancées](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) dans la documentation d’Azure Active Directory.
Utilisez les informations de cette rubrique pour créer un groupe d’appareils avec une règle avancée à l’aide de l’attribut **deviceCategory**.
Par exemple (**device.deviceCategory -eq** "<*nom de catégorie d’appareil que vous avez obtenu à partir de la console d’administration Intune*>")


## <a name="after-you-configure-device-groups"></a>Après avoir configuré des groupes d’appareils

Quand des utilisateurs inscrivent leur appareil, une liste des catégories que vous avez configurées leur est présentée. Une fois qu’ils ont choisi une catégorie et terminé l’inscription, leur appareil est ajouté au groupe d’appareils Intune ou au groupe de sécurité Active Directory correspondant à la catégorie choisie.

### <a name="see-also"></a>Voir aussi
[Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)

