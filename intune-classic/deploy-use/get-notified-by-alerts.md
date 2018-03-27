---
title: Recevoir des alertes | Microsoft Docs
description: Découvrez comment les alertes vous tiennent informé de ce qu’il se passe dans Microsoft Intune.
keywords: ''
author: nathbarn
ms.author: dougeby
manager: dougeby
ms.date: 8/31/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 396ea714 0433 4bd5 a934 8d0b477f28e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune classic
ms.openlocfilehash: daa936b43c53d14d57f2c48f80dff7e908354054
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
#  <a name="use-alerts-to-get-notified-by-microsoft-intune"></a>Utiliser des alertes pour être informé par Microsoft Intune

[!INCLUDE[classic portal](../includes/classic-portal.md)]

Les alertes vous tiennent informé de ce qu’il se passe dans Microsoft Intune. Par exemple, les alertes peuvent vous informer des événements suivants :
- Problème au niveau du connecteur Exchange affectant la gestion des appareils mobiles
- Détection d’un programme malveillant sur un ordinateur
- Détection d’un conflit entre deux stratégies Intune
- Échec du déploiement d’un client logiciel Intune

## <a name="how-alerts-work"></a>Fonctionnement des alertes

Les alertes générées varient en fonction des **types d’alerte**, c’est-à-dire d’un ensemble de règles préconfigurées intégrées à Intune. Par exemple, le type d’alerte **Le stockage cloud dispose de 10 % ou moins d’espace libre** vous avertit qu’il vous manque de l’espace pour stocker vos applications dans le cloud. Vous pouvez activer ou désactiver des types d’alertes, et configurer des propriétés pour chaque type d’alerte. Par exemple, pour le type d'alerte évoqué ci-dessus, vous pouvez configurer les éléments suivants :

- **État :** indique si ce type d'alerte est activé ou désactivé.
- **Gravité :** indique la sévérité de l'alerte.

|Niveau de gravité|Détails|
|--|---|
|**Alerte critique**|Indique l’existence d’un problème sérieux que vous devez examiner au plus vite. Il peut s’agir par exemple de la détection d’un programme malveillant sur un ordinateur.|
|**Alerte d’avertissement**|Indique la présence d’un problème qui n’est pas sérieux pour le moment, mais qui pourrait le devenir si vous n’y prêtez pas attention. Il peut s’agir par exemple de mises à jour de sécurité en attente d’installation.|
|**Alerte d’information**|Indique des informations non essentielles à vos activités comme, par exemple, la mise à disposition d'une nouvelle version du connecteur Exchange.|

D’autres types d’alertes peuvent avoir d’autres éléments configurables, par exemple le pourcentage d’appareils devant être affectés par un problème avant qu’une alerte soit générée.

**Quand les critères d’un type d’alerte sont remplis, une alerte est générée et affichée dans la console d’administration Intune.**

Par ailleurs, vous pouvez configurer Intune de façon à être averti par courrier électronique quand une alerte est générée.

## <a name="set-up-alerts"></a>Configurer des alertes

Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Administration** &gt; **Alertes et notifications**, puis choisissez l’une des tâches suivantes :

|Tâche|Description|
|---|------|
|**Types d’alerte**|Choisissez le type d’alerte que vous voulez configurer, puis procédez de l’une des façons suivantes :<br /><br />Choisissez **Configurer**. Dans la boîte de dialogue **Configurer le type d’alerte**, configurez les paramètres de votre choix, puis choisissez **OK**.<br /><br />**Activez** ou **désactivez** l’alerte.<br /><br />Développez le nœud **Types d’alerte** et choisissez une catégorie pour afficher uniquement les types d’alertes de cette catégorie.|
|**Destinataires**|Choisissez **Ajouter** pour ajouter une nouvelle adresse e-mail destinée à recevoir les notifications par e-mail que vous configurez.<br /><br />Vous pouvez aussi **modifier** ou **supprimer** des destinataires existants.<br /><br />Pour recevoir des notifications, vous devez aussi ajouter cette adresse e-mail comme destinataire sous **Règles de notification**.|
|**Règles de notification**|Permet de configurer des règles qui définissent le ou les destinataires d'une alerte par courrier électronique. Voici les possibilités qui s'offrent à vous :<br /><br />**Choisir une règle existante**   Choisissez une règle, puis choisissez **Sélectionner les destinataires**. Vous pouvez ensuite sélectionner tous les destinataires appelés à recevoir un message électronique dès qu'une alerte conforme à cette règle est générée.<br /><br />**Créer une règle**   Entrez un nom pour la règle, sélectionnez les catégories d’alerte et la gravité d’alerte qui s’appliquent aux règles, sélectionnez les groupes d’appareils auxquels la règle s’applique et sélectionnez les utilisateurs qui reçoivent un e-mail quand une alerte est générée.<br /><br />Vous pouvez aussi **activer**, **désactiver**, **modifier**ou **supprimer** une règle existante.|

## <a name="working-with-alerts"></a>Utilisation d'alertes

Pour afficher les alertes dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), choisissez **Alertes**, puis le type d’alerte à afficher.

Utilisez les options suivantes pour gérer les alertes à partir de la console d'administration Intune.

|Option|Description|
|-----|----|
|**Afficher les alertes actives**|Choisissez parmi :<br /><br />**Afficher une synthèse des alertes**   Dans l’espace de travail **Tableau de bord**, les principales erreurs sont affichées dans le volet Alertes. Choisissez le volet pour afficher des informations plus détaillées.<br /><br />Par ailleurs, vous pouvez afficher une synthèse des alertes dans la page **Vue d'ensemble** de l'espace de travail **Alertes** .<br /><br />**Afficher toutes les alertes**   Dans l’espace de travail **Alertes**, choisissez **Toutes les alertes**.|
|**Consulter les remarques**|Choisissez parmi :<br /><br />Dans l’espace de travail **Tableau de bord**, choisissez **Remarques**.<br /><br />Dans l’espace de travail **Alertes**, choisissez **Toutes les alertes** &gt; **Remarques**.|
|**Fermer une alerte**|Dans la liste des alertes, sélectionnez l’alerte à fermer, puis choisissez **Fermer l’alerte**.<br /><br />Les alertes fermées sont définitivement supprimées au bout de 90 jours.|
|**Réactiver une alerte fermée**|Dans la liste des alertes, définissez le menu déroulant **Filtres** sur **Fermé**.<br /><br />Dans la liste des alertes fermées, sélectionnez l’alerte que vous souhaitez réactiver, puis choisissez **Réactiver l’alerte**.|

Les alertes Intune restent actives pendant 30 jours ou tant que :

- Le problème à l’origine de l’alerte n’a pas été résolu.
- L'alerte est fermée manuellement.

Les alertes fermées peuvent être réactivées pendant 30 jours après la fermeture. Après 30 jours, les alertes fermées et inactives sont supprimées d’Intune.

> [!TIP]
> Si une même alerte est générée par des appareils qui exécutent des systèmes d'exploitation différents, vous risquez de voir apparaître plusieurs versions de la même alerte dans la liste des alertes.
