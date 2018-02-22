---
title: "Inclure et exclure des affectations d’applications"
titlesuffix: Microsoft Intune
description: "Découvrez comment utiliser Intune pour inclure et exclure des affectations d’applications."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Inclure et exclure des affectations d’applications dans Microsoft Intune

Intune vous permet de déterminer qui a accès à une application en affectant des groupes à inclure et à exclure. Vous incluez et excluez des affectations d’applications à un groupe d’utilisateurs ou d’appareils à l’aide d’une combinaison d’affectations de groupe d’inclusion et d’exclusion. Après avoir sélectionné une application, vous pouvez choisir comment l’application est attribuée. Cette fonctionnalité est utile quand vous rendez l’application disponible en incluant un grand groupe, puis que vous affinez les utilisateurs sélectionnés en excluant un groupe plus petit. Le groupe plus petit peut être un groupe de test ou un groupe exécutif. 

Quand vous excluez des groupes d’une affectation, vous devez exclure uniquement des groupes d’utilisateurs ou d’appareils, mais pas un mélange des deux groupes. Intune ne prend pas en compte l’association entre utilisateurs et appareils quand vous excluez des groupes. L’inclusion de groupes d’utilisateurs tout en excluant des groupes d’appareils ne peut pas aboutir aux résultats voulus, car l’inclusion est prioritaire sur l’exclusion. Par exemple, si vous ciblez une application iOS sur **Tous les utilisateurs** et excluez **Tous les iPad**, le résultat net est que tous les utilisateurs utilisant un iPad peuvent obtenir l’application. Si, toutefois, vous ciblez l’application iOS sur **Tous les appareils** et excluez **Tous les iPad**, le déploiement est réussi.  

>[!NOTE]
>Quand vous définissez une affectation de groupe pour une application, le type **Non applicable** est déprécié et remplacé par la fonctionnalité d’exclusion de groupe. 
>
>Intune fournit des groupes **Tous les utilisateurs** et **Tous les appareils** précréés dans la console avec des optimisations intégrées pour votre commodité. Nous vous recommandons vivement d’utiliser ces groupes pour cibler tous les utilisateurs et tous les appareils au lieu de créer vous-même des groupes « Tous les utilisateurs » ou « Tous les appareils ».  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Inclusion et exclusion de groupes pendant l’affectation d’applications 
Pour attribuer une application à des groupes à l’aide de l’affectation d’inclusion et d’exclusion :
1. Dans le panneau Microsoft Intune, sélectionnez **Applications mobiles**.
2. Dans le panneau **Applications mobiles**, sélectionnez **Applications**. La liste des applications ajoutées s’affiche.
3. Sélectionnez l’application que vous voulez attribuer. Un tableau de bord lié à l’application s’affiche. 
4. Sélectionnez **Affectations** sous la section **Gérer**. 

    ![Affectations d’applications Intune](./media/apps-inc-exl-01.png)
5. Sélectionnez **Ajouter un groupe** pour ajouter les groupes d’utilisateurs affectés à l’application. 
6. Sélectionnez un **Type d’affectation** parmi les types d’affectation disponibles dans le panneau **Ajouter un groupe**.
7. Sélectionnez **Disponible avec ou sans inscription** comme type d’affectation.

    ![Affectations d’applications Intune - Ajouter un groupe](./media/apps-inc-exl-02.png)
8. Sélectionnez **Groupes inclus** pour sélectionner le groupe d’utilisateurs qui peut accéder à cette application.

    >[!NOTE]
    >Quand vous ajoutez un groupe, si un autre groupe a déjà été inclus pour un type d’affectation donnée, il est présélectionné et ne peut pas être affecté à un autre type d’affectation d’inclusion. Par conséquent, ce groupe déjà utilisé ne peut pas être sélectionné comme groupe à inclure.

9. Sélectionnez **Oui** pour rendre cette application disponible pour tous les utilisateurs.

    ![Affectations d’applications Intune - Inclure des groupes](./media/apps-inc-exl-03.png)
10. Cliquez sur **OK** pour définir le groupe à inclure.
11. Sélectionnez **Groupes exclus** pour sélectionner les groupes d’utilisateurs ne pouvant pas accéder à cette application. 
12. Sélectionnez les groupes à exclure, ce qui rend cette application indisponible.

    ![Affectations d’applications Intune - Exclure des groupes](./media/apps-inc-exl-04.png)
13. Cliquez sur **Sélectionner** pour effectuer votre sélection de groupes.
14. Cliquez sur **OK** dans le panneau **Ajouter un groupe**. La liste **Affectations** de l’application s’affiche.
15. Cliquez sur **Enregistrer** pour activer les affectations de groupes pour l’application.

Quand vous créez des affectations de groupes, les groupes qui ont été déjà affectés ou sélectionnés sont désactivés. Si vous voulez sélectionner un groupe qui est actuellement désactivé, supprimez-le de la liste d’affectations de l’application. Vous pouvez modifier les affectations de la liste **Affectations** de l’application en sélectionnant la ligne contenant l’affectation spécifique à changer. Par ailleurs, vous pouvez supprimer une affectation en cliquant sur les points de suspension (...) à la fin d’une ligne et en sélectionnant **Supprimer**. Vous pouvez aussi changer la vue de la liste **Affectations** en choisissant de regrouper par **Type d’affectation** ou par **Inclus/exclus**.

![Affectations d’applications Intune - Terminer](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Étapes suivantes

* Pour plus d’informations sur l’inclusion et l’exclusion d’affectations de groupes pour les applications, consultez le [Blog Microsoft Intune](https://aka.ms/new_app_assignment_process).
