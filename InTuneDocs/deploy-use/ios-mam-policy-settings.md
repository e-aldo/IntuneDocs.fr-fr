---
title: "Paramètres de stratégie de gestion des applications mobiles iOS | Microsoft Docs"
description: "Cette rubrique décrit les paramètres de stratégie de gestion des applications mobiles pour les appareils iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 673ff872-943c-4076-931c-0be90363aea9
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: fbb41a8cf6fada76b72213b8cb04fdc0428515e9
ms.openlocfilehash: bccadaed116eb0c358127881742c5a768bb6d129
ms.lasthandoff: 02/14/2017


---

#  <a name="ios-mobile-app-protection-policy-settings"></a>Paramètres de stratégie de protection des applications mobiles iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Les paramètres de stratégie décrits dans cette rubrique peuvent être [configurés](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) pour une stratégie de protection des applications dans le panneau **Tous les paramètres** dans le portail Azure.

Il existe deux catégories de paramètres de stratégie : réadressage des données et accès. Dans cette rubrique, le terme _**applications gérées par une stratégie**_ fait référence aux applications qui sont configurées avec des stratégies de protection des applications.

##  <a name="data-relocation-settings"></a>Paramètres de réadressage des données

| Paramètre | Procédure d'utilisation | Valeur par défaut |
|------|------|------|
| **Interdire les sauvegardes iTunes et iCloud** | Choisissez **Oui** pour empêcher cette application de sauvegarder les données professionnelles ou scolaires sur iTunes et iCloud. Choisissez **Non** pour permettre à cette application de sauvegarder des données professionnelles ou scolaires dans iTunes et iCloud.| Oui |
| **Autoriser l'application à transférer des données vers d'autres applications** | Spécifiez les applications qui peuvent recevoir des données à partir de cette application : <ul><li> **Applications gérées par la stratégie** : autoriser le transfert uniquement vers d’autres applications gérées par la stratégie.</li> <li>**Toutes les applications** : autoriser le transfert vers n’importe quelle application. </li> <li>**Aucune** : interdire le transfert de données vers n’importe quelle application, y compris d’autres applications gérées par la stratégie.</li></ul> En outre, si vous affectez à cette option la valeur **Applications gérées par la stratégie** ou **Aucune**, la fonctionnalité iOS 9 qui autorise la Recherche Spotlight à rechercher des données dans les applications est bloquée. <br><br> Intune peut toutefois autoriser le transfert de données vers des applications et des services exemptés. Pour obtenir la liste complète de ces applications et services, consultez [Exemptions au transfert de données](#Data-transfer-exemptions). | Toutes les applications |
| **Autoriser l'application à recevoir des données d'autres applications** | Spécifiez quelles applications peuvent transférer des données vers cette application : <ul><li>**Applications gérées par la stratégie** : autoriser le transfert uniquement à partir d’autres applications gérées par la stratégie.</li><li>**Toutes les applications** : autoriser le transfert de données à partir de n’importe quelle application.</li><li>**Aucune** : interdire le transfert de données depuis n’importe quelle application, y compris d’autres applications gérées par la stratégie.</li></ul> Intune peut toutefois autoriser le transfert de données à partir d’applications et de services exemptés. Pour obtenir la liste complète de ces applications et services, consultez [Exemptions au transfert de données](#Data-transfer-exemptions).  | Toutes les applications |
| **Empêcher « Enregistrer sous »** | Sélectionnez **Oui** pour interdire l’utilisation de l’option Enregistrer sous dans cette application. Choisissez **Non** pour autoriser l’utilisation de l’option Enregistrer sous. | Non |
| **Restreindre les opérations couper, copier et coller avec d'autres applications** | Spécifiez quand autoriser les actions couper, copier et coller avec cette application. Choisissez parmi : <ul><li>**Bloqué** : ne pas autoriser les actions couper, copier et coller entre cette application et une autre application.</li><li>**Applications gérées par la stratégie** : autoriser seulement les actions couper, copier et coller entre cette application et les autres applications gérées par la stratégie.</li><li>**Applications gérées par la stratégie avec Coller dans** : autoriser les actions couper et copier entre cette application et les autres applications gérées par la stratégie. Autoriser le collage dans cette application de données à partir de n'importe quelle application.</li><li>**N’importe quelle application** : aucune restriction pour les actions couper, copier et coller vers et depuis cette application. | N’importe quelle application |
|**Limiter le contenu web à afficher dans Managed Browser** | Choisissez **Oui** pour appliquer des liens web dans l’application à ouvrir dans l’application Managed Browser. <br><br> Pour les appareils non inscrits dans Intune, les liens web contenus dans les applications gérées par la stratégie peuvent s’ouvrir uniquement dans l’application Managed Browser. <br><br> Si vous utilisez Intune pour gérer vos appareils, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](manage-internet-access-using-managed-browser-policies.md). | Non |
| **Chiffrer les données de l'application** | Pour les applications gérés par la stratégie, les données sont chiffrées au repos à l'aide du schéma de chiffrement au niveau de l'appareil fourni par iOS. Quand un code confidentiel est nécessaire, les données sont chiffrées selon les paramètres de la stratégie de protection des applications. <br><br> Accédez à la documentation officielle Apple [ici](https://support.apple.com/HT202739) pour savoir quels modules de chiffrement iOS sont certifiés FIPS 140-2 ou en attente de la certification FIPS 140-2. <br><br> Spécifiez quand les données professionnelles ou scolaires de cette application sont chiffrées. Choisissez parmi : <ul><li>**Quand l’appareil est verrouillé** : toutes les données d’application associées à cette stratégie sont chiffrées pendant que l’appareil est verrouillé.</li><li>**Quand l'appareil est verrouillé et que des fichiers sont ouverts** : toutes les données d’application associées à cette stratégie sont chiffrées pendant que l’appareil est verrouillé, à l’exception des données figurant dans les fichiers qui sont ouverts dans l’application.</li><li>**Après le redémarrage de l’appareil** : toutes les données d’application associées à cette stratégie sont chiffrées quand l’appareil est redémarré, jusqu’à ce que l’appareil soit déverrouillé pour la première fois.</li><li>**Utiliser les paramètres de l’appareil** : les données d’application sont chiffrées conformément aux paramètres par défaut de l’appareil. Quand vous activez ce paramètre, l’utilisateur doit configurer et utiliser un code confidentiel pour accéder à son appareil.  S’il n’existe pas de code confidentiel, les applications ne s’ouvrent pas et l’utilisateur est invité à définir un code confidentiel par le message « Votre entreprise exige que vous activiez d’abord un code confidentiel sur l’appareil pour accéder à cette application. ». </li></ul> | Quand l’appareil est verrouillé |
| **Désactiver la synchronisation des contacts** | Choisissez **Oui** pour empêcher l’application d'enregistrer les données vers l’application Contacts native sur l'appareil. Si vous choisissez **Non**, l’application peut enregistrer des données vers l’application Contacts native sur l'appareil. <br><br>Lorsque vous effectuez une réinitialisation sélective pour supprimer des données professionnelles ou scolaires à partir de l’application, les contacts directement synchronisés à partir de l’application vers l'application Contacts native sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être effacés. Ceci s’applique uniquement à l’application Microsoft Outlook. | Non |
| **Désactiver l’impression** | Choisissez **Oui** pour empêcher l’application d'imprimer des données professionnelles ou scolaires. | Non |


> [!NOTE]
> Aucun des paramètres de réadressage des données ne contrôle la fonctionnalité Open In d'Apple sur les appareils iOS. Pour gérer la fonctionnalité « Open In », consultez [Gérer les transferts de données entre applications iOS avec Microsoft Intune](manage-data-transfer-between-ios-apps-with-microsoft-intune.md).

## <a name="data-transfer-exemptions"></a>Exemptions au transfert de données

La stratégie de protection des applications Intune peut autoriser le transfert de données à destination et à partir d’applications et de services de plateforme exemptés dans certains scénarios. Cette liste, qui est susceptible d’être modifiée, reflète les services et les applications considérés comme utiles pour sécuriser la productivité.

| Nom(s) de l’application ou du service | Description |
| ---- | --- |
|tel ; telprompt | Application de téléphone native |
| Skype | Skype |
| paramètres de l’application | Paramètres de l’appareil |
| itms ; itmss ; itms-apps ; itms-appss ; itms-services | App Store |
| calshow | Calendrier natif |




## <a name="access-settings"></a>Paramètres d’accès

| Paramètre | Procédure d'utilisation | Valeur par défaut |
|------|------|------|
| **Exiger un code confidentiel d’accès** | Choisissez **Oui** afin d'exiger un code confidentiel pour utiliser cette application. L’utilisateur est invité à définir ce code lors de la première exécution de l’application dans un contexte professionnel ou scolaire. Valeur par défaut = **Oui**.<br><br> Configurez les paramètres suivants pour le niveau de sécurité du code confidentiel : <ul><li>**Nombre de tentatives avant réinitialisation du code confidentiel**: spécifiez le nombre de fois qu'un utilisateur doit saisir correctement son code confidentiel avant de devoir le réinitialiser. Valeur par défaut = **5**.</li><li> **Autoriser un code confidentiel simple :** choisissez **Oui** pour autoriser les utilisateurs à utiliser des séquences de code confidentiel simples telles que 1234 ou 1111. Choisissez **Non** pour empêcher l’utilisation de séquences simples. Valeur par défaut = **Oui**. </li><li> **Longueur du code confidentiel** : spécifiez le nombre minimal de chiffres d’une séquence de code confidentiel. Valeur par défaut = **4**. </li><li> **Autoriser une empreinte digitale à la place du code confidentiel (iOS 8.0 et ultérieur)** : choisissez **Oui** pour autoriser l'utilisateur à se servir de [Touch ID](https://support.apple.com/en-us/HT201371) à la place d’un code confidentiel pour accéder à l’application. Valeur par défaut = **Oui**</li></ul> Sur les appareils iOS, vous pouvez laisser l’utilisateur prouver son identité à l’aide de [Touch ID](https://support.apple.com/en-us/HT201371) au lieu d’un code confidentiel. Quand l’utilisateur tente d'utiliser l’application à l'aide de son compte professionnel ou scolaire, il est invité à s’identifier par empreinte digitale au lieu d’entrer un code confidentiel. Quand ce paramètre est activé, l’image d’aperçu du sélecteur d’application sera floue lors de l’utilisation d’un compte professionnel ou scolaire. </li></ul>| Exiger un code confidentiel : Oui <br><br> Tentatives de réinitialisation du code confidentiel : 5 <br><br> Autoriser un code confidentiel : Oui <br><br> Longueur du code confidentiel : 4 <br><br> Autoriser l'empreinte digitale : Oui |
| **Exiger des informations d'identification d'entreprise pour l'accès** | Choisissez **Oui** pour obliger l’utilisateur à se connecter avec son compte professionnel ou scolaire au lieu d’entrer un code confidentiel pour accéder à l’application. Si vous affectez la valeur **Oui** à ce paramètre, il se substitue à l’obligation de recourir à un code confidentiel ou à un ID tactile.  | Non |
| **Bloquer l’exécution des applications gérées sur les appareils jailbreakés ou rootés** |  Choisissez **Oui** pour empêcher l'exécution de cette application sur les appareils jailbreakés ou rootés. L’utilisateur peut encore utiliser cette application pour des tâches personnelles, mais il doit utiliser un autre appareil pour accéder aux données professionnelles ou scolaires dans cette application. | Oui |
| **Revérifier les exigences d'accès après (minutes)** | Configurez les paramètres suivants : <ul><li>**Délai** : il s’agit du nombre de minutes qui s’écoulent avant que les conditions d’accès (définies plus haut dans la stratégie) ne soient revérifiées. Par exemple, un administrateur active un code confidentiel dans la stratégie, un utilisateur ouvre une application GAM et doit entrer un code confidentiel. Quand ce paramètre est employé, l’utilisateur n’a pas à entrer un code confidentiel pour aucune application GAM pendant encore **30 minutes** (valeur par défaut).</li><li>**Période de grâce hors connexion** : il s’agit du nombre de minutes pendant lesquelles les applications GAM peuvent être exécutées hors connexion ; spécifiez la durée (en minutes) au bout de laquelle les conditions d’accès à l’application sont revérifiées. Valeur par défaut = **720** minutes (12 heures). Après l’expiration de cette période, l’application nécessite une authentification utilisateur auprès d’AAD pour poursuivre son exécution.</li></ul>| Délai d'expiration : 30 <br><br> Hors connexion : 720 |
| **Intervalle en mode hors connexion avant la réinitialisation des données d’application (en jours)** | Après ce nombre de jours (défini par l’administrateur) d’exécution en mode hors connexion, l’application elle-même procède à une réinitialisation sélective. Cette réinitialisation sélective est identique à celle qui peut être lancée par l’administrateur dans le flux de travail de réinitialisation GAM. <br><br> | 90 jours |

##  <a name="add-ins-for-outlook-app"></a>Compléments d’application Outlook

Outlook propose depuis peu des compléments pour Outlook iOS qui vous permettent d’intégrer les applications les plus courantes avec le client de messagerie. Les compléments pour Outlook sont disponibles sur les versions web, Windows, Mac et iOS. Étant donné que les compléments sont gérés par Microsoft Exchange, vous pourrez partager des données et des messages entre Outlook et les applications complémentaires non gérées, sauf si les compléments sont désactivés pour l’utilisateur par Exchange.

Si vous décidez d’empêcher vos utilisateurs d’accéder à et d’installer des compléments Outlook (cela affecte tous les clients Outlook), assurez-vous que les modifications suivantes sont apportées aux rôles dans le centre d’administration Exchange :

- Pour empêcher les utilisateurs d’installer des compléments Office Store, retirez-leur le rôle Mon Marketplace.
- Pour empêcher les utilisateurs de charger des compléments, retirez-leur le rôle Mes applications personnalisées.
- Pour empêcher les utilisateurs d’installer l’ensemble des compléments, retirez-leur les deux rôles, Mes applications personnalisées et Mon Marketplace.

Ces instructions s’appliquent à Office 365, Exchange 2016, Exchange 2013 pour les versions web, Windows, Mac et mobiles d’Outlook.

- En savoir plus sur les [compléments pour Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Lisez-en davantage avec le [Guide pratique de spécification des administrateurs et utilisateurs pouvant installer et gérer les compléments d’application Outlook](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

