---
title: Inscrire des appareils | Microsoft Intune
description: "La gestion des appareils mobiles utilise l’inscription pour gérer les appareils et leur autoriser l’accès aux ressources."
keywords: 
author: NathBarn
manager: arob98
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6256b1ed5edb72bf9f623555a4c6e3fddb864b32
ms.openlocfilehash: 71f0637a1cb6fdafb590ca274fcc0f80707ed6ce


---

# Inscrire des appareils pour la gestion dans Intune
La gestion des appareils mobiles Microsoft Intune utilise l’inscription pour gérer les appareils et leur autoriser l’accès aux ressources. La façon dont vous inscrivez les appareils dépend du type d’appareil, de son propriétaire et du niveau de gestion souhaité. Les scénarios « Apportez votre propre appareil » (BYOD) et les scénarios d’appareils d’entreprise (COD) nécessitent un processus d’inscription. Les organisations qui utilisent Exchange ActiveSync (soit localement, soit hébergé dans le cloud) peuvent activer une gestion allégée sans conditions d’inscription. Vous pouvez également gérer des PC Windows à l’aide du logiciel client Intune.

###  Plateformes d’appareil prises en charge

Intune peut gérer les plateformes d’appareils suivantes :

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Présentation des méthodes d’inscription des appareils

Le tableau suivant présente les méthodes d’inscription d’appareils d’entreprise avec leurs avantages.

**Méthodes d’inscription iOS**

