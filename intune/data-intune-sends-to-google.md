---
title: "Données envoyées par Intune à Google"
titleSuffix: Microsoft Intune
description: "Liste des données envoyées à Google par Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63f1b07d13daad7512dff8e53f9acbafa7bffdd3
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2018
---
# <a name="data-intune-sends-to-google"></a>Données envoyées par Intune à Google

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Quand la gestion des appareils Android est activée sur un appareil, Microsoft Intune établit une connexion avec Google, et partage des informations sur l’utilisateur et sur l’appareil avec Google. Pour que Microsoft Intune puisse établir une connexion, vous devez créer un compte Google.

Le tableau suivant répertorie les données que Microsoft Intune envoie à Google quand la gestion des appareils est activée sur un appareil :


| Données envoyées à Google | Détails | Rôle | Exemple |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Provient de Google après liaison de votre compte Gmail à Intune. | Identificateur principal utilisé pour communiquer entre Intune et Google.  Cette communication inclut la définition de stratégies, la gestion des appareils et la liaison/annulation de la liaison d’entreprise Android avec Intune. | Identificateur unique. Exemple de format : LC04eik8a6 |
| Corps de la stratégie | Provient d’Intune lors de l’enregistrement d’une nouvelle stratégie d’application ou de configuration. | Application de stratégies à des appareils. | Il s’agit d’une collection de tous les paramètres configurés pour une stratégie d’application ou de configuration. Ceci peut contenir des informations du client si elles sont fournies dans le cadre d’une stratégie, comme des noms de réseau, des noms d’application et des paramètres spécifiques à une application. |
| Données des appareils | Les scénarios des appareils pour les profils professionnels commencent par l’inscription dans Intune. Les scénarios des appareils pour les appareils gérés commencent par l’inscription dans Intune. | Des informations sur les données des appareils sont envoyées entre Intune et Google pour différentes actions, comme l’application de stratégies, la gestion de l’appareil et des rapports généraux. | **Identificateur unique pour représenter le nom de l’appareil.** Exemple : enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**Identificateur unique pour représenter le nom de l’utilisateur.** Exemple : Enterprises/LC04ebru7b/users/116838519924207449711<br>**État de l’appareil.** Exemples : Actif, Désactivé, Provisionnement.<br>**État de la conformité.** Exemples : Paramètre non pris en charge, applications obligatoires manquantes<br>**Infos logiciel.** Exemples : versions des logiciels et niveau des correctifs logiciels.<br>**Infos réseau.** Exemples : Numéro IMEI, MEID, WifiMacAddress<br>**Paramètres de l’appareil.** Exemples : Informations sur les niveaux de chiffrement, et si appareil autorise les applications inconnues.<br> Vous pouvez trouver un exemple de message JSON ci-dessous. |
| newPassword | Provient d’Intune. | Réinitialisation du code secret de l’appareil. | Chaîne représentant le nouveau mot de passe. |
| Utilisateur Google | Google | Gestion du profil professionnel pour les scénarios Profil professionnel (BYOD). | Identificateur unique pour représenter le compte Gmail lié. Exemple : 114223373813435875042 |
| Données d'application | Proviennent d’Intune, lors de l’enregistrement d’une stratégie d’application. |  | Chaîne du nom d’application. Exemple : app:com.microsoft.windowsintune.companyportal |
| Compte de service d’entreprise | Provient de Google, suite à une demande d’Intune. | Utilisé pour l’authentification entre Intune et Google, pour les transactions impliquant ce client. | Constitué de plusieurs parties :<br> **Id d’entreprise** : déjà documenté.<br>**UPN** : UPN généré utilisé dans l’authentification pour le compte du client.<br>Exemple : w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Clé** : objet blob codé en Base64 utilisé dans les demandes d’authentification, stocké chiffré dans le service. Voici à quoi ressemble cet objet blob :<br> Identificateur unique pour représenter la clé du client<br>Exemple : a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Exemple de données d’un appareil**

Voici un exemple de message d’appareil JSON provenant de Google :



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Pour arrêter d’utiliser la gestion des appareils Android avec Microsoft Intune et supprimer les données, vous devez à la fois désactiver la gestion des appareils Android de Microsoft Intune et supprimer votre compte Google. Reportez-vous au compte Google pour savoir comment effectuer la gestion du compte.


