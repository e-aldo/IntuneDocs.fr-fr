---
title: "Configurer des stratégies de gestion des applications et de la conformité des appareils lors d’une migration Intune | Microsoft Docs"
description: "Cet article décrit les étapes nécessaires pour configurer des stratégies de gestion des applications et de la conformité des appareils lors d’une migration Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 50a8929ef31e0a322e9460f82af3ed821ade69cf
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="phase-1-configure-device-compliance-and-app-management-policies"></a>Phase 1 : Configurer les stratégies de gestion des applications et de la conformité des appareils

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Lors de la migration vers Intune, l’objectif principal consiste à assurer l’inscription de l’ensemble des appareils et ce, dans le respect des stratégies adéquates. En effet, les stratégies de gestion des appareils vous permettent d’administrer les appareils d’entreprise d’un seul utilisateur, mais également les appareils personnels (BYOD) et partagés tels que les bornes, les terminaux de vente, les tablettes partagées par plusieurs étudiants ou les appareils sans utilisateur (iOS uniquement).

Chaque plate-forme d’appareil peut proposer des paramètres différents, mais les stratégies de gestion des appareils de Microsoft Intune fonctionnent avec chacune d’elles, en fournissant les fonctionnalités de gestion des appareils mobiles suivantes :

-   Régulation du nombre d’appareils inscrits par chaque utilisateur

-   Gestion des paramètres des appareils (inscription au niveau de l’appareil, longueur du mot de passe, utilisation de l’appareil photo, etc.)

-   Fourniture d’applications, de profils de messagerie et VPN, etc.

-   Évaluation des critères au niveau de l’appareil dans le cadre des stratégies de conformité de la sécurité

> [!IMPORTANT]
> Les stratégies de gestion des appareils ne sont pas directement affectées à des appareils ou utilisateurs individuels, mais plutôt à des groupes d’utilisateurs. Les stratégies peuvent être appliquées directement à un groupe d’utilisateurs et, de ce fait, à l’appareil d’un de ces utilisateurs. Cependant, vous pouvez aussi les appliquer à un groupe d’appareils et, partant, aux membres de ce groupe.

## <a name="task-list-for-device-compliance-policies"></a>Liste de tâches relatives aux stratégies de conformité des appareils

### <a name="task-1-add-device-groups-optional"></a>Tâche 1 : Ajouter des groupes d’appareils (facultatif)

Le [portail Intune classique](https://manage.microsoft.com/) vous donne la possibilité de créer des groupes d’appareils lorsque vous devez exécuter diverses tâches d’administration en fonction de l’identité de l’appareil, et non de l’utilisateur.

Les groupes d’appareils sont utiles pour la gestion des appareils sans utilisateur dédié (par exemple, les bornes ou les appareils partagés par plusieurs employés, ou affectés à un lieu spécifique).

En configurant des groupes d’appareils au préalable, vous pouvez tirer parti des catégories d’appareils pour les regrouper automatiquement lors de l’inscription, afin de pouvoir leur affecter automatiquement les stratégies du groupe auxquels ils appartiennent.

-   Découvrez comment [créer des groupes pour organiser les utilisateurs et les appareils](/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5).

-   Découvrez comment [catégoriser les appareils avec le mappage de groupe d’appareils dans Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a>Tâche 2 : Utiliser des profils d’accès aux ressources (Wi-Fi, VPN et certificats de messagerie)

Les profils d’accès aux ressources configurent des certificats et des configurations d’accès sur les appareils inscrits.

Comme indiqué précédemment dans la section Évaluer les besoins concernant la migration de MDM, vous devrez [mettre en place une infrastructure PKI](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) pour pouvoir déployer le VPN, le Wi-Fi et les certificats de messagerie, si vous utilisez l’authentification basée sur un certificat.

#### <a name="direct-import-of-resource-access-profiles-optional"></a>Importation directe des profils d’accès aux ressources (facultatif)

Si votre solution MDM fournit un moyen d’exporter les profils de messagerie, VPN et Wi-Fi au format XML, vous devriez pouvoir simplement importer ce fichier XML dans Intune en créant des profils personnalisés pour les appareils iOS, Android et Windows via la fonction OMA-URI.

-   Découvrez comment ajouter une stratégie personnalisée pour les appareils [iOS](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a>Tâche 3 : Créer et déployer des profils de configuration d’appareil

Vous devez créer un profil de configuration d’appareil pour appliquer des paramètres au niveau de ce dernier, par exemple la désactivation de l’appareil photo et de l’App Store, la configuration du mode d’application unique et de l’écran d’accueil, etc.

- Découvrez plus d’informations sur les [profils de configuration d’appareil](https://docs.microsoft.com/intune/device-profile-create).

####  <a name="direct-import-of-ios-configuration-profiles-optional"></a>Importation directe de profils de configuration iOS (facultatif)

-   **Profils iOS Apple Configurator (iOS 7.1 et versions ultérieures) :** si votre solution MDM utilise des profils Apple Configurator (fichiers .mobileconfig), Intune peut les importer directement en tant que stratégies de configuration personnalisées.

-   **Stratégies de configuration des applications mobiles iOS :** si votre solution MDM utilise des stratégies de configuration des applications mobiles iOS, Intune peut les importer directement, tant que les listes de propriétés présentent le format XML spécifié par Apple.

- Découvrez comment ajouter une stratégie personnalisée pour [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune#custom-policy-settings).

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a>Tâche 4 : Créer et déployer des stratégies de conformité des appareils (facultatif)

Les stratégies de conformité des appareils évaluent les paramètres de sécurité axés sur la sécurité et fournissent des rapports qui indiquent si les appareils sont conformes aux normes de l’entreprise ou non. Ces stratégies évaluent les facteurs relatifs à la sécurité, par exemple :

-   Longueur du code PIN

-   Statut jailbreaké

-   Version de système d'exploitation

Consultez les ressources supplémentaires pour connaître les paramètres de conformité des appareils :

-   Découvrez plus d’informations sur les [stratégies de conformité des appareils](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).

-   Découvrez comment [créer une stratégie de conformité des appareils](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).

### <a name="task-5-publish-and-deploy-apps"></a>Tâche 5 : Publier et déployer des applications

Lorsque vous utilisez MDM Intune, vous pouvez configurer les applications en demandant leur installation automatique ou en les mettant à la disposition des utilisateurs sur le portail d’entreprise.

-   Découvrez comment [ajouter des applications](/intune-classic/deploy-use/add-apps).

-   Voici comment [déployer des applications](/intune-classic/deploy-use/deploy-apps).

### <a name="task-6-enable-device-enrollment"></a>Tâche 6 : Activer l’inscription des appareils

Le processus d’inscription établit la gestion en configurant le mode de contrôle sur l’appareil.

-   Découvrez comment [inscrire des appareils d’entreprise et personnels](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).

-   Voici comment [inscrire des appareils d’entreprise](/intune-classic/deploy-use/manage-corporate-owned-devices).

Si vous devez inscrire des appareils partagés ou sans utilisateur, vous pouvez utiliser un [gestionnaire d’inscription d’appareil /intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="next-steps"></a>Étapes suivantes 

[Phase 1 : Configurer des stratégies de protection d’applications] (/intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

