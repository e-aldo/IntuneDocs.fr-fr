---
title: "Personnaliser les affichages de console pour les rôles d’administrateur | Microsoft Intune"
description: "Cette rubrique vous aidera à filtrer l’affichage de la console Intune pour autoriser vos administrateurs à afficher uniquement les éléments correspondant à leur rôle."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 217655d3c33ac88672f0739302f182cf6a6ae335
ms.openlocfilehash: dc9bb2992d3e3ed8134cfa2146295e16edf4e459


---

# Personnaliser les affichages de la console Intune en fonction des rôles d’administrateur
Vous pouvez filtrer l’affichage de la console d’administration Microsoft Intune pour autoriser vos administrateurs à ne voir que les éléments correspondant à leur rôle. Par exemple, vous pouvez autoriser uniquement les opérateurs de la console d’administration à mettre à jour les définitions des programmes malveillants ou à réinitialiser le code secret sur les appareils. Pour cela, vous devez utiliser des **désignations** prédéfinies que vous attribuez à des utilisateurs spécifiques. Quand ces utilisateurs accèdent à la console d’administration, ils ne peuvent voir que les éléments spécifiques à leur fonction.

## Pour créer un affichage personnalisé

1.  Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration** &gt; **Administrateurs de service**.

2.  Dans la liste des administrateurs de service, choisissez l’utilisateur dont vous souhaitez modifier la désignation, puis choisissez **Gérer l’accès**.

3.  Dans la boîte de dialogue **Gérer l'accès** , choisissez le niveau d'accès que vous souhaitez donner à l'utilisateur sélectionné. Vous pouvez choisir :

    -   **Accès complet**
    -   **Accès en lecture seule**
    -   **Support technique – Nœud Groupes**

    L’accès complet et l’accès en lecture seule sont explicites. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

    **Support technique - Nœud Groupes** limite ce que l’administrateur peut voir et faire à ce qui suit :

    -   Afficher les listes d’utilisateurs et d’appareils. L’administrateur ne peut pas utiliser de filtres pour modifier l’affichage. Toutefois, vous pouvez utiliser le filtrage de groupe pour modifier ce que l’administrateur peut voir. Pour plus d’informations, consultez [Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).

    -   Imprimer la liste des utilisateurs et des appareils.

    -   Exporter la liste des utilisateurs et des appareils.

    -   Afficher les propriétés d’un utilisateur ou d’un appareil.

    -   Effectuer les tâches à distance suivantes :

        -   Effectuer une analyse complète des programmes malveillants

        -   Effectuer une analyse rapide des programmes malveillants

        -   Redémarrer un ordinateur

        -   Mettre à jour les définitions de programmes malveillants

        -   Actualiser les stratégies

        -   Actualiser l'inventaire

        -   Verrouiller un appareil à distance

        -   Réinitialiser un code secret

Quand l’administrateur que vous avez configuré ouvre par la suite la console d’administration Intune, il reçoit le niveau d’accès que vous avez désigné.



<!--HONumber=Jul16_HO4-->