| **Méthode** |  **[Réinitialisation](#Wipe)** | **[Affinité](#Affinity)**   |   **[Verrouillé](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Non|    Oui |   Non |
|**[Gestionnaire d’inscription d’appareil](#DEM)**|   Non |Non |Non  |
|**[DEP](#DEP)**|   Oui |   Facultatif |   Facultatif|
|**[USB-SA](#USB-SA)**| Oui |   Facultatif |   Non|
|**[USB-Direct](#USB-Direct)**| Non |    Non  | Non|

**Méthodes d’inscription Windows et Android**

| **Méthode** |  **[Réinitialisation](#Wipe)** | **[Affinité](#Affinity)**   |   **[Verrouillé](#Lock)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Non|    Oui |   Non |
|**[Gestionnaire d’inscription d’appareil](#DEM)**|   Non |Non |Non  |

**Méthodes d’inscription d’appareils d’entreprise**

### BYOD
« Apportez votre propre appareil ». Les utilisateurs installent l’application Portail d’entreprise et inscrivent leur propre appareil. L’inscription d’un appareil avec le portail d’entreprise joindra l’appareil au lieu de travail. L’inscription d’appareils iOS avec le portail d’entreprise nécessite un ID Apple. La méthode BYOD ne nécessite pas de configuration supplémentaire pour les appareils d’entreprise. Consultez la procédure [Configurer la gestion des appareils](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Retour au tableau](#overview-of-device-enrollment-methods))

### Gestionnaire d’inscription d’appareil
Gestionnaire d’inscription d’appareil. L’administrateur crée des comptes DEM pour gérer des appareils d’entreprise. Les gestionnaires peuvent ensuite installer le portail d’entreprise et inscrire de nombreux appareils sans utilisateur. En savoir plus sur le [gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### DEP
Programme d’inscription d’appareils d’Apple. L’administrateur crée et déploie la stratégie « à distance » sur des appareils iOS d’entreprise achetés et gérés via le programme DEP. L’appareil est inscrit quand l’utilisateur exécute l’Assistant Configuration d’iOS. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  - Inscription verrouillée
  - Accès conditionnel
  - Détection de jailbreak
  - Gestion des applications mobiles

En savoir plus sur le programme [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### USB-SA
Connexion USB, inscription avec l’Assistant Configuration. L’administrateur crée une stratégie Intune et l’exporte vers Apple Configurator. Les appareils d’entreprise connectés par USB sont préparés à l’aide d’une stratégie Intune. L’administrateur doit inscrire manuellement chaque appareil. Les utilisateurs reçoivent leur appareil et exécutent l’Assistant Configuration pour inscrire leur appareil. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  - Accès conditionnel
  - Détection de jailbreak
  - Gestion des applications mobiles

En savoir plus sur l’[inscription de l’Assistant Configuration avec Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### USB-Direct
Inscription directe. L’administrateur crée une stratégie Intune et l’exporte vers Apple Configurator. Les appareils d’entreprise connectés par USB sont inscrits directement sans qu’une réinitialisation aux paramètres d’usine soit nécessaire. L’administrateur doit inscrire manuellement chaque appareil. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ni la gestion des applications mobiles. En savoir plus sur l’[inscription directe avec Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

**Comportement pour les appareils mobiles d’entreprise**

### Réinitialisation
Indique si l’inscription de l’appareil nécessite le rétablissement des paramètres d’usine de l’appareil, la suppression de toutes les données de l’appareil et sa réinitialisation à son état d’origine.
[Retirer les appareils](retire-devices-from-microsoft-intune-management.md) ([Retour au tableau](#overview-of-device-enrollment-methods))

### Affinité
Spécifie si la méthode d’inscription prend en charge l’« affinité utilisateur » qui connecte un appareil à un utilisateur spécifique. Les appareils « Facultatif » peuvent être inscrits avec ou sans affinité utilisateur. Une affinité utilisateur est nécessaire pour prendre en charge les éléments suivants :
  - Applications de gestion des applications mobiles (GAM)
  - Accès conditionnel aux données de messagerie et de l’entreprise
  - Application Portail d’entreprise

[Affinité utilisateur](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#user-affinity-for-ios-corporate-owned-devices-using-the-company-portal) ([Retour au tableau](#overview-of-device-enrollment-methods))

### Verrouiller
Spécifie s’il est possible de verrouiller l’appareil pour empêcher l’utilisateur de supprimer la stratégie Intune, supprimant ainsi l’appareil de la gestion. Pour un appareil iOS, le verrouillage de l’appareil nécessite qu’il soit en mode Supervisé.
([Retour au tableau](#overview-of-device-enrollment-methods))

## Activer l’inscription d’appareil  
 L’inscription permet aux utilisateurs d’accéder aux ressources de l’entreprise sur leurs appareils personnels et permet à l’administrateur de garantir que ces appareils sont conformes aux stratégies de protection des ressources d’entreprise. C’est le meilleur moyen d’activer des scénarios « Apportez votre propre appareil » avec Intune. L’administrateur doit activer l’inscription dans la console Intune, ce qui peut nécessiter la création d’une relation d’approbation avec l’appareil et l’attribution de licences aux utilisateurs. L’appareil est ensuite inscrit, généralement par les utilisateurs qui entrent leurs informations d’identification professionnelles ou scolaires. Ensuite, l’appareil reçoit une stratégie Intune et obtient l’accès aux ressources.

[Se préparer à inscrire des appareils dans Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Inscrire des appareils d’entreprise
Vous pouvez gérer les appareils d’entreprise (COD, Corporate-Owned Devices) avec la console Intune. Vous pouvez inscrire les appareils iOS directement par le biais d’outils fournis par Apple. Tous les types d’appareils peuvent être inscrits par un administrateur ou un gestionnaire à l’aide du Gestionnaire d’inscription d’appareil. Les appareils dotés d’un numéro IMEI peuvent également être identifiés et référencés comme appartenant à l’entreprise pour activer des scénarios COD.

[Inscrire des appareils d’entreprise](manage-corporate-owned-devices.md)

## Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud.

[Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Gérer des PC Windows avec Intune  
Vous pouvez également utiliser Microsoft Intune pour gérer des PC Windows à l’aide du logiciel client Intune pour PC Windows. Les PC gérés avec le client Intune peuvent :

 - Fournir un inventaire logiciel et matériel
 - Installer des applications de bureau (par exemple des fichiers .exe et .msi)
 - Paramètres du pare-feu

Les ordinateurs gérés avec le logiciel client Intune ne peuvent pas être réinitialisés ou mis hors service de manière sélective, et ne peuvent pas tirer parti de nombreuses fonctionnalités de gestion Intune telles que l’accès conditionnel, les paramètres VPN et Wi-Fi, ou le déploiement de certificats et de configurations de messagerie électronique.

[Gérer des PC Windows avec Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


