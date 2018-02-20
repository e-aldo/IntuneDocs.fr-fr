---
title: "Ajout d’écrans État de l’inscription"
titlesuffix: Azure portal
description: "Affichez un message d’accueil aux utilisateurs qui inscrivent des appareils Windows 10."
keywords: 
author: barlan
manager: barlanmsft
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 479f2c1998cd8dfd637f1487a7f4c767b17a5fa7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="set-up-an-enrollment-status-screen"></a>Configurer un Écran de l’état d’inscription

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Quand un utilisateur final inscrit un appareil Windows, il s’attend à pouvoir accéder à tout ce dont il a besoin pour être productif immédiatement après l’inscription. Ce que les utilisateurs finaux ne savent pas, c’est que le contenu, les applications, les stratégies et les paramètres sont toujours en cours de transfert sur leurs appareils une fois l’inscription terminée.

Vous pouvez configurer un Écran de l’état d’inscription pour fournir des informations supplémentaires à vos utilisateurs finaux et les tenir informés de ce qui se produit réellement après le processus d’inscription. Celui-ci se trouve dans **Inscription de l’appareil** > **Inscription Windows** > **Écran de l’état d’inscription**.

![Écran de l’état d’inscription Windows 10](win10-enrollment-status-admin-setup.png)

Vous pouvez définir quatre champs : les **Salutations**, le **Message** et le **Lien hypertexte vers l’aide**, où vous pouvez définir le **Texte du lien** et **l’URL de l’aide aux utilisateurs**.

Les utilisateurs finaux peuvent également voir la progression des éléments **Sécurité**, **Mise en réseau**, **Applications** et **Certificats** qui sont installés.