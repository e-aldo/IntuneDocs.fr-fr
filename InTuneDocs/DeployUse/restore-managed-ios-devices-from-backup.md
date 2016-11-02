---
title: "Restaurer des appareils iOS gérés par Intune à partir d’une sauvegarde | Microsoft Intune"
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
translationtype: Human Translation
ms.sourcegitcommit: e6bb539c87c4a13a490ba98c016d814bea5c7bbc
ms.openlocfilehash: 6395e50b3e4c06e7363acc136b5ed9eb2ef75abd


---

# Restaurer des appareils iOS gérés par Intune à partir d’une sauvegarde

Parfois, vos utilisateurs ou vous-même devez restaurer un appareil iOS à partir d’une sauvegarde ; c’est par exemple le cas quand un utilisateur reçoit un nouvel appareil. Cette rubrique explique les étapes supplémentaires que vous pouvez être amené à effectuer pour configurer la gestion Intune après la restauration de l’appareil.

## Restauration de sauvegardes sur le même appareil

Si la sauvegarde est restaurée sur le même appareil, l’état de l’inscription sur l’appareil est également restauré. Aucune action supplémentaire n’est nécessaire.

## Restauration de sauvegardes sur des appareils différents

Si la sauvegarde est restaurée sur un autre appareil, l’état de l’inscription n’y est pas automatiquement restauré. Les utilisateurs doivent suivre les étapes d’inscription standard dans l’application Portail d’entreprise version 2.1.22 ou ultérieure pour [inscrire leur appareil iOS dans Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Si vous ciblez vos utilisateurs finaux avec des stratégies d’accès conditionnel, ils ne pourront accéder à l’e-mail d’entreprise qu’une fois réinscrits.

> [!TIP]
> Voici un exemple de communication pour vos utilisateurs : pour inscrire votre nouvel appareil, vérifiez que la version de l’application Portail d’entreprise est 2.1.22 ou ultérieure. Pour vérifier la version, ouvrez l’application Portail d’entreprise, appuyez sur le bouton Menu en haut à droite, puis appuyez sur À propos. Si vous utilisez une version antérieure, quittez l’application Portail d’entreprise et ouvrez l’App Store. Appuyez sur le bouton Mises à jour en bas à droite, puis appuyez sur le bouton Mettre à jour en regard de l’élément Portail d’entreprise dans la liste. Une fois la mise à jour terminée, lancez l’application Portail d’entreprise et [inscrivez votre appareil iOS dans Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

## Résolution des problèmes connus liés aux restaurations

Les utilisateurs peuvent rencontrer des difficultés s’ils restaurent leur appareil et lancent l’application Portail d’entreprise alors que la version de Portail d’entreprise est 2.1.21 ou une version antérieure. Ces difficultés peuvent être résolues en prenant les mesures appropriées suivant la situation de l’utilisateur.

### Pour les utilisateurs qui utilisent seulement leur nouvel appareil
Lancez l’application Portail d’entreprise et annulez l’inscription en sélectionnant la vignette d’appareil actuelle et en appuyant sur le bouton __Supprimer__. Ensuite, suivez les étapes d’inscription standard pour [inscrire un appareil iOS dans Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

### Pour les utilisateurs qui utilisent leurs appareils anciens et nouveaux
Effacer les cookies de Safari en appuyant sur __Paramètres__ > __Safari__ > __Effacer l’historique et les données de site web__. Ensuite, désinstallez et réinstallez l’application Portail d’entreprise, puis suivez les étapes d’inscription standard pour [inscrire un appareil iOS dans Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO3-->


