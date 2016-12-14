---
title: "Paramètres de stratégie de gestion des applications mobiles iOS | Microsoft Intune"
description: "Cette rubrique décrit les paramètres de stratégie de gestion des applications mobiles pour les appareils iOS."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: andcerat
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: 126974152c638fc4bc69ef92b5fa79beeb0eed0c


---

#  <a name="ios-mobile-app-management-policy-settings"></a>Paramètres de stratégie de gestion des applications mobiles iOS
Vous pouvez [configurer](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) les paramètres décrits dans cette rubrique pour une stratégie de gestion des applications mobiles (GAM) dans le panneau **Paramètres** du portail Azure.

Il existe deux catégories de paramètres de stratégie : réadressage des données et accès. Dans cette rubrique, le terme *Applications gérées par la stratégie* fait référence aux applications qui sont configurées avec des stratégies de gestion des applications mobiles.

##  <a name="data-relocation-settings"></a>Paramètres de réadressage des données

- **Interdire les sauvegardes iTunes et iCloud** : choisissez **Oui** pour désactiver, ou choisissez **Non** pour autoriser la sauvegarde des données d’entreprise à partir d’applications gérées par la stratégie.

  Valeur par défaut = **Oui**.

- **Autoriser l’application à transférer des données vers d’autres applications** : choisissez une des options pour indiquer les applications qui peuvent recevoir des données à partir d’applications gérées par la stratégie :
  - **Applications gérées par une stratégie** : autoriser le transfert seulement vers des applications qui ont la stratégie de gestion des appareils mobiles
  - **Toutes les applications** : autoriser le transfert vers n’importe quelle application.
  - **Aucune** : interdire le transfert de données vers n’importe quelle application, y compris d’autres applications gérées par la stratégie.

  En outre, si vous affectez à cette option la valeur **Applications gérées par la stratégie** ou **Aucune**, la fonctionnalité iOS 9 qui autorise la Recherche Spotlight à rechercher des données dans les applications est bloquée.

  >[!NOTE]
  >Ce paramètre ne contrôle pas l’utilisation de la fonctionnalité « Ouvrir dans » sur les appareils mobiles. Pour gérer la fonctionnalité « Ouvrir dans », consultez [Gérer les transferts de données entre applications iOS avec Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

  Valeur par défaut = **Applications gérées par la stratégie**.

- **Autoriser l’application à recevoir des données d’autres applications** : spécifiez les applications qui sont autorisées à transférer des données vers les applications gérées par la stratégie :
  -  **Applications gérées par la stratégie** : autoriser les transferts de données uniquement à partir d’autres applications gérées par la stratégie.
  -  **Toutes les applications** : autoriser le transfert de données à partir de n’importe quelle application.
  -  **Aucune** : interdire le transfert de données depuis n’importe quelle application.

  Valeur par défaut = **Toutes les applications**.

- **Empêcher Enregistrer sous** : choisissez **Oui** pour désactiver l’utilisation de l’option Enregistrer sous dans toute application qui utilise cette stratégie. Choisissez **Non** pour autoriser l’utilisation de l’option Enregistrer sous.

  Valeur par défaut = **Oui**.

- **Restreindre les opérations couper, copier et coller avec d’autres applications** : spécifiez quand les actions Couper, Copier et Coller doivent être limitées. Choisissez parmi :
  -   **Bloqué** : interdire les actions Couper, Copier et Coller entre les applications gérées par la stratégie.
  -   **Applications gérées par la stratégie** : autoriser les actions Couper, Copier et Coller seulement entre les applications gérées par la stratégie.
  -   **Applications gérées par la stratégie avec Coller dans** : autoriser les actions Couper et Copier entre les applications gérées par la stratégie. Autorisez le collage dans cette application des données coupées ou copiées depuis n’importe quelle application.
  - **N’importe quelle application** : il n’existe aucune restriction pour les actions Couper, Copier et Coller entre toutes les applications.

  Valeur par défaut = **Applications gérées par la stratégie avec Coller dans**.

- **Afficher le contenu web uniquement dans Managed Browser** : quand ce paramètre est activé, les liens dans l’application sont ouverts dans l’application Managed Browser.

  Pour les appareils non inscrits dans Intune, les liens web contenus dans les applications gérées par la stratégie peuvent s’ouvrir uniquement dans l’application Managed Browser.

  Si vous utilisez Intune pour gérer vos appareils, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).

  Valeur par défaut = **Oui**.

