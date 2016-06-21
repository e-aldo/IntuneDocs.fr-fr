---
# required metadata

title: Protéger les appareils Windows avec l’authentification multifacteur | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: vinaybha
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protect Windows devices with multi-factor authentication
Microsoft Intune intègre l’authentification multifacteur (MFA) pour vous aider à sécuriser vos ressources d’entreprise. L’authentification multifacteur requiert des facteurs d’authentification, notamment l’authentification textuelle, en plus des noms d’utilisateur et mots de passe. Intune prend en charge l’utilisation de l’authentification multifacteur lors de l’inscription d’appareils sous Windows 8.1 ou version ultérieure, Windows Phone 8.1 ou Windows 10 Desktop et Mobile. 

## Conditions requises au niveau de l'infrastructure locale pour l'authentification multifacteur
Pour configurer l'authentification multifacteur, vous avez besoin des éléments suivants :

-   **un domaine Active Directory dont le serveur AD FS est membre ;**

-   **un serveur AD FS (Active Directory Federation Services), configuré pour l'authentification multifacteur ;** un serveur exécutant Windows Server 2012 R2, configuré en tant que serveur AD FS. Pour plus d’informations, consultez : [Sécuriser les ressources cloud et locales à l’aide du serveur Azure Multi-Factor Authentication avec Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/)

Tous les serveurs répertoriés ci-dessus doivent répondre à la configuration requise indiquée dans [Configuration requise et informations d'installation pour Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

#### Authentification multifacteur dans Intune
Si votre organisation a une infrastructure informatique locale qui comprend un domaine Active Directory avec les services AD FS (Active Directory Federation Services), vous pouvez configurer l’authentification multifacteur sur votre serveur de fédération, puis l’activer pour inscription auprès d’Intune. En configurant l’authentification multifacteur sur Intune, vous permettez aux utilisateurs de s’authentifier une seule fois, lors de l’inscription, puis d’accéder aux ressources de l’entreprise sans avoir à répéter le processus d’authentification multifacteur à chaque fois.

>[!NOTE] L’authentification multifacteur est nécessaire par utilisateur ou par groupe sur le serveur AD FS.  

#### Authentification multifacteur sans Intune
Si vous configurez l’authentification MFA sur votre serveur de fédération, mais que vous ne l’activez pas pour l’inscription dans Intune, les utilisateurs doivent recourir à l’authentification MFA chaque fois qu’ils accèdent aux ressources d’entreprise (et pas seulement à l’inscription de l’appareil).

Vous pouvez également utiliser l’authentification Azure Active Directory (AAD) MFA pour exiger l’authentification MFA chaque fois que les utilisateurs accèdent aux ressources de l’entreprise, pour chaque utilisateur. L'authentification multifacteur AAD est un service cloud qui ne nécessite aucune infrastructure informatique locale. Pour savoir comment configurer AAD MFA, consultez [Prise en main d’Azure Multi-Factor Authentication dans le cloud.](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## Exiger l’authentification multifacteur AD FS pendant l’inscription d’appareils Windows
Pour plus d'informations sur la façon d'activer l'authentification multifacteur dans les services AD FS, consultez [Gérer les risques avec une authentification multifacteur supplémentaire pour les applications sensibles](http://technet.microsoft.com/library/dn280949.aspx).

## Configurer l’authentification MFA à l’inscription des appareils dans Intune
>[!Important]  
>Activez l’authentification multifacteur dans votre client Azure AD ou votre environnement local avant de rendre obligatoire l’authentification multifacteur pour l’inscription d’appareils Windows dans Intune. Si vous ne le faites pas, les utilisateurs recevront un message d’erreur quand ils tenteront d’inscrire leurs appareils Windows ou d’enregistrer leurs appareils dans Azure AD, si l’inscription automatique pendant l’enregistrement dans Azure AD est configurée.

1.  Dans la console d’administration Intune, cliquez sur **Administration** &gt; **Gestion des appareils mobiles** &gt; **Authentification multifacteur**.

2.  Cliquez sur **Configurer l’authentification multifacteur**, puis sur **Activer l’authentification multifacteur**.



<!--HONumber=Jun16_HO1-->


