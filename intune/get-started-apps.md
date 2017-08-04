---
title: "Bien démarrer avec les applications"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 71093f8ac17fc6d6938f5c263a40204f89419726
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-apps"></a>Bien démarrer avec les applications

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune prend en charge différentes manières de déployer des applications sur vos appareils d’entreprise :

* **Programmes d’installation du logiciel** : quand vous chargez un fichier qui est téléchargé sur les appareils de vos utilisateurs
* __Liens externes__ : quand vous avez une application dans un App Store public ou une application web
* **Applications gérées** : pour les appareils iOS où vous devez appliquer une gestion des applications mobiles supplémentaire à des applications disponibles dans l’App Store

Vous allez suivre l’une des méthodes de déploiement d’application les plus rapides en affectant une application de Store public.

__Comment affecter une application de Store public ?__

1. Connectez-vous au [portail Azure](https://portal.azure.com).
2. À l’aide de **Rechercher des ressources**, recherchez **Intune**.
3. Sélectionnez **Applications mobiles**, puis **Applications**.
4. Sélectionnez **Ajouter**, puis **Application de l’App Store iOS** comme **Type d’application**.
5. Dans la zone de texte, recherchez une application à affecter à l’appareil. Choisissez l’application, puis sélectionnez **OK**.
6. Dans le panneau **Ajouter une application**, sélectionnez **Informations sur l’application**, puis vérifiez que toutes les informations sur l’application sont renseignées. Vous pouvez ajouter d’autres détails facultatifs pour vous aider à organiser cette application, comme **Propriétaire**, **Remarques**, **Développeur** et une **URL de confidentialité** pour la politique de confidentialité de votre entreprise.
7. Vérifiez que vous avez sélectionné Oui pour Proposer cette application dans le portail d’entreprise, puis sélectionnez OK.
8. Sélectionnez **Ajouter** pour ajouter l’application. Vous accédez alors à la **Vue d’ensemble** de cette application. Choisissez **Affectations**, puis cliquez sur **Sélectionner des groupes** pour l’affecter à votre groupe de test. Rendez l’application **Disponible** pour le téléchargement. L’application doit alors apparaître comme **Application proposée** sur votre appareil de test.
