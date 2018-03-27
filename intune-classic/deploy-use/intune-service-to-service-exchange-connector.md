---
title: Connecteur Exchange pour Exchange Online
description: Connectez Intune au service Office 365 Exchange pour prendre en charge la gestion des appareils mobiles via Exchange ActiveSync.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/29/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 78b4e91fd61bb79c2a3a6d86d5a79c39b320cc5e
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a>Configurer le connecteur service à service d’Intune pour Exchange Online

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez ces informations pour connecter Microsoft Intune et Exchange Online ou le nouveau service Microsoft Exchange Online Dedicated. Pour déterminer si votre environnement Microsoft Exchange Online Dedicated est la version **nouvelle** ou **héritée**, contactez votre responsable de comptes. Microsoft Intune prend en charge une seule connexion du connecteur Exchange par abonnement, quel que soit le type de connecteur.

## <a name="service-to-service-connector-requirements"></a>Configuration requise pour le connecteur de service à service
Le **connecteur de service à service** prend en charge seulement Exchange Online ou Exchange Online Dedicated, et n’a pas de configuration requise pour l’infrastructure locale.

|Exigence|Plus d'informations|
|---------------|--------------------|
|Le serveur Exchange Online configuré et en cours d’exécution|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorité de gestion des appareils mobiles| [Définir Microsoft Intune comme autorité de gestion des appareils mobiles](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|Version Microsoft Exchange|Exchange Online ou le nouveau service Exchange Online Dedicated|/intune/users-permissions-add
|Synchronisation Active Directory|Avant de pouvoir utiliser le connecteur Intune, vous devez [configurer la synchronisation Active Directory](/intune/users-permissions-add) pour que vos utilisateurs et groupes de sécurité locaux soient synchronisés avec votre instance d’Azure Active Directory.|

### <a name="exchange-cmdlet-requirements"></a>Spécifications des applets de commande Exchange

Vous devez aussi créer un compte d’utilisateur Exchange Online utilisé par le connecteur Exchange d’Intune. Le compte doit avoir l’autorisation d’utiliser la console d’administration Intune et d’exécuter les applets de commande Exchange Windows PowerShell nécessaires suivantes :

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## <a name="set-up-the-service-to-service-connector"></a>Configurer Service to Service Connector

1. Ouvrez la [console d’administration Microsoft Intune](https://manage.microsoft.com) avec un compte d’utilisateur disposant des droits d’administrateur Exchange et des autorisations pour les applets de commande décrites [plus haut](#exchange-cmdlet-requirements). Microsoft Intune utilise l’adresse e-mail de l’utilisateur actuellement connecté pour configurer la connexion.

2.  Dans le volet des raccourcis de l’espace de travail, choisissez **ADMIN**>**Gestion des appareils mobiles** > **Microsoft Exchange** > **Configurer la connexion Exchange**.
![Page Configurer le connecteur de service à service](../media/intunesa5cservicetoserviceconnector.png)

3.  Dans la page **Configurer la connexion Exchange**, cliquez sur **Configurer le connecteur de service à service**.


Le connecteur de service à service configure et synchronise automatiquement votre environnement Exchange Online ou votre nouvel environnement Exchange Online Dedicated.

## <a name="validate-your-exchange-connection"></a>Valider votre connexion Exchange

Une fois que vous avez correctement configuré le connecteur Exchange, accédez à la [console d’administration Microsoft Intune](https://manage.microsoft.com). Choisissez **Admin**> **Gestion des appareils mobiles** > **Microsoft Exchange**. Vérifiez ensuite que les détails que vous avez fournis apparaissent sous **Informations de connexion à Exchange**.

Vous pouvez également vérifier la date et l'heure de la dernière tentative de synchronisation réussie.
