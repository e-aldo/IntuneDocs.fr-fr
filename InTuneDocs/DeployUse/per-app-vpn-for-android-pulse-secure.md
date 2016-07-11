---
title: "VPN par application pour Android à l’aide de Pulse Secure | Microsoft Intune"
description: 
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 05/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.sourcegitcommit: 40e5602a4675bd92a85001827fb43426c41ed1e3
ms.openlocfilehash: fc58e71a9b2279200dee2630aab7dbab727ea128


---

# Utiliser une stratégie personnalisée pour créer un profil VPN par application pour les appareils Android

Vous pouvez créer un profil VPN par application pour les appareils Android gérés par Intune. Tout d’abord, vous allez créer un profil VPN qui utilise le type de connexion Pulse Secure, puis une stratégie de configuration personnalisée qui associe ce profil à des applications spécifiques. Une fois que vous avez déployé ces stratégies sur vos groupes d’utilisateurs ou d’appareils Android, l’ouverture d’une des applications spécifiées sur ces appareils ouvre une connexion VPN pour cette application. 

### Étape 1 : Créer un profil VPN

1. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), cliquez sur **Stratégie** > **Ajouter une stratégie**.
2. Sélectionnez un modèle pour la nouvelle stratégie en développant **Android**, puis choisissez **Profil VPN (Android 4 et versions ultérieures)**.

3. Dans le modèle, pour **Type de connexion**, choisissez **Pulse Secure**.
4. Renseignez et enregistrez le profil VPN. Pour plus d’informations sur les profils VPN, consultez [Connexions VPN](vpn-connections-in-microsoft-intune.md).

> [!NOTE]
Notez le nom du profil VPN pour pouvoir l’utiliser à l’étape suivante. Par exemple, **MonProfilVpnApp**.
   
### Étape 2 : Créer une stratégie de configuration personnalisée
    
   1. Dans la console d’administration Intune **Stratégie** -> **Ajouter une stratégie** -> **Android** -> **Configuration personnalisée** -> **Créer une stratégie**.
   2. Spécifiez un nom pour la stratégie.
   3. Sous **Paramètres OMA-URI**, cliquez sur **Ajouter**.
   4. Fournissez un nom de paramètre.
   5. Pour **Type de données**, spécifiez **Chaîne**.
   6. Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/PackageList**, où *Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/PackageList**.
   7.   Dans **Valeur**, fournissez une liste séparée par des points-virgules des packages qui doivent être associés au profil.  Par exemple, si vous souhaitez qu’Excel et le navigateur Google Chrome utilisent la connexion VPN, vous devez entrer : **com.microsoft.office.excel;com.android.chrome**.
  

   ![Exemple de stratégie personnalisée de VPN par application Android](..\media\android_per_app_vpn_oma_uri.png) 
#### Définissez votre liste d’applications comme liste noire ou liste blanche (facultatif)
Vous pouvez spécifier que votre liste d’applications *ne sera pas* autorisée à utiliser la connexion VPN, à l’aide de la valeur **BLACKLIST**.  Toutes les autres applications se connectent via VPN.

Vous pouvez également spécifier que *seules* les applications spécifiées sont en mesure d’utiliser la connexion VPN, à l’aide de la valeur **WHITELIST**.
 

1.  Sous Paramètres OMA-URI, cliquez sur **Ajouter**.
2.  Fournissez un nom de paramètre.
3.  Pour **Type de données**, spécifiez **Chaîne**.
4.  Pour **OMA-URI**, spécifiez la chaîne suivante : **./Vendor/MSFT/VPN/Profile/*Nom*/Mode**, où *Nom* est le nom du profil VPN que vous avez noté à l’étape 1. Dans notre exemple, la chaîne est **./Vendor/MSFT/VPN/Profile/MonProfilVpnApp/Mode**.
5.  Dans **Valeur**, entrez **BLACKLIST** ou **WHITELIST**. 


   
### Étape 3 : Déployer les deux stratégies

Vous devez déployer *les deux* stratégies sur les *mêmes* groupes Intune.

   1.  Dans l’espace de travail **Stratégie** , sélectionnez la stratégie à déployer, puis cliquez sur **Gérer le déploiement**.

2.  Dans la boîte de dialogue **Gérer le déploiement** :

    -   **Pour déployer la stratégie** : sélectionnez un ou plusieurs groupes sur lesquels déployer la stratégie, puis cliquez sur **Ajouter** &gt; **OK**.

    -   **Pour fermer la boîte de dialogue sans la déployer**, cliquez sur **Annuler**.

Un récapitulatif de l'état et des alertes identifient, dans la page **Vue d'ensemble** de l'espace de travail **Stratégie** , les problèmes liés à la stratégie qui nécessitent votre attention. En outre, le Tableau de bord contient un récapitulatif de l'état.




<!--HONumber=Jun16_HO4-->


