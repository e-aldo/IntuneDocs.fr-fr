---
title: Authentification multifacteur avec Azure AD | Microsoft Intune
description: "Comment exiger une authentification multifacteur dans Azure AD pour l’inscription d’appareils."
keywords: 
author: nbigman
ms.author: nbigman
manager: angerobe
ms.date: 09/22/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
translationtype: Human Translation
ms.sourcegitcommit: a7cced90c482498b5f5af424165f8dcf77b79b75
ms.openlocfilehash: ccd55cc8637ebccfdbddd05c4f6b182c7923a2ab


---

# Authentification multifacteur pour Microsoft Intune

Intune intègre l’authentification multifacteur (MFA) Azure AD pour l’inscription d’appareils afin de sécuriser vos ressources d’entreprise. MFA nécessite des facteurs d’authentification comme l’authentification textuelle, en plus des noms d’utilisateur et mots de passe. Ils sont pris en charge avec les appareils iOS, Android, Windows 8.1 ou version ultérieure, ou Windows Phone 8.1 ou version ultérieure.

> [!NOTE]
>
> Dans les versions antérieures du Configuration Manager (antérieures à la version 1610), vous verrez toujours le paramètre MFA dans la console d’administration de Configuration Manager. N’essayez pas de configurer l’authentification multifacteur dans la console d’administration de Configuration Manager, car elle ne fonctionnera pas. Configurez l’authentification multifacteur comme décrit dans cette rubrique.

### Configuration d’Intune pour exiger une authentification multifacteur pour l’inscription d’appareils
Pour exiger l’authentification multifacteur lors de l’inscription de périphériques, procédez comme suit :

1. Connectez-vous à votre [portail Microsoft Azure](https://manage.windowsazure.com) à l’aide de vos informations d’identification d’administrateur.
2. Choisissez votre locataire.
2. Sélectionnez l'onglet **Applications**. Vous verrez une liste de services pour lesquels vous pouvez configurer des fonctionnalités de sécurité Azure AD.
3. Choisissez **l’inscription à Microsoft Intune**.
4. Choisissez **Configurer**. 
5. Sous **Authentification multifacteur et règles d’accès basées sur l’emplacement** vous pouvez :
    -  Activation des règles d’accès
    -  Choisir d’appliquer les règles à tous les utilisateurs ou à des groupes de sécurité Azure AD spécifiques.
    -  Exiger l’authentification multifacteur pour l’inscription de tous les appareils.
    -  Exiger l’authentification multifacteur pour l’inscription d’un appareil lorsqu’il n’est pas en fonctionnement.
    -  Choisissez l’option de **blocage de l’accès aux ressources d’entreprise** pour empêcher l’inscription d’un appareil lorsqu’il n’est pas connecté au réseau d’entreprise. 
4. Vous pouvez également cliquer sur le lien pour **définir/modifier l’emplacement de votre réseau professionnel**, pour configurer des exigences de connectivité réseau pour l’inscription d’appareils.

> [!IMPORTANT]
> 
> Ne configurez pas les **règles d’accès basées sur les appareils** pour l’inscription à Microsoft Intune.



<!--HONumber=Sep16_HO4-->


