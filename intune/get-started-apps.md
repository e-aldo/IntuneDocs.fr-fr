---
title: "Bien démarrer avec les applications dans Microsoft Intune"
titlesuffix: 
description: "Recherchez et ajoutez des applications sur les appareils pour permettre à votre personnel d’effectuer leur travail."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 3/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0185eebbe436da73e1920d7cd834f0897a143894
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2018
---
# <a name="get-started-with-adding-apps-in-microsoft-intune"></a>Bien démarrer avec l’ajout d’applications dans Microsoft Intune

Pour pouvoir affecter, surveiller, configurer ou protéger des applications, vous devez les ajouter à Intune. Intune prend en charge plusieurs types d’applications. Les options disponibles varient selon le type d’application.

Intune vous permet d’ajouter et d’affecter ces types d’applications à vos appareils d’entreprise :
- **Applications du Store** : pour les appareils où vous devez appliquer une gestion des applications mobiles supplémentaire à des applications disponibles dans l’App Store.
- **Applications écrites en interne (métiers)** : quand vous chargez un fichier qui est téléchargé sur les appareils de vos utilisateurs.
- **Applications intégrées** : quand vous affectez des applications gérées organisées, comme les applications Office 365, à des appareils iOS et Android. 
- **Applications sur le web** : quand Intune crée un raccourci vers l’application web sur l’écran d’accueil de l’appareil.

## <a name="how-do-i-assign-a-public-store-app"></a>Comment attribuer une application de magasin public ?

L’exemple suivant vous guide tout au long de la procédure d’ajout d’une application iOS dans Microsoft Intune.

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. Choisissez **Tous les services** > **Intune**. Intune se trouve dans la section **Surveillance + Gestion**.
3. Dans le panneau **Intune**, choisissez **Applications mobiles**.
4. Dans la charge de travail **Applications mobiles**, choisissez **Applications** sous la section **Gérer**.
5. Choisissez **Ajouter** à droite du volet **Applications**.
6. Dans la liste **Type d’application**, sélectionnez **iOS** sous les types **Application de Store** disponibles.
6. Choisissez **Rechercher dans l’App Store**.
7. Dans le panneau **Rechercher dans l’App Store**, commencez par sélectionner les paramètres régionaux du pays de l’App Store.
8. Dans la zone de recherche, tapez le nom (ou une partie du nom). Intune recherche le Store et retourne la liste des résultats pertinents.
9. Dans la liste, sélectionnez l’application souhaitée, puis cliquez sur **Sélectionner**.
10. Sélectionnez **Informations sur l’application** pour configurer les informations sur l’application.
11. (Facultatif) Ajoutez des détails pour vous aider à organiser cette application, comme **Propriétaire**, **Remarques**, **Développeur** et une **URL de confidentialité** (pointant vers la politique de confidentialité de votre entreprise).
12. Sélectionnez **Oui** pour **Proposer cette application dans le portail d’entreprise**. 
13. Cliquez sur **OK** après avoir ajouté toutes les informations nécessaires sur l’application.
14. Cliquez sur **ajouter** dans le panneau **Ajouter une application**. Vous passerez alors à la **Vue d’ensemble** de l’application. 

## <a name="next-steps"></a>Étapes suivantes

Après avoir ajouté une application à Intune, vous pouvez affecter les groupes d’employés qui pourront inclure l’application sur leur appareil.

- [Guide pratique pour affecter des applications à des groupes](apps-deploy.md)
- 
## <a name="learn-more"></a>En savoir plus

* [Qu’est-ce que la gestion des applications avec Intune ?](app-management.md)
* [Vue d’ensemble du cycle de vie des applications](app-lifecycle.md)
* [Que sont les stratégies de protection des applications ?](app-protection-policy.md)
