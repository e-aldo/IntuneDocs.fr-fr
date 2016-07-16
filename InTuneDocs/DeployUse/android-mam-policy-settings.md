---
title: "Paramètres de stratégie de gestion des applications mobiles Android | Microsoft Intune"
description: 
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5a445f06d6c2328f7689468ca4d68a969af1e825
ms.openlocfilehash: 3f43dc871dc0b0a81a6d0b05376a1254957fc35b


---

# Paramètres de stratégie de gestion des applications mobiles Android dans Microsoft Intune
Vous pouvez [configurer](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) les paramètres décrits ci-dessous pour une stratégie de gestion des applications mobiles dans le panneau **Paramètres** du portail Azure.
Il existe deux catégories de paramètres de stratégie : Réadressage des données et Accès :

##  Paramètres de réadressage des données
On utilise le terme **Applications gérées par la stratégie** pour faire référence aux applications qui sont configurées avec des stratégies de gestion des applications mobiles.
- **Interdire les sauvegardes Android :** choisissez **Oui** pour désactiver ou **Non** pour autoriser la sauvegarde des données d’entreprise à partir des applications gérées par la stratégie.

  **Valeur par défaut = Oui**
- **Autoriser l’application à transférer des données vers d’autres applications :** sélectionnez l’une des options pour indiquer les applications qui peuvent recevoir des données d’entreprise à partir des applications gérées par la stratégie :
  -   **Applications gérées par la stratégie** : autoriser le transfert uniquement vers les applications qui disposent de la stratégie de gestion des applications mobiles
  -   **Toutes les applications** : autoriser le transfert vers n’importe quelle application
  -   **Aucune** : n’autoriser le transfert de données vers aucune application

  **Valeur par défaut = Applications gérées par la stratégie**
- **Autoriser l’application à recevoir des données d’autres applications :** spécifiez les applications qui sont autorisées à transférer des données vers les applications gérées par la stratégie :
  -   **Applications gérées par la stratégie** : autoriser les transferts de données uniquement à partir d’autres applications gérées par la stratégie
  -   **Toutes les applications** : autoriser le transfert de données à partir de n’importe quelle application
  -   **Aucune** : n’autoriser le transfert de données à partir d’aucune application

      **Valeur par défaut = Toutes les applications**

-   **Empêcher Enregistrer sous :** sélectionnez **Oui** pour désactiver l’utilisation de l’option Enregistrer sous dans toute application qui utilise cette stratégie. Choisissez **Non** pour autoriser l’utilisation de l’option Enregistrer sous.

  **Valeur par défaut = Oui**
- **Restreindre les opérations couper, copier et coller avec d’autres applications :** spécifiez quand les opérations Couper, Copier et Coller doivent être limitées. Choisissez parmi :
  -   **Bloqué** : interdire les opérations Couper, Copier et Coller entre les applications gérées par la stratégie.
  -   **Applications gérées par la stratégie** : autoriser les opérations Couper, Copier et Coller seulement entre les applications gérées par la stratégie.
  -   **Applications gérées par la stratégie avec Coller dans** : autoriser les opérations Couper et Copier entre les applications gérées par la stratégie. Autorisez le collage dans cette application des données coupées ou copiées depuis n’importe quelle application.
  -   **N’importe quelle application** : aucune restriction pour les opérations Couper, Copier et Coller entre toutes les applications.

    **Valeur par défaut = Applications gérées par la stratégie avec Coller dans**
-   **Afficher le contenu web uniquement dans Managed Browser :** quand ce paramètre est activé, les liens dans l’application sont ouverts dans Managed Browser.

  Pour les appareils non inscrits dans Intune, les liens web contenus dans les applications gérées par la stratégie s’ouvrent uniquement dans l’application Managed Browser qui utilise la stratégie de gestion des applications mobiles.

  Si vous utilisez Intune pour gérer vos appareils, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

    **Valeur par défaut = Oui**