- **Chiffrer les données de l’application** : pour les applications associées à une stratégie GAM Intune, les données sont chiffrées au repos par le biais du chiffrement au niveau de l’appareil fourni par le système d’exploitation. Quand un code confidentiel est nécessaire, les données sont chiffrées selon les paramètres de la stratégie GAM. Comme indiqué dans la documentation Apple, [les modules qu’utilise iOS 7 sont certifiés FIPS 140-2](http://support.apple.com/en-us/HT202739).

  Dans les paramètres de stratégie, vous pouvez spécifier des valeurs de chiffrement de code confidentiel. Ces valeurs déterminent quand les données sont chiffrées. Les options disponibles sont :
  -   **Quand l’appareil est verrouillé** : toutes les données d’application associées à cette stratégie sont chiffrées pendant que l’appareil est verrouillé.
  -   **Quand l’appareil est verrouillé (sauf fichiers ouverts)** : toutes les données d’application associées à cette stratégie sont chiffrées pendant que l’appareil est verrouillé, à l’exception des données figurant dans les fichiers qui sont ouverts dans l’application.
  -   **Après le redémarrage de l’appareil** : toutes les données d’application associées à cette stratégie sont chiffrées quand l’appareil est redémarré, jusqu’à ce que l’appareil soit déverrouillé pour la première fois.
  -   **Utiliser les paramètres de l’appareil** : les données d’application sont chiffrées conformément aux paramètres par défaut de l’appareil.
  Quand vous activez ce paramètre, l’utilisateur doit configurer et utiliser un code confidentiel pour accéder à son appareil.  S’il n’existe pas de code confidentiel, les applications ne s’ouvrent pas et l’utilisateur est invité à définir un code confidentiel par le message « Votre entreprise exige que vous activiez d’abord un code confidentiel sur l’appareil pour accéder à cette application. ».

  Valeur par défaut : l’option de chiffrement n’est pas sélectionnée.
- **Désactiver la synchronisation des contacts** : choisissez **Oui** pour empêcher que les informations de contact soient synchronisées avec l’application de carnet d’adresses native sur l’appareil. Si vous choisissez **Non**, l’application enregistre les informations de contact dans l’application de carnet d’adresses native sur l’appareil.

  Quand vous effectuez une réinitialisation sélective pour supprimer les données d’entreprise, les contacts synchronisés directement à partir de l’application de carnet d’adresses native sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être effacés. Ceci s’applique uniquement à l’application Microsoft Outlook.

  Valeur par défaut = **Oui**.

- **Désactiver l’impression** : choisissez **Oui** pour empêcher d’imprimer des données d’entreprise à partir d’applications qui sont associées à la stratégie GAM.

    Valeur par défaut = **Oui**.

##  <a name="access-settings"></a>Paramètres d’accès

- **Exiger un code confidentiel pour l’accès** : choisissez **Oui** pour exiger un code confidentiel pour l’utilisation des applications gérées par la stratégie. L’utilisateur est invité à définir ce code lors de la première exécution de l’application dans un contexte de travail.

  Valeur par défaut = **Oui**.
    -  **Autoriser un code confidentiel simple** : spécifiez s’il faut permettre aux utilisateurs d’utiliser des séquences de code confidentiel simples telles que 1234 ou 1111. Valeur par défaut = **Oui**.
    - **Longueur du code confidentiel** : spécifiez le nombre minimal de chiffres d’un code confidentiel. Valeur par défaut = **4**.
    - **Nombre de tentatives avant réinitialisation du code confidentiel** : spécifiez le nombre de tentatives que peut effectuer l’utilisateur pour entrer le code confidentiel avant d’être obligé de le réinitialiser. Il n’existe pas de valeur par défaut pour ce paramètre.

- **Demander une empreinte digitale au lieu d’un code confidentiel (iOS 8.0 et ultérieur)** : choisissez **Oui** pour demander une identification par empreinte digitale à la place d’un code confidentiel pour accéder à l’application.
Sur les appareils iOS, vous pouvez laisser les utilisateurs s’identifier à l’aide d’une empreinte digitale sur des appareils iOS au lieu d’un code confidentiel. Quand l’utilisateur tente d’ouvrir l’application en utilisant son compte professionnel, il est invité à s’identifier par empreinte digitale au lieu d’entrer un code confidentiel.

  Valeur par défaut = **Oui**.
- **Exiger des informations d’identification d’entreprise pour l’accès** : choisissez **Oui** pour exiger des informations d’identification d’entreprise au lieu d’un code confidentiel pour accéder à l’application. Si vous affectez la valeur **Oui** à ce paramètre, il se substitue à l’obligation de recourir à un code confidentiel ou à un ID tactile. L’utilisateur est invité à fournir ses informations d’identification d’entreprise.

  Valeur par défaut = **Non**.
- **Bloquer l’exécution des applications gérées sur les appareils jailbreakés ou rootés** : choisissez **Oui** pour bloquer l’exécution des applications sur les appareils jailbreakés ou rootés. L’utilisateur peut encore utiliser les applications pour des tâches personnelles, mais il doit utiliser un autre appareil pour le travail.

  Valeur par défaut = **Oui**.
- **Revérifier les exigences d'accès après (minutes)**
  -   **Délai** : spécifiez le temps (en minutes) au bout duquel les conditions d’accès à l’application sont revérifiées.
  -   **Période de grâce hors connexion** : si l’appareil est hors connexion, spécifiez la durée (en minutes) au bout de laquelle les conditions d’accès à l’application sont revérifiées.

  Valeur par défaut = délai de **30** minutes et période de grâce hors connexion de **720** minutes.
- **Intervalle en mode hors connexion avant la réinitialisation des données d’application (en jours)** : vous pouvez choisir de réinitialiser les données d’entreprise si un appareil est resté hors connexion un certain temps. Spécifiez le nombre de jours pendant lesquels un appareil peut rester hors connexion avant que les données d’entreprise soient supprimées de l’appareil.

  >[!TIP]
  >Entrer **0** désactive ce paramètre.

  Valeur par défaut = **90** jours.



<!--HONumber=Dec16_HO2-->


