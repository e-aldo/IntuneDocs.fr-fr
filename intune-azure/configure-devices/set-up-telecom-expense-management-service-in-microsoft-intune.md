---
title: "Configuration d’un service de gestion des dépenses de télécommunications | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d&quot;Intune Azure : configuration du service de gestion de frais de télécommunications Saaswedo pour l’intégration à Intune."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Configurer un service de gestion des dépenses en télécommunications dans la version préliminaire d’Intune Azure
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune est intégré à la solution de gestion des dépenses de télécommunications Datalert du développeur de logiciels tiers Saaswedo. Datalert est un logiciel de gestion des frais de télécommunications en temps réel qui vous permet de gérer l’utilisation des données de télécommunications et éviter de des dépassements inattendus et coûteux de données d’itinérance pour vos appareils gérés par Intune. L’intégration d’Intune avec Datalert vous permet de définir, surveiller et appliquer de façon centralisée des limites d’utilisation de données d’itinérance et locales à l’aide d’alertes automatiques lorsque les limites dépassent des seuils définis. Vous pouvez configurer le service pour appliquer différentes actions à des individus ou des groupes d’utilisateurs finaux, notamment la désactivation de l’itinérance, lorsque les utilisateurs dépassent le seuil. Des rapports qui fournissent des informations de surveillance et d’utilisation des données sont disponibles à partir de la console de gestion Datalert.

Avant de pouvoir utiliser le service Datalert avec Intune, vous devez configurer les paramètres dans la console Datalert et dans Intune. La connexion doit être activée pour le service Datalert et pour Intune. Si le côté Datalert de la connexion est activé, mais pas la partie Intune, Intune reçoit la communication, mais l’ignore.

>[!NOTE]
>Pour activer cette fonctionnalité dans votre client d’évaluation, veuillez [contacter le support technique Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) pour l’activation et la prise en charge de Datalert pour les licences logicielles requises.

## <a name="supported-platforms"></a>Plateformes prises en charge

- Samsung Knox
- iOS 8.0 et versions ultérieures

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement à Microsoft Intune
- Un abonnement au service de gestion des frais de télécommunications Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Liste de fournisseurs de gestion des dépenses en télécommunications

Actuellement, Intune s’intègre avec les fournisseurs de gestion de frais de télécommunications suivants :

[Service de gestion des dépenses en télécommunications Saaswedo Datalert](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Configuration d’Intune pour fonctionner avec le service Datalert

 

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Installation** > **Gestion des dépenses de télécommunications**.
2. Sous **Gestion des dépenses de télécommunications**, sélectionnez **État de la connexion**.

3. Sélectionnez **Liste de fournisseurs de services de gestion des frais de télécommunications**, puis sélectionnez votre fournisseur dans la liste affichée. Une page spécifique à votre fournisseur s’ouvre. Pour Saaswedo, la page Datalert s’ouvre. Vous devez travailler avec Saaswedo Datalert pour souscrire un abonnement.

4. Dans la console de gestion **Datalert** :

    a. Accédez à l’onglet **Paramètres**, puis à la sectop, **Configuration MDM**.

    b. Sélectionnez **Déverrouiller** pour vous permettre de saisir les paramètres sur la page.

    c. Pour **serveur MDM**, choisissez **Microsoft Intune**.

    d. Pour **ID client**, saisissez votre ID de client Intune, puis sélectionnez le bouton **Connexion**. Sélectionnez **Connexion** pour que le service Datalert vérifie auprès d’Intune qu’il n’existe aucune connexion Datalert préexistante avec Intune. Après quelques secondes, une page de connexion de Microsoft s’affiche, suivie de l’authentification Datalert Azure.

    e. Sur la page d’authentification Microsoft, sélectionnez **Accepter**. Vous êtes redirigé vers une page de remerciement de Datalert, qui se ferme après quelques secondes. Datalert valide la connexion et affiche des coches vertes à côté d’une liste d’éléments validés. Si la validation échoue, vous verrez un message en rouge. Dans ce cas, contactez le support technique de Datalert pour de l’aide.

5. Attendez quelques minutes, puis accédez au portail et vérifiez que l’état de connexion qui s’affiche est **Actif**. 

    >[!NOTE]
    >Pour activer cette fonctionnalité dans votre client d’évaluation, veuillez [contacter le support technique Microsoft](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Revenez à la console de gestion Datalert et configurez vos lignes de données :

    a. Cliquez sur l'onglet **Paramètres**.

    b. Allez dans l’Assistant **Configuration** et suivez les étapes de l'Assistant.



Le service Datalert est maintenant actif, et commence à surveiller l’utilisation des données et la désactivation des données cellulaires et d’itinérance sur les appareils qui dépassent les limites d’utilisation configurées.

## <a name="turning-off-the-datalert-service"></a>Désactivation du service Datalert

Si vous désactivez le service Datalert dans le portail Azure :

- Toutes les actions qui ont été appliquées aux appareils, en raison de violations des limites d’utilisation, sont annulées.
- L’accès aux données et à l’itinérance n’est plus bloqué pour les utilisateurs.
- Intune reçoit toujours les signaux provenant du service, mais les ignore.

**Pour désactiver le service**

1. Dans le panneau **Gestion des dépenses de télécommunications** dans le portail Azure, sélectionnez **Désactiver**.

2. Sélectionnez **Enregistrer**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Affichage de rapports d’utilisation de données et d’itinérance

Pour l’instant, le rapport d’utilisation des données est disponible uniquement dans la console de gestion de Datalert de Saaswedo.



<!--HONumber=Feb17_HO2-->


