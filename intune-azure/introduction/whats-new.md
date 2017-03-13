---
title: "Nouveautés de la préversion de Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Découvrez les nouveautés de la préversion d’Intune Azure"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: ffbc91edbdec4abbb5c3c9e28c3b44df03117492
ms.lasthandoff: 02/18/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Nouveautés de la préversion de Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Nous partagerons ici les avancées faites avec la version préliminaire et les fonctionnalités ajoutées.

## <a name="february-2017"></a>Février 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Possibilité de limiter l’inscription des appareils mobiles <!--747600, 795782-->
Intune ajoute de nouvelles restrictions d’inscription qui contrôlent les plateformes d’appareils mobiles autorisées à être inscrites. Intune sépare les plateformes d’appareils mobiles comme iOS, MacOS, Android, Windows et Windows Mobile.

* La restriction de l’inscription d’appareils mobiles ne limite pas l’inscription des clients de PC.  
* Pour iOS et Android uniquement, il existe une option supplémentaire pour bloquer l’inscription des appareils personnels.

Intune marque tous les nouveaux appareils comme personnels, sauf si l’administrateur prend des mesures pour les marquer comme appareils d’entreprise, comme expliqué dans [cet article](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Afficher toutes les actions sur les appareils gérés <!--677150-->
Un nouveau rapport __Actions de l’appareil__ indique l’utilisateur qui a effectué des actions à distance, comme un rétablissement des paramètres d’usine sur les appareils, et montre également l’état de cette action. Consultez [Qu’est-ce que la gestion des appareils ?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Les appareils non gérés peuvent accéder aux applications attribuées <!--664691-->
Dans le cadre des modifications conceptuelles du site web du portail d’entreprise, les utilisateurs iOS et Android peuvent installer les applications attribuées indiquées comme « disponibles sans inscription » sur leurs appareils non gérés. À l’aide de leurs informations d’identification Intune, les utilisateurs peuvent se connecter au site web du portail d’entreprise et afficher la liste des applications qui leur sont attribuées. Les packages des applications « disponibles sans inscription » peuvent être téléchargés sur le site web du portail d’entreprise. Les applications dont l’installation nécessite une inscription ne sont pas affectées par cette modification, car les utilisateurs sont invités à inscrire leur appareil s’ils souhaitent installer ces applications.

### <a name="custom-app-categories---748805--"></a>Catégories d’applications personnalisées <!--748805-->
Vous pouvez désormais créer, modifier et attribuer des catégories pour les applications que vous ajoutez à Intune. Actuellement, les catégories ne peuvent être spécifiées qu'en anglais.
Consultez [Guide pratique pour ajouter une application à Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Afficher des catégories d’appareils <!--814654-->
Vous pouvez maintenant afficher la catégorie d’appareil sous forme de colonne dans la liste des appareils. Vous pouvez également modifier la catégorie dans la section des propriétés du panneau Propriétés de l’appareil. Consultez [Guide pratique pour ajouter une application à Intune](/intune-azure/manage-apps/add-apps). 

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

#### <a name="how-to-get-ready-for-this-change"></a>Comment se préparer à cette modification
Nous fournissons ces informations à l’avance. Ainsi, si elles vous concernent, vous pouvez informer vos administrateurs de cette modification. Cette modification coïncide avec la migration vers le portail Azure, attendu pour la première moitié de 2017.


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Prise en charge par défaut des profils d’inscription d’appareil professionnel dans Apple DEP
Le portail Azure ne prend pas en charge le profil d’inscription d’appareil d’entreprise « Par défaut » pour les numéros de série d’appareil Apple DEP. Cette fonctionnalité, disponible dans la console Intune classique, est interrompue pour empêcher l’attribution de profils par inadvertance. Dans le portail Azure, les numéros de série synchronisés à partir d’un compte Apple DEP n’auront initialement aucun profil d’inscription d’appareil d’entreprise affecté.

#### <a name="how-this-affects-you"></a>Comment cela vous affecte
Dans le portail Azure, vous ne serez pas en mesure de définir une stratégie de profil par défaut sur tous les appareils Apple. La console Intune classique continuera à prendre en charge cette fonctionnalité.

#### <a name="how-to-get-ready-for-this-change"></a>Comment se préparer à cette modification
Nous fournissons ces informations à l’avance. Ainsi, si elles vous concernent, vous pouvez informer vos administrateurs de cette modification. Cela coïncide avec la migration vers le portail Azure, attendue pour la première moitié de 2017.

