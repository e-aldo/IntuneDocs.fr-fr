---
title: VPN par application avec Android Pulse Secure
description: Vous pouvez créer un profil VPN par application pour les appareils Android gérés par Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fb4b6ad21b83d6ed2844238091f2e24e0d15cea5
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a>Utiliser une stratégie personnalisée pour créer un profil VPN par application pour les appareils Android

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Vous pouvez créer un profil VPN par application pour les appareils Android 5.0 et ultérieur gérés par Intune. Tout d’abord, créez un profil VPN qui utilise le type de connexion Pulse Secure ou Citrix. Ensuite, créez une stratégie de configuration personnalisée qui associe le profil VPN à des applications spécifiques. 

Une fois que vous avez déployé la stratégie sur votre appareil Android ou vos groupes d’utilisateurs, les utilisateurs doivent démarrer le VPN Pulse Secure ou Citrix. La connexion autorise alors uniquement le trafic provenant des applications spécifiées à utiliser la connexion VPN ouverte.

> [!NOTE]
>
> Seul les types de connexions Pulse Secure et Citrix sont pris en charge pour ce profil.


### <a name="step-1-create-a-vpn-profile"></a>Étape 1 : Créer un profil VPN

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Ajouter une stratégie**.
2. Pour sélectionner un modèle pour la nouvelle stratégie, développez **Android**, puis choisissez **Profil VPN (Android 4 et versions ultérieures)**.
3. Dans le modèle, pour **Type de connexion**, choisissez **Pulse Secure** ou **Citrix**.
4. Terminez et enregistrez le profil VPN. Pour plus d’informations sur les profils VPN, consultez [Connexions VPN](../deploy-use/vpn-connections-in-microsoft-intune.md).

> [!NOTE]
>
> Prenez note de la valeur **Nom de connexion VPN (affiché auprès des utilisateurs) :** que vous spécifiez lors de la création du profil VPN. Cela sera nécessaire lors de l’étape suivante. Par exemple, **MonProfilVpnApp**.

### <a name="step-2-create-a-custom-configuration-policy"></a>Étape 2 : Créer une stratégie de configuration personnalisée

   1. Dans la console d’administration Intune, choisissez **Stratégie** > **Ajouter une stratégie** > **Android** > **Configuration personnalisée** > **Créer une stratégie**.
   2. Entrez un nom pour la stratégie.
   3. Sous **Paramètres OMA-URI**, choisissez **Ajouter**.
   4. Entrez un nom de paramètre.
   5. Pour **Type de données**, spécifiez **Chaîne**.
   6. Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/PackageList**, où *Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/PackageList**.
   7.   Pour **Valeur**, créez une liste délimitée par des points-virgules des packages à associer au profil. Par exemple, si vous souhaitez qu’Excel et le navigateur Google Chrome utilisent la connexion VPN, entrez : **com.microsoft.office.excel;com.android.chrome**.

![Exemple de stratégie personnalisée de VPN par application Android](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Définir votre liste d’applications comme liste rouge ou liste verte (facultatif)
  Vous pouvez spécifier une liste d’applications qui *ne peuvent pas* utiliser la connexion VPN en utilisant une valeur **BLACKLIST**. Toutes les autres applications se connecteront par le biais du VPN.
Vous pouvez également utiliser la valeur **WHITELIST** pour spécifier une liste d’applications qui *peuvent* utiliser la connexion VPN. Les applications qui ne figurent pas dans la liste ne se connecteront pas par le biais du VPN.
  1.    Sous **Paramètres OMA-URI**, choisissez **Ajouter**.
  2.    Entrez un nom de paramètre.
  3.    Pour **Type de données**, spécifiez **Chaîne**.
  4.    Pour **OMA-URI**, utilisez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/Mode**, où *Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/Mode**.
  5.    Pour **Valeur**, entrez **BLACKLIST** ou **WHITELIST**.



### <a name="step-3-deploy-both-policies"></a>Étape 3 : Déployer les deux stratégies

Vous devez déployer *les deux* stratégies sur les *mêmes* groupes Intune.

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.
2.  Dans la boîte de dialogue **Gérer le déploiement** :
    -   **Pour déployer la stratégie**, sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis choisissez **Ajouter** > **OK**.
    -   **Pour fermer la boîte de dialogue sans déployer la stratégie**, choisissez **Annuler**.

Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. Le **Tableau de bord** contient aussi un récapitulatif de l’état.
