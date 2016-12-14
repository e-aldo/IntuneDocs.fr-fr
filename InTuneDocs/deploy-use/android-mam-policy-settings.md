---
title: "Paramètres de stratégie de gestion des applications mobiles Android | Microsoft Intune"
description: "Cette rubrique décrit les paramètres de stratégie de gestion des applications mobiles pour les appareils Android."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: d0a1a2b3f4e5dbac8b333db3a5cc4bb32c0d61ef


---

# <a name="android-mobile-app-management-policy-settings-in-microsoft-intune"></a>Paramètres de stratégie de gestion des applications mobiles Android dans Microsoft Intune
Vous pouvez [configurer](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) les paramètres décrits dans cette rubrique pour une stratégie de gestion des applications mobiles (GAM) dans le panneau **Paramètres** du portail Azure.
Il existe deux catégories de paramètres de stratégie : réadressage des données et accès. Dans cette rubrique, le terme *Applications gérées par la stratégie* fait référence aux applications qui sont configurées avec des stratégies de gestion des applications mobiles.

##  <a name="data-relocation-settings"></a>Paramètres de réadressage des données

- **Interdire les sauvegardes Android :** choisissez **Oui** pour désactiver ou **Non** pour activer la sauvegarde des données d’entreprise à partir des applications gérées par la stratégie.

  Valeur par défaut = **Oui**
- **Autoriser l’application à transférer des données vers d’autres applications :** choisissez l’une des options pour indiquer les types d’applications qui peuvent recevoir des données d’entreprise à partir des applications gérées par la stratégie :
  -   **Applications gérées par une stratégie** : permet le transfert vers des applications qui ont la stratégie GAM uniquement.
  -   **Toutes les applications** : permet le transfert vers toutes les applications.
  -   **Aucune** : n’autorise pas le transfert de données vers les applications.

 Valeur par défaut = **Applications gérées par la stratégie**.
- **Autoriser l’application à recevoir des données d’autres applications** : spécifiez quelles applications peuvent transférer des données vers les applications gérées par la stratégie :
  -   **Applications gérées par la stratégie** : permet les transferts de données à partir d’autres applications gérées par la stratégie uniquement.
  -   **Toutes les applications** : permet le transfert de données à partir de n’importe quelle application.
  -   **Aucune** : interdit le transfert de données depuis n’importe quelle application.

  Valeur par défaut = **Toutes les applications**

-   **Empêcher Enregistrer sous** : choisissez **Oui** pour désactiver l’utilisation de l’option Enregistrer sous dans toute application qui utilise cette stratégie. Choisissez **Non** pour permettre l’utilisation de l’option Enregistrer sous.

  Valeur par défaut = **Oui**
- **Restreindre les opérations couper, copier et coller avec d’autres applications** : spécifiez quand les actions Couper, Copier et Coller doivent être limitées. Choisissez parmi :
  -   **Bloqué** : interdit les actions Couper, Copier et Coller entre les applications gérées par la stratégie.
  -   **Applications gérées par la stratégie** : permet les actions Couper, Copier et Coller seulement entre les applications gérées par la stratégie.
  -   **Applications gérées par la stratégie avec Coller dans** : permet les actions Couper et Copier entre les applications gérées par la stratégie. Permet le collage dans cette application des données coupées ou copiées depuis n’importe quelle application.
  -   **N’importe quelle application** : il n’existe aucune restriction pour les actions Couper, Copier et Coller entre toutes les applications.

  Valeur par défaut = **Applications gérées par la stratégie avec Coller dans**.
-   **Afficher le contenu web uniquement dans Managed Browser** : choisissez **Oui** pour spécifier que tous les liens dans l’application sont ouverts dans l’application Managed Browser.

  Pour les appareils non inscrits dans Intune, les liens contenus dans les applications gérées par la stratégie peuvent uniquement s’ouvrir dans l’application Managed Browser si vous utilisez la stratégie GAM.

  Si vous utilisez Intune pour gérer vos appareils, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Valeur par défaut = **Oui**
- **Chiffrer les données de l’application** : choisissez **Oui** pour activer le chiffrement. Quand ce paramètre est activé, Microsoft fournit le chiffrement pour les applications associées à une stratégie GAM. Les données sont chiffrées de façon synchrone durant les tâches d’E/S de fichier. Le contenu figurant sur le stockage de l’appareil est toujours chiffré.
  >[!NOTE]
  >La méthode de chiffrement n'est pas certifiée FIPS 140-2.

  Valeur par défaut = **Oui**