- **Chiffrer les données de l’application :** choisissez **Oui** pour activer le chiffrement. Quand ce paramètre est activé, pour les applications associées à une stratégie de gestion des applications mobiles, le chiffrement est fourni par Microsoft. Les données sont chiffrées de façon synchrone durant les opérations d’E/S de fichier. Le contenu figurant sur le stockage de l’appareil est toujours chiffré.
  >[!NOTE]
  >La méthode de chiffrement n’est pas certifiée FIPS 140-2

  **Valeur par défaut = Oui**

- **Désactiver la synchronisation des contacts :** choisissez **Oui** pour empêcher que les informations de contact soient synchronisées avec l’application de carnet d’adresses native sur l’appareil. Si vous choisissez **Non**, l’application enregistre les informations de contact dans l’application de carnet d’adresses native sur l’appareil.<br/>Quand vous effectuez une réinitialisation sélective pour supprimer les données d’entreprise, les contacts synchronisés directement à partir de l’application de carnet d’adresses native sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être effacés. Actuellement, ceci s’applique uniquement à l’application **Microsoft Outlook**.

  **Valeur par défaut = Oui**

##  Paramètres de stratégie d’accès à Android
On utilise le terme **Applications gérées par la stratégie** pour faire référence aux applications qui sont configurées avec des stratégies de gestion des applications mobiles

- **Exiger un code confidentiel pour l’accès :** choisissez **Oui** pour exiger un code confidentiel pour l’utilisation des applications gérées par la stratégie. L’utilisateur est invité à définir ce code lors de la première exécution de l’application dans un contexte de travail.

 **Valeur par défaut = Oui**

 -  **Autoriser un code confidentiel simple :** spécifiez s’il faut autoriser les utilisateurs à utiliser des séquences de code confidentiel simples telles que 1234 ou 1111. **Valeur par défaut = Oui**.
 - **Longueur du code confidentiel :** spécifiez le nombre minimal de chiffres d’un code confidentiel. **Valeur par défaut = 4**
 - **Nombre de tentatives avant réinitialisation du code confidentiel :** spécifiez le nombre de tentatives que peut effectuer l’utilisateur pour entrer le code confidentiel avant d’être obligé de le réinitialiser. **Il n’existe pas de valeur par défaut pour ce paramètre.**
- **Exiger des informations d’identification d’entreprise pour l’accès :** choisissez **Oui** pour exiger des informations d’identification d’entreprise au lieu d’un code confidentiel pour accéder à l’application.  Si vous affectez la valeur **Oui** à ce paramètre, il se substitue à l’obligation de recourir à un code confidentiel ou à un ID tactile.  L’utilisateur est invité à fournir ses informations d’identification d’entreprise.

  **Valeur par défaut = Non**
- **Bloquer l’exécution des applications gérées sur les appareils jailbroken ou rootés :** choisissez **Oui** pour bloquer l’exécution des applications sur les appareils jailbroken ou rootés. L’utilisateur peut encore utiliser les applications pour des tâches personnelles, mais il doit utiliser un autre appareil pour le travail.

  **Valeur par défaut = Oui**
- **Revérifier les exigences d’accès après (minutes)**-   **Délai :** durée (en minutes) au bout de laquelle les conditions d’accès à l’application sont revérifiées.
  -   **Période de grâce hors connexion :** si l’appareil est hors connexion, spécifiez la durée (en minutes) au bout de laquelle les conditions d’accès à l’application sont revérifiées.

    **Valeur par défaut = délai de 30 minutes et période de grâce hors connexion de 720 minutes**

-   **Intervalle en mode hors connexion avant la réinitialisation des données d’application (en jours) :** vous pouvez choisir de réinitialiser les données d’entreprise si un appareil est resté hors connexion un certain temps.  Spécifiez le nombre de jours pendant lesquels un appareil peut rester hors connexion avant que les données d’entreprise soient supprimées de l’appareil. **Astuce :** Si vous entrez la valeur 0, ce paramètre est désactivé.

  **Valeur par défaut = 90 jours**
- **Bloquer la capture d’écran et l’Assistant Android (Android 6 Marshmallow ou version ultérieure) :** choisissez **Oui** pour bloquer la capture d’écran et les fonctionnalités **Assistant Android** de l’appareil lors de l’utilisation de cette application.



<!--HONumber=Jun16_HO4-->


