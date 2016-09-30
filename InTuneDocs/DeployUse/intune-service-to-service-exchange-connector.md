---
title: "Connecteur Exchange pour Exchange Online | Microsoft Intune"
description: "Connectez Intune au service Office 365 Exchange pour prendre en charge la gestion des appareils mobiles via Exchange ActiveSync."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c880bd9dfb998355a18e78af898a96d4cee393f7
ms.openlocfilehash: a6438bb3ca21e5c46dca5ebe69266fd9bce9a4b8


---

# Configurer le connecteur service à service d’Intune pour Exchange Online

Utilisez ces informations pour connecter Microsoft Intune et Exchange Online, ou un nouveau service Microsoft Exchange Online Dedicated. Pour déterminer si votre environnement Microsoft Exchange Online Dedicated présente la **nouvelle** configuration ou une configuration **héritée**, contactez votre responsable de comptes. Microsoft Intune prend en charge une seule connexion du connecteur Exchange par abonnement, quel que soit le type de connecteur.

## Conditions requises pour le connecteur service à service
Le **connecteur service à service** prend en charge Exchange Online ou un nouvel environnement Microsoft Exchange Online Dedicated uniquement et n’a pas de spécifications quant à l’infrastructure locale.

|Exigence|Plus d'informations|
|---------------|--------------------|
|Le serveur Exchange Online configuré et en cours d’exécution|[Exchange Online](https://technet.microsoft.com/library/jj200580.aspx) |
|Autorité de gestion des appareils mobiles| [Définir Microsoft Intune comme autorité de gestion des appareils mobiles](prerequisites-for-enrollment.md#set-mobile-device-management-authority)|
|Version Microsoft Exchange|Exchange Online ou nouveau service Exchange Online Dedicated|
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


Le connecteur de service à service configure et se synchronise automatiquement avec votre environnement Exchange Online ou votre nouvel environnement Exchange Online Dedicated.

## Valider votre connexion Exchange

Après avoir configuré avec succès le connecteur Exchange, dans la [console d’administration Intune](http://manage.microsoft.com), sélectionnez **Admin**, accédez à **Gestion des appareils mobiles** > **Microsoft Exchange** et vérifiez que les détails que vous avez fournis apparaissent sous **Informations de connexion à Exchange**.

Vous pouvez également vérifier la date et l'heure de la dernière tentative de synchronisation réussie.



<!--HONumber=Sep16_HO4-->


