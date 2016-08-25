---
title: Authentification multifacteur pour Windows | Microsoft Intune
description: "Intune intègre l’authentification multifacteur (MFA) pour vous aider à sécuriser vos ressources d’entreprise."
keywords: 
author: Nbigman
manager: angrobe
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4993982adcfbc960ad71022268cc44d216d1c585
ms.openlocfilehash: fb4ae43ffcbec24147e2e3ce3c96ec795289c925


---

# Protect Windows devices with multi-factor authentication
Microsoft Intune intègre l’authentification multifacteur (MFA) pour vous aider à sécuriser vos ressources d’entreprise. MFA nécessite des facteurs d’authentification comme l’authentification textuelle, en plus des noms d’utilisateur et mots de passe. Intune prend en charge l’utilisation de l’authentification multifacteur lors de l’inscription d’appareils sous Windows 8.1 ou version ultérieure, Windows Phone 8.1 ou Windows 10 Desktop et Mobile.

## Conditions requises au niveau de l'infrastructure locale pour l'authentification multifacteur
Pour configurer l'authentification multifacteur, vous avez besoin des éléments suivants :

-   **un domaine Active Directory dont le serveur AD FS est membre ;**

-   **un serveur AD FS (Active Directory Federation Services), configuré pour l'authentification multifacteur ;** Un serveur exécutant Windows Server 2012 R2 et configuré comme serveur AD FS. Pour plus d’informations, consultez : [Sécuriser les ressources cloud et locales à l’aide du serveur Azure Multi-Factor Authentication avec Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Tous les serveurs répertoriés ci-dessus doivent répondre à la configuration requise indiquée dans [Configuration requise et informations d’installation pour Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx)

#### Authentification multifacteur dans Intune
Si votre organisation a une infrastructure informatique locale qui comprend un domaine Active Directory avec les services AD FS (Active Directory Federation Services), vous pouvez configurer MFA sur votre serveur de fédération, puis l’activer pour inscription auprès d’Intune. Quand vous configurez MFA sur Intune, les utilisateurs peuvent s’authentifier une seule fois, lors de l’inscription, puis utiliser les ressources de l’entreprise sans avoir à répéter le processus MFA à chaque fois.

>[!NOTE]
>L’authentification multifacteur est requise par utilisateur ou par groupe sur le serveur AD FS.  

#### Authentification multifacteur sans Intune
Si vous configurez MFA sur votre serveur de fédération, mais que vous ne l’activez pas pour l’inscription dans Intune, les utilisateurs doivent utiliser MFA chaque fois qu’ils accèdent aux ressources d’entreprise (et pas seulement lors de l’inscription de l’appareil).

Vous pouvez également utiliser Azure Active Directory (AAD) MFA pour exiger l’utilisation de MFA pour chaque utilisateur chaque fois que les utilisateurs accèdent aux ressources de l’entreprise. Azure AD MFA est un service cloud qui ne nécessite aucune infrastructure informatique locale. Pour savoir comment configurer Azure AD MFA, consultez [Prise en main avec Azure Multi-Factor Authentication dans le cloud](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Exiger l’authentification multifacteur AD FS pendant l’inscription d’appareils Windows
Pour plus d'informations sur la façon d'activer l'authentification multifacteur dans les services AD FS, consultez [Gérer les risques avec une authentification multifacteur supplémentaire pour les applications sensibles](http://technet.microsoft.com/library/dn280949.aspx).

## Configurer l’authentification MFA à l’inscription des appareils dans Intune
>[!Important]  
>Activez l’authentification multifacteur dans votre client Azure AD ou votre environnement local avant de rendre obligatoire l’authentification multifacteur pour l’inscription d’appareils Windows dans Intune. Si vous ne le faites pas, les utilisateurs qui tentent d’inscrire leurs appareils Windows ou d’enregistrer leurs appareils dans Azure AD recevront un message d’erreur lors de la configuration de l’inscription automatique pendant l’enregistrement dans Azure AD.

1.  Dans la console d’administration Intune, choisissez **Administration** &gt; **Gestion des appareils mobiles** &gt; **Authentification multifacteur**.

2.  Choisissez **Configurer l’authentification multifacteur**, sur **Activer l’authentification multifacteur**.



<!--HONumber=Aug16_HO3-->