- **Désactiver la synchronisation des contacts** : choisissez **Oui** pour empêcher que les informations de contact soient synchronisées avec l’application de carnet d’adresses native sur l’appareil. Si vous choisissez **Non**, l’application enregistre les informations de contact dans l’application de carnet d’adresses native sur l’appareil.

  Quand vous effectuez une réinitialisation sélective pour supprimer les données d’entreprise, les contacts synchronisés directement entre l’application et le carnet d’adresses natif sont supprimés. Les contacts synchronisés entre le carnet d’adresses natif et une autre source externe ne peuvent pas être réinitialisés. Ceci s’applique uniquement à l’application Microsoft Outlook.

  Valeur par défaut = **Oui**
- **Désactiver l’impression** : choisissez **Oui** pour empêcher l’impression de données d’entreprise à partir d’applications qui sont associées à la stratégie GAM.

  Valeur par défaut = **Oui**

##  <a name="access-settings"></a>Paramètres d’accès

- **Exiger un code confidentiel pour l’accès** : choisissez **Oui** pour exiger un code confidentiel pour l’utilisation des applications gérées par la stratégie. L’utilisateur est invité à définir ce code lors de la première exécution de l’application dans un contexte de travail.

 Valeur par défaut = **Oui**

 -  **Autoriser un code confidentiel simple** : spécifiez s’il faut permettre aux utilisateurs d’utiliser des séquences de code confidentiel simples telles que 1234 ou 1111. Valeur par défaut = **Oui**.
 - **Longueur du code confidentiel** : spécifiez le nombre minimal de chiffres d’un code confidentiel. Valeur par défaut = **4**.
 - **Nombre de tentatives avant réinitialisation du code confidentiel** : spécifiez le nombre de tentatives que peut effectuer l’utilisateur pour entrer le code confidentiel avant d’être obligé de le réinitialiser. Il n’existe pas de valeur par défaut pour ce paramètre.
 - **Demander une empreinte digitale au lieu d’un code confidentiel (Android 6.0 et ultérieur) :** choisissez **Oui** pour demander une identification par empreinte digitale à la place d’un code confidentiel pour accéder à l’application.
 Sur les appareils Android, vous pouvez permettre à l’utilisateur de s’identifier à l’aide d’une empreinte digitale au lieu d’un code confidentiel. Quand l’utilisateur essaie d’accéder à cette application en utilisant son compte professionnel, il est invité à s’identifier par empreinte digitale au lieu d’entrer un code confidentiel.
 - **Exiger des informations d’identification d’entreprise pour l’accès** : choisissez **Oui** pour exiger des informations d’identification d’entreprise au lieu d’un code confidentiel ou d’une empreinte digitale pour accéder à l’application. Si vous affectez la valeur **Oui** à ce paramètre, il se substitue à l’obligation de recourir à un code confidentiel ou à un ID tactile. L’utilisateur est invité à fournir ses informations d’identification d’entreprise. Valeur par défaut = **Non**.


- **Bloquer l’exécution des applications gérées sur les appareils jailbreakés ou rootés** : choisissez **Oui** pour bloquer l’exécution des applications sur les appareils jailbreakés ou rootés. L’utilisateur peut continuer à utiliser les applications pour des tâches personnelles, mais il doit utiliser un autre appareil pour son travail.

  Valeur par défaut = **Oui**
- **Revérifier les exigences d'accès après (minutes)**
  -   **Délai** : spécifiez le temps (en minutes) au bout duquel les conditions d’accès à l’application sont revérifiées.
  -   **Période de grâce hors connexion** : si l’appareil est hors connexion, spécifiez la durée (en minutes) au bout de laquelle les conditions d’accès à l’application sont revérifiées.

  Valeur par défaut = délai de **30** minutes et période de grâce hors connexion de **720** minutes

-   **Intervalle en mode hors connexion avant la réinitialisation des données d’application (en jours)** : choisissez de réinitialiser les données d’entreprise si un appareil est resté hors connexion un certain temps.  Spécifiez le nombre de jours pendant lesquels un appareil peut rester hors connexion avant que les données d’entreprise soient supprimées de l’appareil.

    >[!TIP]
    >Entrer **0** désactive ce paramètre.

  Valeur par défaut = **90** jours
- **Bloquer la capture d’écran et l’Assistant Android (Android 6 Marshmallow ou version ultérieure)** : choisissez **Oui** pour bloquer la capture d’écran et les fonctionnalités **Assistant Android** de l’appareil durant l’utilisation de cette application.



<!--HONumber=Dec16_HO2-->


