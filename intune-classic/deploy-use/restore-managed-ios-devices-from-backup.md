---
title: "Restaurer des appareils iOS gérés par Intune à partir d’une sauvegarde"
description: "Indiquez aux utilisateurs finaux comment réinscrire leurs appareils après une restauration à partir d’une sauvegarde."
keywords: "restauration, géré, iOS"
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7fc99a944000a8d5ecfc09ebc2e956e7c0f201c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="restore-intune-managed-ios-devices-from-backup"></a>Restaurer des appareils iOS gérés par Intune à partir d’une sauvegarde

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Parfois, vos utilisateurs ou vous-même devez restaurer un appareil iOS à partir d’une sauvegarde ; c’est par exemple le cas quand un utilisateur reçoit un nouvel appareil. Cette rubrique explique les étapes supplémentaires que vous pouvez être amené à effectuer pour configurer la gestion Intune après la restauration de l’appareil.

## <a name="restoring-backups-onto-the-same-device"></a>Restauration de sauvegardes sur le même appareil

Si la sauvegarde est restaurée sur le même appareil, l’état de l’inscription sur l’appareil est également restauré. Aucune action supplémentaire n’est nécessaire.

## <a name="restoring-backups-onto-different-devices"></a>Restauration de sauvegardes sur des appareils différents

Si la sauvegarde est restaurée sur un autre appareil, l’état de l’inscription n’y est pas automatiquement restauré. Les utilisateurs doivent suivre les étapes d’inscription standard dans l’application Portail d’entreprise version 2.1.22 ou ultérieure pour [inscrire leur appareil iOS dans Intune](/intune-user-help/enroll-your-device-in-intune-ios).

> [!NOTE]
> Si vous ciblez vos utilisateurs finaux avec des stratégies d’accès conditionnel, ils ne pourront accéder à l’e-mail d’entreprise qu’une fois réinscrits.

> [!TIP]
> Voici un exemple de communication pour vos utilisateurs : pour inscrire votre nouvel appareil, vérifiez que la version de l’application Portail d’entreprise est 2.1.22 ou ultérieure. Pour vérifier la version, ouvrez l’application Portail d’entreprise, appuyez sur le bouton Menu en haut à droite, puis appuyez sur À propos. Si vous utilisez une version antérieure, quittez l’application Portail d’entreprise et ouvrez l’App Store. Appuyez sur le bouton Mises à jour en bas à droite, puis appuyez sur le bouton Mettre à jour en regard de l’élément Portail d’entreprise dans la liste. Une fois la mise à jour terminée, lancez l’application Portail d’entreprise et [inscrivez votre appareil iOS dans Intune](/intune-user-help/enroll-your-device-in-intune-ios).

## <a name="resolving-known-issues-with-restores"></a>Résolution des problèmes connus liés aux restaurations

Les utilisateurs peuvent rencontrer des difficultés s’ils restaurent leur appareil et lancent l’application Portail d’entreprise alors que la version de Portail d’entreprise est 2.1.21 ou une version antérieure. Ces difficultés peuvent être résolues en prenant les mesures appropriées suivant la situation de l’utilisateur.

### <a name="for-users-who-will-only-use-their-new-device"></a>Pour les utilisateurs qui utilisent seulement leur nouvel appareil
Lancez l’application Portail d’entreprise et annulez l’inscription en sélectionnant la vignette d’appareil actuelle et en appuyant sur le bouton __Supprimer__. Ensuite, suivez les étapes d’inscription standard pour [inscrire un appareil iOS dans Intune](/intune-user-help/enroll-your-device-in-intune-ios).

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a>Pour les utilisateurs qui utilisent leurs appareils anciens et nouveaux
Effacer les cookies de Safari en appuyant sur __Paramètres__ > __Safari__ > __Effacer l’historique et les données de site web__. Ensuite, désinstallez et réinstallez l’application Portail d’entreprise, puis suivez les étapes d’inscription standard pour [inscrire un appareil iOS dans Intune](/intune-user-help/enroll-your-device-in-intune-ios).
