---
title: "Paramètres de restriction d’appareil Intune pour macOS"
titleSuffix: Intune Azure preview
description: "Préversion Intune Azure : Découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: e6b308547331e20a8373aca56f9a0781dcd210a2
ms.lasthandoff: 02/18/2017


---

# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Mac OS dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="password"></a>Mot de passe
-     **Mot de passe requis** - Oblige l’utilisateur final à saisir un mot de passe pour accéder à l’appareil.
    -     **Type de mot de passe requis** - Indique si le mot de passe peut être uniquement de nature numérique ou s’il doit être alphanumérique (c’est-à-dire, contenir des lettres et des chiffres). Ce paramètre est uniquement pris en charge sur les systèmes Mac OS X 10.10.3 et les versions ultérieures.
    -     **Nombre de caractères non alphanumériques dans le mot de passe** : spécifie le nombre de caractères complexes requis dans le mot de passe (**0** à **4**).<br>Un caractère complexe est un symbole, tel que **?**.
    -     **Longueur minimale du mot de passe** - Entrez la longueur minimale du mot de passe qu’un utilisateur doit configurer (entre **4** et **16** caractères).
    -     **Mots de passe simples** - Permet d’utiliser des mots de passe simples, tels que **0000** ou **1234**.
    -     **Nombre maximal de minutes entre le verrouillage de l'écran et la demande du mot de passe** - Indique la durée pendant laquelle l’ordinateur doit être inactif avant qu’un mot de passe soit requis pour le déverrouiller.
    -     **Nombre de minutes d'inactivité avant le verrouillage de l'appareil** - Indique la durée pendant laquelle l’ordinateur doit être inactif avant le verrouillage de l’écran.
    -     **Expiration du mot de passe (jours)** - Spécifie le nombre de jours qui s’écoule avant que l’utilisateur ne doive changer le mot de passe (entre **1** et **255** jours).
    -     **Empêcher la réutilisation des mots de passe précédents** - Spécifie le nombre de mots de passe précédents qui ne peuvent pas être réutilisés (**1** à **24**).

## <a name="restricted-apps"></a>Applications restreintes

Dans la liste des applications restreintes, vous pouvez configurer une des listes suivantes :

Une liste **Applications interdites** : répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.
Une liste **Applications approuvées** : répertorie les applications que les utilisateurs sont autorisés à installer. Pour rester conformes, les utilisateurs ne doivent pas installer d’applications qui ne sont pas répertoriées. Les applications qui sont gérées par Intune sont autorisées automatiquement.

Pour configurer la liste, cliquez sur **Ajouter**, puis spécifiez un nom de votre choix, éventuellement l'éditeur de l'application et l’ID d’ensemble de l'application (par exemple *com.apple.calculator*).



