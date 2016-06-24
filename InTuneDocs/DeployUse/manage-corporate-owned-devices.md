---
# required metadata

title: Gérer les appareils d’entreprise | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Inscrire les appareils d’entreprise avec Microsoft Intune
Les appareils d’entreprise ou d’organisation peuvent être placés sous gestion par Intune de diverses façons en fonction de l’appareil, de la méthode utilisée pour son achat et des besoins de l’organisation.

## Appareils iOS d’entreprise
Ces méthodes d’inscription sont adaptées aux scénarios CYOD (Choisissez votre propre appareil) dans lesquels l’organisation achète les appareils pour les utilisateurs mais souhaite conserver la gestion de l’appareil. Si votre organisation a acheté des appareils iOS, vous pouvez préconfigurer l’inscription afin que l’appareil soit géré dès la première fois que l’utilisateur l’allume. Intune prend en charge l’inscription à l’aide du programme d’inscription d’appareils (DEP, Device Enrollment Program) d’Apple ou de l’outil [Apple Configurator](ios-device-enrollment-program-in-microsoft-intune.md) à exécuter sur un ordinateur Mac pour l’inscription [directe](ios-direct-enrollment-in-microsoft-intune.md) ou avec l’[Assistant de configuration](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Inscrire des appareils iOS d'entreprise](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Gestionnaire d'inscription d'appareil
Les organisations peuvent utiliser Intune pour gérer un grand nombre d’appareils mobiles avec un seul compte de gestionnaire des inscriptions d’appareils. Après avoir créé un compte de gestionnaire d’inscription d’appareils, ce compte peut être utilisé par un gestionnaire pour inscrire plus que les cinq appareils standards autorisés par défaut pour les utilisateurs normaux. L’inscription d’appareils avec un gestionnaire d’inscription des appareils ne fonctionne que pour les appareils qui ne sont pas utilisés par un utilisateur spécifique. Ces appareils sont adaptés aux applications utilitaires ou de point de vente, par exemple, mais ne le sont pas pour les utilisateurs qui doivent accéder à des messages électroniques ou ressources de l’entreprise.

[Inscrire des appareils d’entreprise avec le gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Numéro d’identité internationale d’équipement mobile (IMEI, International Mobile Equipment Identity)
Les numéros IMEI uniques sont une propriété d’appareil commune pour de nombreux fabricants d’appareils mobiles. Les administrateurs Intune peuvent importer des numéros IMEI pour les appareils appartenant à l’entreprise. Lorsque l’appareil est géré par Intune, il peut être marqué comme appareil de l’entreprise et être ciblé avec la stratégie appropriée.

[Spécifier des appareils d’entreprise avec des numéros IMEI (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Présentation des méthodes d’inscription des appareils d’entreprise

Le tableau suivant présente les méthodes d’inscription d’appareils d’entreprise avec leurs avantages.

**Méthodes d’inscription iOS**

| **Méthode** |  **[Réinitialiser](#Reset)** |   **[Affinité](#Affinity)**   |   **[Verrouillé](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Non|    Oui |   Non |
|**[Gestionnaire d’inscription d’appareil](#DEM)**|   Non |Non |Non  |
|**[DEP](#DEP)**|   Oui |   Facultatif |   Facultatif|
|**[USB-SA](#USB-SA)**| Oui |   Facultatif |   Non|
|**[USB-Direct](#USB-Direct)**| Non |    Non  | Non|

**Méthodes d’inscription Windows et Android**

| **Méthode** |  **[Réinitialisation](#Wipe)** | **[Utilisateur](#User)**   |   **[Verrouillé](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Non|    Oui |   Non |
|**[Gestionnaire d’inscription d’appareil](#DEM)**|   Non |Non |Non  |

**Méthodes d’inscription d’appareils d’entreprise**

### BYOD
« Apportez votre propre appareil ». Les utilisateurs installent l’application Portail d’entreprise et inscrivent leur propre appareil. L’inscription d’un appareil avec le portail d’entreprise joindra l’appareil au lieu de travail. L’inscription d’appareils iOS avec le portail d’entreprise nécessite un ID Apple. La méthode BYOD ne nécessite pas de configuration supplémentaire pour les appareils d’entreprise. Consultez la procédure [Configurer la gestion des appareils](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

### Gestionnaire d’inscription d’appareil
Gestionnaire d’inscription d’appareil. L’administrateur crée des comptes de gestionnaire d’inscription d’appareil. Les gestionnaires peuvent ensuite installer le portail d’entreprise et inscrire de nombreux appareils sans utilisateur. En savoir plus sur le [gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Programme d’inscription d’appareils d’Apple. L’administrateur crée et déploie la stratégie « à distance » sur des appareils iOS achetés et gérés via le programme DEP. L’appareil est inscrit quand l’utilisateur exécute l’Assistant Configuration d’iOS. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  - Inscription verrouillée
  - Accès conditionnel
  - Détection de jailbreak
  - Gestion des applications mobiles

En savoir plus sur le programme [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
Connexion USB, inscription avec l’Assistant Configuration. L’administrateur crée une stratégie Intune et l’exporte vers Apple Configurator. Les appareils connectés par USB sont préparés à l’aide de la stratégie Intune. L’administrateur doit inscrire manuellement chaque appareil. Les utilisateurs reçoivent leur appareil et exécutent l’Assistant Configuration pour inscrire leur appareil. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  - Inscription verrouillée
  - Accès conditionnel
  - Détection de jailbreak
  - Gestion des applications mobiles

En savoir plus sur l’[inscription de l’Assistant Configuration avec Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Inscription directe. L’administrateur crée une stratégie Intune et l’exporte vers Apple Configurator. Les appareils connectés par USB sont inscrits directement sans qu’un rétablissement des paramètres d’usine soit nécessaire. L’administrateur doit inscrire manuellement chaque appareil. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ni la gestion des applications mobiles. En savoir plus sur l’[inscription directe avec Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

**Comportement pour les appareils mobiles d’entreprise**

### Réinitialiser
Indique si l’inscription de l’appareil nécessite le rétablissement des paramètres d’usine de l’appareil, la suppression de toutes les données de l’appareil et sa réinitialisation à son état d’origine.
([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

### Affinité
Spécifie si la méthode d’inscription prend en charge l’« affinité utilisateur » qui connecte un appareil à un utilisateur spécifique. Les appareils « Facultatif » peuvent être inscrits avec ou sans affinité utilisateur. Une affinité utilisateur est nécessaire pour prendre en charge les éléments suivants :
  - Applications de gestion des applications mobiles (GAM)
  - Accès conditionnel aux données de messagerie et de l’entreprise
  - Application Portail d’entreprise

([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))

### Verrouiller
Spécifie s’il est possible de verrouiller l’appareil pour empêcher l’utilisateur de supprimer la stratégie Intune, supprimant ainsi l’appareil de la gestion. Pour un appareil iOS, le verrouillage de l’appareil nécessite qu’il soit en mode Supervisé.
([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods)) ([Retour au tableau](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


