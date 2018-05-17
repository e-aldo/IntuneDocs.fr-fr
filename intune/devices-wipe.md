---
title: Supprimer des données d’entreprise sur des appareils à l’aide de Microsoft Intune - Azure | Microsoft Docs
description: Découvrez comment supprimer des données d’entreprise sur un appareil ou effectuer une réinitialisation aux paramètres d’usine sur un appareil Android, Android for work, iOS, macOS ou Windows à l’aide de Microsoft Intune. Découvrez également comment supprimer un appareil d’Azure Active Directory.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 84fc162eda25970c14ed1014b9f67ef3e782c663
ms.sourcegitcommit: 7e80388b6223c9a632c5729bf9b157f848fe52cc
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Supprimer des appareils en réinitialisant les paramètres d’usine ou en supprimant les données d’entreprise

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Avec les actions **Supprimer les données d’entreprise** et **Réinitialisation aux paramètres d’usine**, vous pouvez supprimer d’Intune les appareils dont vous n’avez plus besoin, qui ont été réaffectés ou qui ont disparu. Les utilisateurs peuvent également émettre une commande à distance à partir de l’application Portail d’entreprise Intune sur les appareils personnels inscrits dans Intune.

> [!NOTE]
> Avant de supprimer un utilisateur d’Azure Active Directory (Azure AD), utilisez l’action **Réinitialisation aux paramètres d’usine** ou **Supprimer les données d’entreprise** pour tous les appareils qui sont associés à cet utilisateur. Si vous supprimez d’Azure Active Directory des utilisateurs avec des appareils gérés, Intune ne peut plus émettre de commande de réinitialisation aux paramètres d’usine ou de suppression des données d’entreprise pour ces appareils.

## <a name="factory-reset"></a>Réinitialisation des paramètres d’usine

L’action **Réinitialisation aux paramètres d’usine** rétablit les paramètres d’usine d’un appareil. Les données utilisateur sont conservées ou réinitialisées selon que vous avez coché ou non la case **Conserver le compte d’utilisateur et l’état d’inscription**.

|Action Réinitialisation aux paramètres d’usine|**Conserver le compte d’utilisateur et l’état d’inscription**|Supprimé de la gestion Intune|Description|
|:-------------:|:------------:|:------------:|------------|
|**Réinitialisation aux paramètres d’usine**| Désactivée | Oui | Efface tous les comptes d’utilisateur, les données, les stratégies de gestion des appareils mobiles et les paramètres. Réinitialise le système d’exploitation à son état et ses paramètres par défaut.|
|**Réinitialisation aux paramètres d’usine**| Activée | Non | Réinitialise toutes les stratégies de gestion des appareils mobiles. Conserve les données et les comptes d’utilisateur. Réinitialise les paramètres utilisateur par défaut. Réinitialise le système d’exploitation à son état et ses paramètres par défaut.|

L’option **Conserver le compte d’utilisateur et l’état d’inscription** est disponible uniquement pour Windows 10 version 1709 ou ultérieure.

Les stratégies MDM seront réappliquées lors de la prochaine connexion de l’appareil à Intune.

La réinitialisation aux paramètres d’usine est utile pour réinitialiser un appareil avant de le donner à un nouvel utilisateur ou en cas de perte ou de vol de l’appareil. Faites attention lors de la sélection de la **Réinitialisation aux paramètres d’usine**. Les données sur l’appareil ne peuvent pas être récupérées.

### <a name="factory-reset-a-device"></a>Réinitialiser un appareil aux paramètres d’usine

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Sélectionnez **Tous les services**, filtrez sur **Intune**, puis sélectionnez **Microsoft Intune**.
3. Sélectionnez **Appareils** > **Tous les appareils**.
4. Sélectionnez le nom de l’appareil à réinitialiser aux paramètres d’usine.
5. Dans le volet qui affiche le nom de l’appareil, sélectionnez **Réinitialisation aux paramètres d’usine**.
6. Pour Windows 10 version 1709 ou ultérieure, vous avez également l’option **Conserver le compte d’utilisateur et l’état d’inscription**. 
    
    |Éléments conservés pendant une réinitialisation aux paramètres d’usine|Éléments non conservés|
    | -------------|------------|
    |Comptes d’utilisateur associés à l’appareil|Fichiers utilisateur|
    |État de l’ordinateur \(jonction de domaine, jonction à Azure AD)| Applications installées par l’utilisateur \(applications Win32 et du Store)|
    |Inscription à la Gestion des appareils mobiles (MDM)|Paramètres d’appareil autres que les paramètres par défaut|
    |Applications OEM installées \(applications Win32 et du Store)||
    |Profil utilisateur||
    |Données utilisateur hors du profil utilisateur||
    |Ouverture de session automatique de l’utilisateur|| 
    
         
7. Pour confirmer la réinitialisation aux paramètres d’usine, sélectionnez **Oui**.

