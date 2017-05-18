---
title: "Authentification multifacteur pour l’inscription d’appareils Intune | Microsoft Docs"
description: "Comment exiger une authentification multifacteur dans Azure AD pour l’inscription d’appareils."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 7768013a1cc764b6dfbf4b7d22be4f5cf95f50bf
ms.openlocfilehash: dba070ef76de8015b347e760b424a5e28ce6ddec
ms.lasthandoff: 02/18/2017


---

# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Authentification multifacteur pour les inscriptions d’appareils Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune intègre l’authentification multifacteur (MFA) Azure AD pour l’inscription d’appareils afin de sécuriser vos ressources d’entreprise.

Elle nécessite au moins deux des méthodes de vérification suivantes : 

- Quelque chose que vous connaissez (généralement un mot de passe ou code PIN).
- Quelque chose que vous possédez (un appareil de confiance difficilement copiable, comme un téléphone).
- Quelque chose que vous êtes (biométrie).

L’authentification multifacteur est prise en charge sur les appareils iOS, Android, Windows 8.1 ou version ultérieure, ou Windows Phone 8.1 ou version ultérieure.

> [!NOTE]
> Dans les versions antérieures du Configuration Manager (antérieures à la version 1610), vous verrez toujours le paramètre MFA dans la console d’administration de Configuration Manager. N’essayez pas de configurer l’authentification multifacteur dans la console d’administration de Configuration Manager, car elle ne fonctionnera pas. Configurez l’authentification multifacteur comme décrit dans cette rubrique.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Configurer Intune pour exiger une authentification multifacteur lors de l’inscription des appareils
Pour exiger l’authentification multifacteur à l’inscription d’un appareil, procédez comme suit :

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

