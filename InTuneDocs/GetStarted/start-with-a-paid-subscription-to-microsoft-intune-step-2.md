---
title: "Configurer un nom de domaine personnalisé | Microsoft Intune"
description: "Cette rubrique décrit la procédure d’ajout d’un nom de domaine personnalisé à votre abonnement Intune"
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2382f36f-13d8-4a32-81ad-6cfa604889c3
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 1be1e1846281d930fadcf7eadaa6afe77146f0a2


---


# configurer un nom de domaine personnalisé

Par défaut, Intune utilise le nom de domaine **<domain>.onmicrosoft.com** qui a été créé lors de votre première inscription au service. Si votre organisation possède un domaine personnalisé, vous pouvez configurer votre instance d’Intune de sorte qu’elle utilise ce nom de domaine à la place du domaine attribué avec votre abonnement.

Avant de créer de nouveaux comptes d'utilisateur ou de synchroniser des comptes à partir de votre instance Active Directory locale, nous vous recommandons vivement de choisir entre l'utilisation seule du domaine .onmicrosoft.com et l'ajout d'un ou plusieurs de vos domaines personnalisés. Le fait de configurer un domaine personnalisé avant d'ajouter des utilisateurs peut simplifier la gestion des identités des utilisateurs de votre abonnement en permettant aux utilisateurs de se connecter à l'aide des informations d'identification qu'ils utilisent pour accéder aux autres ressources du domaine.

Lorsque vous vous abonnez à un service cloud Microsoft, votre instance de ce service devient un client Microsoft [Azure AD](http://technet.microsoft.com/library/jj573650.aspx#BKMK_WhatIsAnAzureADTenant), qui fournit des services d’identité et d’annuaires à votre service cloud. Et puisque les tâches permettant de configurer Intune pour utiliser le nom de domaine personnalisé de votre organisation sont identiques à celles appliquées aux autres clients Azure AD, vous pouvez utiliser les informations et les procédures du document [Ajouter votre domaine](https://azure.microsoft.com/documentation/articles/active-directory-add-domain/).

> [!TIP]
> Pour plus d’informations sur l’utilisation de votre domaine personnalisé avec un service cloud Microsoft, consultez [Vue d’ensemble conceptuelle des noms de domaine personnalisés dans Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-add-domain-concepts/).

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 2 du *Guide de démarrage rapide Intune*.

>[!div class="step-by-step"]

>[&larr; **Se connecter à Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-1.md)     [**Ajouter des utilisateurs à Intune** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-3.md)  



<!--HONumber=Jul16_HO4-->


