---
title: "Restaurer des appareils iOS gérés par Intune à partir d’une sauvegarde | Microsoft Intune"
description: "Indiquez aux utilisateurs finaux comment réinscrire leurs appareils après une restauration à partir d’une sauvegarde."
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 612b0954a81de1ee8d4a1e96c7440239437dec14
ms.openlocfilehash: 5fc4423f8fd0c5829be5fe6c96949e126991e430


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



<!--HONumber=Oct16_HO2-->


