---
title: Qu’est-ce que la gestion des applications Microsoft Intune ?
titlesuffix: ''
description: Découvrez les concepts de base de la gestion des applications avec Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 86cb0dfb67e81a7abbdc8f38dcbf5539b9855adb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>Qu’est-ce que la gestion des applications Microsoft Intune ?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune vous permet, en tant qu’administrateur informatique, de gérer les applications mobiles utilisées par le personnel de votre entreprise. Cette fonctionnalité s’ajoute à la gestion des appareils et à la protection des données. Dans le cadre de cette fonctionnalité, une de vos priorités est que vos utilisateurs finaux aient accès aux applications dont ils ont besoin pour effectuer leur travail. Cela peut être un défi, car :
- Il existe un large éventail de plateformes d'appareils et de types d’applications.
- Vous devrez peut-être gérer des applications sur des appareils d’entreprise ainsi que des appareils personnels des utilisateurs.
- Vous devez vous assurer que votre réseau et vos données restent sécurisés.

Vous pourrez également souhaiter affecter et gérer des applications sur les appareils qui ne sont pas inscrits avec Intune.

Intune propose une gamme de fonctionnalités pour vous aider à obtenir les applications dont vous avez besoin, sur les appareils de votre choix. Le tableau suivant fournit un récapitulatif des fonctionnalités de gestion des applications. Le tableau ci-dessous est un point de départ pour comprendre Microsoft Intune dans le portail Azure.

## <a name="app-management-capabilities-by-platform"></a>Fonctionnalités de gestion d’application par plateforme

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Ajout et affectation d’applications pour des appareils et utilisateurs|Oui|Oui|Oui|Oui|
|Affectation d’applications pour les appareils non inscrits avec Intune|Oui|Oui|Non|Non|
|Utilisation de stratégies de configuration d’application pour contrôler le comportement des applications au démarrage|Non|Oui|Non|Non|
|Utilisation de stratégies de configuration d’application mobile pour renouveler les applications arrivées à expiration|Non|Oui|Non|Non|
|Protection des données dans les applications avec des stratégies de protection d’application|Oui|Oui|Non|Non<sup>1</sup>|
|Suppression des données d’entreprise uniquement à partir d’une application installée (réinitialisation sélective d’application)|Oui|Oui|Oui|Oui|
|Surveillance des affectations d’applications|Oui|Oui|Oui|Oui|
|Affectation et suivi des applications achetées en volume dans un App Store|Non|Non|Non|Oui|
|Installation obligatoire d’applications sur des appareils (requis)<sup>2</sup>|Oui|Oui|Oui|Oui|
|Installation facultative sur des appareils à partir du portail d’entreprise (installation disponible)|Oui|Oui|Oui|Oui|
|Installer un raccourci vers une application sur le Web (lien Web)|Oui|Oui|Oui|Oui|
|Applications métier internes|Oui|Oui|Non|Oui|
|Applications de Store|Oui|Oui|Oui|Oui|
|Mettre à jour des applications|Oui|Oui|Oui|Oui|

<sup>1</sup> Envisagez d’utiliser [Windows Information Protection](windows-information-protection-configure.md) pour protéger les applications sur les appareils qui exécutent Windows 10.

<sup>2</sup>S’applique aux appareils gérés par Intune uniquement.

## <a name="how-to-get-started"></a>Mise en route

Vous trouverez la plupart des éléments liés à l’application dans la charge de travail **Mobile Apps**, à laquelle vous pouvez accéder comme suit :

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.

    ![La charge de travail Mobile Apps](./media/apps-workload.png)

Les informations ci-dessous correspondent aux options disponibles dans le panneau **Applications mobiles**.

### <a name="manage"></a>Gérer
- **Applications** : sélectionnez cette option pour ajouter, afficher, assigner et analyser les applications que votre personnel utilise. Pour plus d’informations, consultez les articles suivants :
    - [Ajouter des applications](apps-add.md)
    - [Attribuer des applications](apps-deploy.md)
    - [Surveillance des applications](apps-monitor.md)
- **Stratégies de configuration des applications** : les stratégies de configuration des applications vous permettent de fournir des paramètres pouvant être nécessaires quand un utilisateur exécute une application. Pour plus d’informations, consultez les articles suivants :
    - [Stratégies de configuration des applications pour Intune](app-configuration-policies-overview.md)
        - [Stratégies de configuration des applications iOS](app-configuration-policies-use-ios.md)
        - [Stratégies de configuration des applications Android](app-configuration-policies-use-android.md)
