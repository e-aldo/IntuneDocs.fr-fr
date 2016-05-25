---
# required metadata

title: Créer des groupes pour organiser les utilisateurs et les appareils de l’abonnement à la version d’évaluation | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Créer des groupes pour organiser les utilisateurs et les appareils de l’abonnement à la version d’évaluation
Les groupes dans Intune vous permettent de gérer les utilisateurs et appareils avec une grande souplesse. Vous pouvez configurer des groupes qui répondent aux besoins de votre organisation (par exemple, en fonction de l'emplacement géographique, du service ou de caractéristiques matérielles) et les utiliser pour effectuer diverses tâches d'administration à grande échelle, de la définition de stratégies pour un ensemble d'utilisateurs au déploiement d'applications sur un ensemble d'appareils.

## Créer un groupe d'appareils
Les groupes d'appareils permettent de déployer des logiciels et des mises à jour, et de configurer des stratégies pour les paramètres de l'Agent Microsoft Intune et les paramètres du Pare-feu Windows. Par exemple, vous pouvez configurer un groupe « Appareils de mon évaluation » en procédant comme suit :

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Groupes** &gt; **Vue d’ensemble** &gt; **Créer un groupe**.

2.  Dans **Nom de groupe**, tapez « Appareils de mon évaluation » et, dans la liste des groupes parents, sélectionnez **Tous les appareils**, puis cliquez sur **Suivant**.

3.  Dans la page **Définir les critères d'appartenance** , sélectionnez **Tous les appareils** , pour indiquer que le groupe inclut à la fois des appareils mobiles et des ordinateurs.

4.  Dans la page **Définir l’appartenance directe**, cliquez sur **Suivant**. Si vous avez créé un groupe qui n'inclut pas tous les appareils et que vous voulez ajouter des appareils spécifiques à votre nouveau groupe, vous pouvez le faire ici.

5.  Dans la page **Résumé**, passez en revue les actions à entreprendre, puis cliquez sur **Terminer**.

Le groupe récemment créé est disponible dans la liste **Groupes** et dans l'espace de travail **Groupes** , sous **Tous les appareils**. À ce stade, vous pouvez également modifier ou supprimer le groupe.

## Créer un groupe d'utilisateurs
Les groupes d'utilisateurs permettent de déployer des stratégies d'appareils et de logiciels. Par exemple, vous pouvez configurer un groupe « Utilisateurs de mon évaluation » en procédant comme suit :

1.  Dans la [console d’administration Intune](https://manage.microsoft.com/), cliquez sur **Groupes** &gt; **Vue d’ensemble** &gt; **Créer un groupe**.

2.  Dans **Nom de groupe**, tapez « Utilisateurs de mon évaluation » et, dans la liste des groupes parents, sélectionnez **Tous les utilisateurs**, puis cliquez sur **Suivant**.

3.  Dans la page **Définir les critères d’appartenance**, définissez **Commencer l’appartenance au groupe par** avec la valeur **Tous les utilisateurs du groupe parent**.

4.  En regard de l’option **Exclure les membres de ces groupes de sécurité**, cliquez sur **Parcourir** , puis sélectionnez **Administrateur de la société** Cette exclusion vous permet de gérer le groupe Utilisateurs de mon évaluation sans affecter le compte Administrateur de la société (également appelé Administrateur client).

5.  Dans la page **Définir l’appartenance directe**, cliquez sur **Suivant**. Vous n'avez pas besoin de faire quoi que ce soit ici, car vous voulez que le groupe Mes utilisateurs d'évaluation intègre tous les utilisateurs, à l'exception de l'administrateur de la société.

6.  Dans la page **Résumé**, passez en revue les actions à entreprendre, puis cliquez sur **Terminer**.

Le groupe récemment créé est disponible dans la liste **Groupes** et dans l'espace de travail **Groupes** , sous **Tous les utilisateurs**. À ce stade, vous pouvez également modifier ou supprimer le groupe.

Pour en savoir plus sur l’utilisation des groupes, consultez [Utiliser des groupes pour gérer les utilisateurs et les appareils](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

### Étapes suivantes
Félicitations ! Vous venez d’effectuer l’étape 3 de la procédure pas à pas de la *version d’évaluation de Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Ajouter des utilisateurs**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md)     [**Créer des stratégies** &larr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  


<!--HONumber=May16_HO1-->


