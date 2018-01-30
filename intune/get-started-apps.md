---
title: "Bien démarrer avec les applications"
titlesuffix: Azure portal
description: "Recherchez et ajoutez des applications sur les appareils pour permettre à vos employés d’effectuer leur travail."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c1838f1d856efdebb7e2114cb61dd8d88ca100f7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-adding-apps"></a>Bien démarrer avec l’ajout d’applications

Intune prend en charge différentes manières de déployer des applications sur vos appareils d’entreprise :

* **Programmes d’installation du logiciel** : quand vous chargez un fichier qui est téléchargé sur les appareils de vos utilisateurs
* __Liens externes__ : quand vous avez une application dans un App Store public ou une application web
* **Applications gérées** : pour les appareils iOS où vous devez appliquer une gestion des applications mobiles supplémentaire à des applications disponibles dans l’App Store

Vous allez suivre l’une des méthodes de déploiement d’application les plus rapides en affectant une application de Store public.

## <a name="how-do-i-assign-a-public-store-app"></a>Comment attribuer une application de magasin public ?

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. À l’aide de **Rechercher des ressources**, recherchez **Intune**.
3. Sélectionnez **Applications mobiles**, puis **Applications**.
4. Sélectionnez **Ajouter**, puis sélectionnez **iOS** comme **Type d’application** sous **Application du Windows Store**.
5. Choisissez **Sélectionner une application** pour afficher le panneau **Rechercher dans l’App Store**.
6. Dans la zone de texte, recherchez une application à affecter à l’appareil. Choisissez l’application, puis cliquez sur **Sélectionner**.
7. Dans le panneau **Ajouter une application**, sélectionnez **Informations sur l’application**, puis vérifiez que toutes les informations sur l’application sont renseignées. Vous pouvez ajouter d’autres détails facultatifs pour vous aider à organiser cette application, comme **Propriétaire**, **Remarques**, **Développeur** et une **URL de confidentialité** pour la politique de confidentialité de votre entreprise.
8. Vérifiez que vous avez sélectionné **Oui** pour **Proposer cette application dans le portail d’entreprise**, puis sélectionnez **OK**.
9. Sélectionnez **Ajouter** dans le panneau **Ajouter une application** pour ajouter l’application. Vous accédez alors à la **Vue d’ensemble** de cette application. Choisissez **Affectations**, puis cliquez sur **Sélectionner des groupes** pour l’affecter à votre groupe de test. Rendez l’application **Disponible** pour le téléchargement. L’application doit alors apparaître comme **Application proposée** sur votre appareil de test.

## <a name="learn-more"></a>En savoir plus

* [Qu’est-ce que la gestion des applications avec Intune ?](app-management.md)
* [Vue d’ensemble du cycle de vie des applications](app-lifecycle.md)
* [Que sont les stratégies de protection des applications ?](app-protection-policy.md)