Si l’appareil est allumé et connecté, la propagation de l’action **Réinitialisation aux paramètres d’usine** prend moins de 15 minutes, quel que soit le type de l’appareil.

## <a name="remove-company-data"></a>Supprimer les données d’entreprise

L’action **Supprimer les données d’entreprise** supprime les paramètres, les profils de messagerie et les données de l’application gérée (le cas échéant) qui ont été affectés à l’aide d’Intune. L’appareil n’est plus géré par Intune. Cela se produit la prochaine fois que l’appareil se connecte et reçoit l’action **Supprimer les données d’entreprise** à distance.

**Supprimer les données d’entreprise** conserve les données personnelles de l’utilisateur sur l’appareil.  

Les tableaux suivants décrivent la nature des données supprimées et l’effet de l’action **Supprimer les données d’entreprise** sur les données qui restent sur l’appareil après la suppression des données d’entreprise.

### <a name="ios"></a>iOS

|Type de données|iOS|
|-------------|-------|
|Applications d’entreprise et données associées installées par Intune|Les applications sont désinstallées. Les données des applications de l'entreprise sont supprimées.<br /><br />Les données d'application des applications Microsoft qui utilisent la gestion des applications mobiles sont supprimées. L'application n'est pas supprimée.|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|
|Paramètres de profil de certificat|Les certificats sont supprimés et révoqués.|
|Agent de gestion|Le profil de gestion est supprimé.|
|E-mail|Les profils de messagerie provisionnés par le biais d’Intune sont supprimés. Les e-mails mis en cache sur l’appareil sont supprimés.|
|Outlook|Les e-mails reçus par l’application Microsoft Outlook pour iOS sont supprimés. Cela nécessite que l’application mobile Outlook soit d’abord déployée en tant qu’application requise pour les utilisateurs iOS.|
|Disjonction d’Azure AD|L’enregistrement Azure AD est supprimé.|
|Contacts |Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être supprimés. <br /> <br />Actuellement, seule l’application Outlook est prise en charge.

### <a name="android"></a>Android

|Type de données|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Liens web|Supprimé.|Supprimé.|
|Applications Google Play non gérées|Les applications et les données sont toujours installées.|Les applications et les données sont toujours installées.|
|Applications métier non gérées|Les applications et les données sont toujours installées.|Les applications sont désinstallées et les données locales propres aux applications sont supprimées. Aucune donnée extérieure à l’application (par exemple, sur une carte SD) n’est supprimée.|
|Applications Google Play gérées|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par le chiffrement MAM (Gestion des applications mobiles) extérieures à l’application (par exemple, une carte SD) restent chiffrées et inutilisables, mais ne sont pas supprimées.|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par le chiffrement MAM extérieures à l’application (par exemple, une carte SD) restent chiffrées, mais ne sont pas supprimées.|
|Applications métier gérées|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par le chiffrement MAM extérieures à l’application (par exemple, une carte SD) restent chiffrées et inutilisables, mais ne sont pas supprimées.|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par le chiffrement MAM extérieures à l’application (par exemple, une carte SD) restent chiffrées et inutilisables, mais ne sont pas supprimées.|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|Supprimé.|
|Paramètres de profil de certificat|Les certificats sont révoqués, mais pas supprimés.|Les certificats sont supprimés et révoqués.|
|Agent de gestion|Le privilège d'administrateur d'appareil est révoqué.|Le privilège d'administrateur d'appareil est révoqué.|
|E-mail|N/A (les profils de messagerie ne sont pas pris en charge par les appareils Android)|Les profils de messagerie provisionnés par le biais d’Intune sont supprimés. Les e-mails mis en cache sur l’appareil sont supprimés.|
|Outlook|Les e-mails reçus par l’application Outlook pour Android sont supprimés, mais uniquement si Outlook est protégé par des stratégies MAM. Dans le cas contraire, Outlook n’est pas réinitialisé quand l’appareil est désinscrit.|Les e-mails reçus par l’application Outlook pour Android sont supprimés, mais uniquement si Outlook est protégé par des stratégies MAM. Dans le cas contraire, Outlook n’est pas réinitialisé quand l’appareil est désinscrit.|
|Disjonction d’Azure AD|L’enregistrement Azure AD est supprimé.|L’enregistrement Azure AD est supprimé.|
|Contacts |Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être supprimés. <br /> <br />Actuellement, seule l’application Outlook est prise en charge.|Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être supprimés. <br /> <br />Actuellement, seule l’application Outlook est prise en charge.

### <a name="android-for-work"></a>Android for Work

La suppression des données d’entreprise d’un appareil Android for Work supprime l’ensemble des données, applications et paramètres dans le profil professionnel de l’appareil. L’appareil est retiré de la gestion avec Intune. La réinitialisation aux paramètres d’usine n’est pas prise en charge pour Android for Work.


### <a name="macos"></a>macOS

