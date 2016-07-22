---
title: "Configurer le connecteur Exchange de Microsoft Intune pour Exchange hébergé | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6951ccdb0e37489217ef939f0cbf6fc1133a6d3c
ms.openlocfilehash: 6cfc532cba2f53034c4c3ef0c2df3d6c1e6e7841


---

# Configurer le connecteur service à service d’Intune pour Exchange Online

Utilisez ces informations pour connecter Microsoft Intune et le service Exchange Online hébergé par Office 365.

## Conditions requises pour le connecteur service à service
Le **connecteur service à service** prend en charge seulement Exchange hébergé et n’a pas de spécifications quant à l’infrastructure locale.

|Condition requise|Plus d'informations|
|---------------|--------------------|
|Le serveur Exchange hébergé configuré et en cours d’exécution|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorité de gestion des appareils mobiles| [Définir Microsoft Intune comme autorité de gestion des appareils mobiles](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority)|
|Version Microsoft Exchange|Vous devez avoir un abonnement Office 365 avec un client Exchange Server 2013 ou ultérieur. Si le client est Exchange Server 2013 ou ultérieur, le connecteur prend en charge Exchange Server 2010 dans ce même environnement.|
|Synchronisation Active Directory|Avant de pouvoir utiliser le connecteur Intune, vous devez [configurer la synchronisation Active Directory](/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) pour que vos utilisateurs et groupes de sécurité locaux soient synchronisés avec votre instance d’Azure Active Directory.|

### Spécifications des applets de commande Exchange

Vous devez aussi créer un compte d’utilisateur Exchange Online utilisé par le connecteur Exchange d’Intune. Le compte doit avoir l’autorisation d’utiliser la console d’administration Intune et d’exécuter ces applets de commande Exchange Windows PowerShell requis :

 - Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings
 - Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy
 - Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule
 - Get-MobileDeviceStatistics
 - Get-MobileDevice
 - Get-ActiveSyncDeviceClass

## Configurer le connecteur service à service

1. Ouvrez la [console d’administration Microsoft Intune](http://manage.microsoft.com) avec un compte d’utilisateur disposant des droits d’administrateur Exchange et des autorisations pour les applets de commande [ci-dessus](#exchange-cmdlet-requirements). Microsoft Intune utilise l’adresse de messagerie de l’utilisateur actuellement connecté pour configurer la connexion.

2.  Dans le volet des raccourcis de l’espace de travail, choisissez **ADMIN**, puis accédez à **Gestion des appareils mobiles** > **Microsoft Exchange** > **Configurer la connexion Exchange**.
![Page Configurer le connecteur de service à service](../media/intunesa5cservicetoserviceconnector.png)

3.  Dans la page **Configurer la connexion Exchange**, cliquez sur **Configurer le connecteur de service à service**.


Le connecteur de service à service se configure et se synchronise automatiquement avec votre environnement Exchange hébergé.

## Valider votre connexion Exchange

Après avoir configuré avec succès le connecteur Exchange, dans la console d’administration Intune, choisissez l’espace de travail **ADMIN** et accédez à **Gestion des appareils mobiles** > **Microsoft Exchange** et vérifiez que les détails que vous avez fournis apparaissent sous **Informations de connexion à Exchange**.

Vous pouvez également vérifier la date et l'heure de la dernière tentative de synchronisation réussie.



<!--HONumber=Jun16_HO4-->


