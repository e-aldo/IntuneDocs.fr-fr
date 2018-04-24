---
title: Protéger les applications et les données
description: Cette rubrique décrit diverses fonctionnalités Intune qui sont disponibles pour vous aider à protéger vos données et applications d’entreprise.
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5c46e188-87eb-4ce2-b184-24809e8bf783
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2a05444c757b8e99ca0b897acfcd6238d960aeb2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="protect-apps-and-data-with-microsoft-intune"></a>Protéger les données et les applications avec Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune protège les données d’entreprise à travers plusieurs couches de technologie. Dans la couche d’identité, un accès conditionnel protège l’accès aux services en autorisant uniquement l’accès à partir d’appareils conformes et gérés. Dans la couche d’application cliente, la gestion des applications mobiles assure une protection contre la perte de données en empêchant le déplacement de données vers des applications ou des emplacements de stockage non protégés et en effaçant les données quand un appareil est perdu ou volé. Nous vous conseillons d’utiliser ces deux couches de protection ensemble afin de sécuriser les données tout en préservant la productivité de votre personnel mobile.

Une première étape importante pour la protection des données d’entreprise consiste à implémenter l’accès conditionnel. Pour cela, vérifiez que les appareils qui sont utilisés pour accéder à ces données utilisent des protections de sécurité, telles que des mots de passe forts et un chiffrement, et qu’ils ne sont pas jailbreakés. Intune vous permet de définir les conditions auxquelles les appareils doivent se conformer pour être autorisés à accéder à la messagerie et aux données de l’entreprise.

L’[accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) est déterminé par deux types de stratégies que vous pouvez définir dans Intune :
- Vous utilisez des [stratégies de conformité](introduction-to-device-compliance-policies-in-microsoft-intune.md) pour déterminer la conformité d’un appareil. Elles évaluent les paramètres et les conditions telles que :
  - Codes confidentiels et mots de passe : vous pouvez créer des règles exigeant des mots de passe pour déverrouiller un appareil, pour les exigences de complexité du mot de passe et pour d’autres paramètres associés.
  - Chiffrement : vous pouvez restreindre l’accès aux appareils chiffrés.
  - Quand un appareil n’est pas jailbreaké ni rooté : Intune peut déterminer si un appareil inscrit est jailbreaké. Vous pouvez définir la stratégie pour bloquer l’accès à ces appareils.
- Vous configurez les [stratégies d’accès conditionnel](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) pour un service particulier comme Exchange Online ou SharePoint Online. Pour chaque service, vous pouvez définir les groupes d’utilisateurs auxquels ces stratégies doivent s’appliquer. Par exemple, vous pouvez faire en sorte que tous les employés du service financier ne puissent accéder à la messagerie professionnelle qu’à partir d’appareil inscrits et conformes.

La sécurisation de l’accès aux ressources de l’entreprise n’est que la première étape de protection des données de l’entreprise. Vous devez toujours être en mesure de protéger les données une fois qu’elles ont fait l’objet d’un accès sur l’appareil. Les données peuvent être copiées, déplacées, enregistrées dans un emplacement différent ou partagées. Intune résout ce problème en vous offrant la possibilité de limiter le déplacement des données grâce à un ensemble de règles du type :
- Blocage des opérations de copier et coller, ou interdiction du transfert de données en dehors du contexte professionnel.
- Interdiction de sauvegarde sur un stockage du cloud personnel et interdiction de l’action Enregistrer sous.
- Sécurisation de l’accès aux applications en demandant un code confidentiel/code secret ou des informations d’identification d’entreprise.
- Ouverture de tous les liens web dans Intune Managed Browser.

Ces règles sont appelées [stratégies de gestion des applications mobiles](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md). Vous pouvez appliquer des stratégies de gestion des applications mobiles aux applications qui sont exécutées sur des appareils qui peuvent être ou non gérés par vous.  

Vous pouvez protéger vos données d’entreprise à l’aide de stratégies de gestion des applications mobiles sur les appareils **inscrits dans Intune**, **inscrits et gérés par une autre solution de gestion des appareils mobiles tierce** ou **non inscrits dans une solution de gestion des appareils mobiles**, par exemple les appareils des employés.

Pour associer une application à une stratégie de gestion des applications mobiles, l’application doit intégrer le Kit SDK d’application Microsoft Intune, ou vous pouvez utiliser l’outil de création de package de restrictions d’application.

Certaines applications, par exemple les applications Microsoft Office, intègrent le SDK d’application Intune. Vous pouvez afficher la liste complète des applications prises en charge dans la [Galerie d’applications mobiles Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) dans la page des partenaires de l’application Microsoft Intune. Sélectionnez l’application pour afficher les plateformes et scénarios pris en charge, et pour savoir si elle prend en charge plusieurs identités.

Vous pouvez également [activer les applications métier intégrées personnalisées](/intune/apps-prepare-mobile-application-management) à utiliser avec les stratégies de gestion des applications mobiles.

En plus de restreindre le déplacement des données, si un appareil est perdu ou volé ou que l’utilisateur ne travaille plus avec votre entreprise, vous pouvez [effacer de façon sélective des données d’entreprise](wipe-managed-company-app-data-with-microsoft-intune.md) et laisser uniquement les données personnelles.
