---
title: "Quelles sont les nouveautés dans la version préliminaire de Microsoft Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : découvrez les nouveautés de la version préliminaire d’Intune Azure"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/02/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e405363f9d0a89b1589b01d18ee8d2861b07ec60
ms.openlocfilehash: 70007f5501fba37964a0a54807c0e0f565510a74


---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Nouveautés de la version préliminaire de Microsoft Intune


[!INCLUDE[azure_preview](../includes/azure_preview.md)]


Nous partagerons ici les avancées faites avec la version préliminaire et les fonctionnalités ajoutées.

<!--## February 2017-->

<!--### Custom app categories <!--748805
You can now create, edit, and assign categories for apps you add to Intune. Currently, categories can only be specified in English.
See [How to add an app to Intune](/intune-azure/manage-apps/add-apps).-->

<!--### Display device categories <!--814654
You can now view the device category as a column in the device list. You can also edit the category from the properties section of the device properties blade.-->

## <a name="january-2017"></a>Janvier 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Attribuer des applications métier que les appareils soient inscrits ou non<!--748823-->
Vous pouvez désormais attribuer aux utilisateurs des applications métier à partir du magasin, que leurs appareils soient inscrits ou non auprès d'Intune. Si l'appareil de l’utilisateur n’est pas inscrit auprès d'Intune, ce dernier doit se rendre sur le site Web du portail d’entreprise, au lieu de l’application du portail d’entreprise, pour l'installer. Consultez [Qu’est-ce que la gestion des applications](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Résoudre le problème quand les appareils iOS sont inactifs ou que la console d’administration ne peut pas communiquer avec eux
Quand les appareils des utilisateurs perdent le contact avec Intune, vous pouvez leur appliquer de nouvelles étapes de dépannage pour leur permettre de récupérer l’accès aux ressources d’entreprise. Consultez [Les appareils sont inactifs ou la console d’administration ne peut pas communiquer avec eux](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>Décembre 2016 (première version)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Intégration de la gestion des dépenses de télécommunications dans la version préliminaire publique du portail Azure<!--747605-->
Nous avons commencé à afficher un aperçu de l’intégration aux services de gestion des dépenses de télécommunications au sein du portail Azure. Vous pouvez utiliser Intune pour appliquer des limites à l’utilisation des données domestiques et itinérantes. Nous allons commencer ces intégrations avec [Saaswedo](http://www.saaswedo.com). Pour activer cette fonctionnalité dans votre client d’évaluation, veuillez [contacter le support technique Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Déploiement et gestion des applications depuis une boutique pour appareils iOS, Android et Windows
- Déploiement et gestion des applications métier (LOB) pour appareils iOS, Android et Windows
- Déploiement et gestion des applications achetées en volume pour appareils iOS et Windows
- Déploiement et gestion des applications web pour les appareils Android, iOS et Windows
- Profils de configuration des applications gérées iOS
- Configuration de stratégies de protection d’application et déploiement d’applications métier sur des appareils qui ne sont pas inscrits avec Intune
- Profils VPN, VPN par application, Wi-Fi, messagerie et profils de certificat
- Stratégies de conformité
- Accès conditionnel pour Azure AD
- Accès conditionnel à Exchange local
- Inscription de périphériques
- Contrôle d'accès en fonction du rôle

## <a name="deprecated-features-in-the-azure-portal"></a>Fonctionnalités déconseillées dans le portail Azure

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Prise en charge de l’analyse ligne par ligne des identificateurs de matériel
Le portail Azure ne prend pas en charge l’analyse ligne par ligne des identificateurs de matériel pour les numéros IMEI et les numéros de série Apple. Dans la console Intune classique, vous pouvez importer des informations à partir d’un fichier à valeurs séparées par des virgules (.csv) et remplacer les informations existantes des identificateurs de matériel. Le portail Azure propose une option unique et simplifiée pour automatiquement remplacer les informations pour tous les identificateurs de matériel ou ignorer les nouvelles informations pour les identificateurs existants.

#### <a name="how-this-affects-you"></a>Comment cela vous affecte
Dans le portail Azure, vous ne serez pas en mesure de choisir, ligne par ligne, les appareils International Mobile Equipment Identity (IMEI) à mettre à jour. La console Intune classique continuera à prendre en charge cette fonctionnalité.

#### <a name="how-to-get-ready-for-this-change"></a>Guide pratique de préparation à cette modification
Nous fournissons ces informations à l’avance. Ainsi, si elles vous concernent, vous pouvez informer vos administrateurs de cette modification. Cette modification coïncide avec la migration vers le portail Azure, attendu pour la première moitié de 2017.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Prise en charge par défaut des profils d’inscription d’appareil professionnel dans Apple DEP
Le portail Azure ne prend pas en charge le profil d’inscription d’appareil d’entreprise « Par défaut » pour les numéros de série d’appareil Apple DEP. Cette fonctionnalité, disponible dans la console Intune classique, est interrompue pour empêcher l’attribution de profils par inadvertance. Dans le portail Azure, les numéros de série synchronisés à partir d’un compte Apple DEP n’auront initialement aucun profil d’inscription d’appareil d’entreprise affecté.

#### <a name="how-this-affects-you"></a>Comment cela vous affecte
Dans le portail Azure, vous ne serez pas en mesure de définir une stratégie de profil par défaut sur tous les appareils Apple. La console Intune classique continuera à prendre en charge cette fonctionnalité.

#### <a name="how-to-get-ready-for-this-change"></a>Guide pratique de préparation à cette modification
Nous fournissons ces informations à l’avance. Ainsi, si elles vous concernent, vous pouvez informer vos administrateurs de cette modification. Cela coïncide avec la migration vers le portail Azure, attendue pour la première moitié de 2017.



<!--HONumber=Feb17_HO1-->


