---
title: "Qu’est-ce que la gestion des applications ?"
titlesuffix: Azure portal
description: Utilisez cette rubrique pour apprendre les notions de gestion des applications avec Microsoft Intune
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 616589e02ba3c499e73431889f5a849a16538f90
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-microsoft-intune-app-management"></a>Qu’est-ce que la gestion des applications Microsoft Intune ?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


En tant qu’administrateur informatique, vous allez probablement avoir la responsabilité de vous assurer que vos utilisateurs ont accès aux applications dont ils ont besoin pour effectuer leur travail. Cela peut être un défi, car :
- Il existe un large éventail de plateformes d'appareils et de types d’applications.
- Vous devrez peut-être gérer des applications sur des appareils d’entreprise ainsi que des appareils personnels des utilisateurs.
- Vous devez vous assurer que votre réseau et vos données restent sécurisés.

Vous pourrez également souhaiter affecter et gérer des applications sur les appareils qui ne sont pas inscrits avec Intune.

Intune propose une gamme de fonctionnalités pour vous aider à obtenir les applications dont vous avez besoin, sur les appareils de votre choix.

## <a name="app-management-capabilities-by-platform"></a>Fonctionnalités de gestion d’application par plateforme

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
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
|Installation d’un raccourci vers une application sur le web (clip web)|Oui|Oui|Oui|Oui|
|Applications métier internes|Oui|Oui|Non|Non|
|Applications de Store|Oui|Oui|Oui|Oui|
|Mettre à jour des applications|Oui|Oui|Oui|Oui|

<sup>1</sup> Envisagez d’utiliser [Windows Information Protection](windows-information-protection-configure.md) pour protéger les applications sur les appareils qui exécutent Windows 10.

<sup>2</sup>S’applique aux appareils gérés par Intune uniquement.

## <a name="how-to-get-started"></a>Mise en route

Vous trouverez la plupart des éléments liés à l’application dans la charge de travail **Mobile Apps**, à laquelle vous pouvez accéder comme suit :

1. Connectez-vous au portail Azure.
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.

    ![La charge de travail Mobile Apps](./media/apps-workload.png)

### <a name="manage"></a>Gestion
- **Applications** : c’est sur ce nœud que vous allez ajouter, affecter et surveiller la plupart de vos applications.
    - [Ajouter des applications](apps-add.md)
    - [Attribuer des applications](apps-deploy.md)
    - [Surveillance des applications](apps-monitor.md)
- **Stratégies de configuration d’application** : les stratégies de configuration d’application vous permettent de fournir des paramètres pouvant être nécessaires quand un utilisateur exécute une application.
    - [Stratégies de configuration des applications iOS](app-configuration-policies-use-ios.md)
    - [Stratégies de configuration des applications Android](app-configuration-policies-use-android.md)
- **Stratégies de protection d’application** : vous permettent d’associer des paramètres à une application afin de protéger les données d’entreprise qu’elle utilise. Par exemple, vous pourrez limiter les fonctionnalités d’une application pour communiquer avec d’autres applications, ou demander à l’utilisateur d’entrer un code confidentiel pour accéder à une application d’entreprise.
    - [Stratégies de protection des applications](app-protection-policies.md)
- **Réinitialisation sélective d’application** : supprime uniquement les données d’entreprise à partir d’un appareil utilisateur que vous sélectionnez.
    - [Réinitialisation sélective d’applications](apps-selective-wipe.md)
- **Profils de configuration iOS** : les applications iOS incluent un profil de configuration et du code signé par un certificat. Lors de l’expiration du certificat, l’application ne peut plus être exécutée. Intune vous offre les outils pour affecter de façon proactive une nouvelle stratégie de profil de configuration pour les appareils qui disposent d’applications arrivant prochainement à expiration.
    - [Profils de configuration d’applications iOS](app-provisioning-profile-ios.md)

### <a name="monitor"></a>Surveillance
- **Applications sous licence** : affichez, affectez et surveillez les applications achetées en volume dans les App Stores.
    - [Applications achetées en volume sur le Microsoft Store pour Entreprises](windows-store-for-business.md)
- **Applications découvertes** : affiche toutes les applications qui ont été affectées par Intune et installées sur un appareil.
- **État d’installation de l’application** : affiche l’état d’une affectation d’application que vous avez créée.
- **État de protection de l’application** : affiche l’état d’une stratégie de protection d’application pour un utilisateur que vous sélectionnez.

Pour plus d’informations, consultez [Surveiller des applications](apps-monitor.md)

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Microsoft Store pour Entreprises** : configurez l’intégration au Microsoft Store pour Entreprises. Après cela, vous pouvez synchroniser les applications achetées à Intune, et affecter puis suivre l’utilisation de votre licence.
    - [Applications achetées en volume sur le Microsoft Store pour Entreprises](windows-store-for-business.md)
- **Personnalisation du portail d’entreprise** : personnalisez le portail d’entreprise pour lui donner une image proche de votre société.
    - [Configuration du portail d’entreprise](company-portal-app.md)
