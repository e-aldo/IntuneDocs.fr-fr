---
title: "Utiliser la réinitialisation aux paramètres d’usine ou la suppression des données d’entreprise sur des appareils à l’aide d’Intune"
titlesuffix: Azure portal
description: "Découvrez comment supprimer les données d’entreprise d’un appareil ou le réinitialiser aux paramètres d’usine."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 41bfb62f90965288d73948650b6935434c986d92
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/09/2017
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Supprimer des appareils en réinitialisant les paramètres d’usine ou en supprimant les données d’entreprise

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vous pouvez supprimer d’Intune les appareils dont vous n’avez plus besoin, qui ont été réaffectés ou qui ont disparu. Pour cela, vous pouvez émettre une commande de **suppression des données d’entreprise** ou de **réinitialisation aux paramètres d’usine**. Les utilisateurs peuvent également émettre une commande à distance à partir de l’application Portail d’entreprise Intune sur les appareils personnels inscrits dans Intune.

> [!NOTE]
> Avant de supprimer un utilisateur d’Azure Active Directory, émettez une commande de **réinitialisation aux paramètres d’usine** ou de **suppression des données d’entreprise** à tous les appareils associés à cet utilisateur. Si vous supprimez des utilisateurs avec des appareils gérés d’Azure Active Directory, Intune ne peut plus émettre de commande de réinitialisation aux paramètres d’usine ou de suppression des données d’entreprise à ces appareils.

## <a name="factory-reset"></a>Réinitialisation des paramètres d’usine

La commande de **réinitialisation aux paramètres d’usine** rétablit les paramètres d’usine d’un appareil et supprime l’ensemble des données et des paramètres de l’entreprise et de l’utilisateur. L’appareil n’est plus géré par Intune. La réinitialisation aux paramètres d’usine est utile pour réinitialiser un appareil avant de le transmettre à un nouvel utilisateur ou dans les cas où l’appareil a été perdu ou volé. Faites attention lors de la sélection de la réinitialisation aux paramètres d’usine. Les données sur l’appareil ne peuvent pas être récupérées.

### <a name="to-factory-reset-a-device"></a>Pour réinitialiser un appareil aux paramètres d’usine

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
4. Cliquez sur le nom de l’appareil à réinitialiser aux paramètres d’usine.
5. Dans le panneau présentant le nom de l’appareil, choisissez **Réinitialisation aux paramètres d’usine**, puis **Oui** pour confirmer.

Si l’appareil est allumé et connecté, la propagation de la commande de réinitialisation aux paramètres d’usine prend moins de 15 minutes, quel que soit le type de l’appareil.

## <a name="remove-company-data"></a>Supprimer les données d’entreprise

La commande de **suppression des données d’entreprise** supprime les paramètres, les profils de messagerie et les données de l’application gérée (le cas échéant) qui ont été affectés à l’aide d’Intune. La suppression des données d’entreprise conserve les données personnelles de l’utilisateur sur l’appareil. L’appareil n’est plus géré par Intune. Les tableaux suivants décrivent la nature des données supprimées et l’effet de cette opération sur les données qui restent sur l’appareil après la suppression des données d’entreprise.

### <a name="ios"></a>iOS

|Type de données|iOS|
|-------------|-------|
|Applications d’entreprise et données associées installées par Intune|Les applications sont désinstallées. Les données des applications de l'entreprise sont supprimées.<br /><br />Les données d'application des applications Microsoft qui utilisent la gestion des applications mobiles sont supprimées. L'application n'est pas supprimée.|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|
|Paramètres de profil de certificat|Les certificats sont supprimés et révoqués.|
|Agent de gestion|Le profil de gestion est supprimé.|
|Courrier électronique|Les profils de messagerie approvisionnés via Intune sont supprimés. Les e-mails mis en cache sur l’appareil le sont également.|
|Outlook|Les messages reçus par l’application Microsoft Outlook pour iOS sont supprimés.|
|Disjonction d’Azure Active Directory (AD)|L’enregistrement AD est supprimé.|
|Contacts | Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés.  Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être supprimés. <br /> <br />Actuellement, seule l’application Outlook est prise en charge.

### <a name="android"></a>Android

|Type de données|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|Liens web|Supprimé.|Supprimé.|
|Applications Google Play non gérées|Les applications et les données sont toujours installées.|Les applications et les données sont toujours installées.|
|Applications métier non gérées|Les applications et les données sont toujours installées.|Les applications sont désinstallées et les données locales propres aux applications sont supprimées en conséquence. Aucune donnée extérieure à l’application (par exemple, sur une carte SD) n’est supprimée.|
|Applications Google Play gérées|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par chiffrement GAM extérieures à l’application (par exemple, une carte SD) restent chiffrées et inutilisables, mais ne sont pas supprimées.|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par chiffrement GAM extérieures à l’application (par exemple, une carte SD) restent chiffrées, mais ne sont pas supprimées.|
|Applications métier gérées|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par chiffrement GAM extérieures à l’application (par exemple, une carte SD) restent chiffrées et inutilisables, mais ne sont pas supprimées.|Les données d’application sont supprimées. L’application n’est pas supprimée. Les données protégées par chiffrement GAM extérieures à l’application (par exemple, une carte SD) restent chiffrées et inutilisables, mais ne sont pas supprimées.|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|Supprimé.|
|Paramètres de profil de certificat|Certificats révoqués, mais pas supprimés.|Certificats supprimés et révoqués.|
|Agent de gestion|Le privilège d'administrateur d'appareil est révoqué.|Le privilège d'administrateur d'appareil est révoqué.|
|Courrier électronique|n/a (profils de messagerie non pris en charge par les appareils Android)|Les profils de messagerie approvisionnés via Intune sont supprimés. Les e-mails mis en cache sur l’appareil le sont également.|
|Outlook|Les messages reçus par l’application Microsoft Outlook pour Android sont supprimés.|Les messages reçus par l’application Microsoft Outlook pour Android sont supprimés.|
|Disjonction d’Azure Active Directory (AD)|Enregistrement AD supprimé.|Enregistrement AD supprimé.|
|Contacts | Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés.  Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être supprimés. <br /> <br />Actuellement, seule l’application Outlook est prise en charge.|Les contacts synchronisés avec le carnet d’adresses natif directement à partir de l’application sont supprimés.  Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être supprimés. <br /> <br />Actuellement, seule l’application Outlook est prise en charge.

