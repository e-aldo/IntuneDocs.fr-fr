---
# required metadata

title: [Protéger les données et applications métier sur des appareils non inscrits | Microsoft Intune]
description:
keywords:
author: [karthikaraman]
manager: [jeffgilb]
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service:
ms.technology:
ms.assetid: [00219467-a62e-43b6-954b-3084f54c45ba]

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: [joglocke]
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protéger les données et applications métier sur des appareils non inscrits dans Microsoft Intune

Les stratégies de gestion des applications mobiles (GAM) contribuent à protéger vos données d’entreprise en limitant les déplacements des données, tels que les copier-coller, ou en empêchant les utilisateurs d’enregistrer des documents d’entreprise dans un emplacement personnel.   Pour appliquer les stratégies GAM aux applications métier iOS et Android, vous devez tout d’abord encapsuler l’application à l’aide de l’outil de création de package de restrictions d’application Microsoft Intune.  L’encapsulation d’application est le processus visant à appliquer une couche de gestion à une application mobile sans exiger la moindre modification de l’application sous-jacente.  Une fois l’application encapsulée, vous pouvez lui appliquer des stratégies GAM et la distribuer aux utilisateurs finaux.  

Cette rubrique explique les étapes nécessaires pour appliquer des stratégies GAM pour les applications accessibles sur les **appareils personnels des employés qui ne sont pas gérés** et les appareils qui sont gérés par une **solution tierce de gestion des appareils mobiles**.  Pour préparer des applications métier qui s’exécutent sur des **appareils inscrits dans Intune**, consultez [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md).
##  Étape 1: Préparer l’application
Avant de pouvoir appliquer les stratégies GAM à une application, vous devez tout d’abord encapsuler l’application à l’aide de l’outil de création de package de restrictions d’application Microsoft Intune.  Les instructions pour installer et utiliser l’outil de création de package de restrictions d’application sont incluses dans le téléchargement.  
>[!IMPORTANT]  
>Cette version de l’outil de création de package de restrictions d’application, qui prend en charge les appareils non inscrits dans Intune, sera disponible en préversion privée dans les semaines à venir. Si vous souhaitez participer, envoyez un e-mail à msintuneappsdk@microsoft.com pour obtenir plus d’informations.

## Étape 2 : Ajouter l’application

Pour associer votre application métier aux stratégies GAM, vous devez ajouter les détails de l’application à votre abonnement/client Intune en procédant comme suit :

1. Dans le [portail Azure](https://portal.azure.com/), accédez à **Gestion des applications mobiles Intune > Paramètres** et choisissez **Applications métier**.

  ![Capture d’écran du panneau de paramètres avec l’option métier](../media/mam-azure-portal-lob-on-settings.png)

2. Dans le panneau **Applications métier**, choisissez **Ajouter une application personnalisée**.

  ![Capture d’écran du panneau des applications métier avec le bouton Ajouter une application personnalisée en haut](../media/mam-azure-portal-add-lob-app-action.png)
3.  Fournissez un nom pour l’application, l’identificateur de lot dans le champ Identificateur de l’application et la plateforme (iOS ou Android).

  ![Capture d’écran du panneau Ajouter une application personnalisée ](../media/mam-azure-portal-add-app-details.png) Cette étape permet de créer une liste unique de votre application.  L’application est également affichée dans la liste des applications ciblées pour une stratégie GAM pour votre client, telle que décrite à l’étape suivante.

## Étape 3 : Appliquer des stratégies GAM
Une fois que les métadonnées de l’application sont chargées sur le service, l’application s’affiche dans la liste des applications.  Vous pouvez à présent [créer une stratégie ou utiliser une stratégie existante](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) et l’appliquer à l’application métier que vous avez ajoutée à l’étape 2.
  ![Capture d’écran du panneau des applications ciblées avec la nouvelle application métier](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## Étape 4 : Distribuer l’application
Vous pouvez déployer des applications sur vos utilisateurs finaux de diverses manières :
* Pour les appareils inscrits dans une solution tierce de gestion des appareils mobiles, vous pouvez distribuer les applications via votre solution de gestion des appareils mobiles.
* Pour les appareils gérés par aucune solution de gestion des appareils mobiles, vous avez besoin d’une solution personnalisée. Les utilisateurs finaux doivent télécharger et installer l’application sur leur appareil.

## Modification des métadonnées
Si vous devez modifier les détails de l’application, tels que le nom de l’application ou l’identificateur de lot, vous devez [supprimer l’application](#remove-apps) et [l’ajouter](#add-the-app) avec les nouvelles métadonnées.

##  Supprimer des applications
Vous pouvez supprimer une application métier de la liste des applications.  Cela supprime l’application de la liste ainsi que l’association avec les stratégies GAM, mais ne supprime pas et ne désinstalle pas l’application sur l’appareil de l’utilisateur final.  

1.  Dans le [portail Azure](https://portal.azure.com/), accédez à **Gestion des applications mobiles Intune > Paramètres**.  Dans le panneau **Paramètres**, choisissez **Activité commerciale** pour ouvrir la liste des applications existantes.  
2.  Sélectionnez l’application que vous souhaitez supprimer, puis choisissez le menu contextuel **(...)**.

  ![Capture d’écran du panneau des applications métier avec les points de suspension](../media/mam-azure-portal-lob-context-menu.png)
3.  Choisissez **Supprimer l’application** pour supprimer l’application.

  ![Capture d’écran du panneau des applications métier avec l’option de suppression d’application](../media/mam-azure-portal-delete-app.png)

  Cela supprime les applications de la liste des applications métier et de la liste des applications ciblées dans la stratégie GAM.


<!--HONumber=Jun16_HO1-->


