---
title: "Catégoriser les appareils avec le mappage de groupe d’appareils | Microsoft Intune"
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8b8c06a3-6b6c-4cf1-8646-b24fa9b1a39e
ms.reviewer: sumitp
ms.suite: ems
ms.sourcegitcommit: bb30b8e61a768b15e2f09993f4dceae8f4e1bd8a
ms.openlocfilehash: 55f811153bf37048a4fcdfc6da301a5f181700c3


---

# Catégoriser les appareils avec le mappage de groupe d’appareils dans Microsoft Intune
Le **mappage de groupe d’appareils** dans Microsoft Intune vous permet de regrouper des appareils dans des catégories que vous définissez afin d’en faciliter la gestion. 

Le mappage de groupe d’appareils utilise le flux de travail suivant :
1. Vous créez des groupes d’appareils Intune pour chaque catégorie que vous souhaitez utiliser.
2. Vous configurez des règles de mappage de groupe d’appareils qui mappent la catégorie choisie au groupe d’appareils que vous avez créé.
3. Quand des utilisateurs finaux inscrivent leur appareil, ils doivent choisir une catégorie parmi celles que vous avez configurées. Une fois ce choix effectué, leur appareil est ajouté automatiquement au groupe d’appareils correspondant que vous avez créé.
4. Vous pouvez ensuite utiliser ces groupes d’appareils quand vous déployez des stratégies et des applications.

Voici quelques exemples de catégories :
* Personnel
* Appareil de point de vente
* Appareil de démonstration
* Ventes
* Gestion des comptes
* Manager

Vous pouvez cependant configurer n’importe quelle catégorie.

## Comment configurer le mappage de groupe d’appareils
1. Pour chaque catégorie que vous souhaitez utiliser, créez un groupe d’appareils Intune. Pour plus d’informations sur la création de groupes, consultez [Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).
2. Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration**
3. Dans l’espace de travail **Administration**, développez **Gestion des appareils mobiles**, puis choisissez **Mappage de groupe d’appareils**.
4. Dans la page **Mappage de groupe d’appareils**, activez le mappage de groupe d’appareils.
5. Choisissez **Ajouter** pour créer une règle de mappage.
6. Dans la boîte de dialogue **Ajouter une règle de mappage de groupe d’appareils**, entrez le nom de la catégorie que vous souhaitez créer puis, dans la liste déroulante, choisissez le regroupement d’appareils auquel vous souhaitez mapper cette catégorie. Choisissez **Ajouter** quand vous avez terminé.
7. Une fois que vous avez fini d’ajouter des catégories et des groupes, Choisissez **Enregistrer**.

À présent, quand des utilisateurs inscriront leur appareil, une liste des catégories que vous avez configurées leur sera présentée. Une fois qu’ils auront choisi une catégorie et terminé l’inscription, leur appareil sera ajouté au groupe d’appareils correspondant à la catégorie choisie.

### Voir aussi
[Utiliser des groupes pour gérer les utilisateurs et les appareils avec Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)


<!--HONumber=Jun16_HO3-->