### <a name="android-for-work"></a>Android for Work

La suppression des données d’entreprise d’un appareil Android for Work supprime l’ensemble des données, applications et paramètres dans le profil professionnel de l’appareil. L’appareil n’est plus géré par Intune. La réinitialisation aux paramètres d’usine n’est pas prise en charge pour Android for Work.

### <a name="windows"></a>Windows

|Type de données|Windows 8.1 (MDM) et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Applications d’entreprise et données associées installées par Intune|Les fichiers protégés par le système EFS voient leur clé révoquée et l'utilisateur n'est pas en mesure d'ouvrir ces fichiers.|Ne supprime pas les applications de la société.|Les applications installées à l'origine via le portail d'entreprise sont désinstallées. Les données des applications de l'entreprise sont supprimées.|Les applications sont désinstallées et les clés de chargement de version test sont supprimées.<br>Pour Windows 10 version 1703 (Creator Update) et ultérieur, les applications Office 365 ProPlus ne sont pas supprimées.|
|Paramètres|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|Les configurations qui ont été définies par la stratégie Intune ne sont plus appliquées et les utilisateurs peuvent modifier les paramètres.|
|Paramètres de profil Wi-Fi et VPN|Supprimé.|Supprimé.|Non pris en charge.|Supprimé.|
|Paramètres de profil de certificat|Certificats supprimés et révoqués.|Certificats supprimés et révoqués.|Non pris en charge.|Certificats supprimés et révoqués.|
|Courrier électronique|Supprime la messagerie électronique compatible avec EFS, qui inclut l’application de messagerie électronique pour la messagerie et les pièces jointes Windows.|Non pris en charge.|Les profils de messagerie approvisionnés via Intune sont supprimés. Les e-mails mis en cache sur l’appareil le sont également.|Supprime la messagerie électronique compatible avec EFS, qui inclut l’application de messagerie électronique pour la messagerie et les pièces jointes Windows. Supprime les comptes de messagerie approvisionnés par Intune.|
|Disjonction d’Azure Active Directory (AD)|Non.|Non.|Enregistrement AD supprimé.|Non applicable. Windows 10 ne prend pas en charge la suppression des données d’entreprise pour les appareils joints à Azure Active Directory.|

### <a name="to-remove-company-data"></a>Pour supprimer les données d’entreprise

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Autres services** > **Surveillance + Gestion** > **Intune**.
3. Dans le panneau **Appareils et groupes**, choisissez **Tous les appareils**.
4. Choisissez le nom de l’appareil dont vous souhaitez supprimer les données d’entreprise.
5. Dans le panneau présentant le nom de l’appareil, choisissez **Supprimer les données d’entreprise**, puis **Oui** pour confirmer.

Si l’appareil est allumé et connecté, la propagation de la commande de suppression des données prend moins de 15 minutes, quel que soit le type de l’appareil.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Supprimer des appareils du portail Azure Active Directory

En cas de problèmes de communication ou d’appareils manquants, vous devrez peut-être supprimer des appareils d’Azure Active Directory (AD). La commande de suppression ne supprime pas un appareil de la gestion, mais vous pouvez utiliser **Supprimer** pour supprimer du portail Azure les enregistrements de l’appareil inaccessibles et peu susceptibles de recommuniquer avec Azure.

1.  Connectez-vous à [Azure Active Directory dans le portail Azure](http://aka.ms/accessaad) avec vos informations d’identification d’administrateur. Vous pouvez également vous connecter au [portail Office 365](https://portal.office.com) , puis choisir **Administrateur** &gt; **Azure AD** à l’aide du lien à gauche de la page.
3.  Créez un abonnement Azure si vous n’en avez pas. Vous ne devriez pas avoir besoin de carte de crédit ni d’effectuer un paiement si vous disposez d’un compte payant (choisissez le lien d’abonnement **Enregistrer votre abonnement Azure Active Directory gratuit**).
4.  Sélectionnez **Active Directory** , puis le nom de votre organisation.
5.  Sélectionnez l’onglet **Utilisateurs** .
6.  Sélectionnez l’utilisateur dont vous voulez supprimer les appareils.
7.  Choisissez **Appareils**.
8.  Supprimez les appareils appropriés, par exemple, ceux qui ne sont plus utilisés ou qui n’ont pas de définitions précises.
