---
title: "Introduction à Intune dans le portail Azure"
titleSuffix: Intune on Azure
description: "Découvrez les bases d’Intune dans le portail Azure et comment celui-ci peut vous aider à gérer vos appareils."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7549f3277c23c3951090502f2babfe7c47b0a201
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Introduction à Microsoft Intune dans le portail Azure


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune se trouve désormais dans le portail Azure, ce qui signifie que les flux de travail et fonctionnalités que vous utilisiez sont maintenant différents.
Le nouveau portail vous offre des fonctionnalités nouvelles et mises à jour dans le portail Azure, où vous pouvez gérer les appareils mobiles, PC et applications de votre entreprise.

> [!IMPORTANT]
> **Vous ne voyez pas encore le nouveau portail ?**<br>
> Les clients existants sont migrés vers la nouvelle expérience. Une notification s’affiche dans le centre de messages Office avant migration de votre client.
>
> Les comptes Intune créés avant janvier 2017 nécessiteront une migration unique pour que les workflows Apple Enrollment soient disponibles dans Azure. Le calendrier de migration n’a pas encore été annoncé. Si votre compte ne peut pas accéder au portail Azure, nous vous recommandons de créer un compte d’évaluation.
>
> Passez en revue la liste des bloqueurs potentiels https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/


Vous trouverez plus d’informations sur le nouveau portail dans cette bibliothèque, qui est continuellement mise à jour. Si vous avez des suggestions, n’hésitez pas à laisser des commentaires dans la section dédiée de la rubrique. Nous sommes à votre écoute.

Points clés de la nouvelle expérience :

- Une console intégrée pour tous vos composants Enterprise Mobility + Security (EMS)
- Une console HTML basée sur les normes web
- Prise en charge de l’API Microsoft Graph pour automatiser de nombreuses actions
- Groupes Azure AD (Active Directory) pour assurer la compatibilité dans toutes vos applications Azure
- Prise en charge des navigateurs web les plus récents

Si vous recherchez une documentation pour la console Intune classique, consultez la [bibliothèque de documentation pour Intune](https://docs.microsoft.com/intune-classic/).

## <a name="before-you-start"></a>Avant de commencer

Pour utiliser Intune dans le portail Azure, vous devez disposer d’un compte d’administration et d’un compte client Intune. [Inscrivez-vous pour obtenir un compte](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) si vous n’en avez pas déjà un.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Navigateurs web pris en charge pour le portail Azure

Le portail Azure s’exécute sur la plupart des PC, Mac et tablettes. Les téléphones mobiles ne sont pas pris en charge.
Actuellement, les navigateurs suivants sont pris en charge :

- Microsoft Edge (dernière version)
- Microsoft Internet Explorer 11
- Safari (dernière version, Mac uniquement)
- Chrome (dernière version)
- Firefox (dernière version)

Pour obtenir les informations les plus récentes sur les navigateurs pris en charge, consultez le [portail Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Que contient cette bibliothèque ?

La documentation reflète la disposition du portail Intune faciliter la recherche des informations dont vous avez besoin.

![Charges de travail sur le portail Azure](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Introduction et prise en main
Cette section contient une [introduction](introduction-intune.md) qui vous explique comment prendre en main Intune.
### <a name="plan-and-design"></a>Planifier et concevoir
Informations pour vous aider à [planifier et concevoir](/intune-classic/plan-design/introduction) votre environnement Intune.
### <a name="device-enrollment"></a>Inscription des appareils
[Apprenez à configurer la gestion de vos appareils par Intune](device-enrollment.md).
### <a name="device-compliance"></a>Conformité de l’appareil
[Définissez un niveau de conformité pour vos appareils, puis créez un rapport sur tous les appareils qui ne sont pas conformes](device-compliance.md).
### <a name="device-configuration"></a>Configuration des appareils
[Apprenez-en davantage sur les profils que vous pouvez utiliser pour configurer les paramètres et fonctionnalités sur les appareils que vous gérez](device-profiles.md).
### <a name="devices"></a>Appareils
[Découvrez les appareils que vous gérez avec un inventaire et des rapports](device-management.md).
### <a name="mobile-apps"></a>Applications mobiles
[Apprenez à publier, gérer, configurer et protéger les applications](app-management.md).
### <a name="conditional-access"></a>Accès conditionnel
[Restreignez l’accès aux services Exchange en fonction des conditions que vous spécifiez](conditional-access.md).
### <a name="on-premises-access"></a>Accès local
[Configurer l’accès à Exchange ActiveSync et Exchange sur site](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Utilisateurs
[Découvrez-en davantage sur les utilisateurs des appareils que vous gérez et triez les ressources en les regroupant en groupes](user-management.md).
### <a name="groups"></a>Groupes
[Découvrez comment vous pouvez utiliser des groupes Active Directory Azure avec Intune](groups-get-started.md)
### <a name="intune-roles"></a>Rôles Intune
[Contrôlez les utilisateurs pouvant effectuer diverses actions Intune, et à qui ces actions s’appliquent](role-based-access-control.md). Vous pouvez utiliser les rôles intégrés, qui couvrent des scénarios courants dans Intune, ou vous pouvez créer vos propres rôles.
### <a name="software-updates"></a>Mises à jour logicielles
[Découvrez comment configurer les mises à jour logicielles pour les appareils Windows 10](windows-update-for-business-configure.md).



## <a name="whats-new"></a>Nouveautés

[Découvrez les nouveautés d’Intune](whats-new.md).
