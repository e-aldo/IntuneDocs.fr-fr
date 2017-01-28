---
title: "Créer des groupes pour organiser les utilisateurs et les appareils de l’abonnement à la version d’évaluation | Microsoft Docs"
description: "Comment créer des groupes d’appareils et d’utilisateurs quand vous vous inscrivez à un essai gratuit de Microsoft Intune de 30 jours."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89e190e6a3e514c0f38b33409cde2abea0776885
ms.openlocfilehash: 0cdf5bf8f9fad1f44dbb0ef11de71aea55949d89


---

# <a name="create-groups-to-organize-evaluation-subscription-users-and-devices"></a>Créer des groupes pour organiser les utilisateurs et les appareils de l’abonnement à la version d’évaluation

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les groupes créés dans Intune vous permettent de gérer vos utilisateurs et appareils avec une grande souplesse. Vous pouvez configurer des groupes qui répondent aux besoins de votre organisation (par exemple, en fonction de l'emplacement géographique, du service ou de caractéristiques matérielles) et les utiliser pour effectuer diverses tâches d'administration à grande échelle, de la définition de stratégies pour un ensemble d'utilisateurs au déploiement d'applications sur un ensemble d'appareils.

## <a name="create-a-device-group"></a>Créer un groupe d'appareils
Les groupes d'appareils permettent de déployer des logiciels et des mises à jour, et de configurer des stratégies pour les paramètres de l'Agent Microsoft Intune et les paramètres du Pare-feu Windows. Par exemple, vous pouvez configurer un groupe « Appareils de mon évaluation » en procédant comme suit :

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Vue d’ensemble** &gt; **Créer un groupe**.

2.  Dans **Nom de groupe**, tapez « Appareils de mon évaluation » et, dans la liste des groupes parents, sélectionnez **Tous les appareils**, puis cliquez sur **Suivant**.

3.  Dans la page **Définir les critères d'appartenance** , sélectionnez **Tous les appareils** , pour indiquer que le groupe inclut à la fois des appareils mobiles et des ordinateurs.

4.  Dans la page **Définir l’appartenance directe**, cliquez sur **Suivant**. Si vous avez créé un groupe qui n'inclut pas tous les appareils et que vous voulez ajouter des appareils spécifiques à votre nouveau groupe, vous pouvez le faire ici.

5.  Dans la page **Résumé**, passez en revue les actions à entreprendre, puis cliquez sur **Terminer**.

Le groupe récemment créé est disponible dans la liste **Groupes** et dans l'espace de travail **Groupes** , sous **Tous les appareils**. À ce stade, vous pouvez également modifier ou supprimer le groupe.

## <a name="create-a-user-group"></a>Créer un groupe d'utilisateurs
Les groupes d'utilisateurs permettent de déployer des stratégies d'appareils et de logiciels. Par exemple, vous pouvez configurer un groupe « Utilisateurs de mon évaluation » en procédant comme suit :

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), choisissez **Groupes** &gt; **Vue d’ensemble** &gt; **Créer un groupe**.

2.  Dans **Nom de groupe**, tapez « Utilisateurs de mon évaluation » et, dans la liste des groupes parents, sélectionnez **Tous les utilisateurs**, puis cliquez sur **Suivant**.

3.  Dans la page **Définir les critères d'appartenance** , définissez **Commencer l'appartenance au groupe par** avec la valeur **Tous les utilisateurs du groupe parent**.

4.  En regard de l’option **Exclure les membres de ces groupes de sécurité**, cliquez sur **Parcourir** , puis sélectionnez **Administrateur de la société** Cette exclusion vous permet de gérer le groupe Utilisateurs de mon évaluation sans affecter le compte Administrateur de la société (également appelé Administrateur client).

5.  Dans la page **Définir l’appartenance directe**, cliquez sur **Suivant**. Vous n'avez pas besoin de faire quoi que ce soit ici, car vous voulez que le groupe Mes utilisateurs d'évaluation intègre tous les utilisateurs, à l'exception de l'administrateur de la société.

6.  Dans la page **Résumé**, passez en revue les actions à entreprendre, puis cliquez sur **Terminer**.

Le groupe récemment créé est disponible dans la liste **Groupes** et dans l'espace de travail **Groupes** , sous **Tous les utilisateurs**. À ce stade, vous pouvez également modifier ou supprimer le groupe.

Pour en savoir plus sur l’utilisation des groupes, consultez [Créer des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="next-steps"></a>Étapes suivantes
[Créer des stratégies](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  



<!--HONumber=Jan17_HO1-->