- **Stratégies de protection des applications** : les stratégies de protection des applications vous permettent d’associer des paramètres à une application afin de protéger les données d’entreprise qu’elle utilise. Par exemple, vous pourrez limiter les fonctionnalités d’une application pour communiquer avec d’autres applications, ou demander à l’utilisateur d’entrer un code confidentiel pour accéder à une application d’entreprise. Pour plus d'informations, consultez les articles suivants :
    - [Stratégies de protection des applications](app-protection-policies.md)
- **Réinitialisation sélective des applications** : supprime uniquement les données d’entreprise à partir d’un appareil d’utilisateurs que vous sélectionnez. Pour plus d'informations, consultez les articles suivants :
    - [Réinitialisation sélective d’applications](apps-selective-wipe.md)
- **Profils d’approvisionnement des applications iOS** : les applications iOS incluent un profil et un code d’approvisionnement signé par un certificat. Lors de l’expiration du certificat, l’application ne peut plus être exécutée. Intune vous offre les outils pour affecter de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration. Pour plus d'informations, consultez les articles suivants :
    - [Profils de configuration d’applications iOS](app-provisioning-profile-ios.md)

Pour plus d'informations, voir [Gérer les applications](app-management.md).

### <a name="monitor"></a>Surveillance
- **Licences d’applications** : affichez, affectez et surveillez les applications achetées en volume dans les App Stores. Pour plus d’informations, consultez les articles suivants :
    - [Applications du Programme d'achat en volume (VPP) iOS](vpp-apps-ios.md)
    - [Applications achetées en volume sur le Microsoft Store pour Entreprises](windows-store-for-business.md)
- **Applications découvertes** : affiche toutes les applications qui ont été affectées par Intune et installées sur un appareil.
- **État d’installation de l’application** : affiche l’état d’une affectation d’application que vous avez créée.
- **État de protection de l’application** : affiche l’état d’une stratégie de protection d’application pour un utilisateur que vous sélectionnez.
- **Journaux d’audit** : affiche les activités liées à l’application Intune et effectuées par tous les administrateurs informatiques.

Pour plus d’informations, consultez [Surveiller des applications](apps-monitor.md).

### <a name="setup"></a>Setup
- **Jetons VPP iOS** : appliquez et affichez vos licences du programme VPP (Volume Purchase Program) iOS.
    - [Applications iOS achetées en volume](vpp-apps-ios.md)
- **Certificat d'entreprise Windows** : appliquez ou affichez l’état d’un certificat de signature de code permettant de distribuer des applications métier sur vos appareils Windows gérés.
- **Certificat Symantec Windows** : appliquez ou affichez l’état d’un certificat de signature de code Symantec nécessaire pour distribuer des fichiers appx XAP et WP8.x sur des appareils Windows 10 Mobile.
- **Microsoft Store pour Entreprises** : configurez l’intégration au Microsoft Store pour Entreprises. Après cela, vous pouvez synchroniser les applications achetées à Intune, et affecter puis suivre l’utilisation de votre licence. Pour plus d'informations, consultez les articles suivants :
    - [Applications achetées en volume sur le Microsoft Store pour Entreprises](windows-store-for-business.md)
- **Clés de chargement indépendant Windows** : vous pouvez ajouter une clé de chargement indépendant Windows pour installer une application directement sur des appareils plutôt que de publier et de télécharger l’application à partir du Windows Store. Pour plus d'informations, consultez les articles suivants :
    - [Chargement indépendant d’une application Windows](app-sideload-windows.md)
- **Personnalisation du portail d’entreprise** : personnalisez le portail d’entreprise pour lui donner une image proche de votre société. Pour plus d'informations, consultez les articles suivants :
    - [Configuration du portail d’entreprise](company-portal-app.md)
- **Catégories d’applications** : ajoutez, épinglez et supprimez des noms de catégories d’applications.
- **Android for Work** : approuvez et synchronisez les applications que vous avez approuvées pour votre entreprise. Pour plus d'informations, consultez les articles suivants :
    - [Applications Android for Work](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Aide et support
- **Aide et support** : dépannez, demandez de l’aide ou affichez l’état d’Intune. Pour plus d'informations, consultez les articles suivants :
    - [Résolution des problèmes](help-desk-operators.md)

## <a name="next-steps"></a>Étapes suivantes

- [Guide pratique pour ajouter une application à Microsoft Intune](apps-add.md)
