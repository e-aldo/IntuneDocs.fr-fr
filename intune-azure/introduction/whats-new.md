---
title: "Nouveautés de la préversion de Microsoft Intune"
titleSuffix: Intune Azure preview
description: "Découvrez les nouveautés de la préversion d’Intune Azure"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 03/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 586bdab54ee60ba8d620857ab3506aa27622d17a
ms.lasthandoff: 03/17/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Nouveautés de la préversion de Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Nous partagerons ici les avancées faites avec la version préliminaire et les fonctionnalités ajoutées.

> [!Note]
> Nous déployons actuellement les modifications répertoriées dans cette page pour la préversion du portail Azure. Toutefois, il se peut que les modifications ne soient pas disponibles immédiatement selon la façon dont le service Intune est mis à jour.  Plusieurs composants du service doivent être actualisés de façon séquentielle avant que les nouvelles fonctionnalités du portail soient disponibles. Recherchez ces modifications lors de la publication à une date ultérieure ce mois-ci.

## <a name="march-2017"></a>Mars 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Prise en charge du mode Perdu iOS<!--431695-->

Pour les appareils iOS 9.3 et versions ultérieures, Intune a ajouté la prise en charge du **Mode Perdu**. Vous pouvez maintenant verrouiller un appareil pour éviter toute utilisation et afficher un numéro de téléphone de contact et un message sur l’écran de verrouillage de l’appareil.

L’utilisateur final ne peut pas déverrouiller l’appareil tant qu’un administrateur n’a pas désactivé le mode Perdu. Lorsque le mode Perdu est activé, vous pouvez utiliser l’action **Localiser l’appareil** pour afficher l’emplacement géographique de l’appareil sur une carte dans la console Intune.

L’appareil doit être un appareil iOS d’entreprise, inscrit via le programme DEP, qui est en mode supervisé.

Pour plus d’informations, consultez [Qu’est-ce que la gestion des appareils Microsoft Intune ?](/intune-azure/manage-devices/what-is)

### <a name="improvements-to-device-actions-report---677150--"></a>Améliorations du rapport Actions de l’appareil <!--677150-->

Nous avons apporté des améliorations au rapport Actions de l’appareil afin d’optimiser les performances. En outre, il est désormais possible de filtrer le rapport par état. Par exemple, vous pouvez filtrer le rapport pour qu’il affiche uniquement les actions d’appareil qui ont été effectuées.

### <a name="actions-for-non-compliance---730266--"></a>Actions en cas de non-conformité <!--730266-->

**Actions en cas de non-conformité** est une nouvelle fonctionnalité de stratégies de conformité qui vous permet de prendre des mesures au niveau des appareils non conformes. Vous pouvez spécifier une ou plusieurs actions ainsi que la période à laquelle ces actions doivent se produire. Par exemple, vous pouvez avertir par courrier électronique les utilisateurs d'appareils non conformes immédiatement lorsque ces appareils deviennent non conformes, ou empêcher les appareils non conformes d’accéder aux ressources de l’entreprise après une période de grâce de 3 jours via l’accès conditionnel.


### <a name="custom-app-categories---748805--"></a>Catégories d’applications personnalisées <!--748805-->

Vous pouvez désormais créer, modifier et attribuer des catégories pour les applications que vous ajoutez à Intune. Actuellement, les catégories ne peuvent être spécifiées qu'en anglais.
Consultez [Guide pratique pour ajouter une application à Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>Attribuer des applications cœur de métier aux utilisateurs disposant d’appareils non inscrits <!--748823-->

Vous pouvez désormais attribuer aux utilisateurs des applications cœur de métier à partir de la boutique, que leurs appareils soient ou non inscrits auprès d’Intune. Si l’appareil n’est pas inscrit auprès de Intune, l’utilisateur doit se rendre sur le site web du portail d’entreprise, au lieu de l’application du portail d’entreprise, pour l’installer.

### <a name="new-compliance-reports---846671--"></a>Nouveaux rapports de conformité <!--846671-->

Vous disposez désormais de rapports de conformité qui vous indiquent la situation de conformité des appareils de votre société et vous permettent de résoudre rapidement les problèmes liés à la conformité rencontrés par vos utilisateurs. Vous pouvez visualiser des informations sur les éléments suivants :

- État de conformité global des appareils
- État de conformité d’un paramètre spécifique
- État de conformité d’une stratégie spécifique

Vous pouvez également utiliser ces rapports pour explorer les détails d’un appareil individuel afin de visualiser les paramètres et stratégies spécifiques affectant cet appareil.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Accès direct aux scénarios d’inscription d’Apple <!--951869-->

Pour les comptes Intune créés après janvier 2017, Intune a activé un accès direct aux scénarios d’inscription Apple à l’aide de la charge de travail Inscrire des appareils dans le portail Azure en version préliminaire. Auparavant, la version préliminaire de l’inscription Apple était uniquement accessible à partir de liens dans le portail Intune classique. Les comptes Intune créés avant janvier 2017 nécessiteront une migration unique pour que ces fonctionnalités deviennent disponibles dans Azure. La planification de la migration n’a pas encore été annoncée, mais les détails correspondants seront diffusés dès que possible. Si votre compte existant ne peut pas accéder à la version préliminaire, nous vous recommandons vivement de créer un compte d’évaluation afin de tester la nouvelle expérience.


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

### <a name="configure-windows-update-for-business-settings---776716--"></a>Configurer les paramètres Windows Update for Business <!--776716-->

Windows en tant que service est la nouvelle façon de fournir des mises à jour pour Windows 10. À partir de Windows 10, les nouvelles mises à jour de fonctionnalités et qualité incluent le contenu de toutes les mises à jour précédentes. Cela signifie que tant que vous avez installé la dernière mise à jour, vous savez que vos appareils Windows 10 sont entièrement à jour. À la différence des versions précédentes de Windows, vous devez maintenant installer la mise à jour complète au lieu d’une partie seulement.

En utilisant Windows Update for Business, vous pouvez simplifier l’expérience de gestion des mises à jour et vous ne devez plus approuver des mises à jour propres à des groupes d’appareils. Vous pouvez toujours gérer les risques dans votre environnement en configurant une stratégie de déploiement de mises à jour afin que Windows Update fasse en sorte que les mises à jour soient installées au moment opportun. Microsoft Intune permet de configurer les paramètres de mise à jour des appareils et vous donne la possibilité de reporter l’installation des mises à jour. Intune ne stocke pas les mises à jour, seulement l’attribution des stratégies de mise à jour. Les appareils accèdent directement à Windows Update. Utilisez Intune pour configurer et gérer les **anneaux de mise à jour Windows 10**. Un anneau de mise à jour contient un groupe de paramètres permettant de configurer le moment et la façon d’installer les mises à jour Windows 10. Pour plus d’informations, consultez [Configurer les paramètres Windows Update for Business](/intune-azure/configure-devices/how-to-configure-windows-update-for-business).

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