|Type de données|macOS|
|-------------|-------|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|
|Paramètres de profil de certificat|Les certificats qui ont été déployées via MDM sont supprimés et révoqués.|
|Agent de gestion|Le profil de gestion est supprimé.|
|Outlook|Si l’accès conditionnel est activé, l’appareil ne reçoit pas de nouveau courrier.|
|Disjonction d’Azure AD|L’enregistrement Azure AD est supprimé.|

### <a name="windows"></a>Windows

|Type de données|Windows 8.1 (MDM) et Windows RT 8.1|Windows RT|Windows Phone 8.1 et Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Applications d’entreprise et données associées installées par Intune|Les clés sont révoquées pour les fichiers protégées par EFS. L’utilisateur ne peut pas ouvrir les fichiers.|Les applications d’entreprise ne sont pas supprimées.|Les applications installées à l’origine par le biais du portail d’entreprise sont désinstallées. Les données des applications de l'entreprise sont supprimées.|Les applications sont désinstallées. Les clés de chargement indépendant (sideloading) sont supprimées.<br>Pour Windows 10 versions 1703 (Creator Update) et ultérieures, les applications Office 365 ProPlus ne sont pas supprimées.|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées. Les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|Supprimé.|Non pris en charge.|Supprimé.|
|Paramètres de profil de certificat|Les certificats sont supprimés et révoqués.|Les certificats sont supprimés et révoqués.|Non pris en charge.|Les certificats sont supprimés et révoqués.|
|E-mail|Supprime les e-mails qui sont activés pour le système EFS. Cela comprend les e-mails et pièces jointes dans l’application Courrier pour Windows.|Non pris en charge.|Les profils de messagerie provisionnés par le biais d’Intune sont supprimés. Les e-mails mis en cache sur l’appareil sont supprimés.|Supprime les e-mails qui sont activés pour le système EFS. Cela comprend les e-mails et pièces jointes dans l’application Courrier pour Windows. Supprime les comptes de messagerie approvisionnés par Intune.|
|Disjonction d’Azure AD|Non.|Non.|L’enregistrement Azure AD est supprimé.|Non applicable. Sur Windows 10, vous ne pouvez pas supprimer les données d’entreprise pour les appareils joints à Azure AD.|

### <a name="remove-company-data"></a>Supprimer les données d’entreprise

1. Connectez-vous à [Intune dans le portail Azure](https://aka.ms/intuneportal).
2. Dans le volet **Appareils**, sélectionnez **Tous les appareils**.
3. Sélectionnez le nom de l’appareil dont vous souhaitez supprimer les données d’entreprise.
4. Dans le volet qui affiche le nom de l’appareil, sélectionnez **Supprimer les données d’entreprise**. Pour confirmer, sélectionnez **Oui**.

Si l’appareil est allumé et connecté, la propagation de l’action **Supprimer les données d’entreprise** prend moins de 15 minutes, quel que soit le type de l’appareil.

## <a name="delete-devices-from-the-intune-portal"></a>Supprimer des appareils à partir du portail Intune

Pour supprimer des appareils à partir du portail Intune, vous pouvez accéder au volet de l’appareil spécifique. La prochaine fois que l’appareil se connecte, toutes les données d’entreprise qu’il contient seront supprimées.

1. Connectez-vous à [Intune dans le portail Azure](https://aka.ms/intuneportal).
2. Choisissez **Appareils** > **Tous les appareils** > choisissez les appareils à supprimer > **Supprimer**.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Supprimer des appareils du portail Azure Active Directory

Vous devrez peut-être supprimer des appareils d’Azure AD en cas de problèmes de communication ou d’appareils manquants. Vous pouvez utiliser l’action **Supprimer** pour supprimer du portail Azure les enregistrements de l’appareil inaccessibles et peu susceptibles de recommuniquer avec Azure. L’action **Supprimer** ne retire pas un appareil de la gestion.

1.  Connectez-vous à [Azure Active Directory dans le portail Azure](http://aka.ms/accessaad) avec vos informations d’identification d’administrateur. Vous pouvez également vous connecter au [portail Office 365](https://portal.office.com). Dans le menu, sélectionnez **Centres d’administration** > **AD Azure**.
2.  Créez un abonnement Azure si vous n’en avez pas. Vous ne devriez pas avoir besoin de carte de crédit ni d’effectuer un paiement si vous disposez d’un compte payant (sélectionnez le lien d’abonnement **Enregistrer votre abonnement Azure Active Directory gratuit**).
3.  Sélectionnez **Azure Active Directory**, puis votre organisation.
4.  Sélectionnez l’onglet **Utilisateurs** .
5. Sélectionnez l’utilisateur associé à l’appareil que vous souhaitez supprimer.
6.  Sélectionnez **Appareils**.
7.  Supprimez les appareils appropriés. Par exemple, vous pouvez supprimer les appareils qui ne sont plus utilisés ou ceux dont les définitions sont incorrectes.
