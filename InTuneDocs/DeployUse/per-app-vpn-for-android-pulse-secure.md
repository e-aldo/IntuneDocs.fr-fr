---
title: "VPN par application pour Android à l’aide de Pulse Secure | Microsoft Intune"
description: "Vous pouvez créer un profil VPN par application pour les appareils Android gérés par Intune."
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a2464a9d2276319f75a3da7db70c2613152bed9b
ms.openlocfilehash: 177ed5f693b8f1ce16d96e1b3e729630d661475f


---

# Utiliser une stratégie personnalisée pour créer un profil VPN par application pour les appareils Android

Vous pouvez créer un profil VPN par application pour les appareils Android gérés par Intune. Tout d’abord, créez un profil VPN qui utilise le type de connexion Pulse Secure. Ensuite, créez une stratégie de configuration personnalisée qui associe le profil VPN à des applications spécifiques. Une fois que vous avez déployé la stratégie sur vos groupes d’utilisateurs ou d’appareils Android, quand un utilisateur ouvre l’une des applications spécifiées sur l’un de ces appareils, une connexion VPN pour cette application s’ouvre.

> [!NOTE]
>
> Seul le type de connexion sécurisé Pulse Secure est pris en charge pour ce profil.


### Étape 1 : Créer un profil VPN

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Stratégie** > **Ajouter une stratégie**.
2. Pour sélectionner un modèle pour la nouvelle stratégie, développez **Android**, puis choisissez **Profil VPN (Android 4 et versions ultérieures)**.
3. Dans le modèle, pour **Type de connexion**, choisissez **Pulse Secure**.
4. Terminez et enregistrez le profil VPN. Pour plus d’informations sur les profils VPN, consultez [Connexions VPN](../deploy-use/vpn-connections-in-microsoft-intune.md).

> [!NOTE]
>
> Notez le nom du profil VPN pour pouvoir l’utiliser à l’étape suivante. Par exemple, MonProfilVpnApp.

### Étape 2 : Créer une stratégie de configuration personnalisée

   1. Dans la console d’administration Intune, choisissez **Stratégie** > **Ajouter une stratégie** > **Android** > **Configuration personnalisée** > **Créer une stratégie**.
   2. Entrez un nom pour la stratégie.
   3. Sous **Paramètres OMA-URI**, choisissez **Ajouter**.
   4. Entrez un nom de paramètre.
   5. Pour **Type de données**, spécifiez **Chaîne**.
   6. Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/PackageList**, où *Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/PackageList**.
   7.   Pour **Valeur**, créez une liste délimitée par des points-virgules des packages à associer au profil. Par exemple, si vous souhaitez qu’Excel et le navigateur Google Chrome utilisent la connexion VPN, entrez : **com.microsoft.office.excel;com.android.chrome**.


    ![Exemple de stratégie personnalisée de VPN par application Android](..\media\android_per_app_vpn_oma_uri.png)

#### Définir votre liste d’applications comme liste rouge ou liste verte (facultatif)
  Vous pouvez spécifier une liste d’applications qui *ne peuvent pas* utiliser la connexion VPN en utilisant une valeur **BLACKLIST**. Toutes les autres applications se connecteront par le biais du VPN.
Vous pouvez également utiliser la valeur **WHITELIST** pour spécifier une liste d’applications qui *peuvent* utiliser la connexion VPN. Les applications qui ne figurent pas dans la liste ne se connecteront pas par le biais du VPN.
  1.    Sous **Paramètres OMA-URI**, choisissez **Ajouter**.
  2.    Entrez un nom de paramètre.
  3.    Pour **Type de données**, spécifiez **Chaîne**.
  4.    Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/Mode**, où *Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/Mode**.
  5.    Pour **Valeur**, entrez **BLACKLIST** ou **WHITELIST**.



### Étape 3 : Déployer les deux stratégies

Vous devez déployer *les deux* stratégies sur les *mêmes* groupes Intune.

1.  Dans l’espace de travail **Stratégie**, sélectionnez la stratégie à déployer, puis choisissez **Gérer le déploiement**.
2.  Dans la boîte de dialogue **Gérer le déploiement** :
    -   **Pour déployer la stratégie**, sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis choisissez **Ajouter** > **OK**.
    -   **Pour fermer la boîte de dialogue sans déployer la stratégie**, choisissez **Annuler**.

Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. Le **Tableau de bord** contient aussi un récapitulatif de l’état.



<!--HONumber=Aug16_HO3-->


