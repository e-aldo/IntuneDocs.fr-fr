---
title: "Déployer l’application Lookout for Work | Microsoft Intune"
description: "Configurer et déployer l’application Lookout for Work pour Android."
author: karthikaraman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9c2ffb5fe497d56d8250fe3dec7db606c2067a1c
ms.openlocfilehash: c43104ff199e1800bfded35154d2be0cfd0c40f3


---

# Configurer et déployer l’application Lookout for Work
Cette version prend en charge l’application Lookout for Work sur les appareils exécutant Android 4.1 ou ultérieur.
## Android
Cette section explique comment configurer et déployer l’application Lookout for Work sur des appareils Android inscrits dans Intune.  
* Étape 1 : Dans la [console Administrateur Microsoft Intune](https://manage.microsoft.com), accédez à **Applications** et choisissez **Ajouter des applications**.   
* Étape 2 : Dans la page **Installation du logiciel** du serveur de publication, choisissez **Lien externe**, puis indiquez l’URL suivante : https://play.google.com/store/apps/details?id=com.lookout.enterprise
>[!NOTE]
>Ne cliquez pas sur l’option pour obtenir Managed Browser.

* Étape 3 : Dans la page **Description du logiciel**, renseignez les informations suivantes :
  * **Serveur de publication :** Lookout Mobile Security
  * **Nom :** Lookout for Work
  * **Description :** Lookout offre la meilleure protection contre les menaces mobiles pour sécuriser votre appareil. Quand l’application Lookout est installée sur l’appareil, elle protège votre appareil contre les menaces et elle vous avertit (ainsi que l’administrateur de votre entreprise) des menaces détectées.
  * **Catégorie :** Gestion de l’ordinateur
* Étape 4 : En cas de réussite de l’opération, le message **Le téléchargement des données s’est terminé correctement dans Microsoft Intune** s’affiche.

Dans la console Intune, quand vous cliquez sur **Applications**, vous voyez maintenant l’application Lookout for Work dans la liste. ![Capture d’écran de la page Applications dans la console Administrateur Intune montrant l’application Lookout for Work dans la liste](../media/mtp/lookout-app-listed-intune-console.png)

Étape 5 : À ce stade, Intune sait comment déployer l’application Lookout for Work pour Android.   Vous pouvez déployer l’application pour des utilisateurs, en sélectionnant l’application Lookout for Work illustrée dans l’écran ci-dessus et en sélectionnant **Gérer le déploiement**.

Vous devez sélectionner les mêmes utilisateurs que ceux qui ont été ajoutés à l’option Gestion des inscriptions dans la console Lookout MTP.  Pour plus d’informations sur l’ajout de groupes d’utilisateurs dans Lookout MTP, consultez l’étape 3 dans la section [Configurer votre abonnement à Lookout MTP](set-up-your-subscription-with-lookout-mtp#configure-your-subscription-with-lookout-mtp).
>[!IMPORTANT]
> L’Assistant Déploiement d’application Intune n’a pas connaissance des groupes d’utilisateurs Azure AD et utilise les groupes d’utilisateurs Intune à la place. Vous devez donc créer un groupe d’utilisateurs Intune basé sur le groupe d’utilisateurs Azure AD qui est inscrit dans la console Lookout MTP, comme cela est décrit dans [cette](plan-your-user-and-device-groups.md) rubrique.

Étape 6 : Choisissez l’option **Installation requise** pour exiger que l’application Lookout soit installée sur l’appareil de l’utilisateur.

### Activation de l’appareil
Si l’option **Installation requise** est sélectionnée pour le déploiement, Intune transfère l’application Lookout for Work sur l’appareil.   

Quand l’utilisateur ouvre l’application Lookout for Work sur l’appareil, il est invité à activer l’application et à choisir l’option Se connecter avec Azure Active Directory. Une procédure pas à pas pour l’utilisateur final est décrite dans les rubriques suivantes :

* [Vous êtes invité à installer Lookout for Work sur votre appareil Android](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

* [Vous devez résoudre une menace que Lookout for Work a détectée sur votre appareil Android](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## Étapes suivantes
* [Activer une règle de protection de l’appareil contre les menaces dans la stratégie de conformité](enable-device-threat-protection-rule-in-compliance-policy.md)



<!--HONumber=Sep16_HO2-->


