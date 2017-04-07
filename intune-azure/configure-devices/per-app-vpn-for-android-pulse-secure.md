---
title: Profil VPN par application pour Android - Pulse Secure
titleSuffix: Intune Azure preview
description: "Version préliminaire d’Intune Azure : découvrez comment créer un profil VPN par application pour les appareils Android gérés par Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 2c79f5f796152e930c4a952388541383ab50e595
ms.lasthandoff: 03/17/2017


---

# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Utiliser un profil personnalisé Microsoft Intune pour créer un profil VPN par application pour les appareils Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vous pouvez créer un profil VPN par application pour les appareils Android 5.0 et ultérieur gérés par Intune. Tout d’abord, créez un profil VPN qui utilise le type de connexion Pulse Secure. Ensuite, créez une stratégie de configuration personnalisée qui associe le profil VPN à des applications spécifiques.

Une fois que vous avez déployé la stratégie sur votre appareil Android ou vos groupes d’utilisateurs, les utilisateurs doivent démarrer le VPN PulseSecure. PulseSecure autorise alors uniquement le trafic provenant des applications spécifiées à utiliser la connexion VPN ouverte.

> [!NOTE]
>
> Seul le type de connexion sécurisé Pulse Secure est pris en charge pour ce profil.


## <a name="step-1-create-a-vpn-profile"></a>Étape 1 : Créer un profil VPN


1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
2. Dans le panneau de la liste des profils, sélectionnez **Créer un profil**.
3. Dans le panneau **Créer un profil**, entrez un **nom** et éventuellement une **description** pour le profil VPN.
4. Dans la liste déroulante **Plateforme**, choisissez **Android**.
5. Dans la liste déroulante **Type de profil**, choisissez **VPN**.
3. Choisissez **Paramètres** > **Configurer**, puis configurez le profil VPN selon les paramètres de la [configuration des paramètres VPN](how-to-configure-vpn-settings.md) et des [paramètres Intune VPN pour les appareils Android](vpn-for-android.md).

Notez le nom du profil VPN pour pouvoir l’utiliser à l’étape suivante. Par exemple, **MonProfilVpnApp**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Étape 2 : Créer une stratégie de configuration personnalisée

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configuration de l’appareil**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau de profils, cliquez sur **Créer un profil**.
4. Dans le panneau **Créer un profil**, saisissez un **Nom** et une **Description** pour votre profil personnalisé.
5. Dans la liste déroulante **Plateforme**, choisissez **Android**.
6. Dans la liste déroulante **Type de profil**, choisissez **Personnalisé**.
7. Choisissez **Paramètres** > **Configurer**.
3. Dans le panneau **Paramètres OMA-URI personnalisés**, choisissez **Ajouter**.
    - Entrez un nom de paramètre.
    - Pour **Type de données**, spécifiez **Chaîne**.
    - Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/PackageList**, où*Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans cet exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/PackageList**.
    - Pour **Valeur**, créez une liste délimitée par des points-virgules des packages à associer au profil. Par exemple, si vous souhaitez qu’Excel et le navigateur Google Chrome utilisent la connexion VPN, entrez : **com.microsoft.office.excel;com.android.chrome**.

![Exemple de stratégie personnalisée de VPN par application Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Définir votre liste d’applications comme liste rouge ou liste verte (facultatif)
  Vous pouvez spécifier une liste d’applications qui *ne peuvent pas* utiliser la connexion VPN en utilisant une valeur **BLACKLIST**. Toutes les autres applications se connecteront par le biais du VPN.
Vous pouvez également utiliser la valeur **WHITELIST** pour spécifier une liste d’applications qui *peuvent* utiliser la connexion VPN. Les applications qui ne figurent pas dans la liste ne se connecteront pas par le biais du VPN.
  1.    Dans le panneau **Paramètres OMA-URI personnalisés**, choisissez **Ajouter**.
  2.    Entrez un nom de paramètre.
  3.    Pour **Type de données**, spécifiez **Chaîne**.
  4.    Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/Mode**, où*Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/Mode**.
  5.    Pour **Valeur**, entrez **BLACKLIST** ou **WHITELIST**.



## <a name="step-3-assign-both-policies"></a>Étape 3 : Affecter les deux stratégies

Suivez les instructions du [Guide pratique pour attribuer des profils d’appareils](how-to-assign-device-profiles.md) pour affecter les deux profils aux utilisateurs ou appareils nécessaires.

