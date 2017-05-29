---
title: "Paramètres de stratégie de gestion des applications mobiles Android | Microsoft Docs"
description: "Cette rubrique décrit les paramètres de stratégie de gestion des applications mobiles pour les appareils Android."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5dbb702a-1df5-4637-95c9-77a5f0b1a0e3
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 017c316ce102b71b3ef9552d8fe69181b79473de
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="android-app-protection-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie de protection des applications Android dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez [configurer](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) les paramètres de la stratégie de protection des applications décrits dans cette rubrique dans le panneau **Paramètres** du portail Azure.
Il existe deux catégories de paramètres de stratégie : réadressage des données et accès. Dans cette rubrique, le terme _**applications gérées par une stratégie**_ fait référence aux applications qui sont configurées avec des stratégies de protection des applications.

##  <a name="data-relocation-settings"></a>Paramètres de réadressage des données

| Paramètre | Procédure d'utilisation | Valeur(s) par défaut |
|------|------|------|
| **Interdire les sauvegardes Android** | Choisissez **Oui** pour empêcher cette application de sauvegarder les données professionnelles ou scolaires dans le [service de sauvegarde Android](https://developer.android.com/google/backup/index.html) Choisissez **Non** pour permettre à cette application de sauvegarder les données professionnelles ou scolaires.| Oui |
| **Autoriser l'application à transférer des données vers d'autres applications** | Spécifiez les applications qui peuvent recevoir des données à partir de cette application : <ul><li> **Applications gérées par la stratégie** : autoriser le transfert uniquement vers d’autres applications gérées par la stratégie.</li> <li>**Toutes les applications** : autoriser le transfert vers n’importe quelle application. </li> <li>**Aucune** : interdire le transfert de données vers n’importe quelle application, y compris d’autres applications gérées par la stratégie.</li></ul> <p>Intune peut toutefois autoriser le transfert de données vers des applications et des services exemptés. Pour obtenir la liste complète de ces applications et services, consultez [Exemptions au transfert de données](#Data-transfer-exemptions).| Toutes les applications |
| **Autoriser l'application à recevoir des données d'autres applications** | Spécifiez quelles applications peuvent transférer des données vers cette application : <ul><li>**Applications gérées par la stratégie** : autoriser le transfert uniquement à partir d’autres applications gérées par la stratégie.</li><li>**Toutes les applications** : autoriser le transfert de données à partir de n’importe quelle application.</li><li>**Aucune** : interdire le transfert de données depuis n’importe quelle application, y compris d’autres applications gérées par la stratégie. </li></ul> <p>Intune peut toutefois autoriser le transfert de données à partir d’applications et de services exemptés. Pour obtenir la liste complète de ces applications et services, consultez [Exemptions au transfert de données](#Data-transfer-exemptions). | Toutes les applications |
| **Empêcher « Enregistrer sous »** | Sélectionnez **Oui** pour interdire l’utilisation de l’option Enregistrer sous dans cette application. Choisissez **Non** pour autoriser l’utilisation de l’option Enregistrer sous. <p><br>**Sélectionnez dans quels services de stockage les données d'entreprise peuvent être enregistrées** <br>Les utilisateurs peuvent enregistrer dans les services sélectionnés (OneDrive Entreprise, SharePoint et le stockage local). Tous les autres services seront bloqués.</p> | Non <br><br> 0 sélectionné |
| **Restreindre les opérations couper, copier et coller avec d'autres applications** | Spécifiez quand autoriser les actions couper, copier et coller avec cette application. Choisissez parmi : <ul><li>**Bloqué** : ne pas autoriser les actions couper, copier et coller entre cette application et une autre application.</li><li>**Applications gérées par la stratégie** : autoriser seulement les actions couper, copier et coller entre cette application et les autres applications gérées par la stratégie.</li><li>**Applications gérées par la stratégie avec Coller dans** : autoriser les actions couper et copier entre cette application et les autres applications gérées par la stratégie. Autoriser le collage dans cette application de données à partir de n'importe quelle application.</li><li>**N’importe quelle application** : aucune restriction pour les actions couper, copier et coller vers et depuis cette application. | N’importe quelle application |
|**Limiter le contenu web à afficher dans Managed Browser** | Choisissez **Oui** pour appliquer des liens web dans l’application à ouvrir dans l’application Managed Browser. <br><br> Pour les appareils non inscrits dans Intune, les liens web contenus dans les applications gérées par la stratégie peuvent s’ouvrir uniquement dans l’application Managed Browser. <br><br> Si vous utilisez Intune pour gérer vos appareils, consultez [Gérer l’accès à Internet à l’aide de stratégies Managed Browser avec Microsoft Intune](manage-internet-access-using-managed-browser-policies.md). | Non |
| **Chiffrer les données de l'application** | Choisissez **Oui** pour activer le chiffrement des données professionnels ou scolaires dans cette application. Intune utilise un schéma de chiffrement AES 128 bits OpenSSL ainsi que le système Android Keystore pour chiffrer en toute sécurité les données de l’application. Les données sont chiffrées de façon synchrone durant les tâches d’E/S de fichier. Le contenu figurant sur le stockage de l’appareil est toujours chiffré. <br><br> La méthode de chiffrement n'est **pas** certifiée FIPS 140-2.  | Oui |
| **Désactiver la synchronisation des contacts** | Choisissez **Oui** pour empêcher l’application d'enregistrer les données vers l’application Contacts native sur l'appareil. Si vous choisissez **Non**, l’application peut enregistrer des données vers l’application Contacts native sur l'appareil. <br><br>Lorsque vous effectuez une réinitialisation sélective pour supprimer des données professionnelles ou scolaires à partir de l’application, les contacts directement synchronisés à partir de l’application vers l'application Contacts native sont supprimés. Les contacts synchronisés à partir du carnet d’adresses natif vers une autre source externe ne peuvent pas être effacés. Ceci s’applique uniquement à l’application Microsoft Outlook. | Non |
| **Désactiver l’impression** | Choisissez **Oui** pour empêcher l’application d'imprimer des données professionnelles ou scolaires. | Non |

  >[!NOTE]
  >La méthode de chiffrement du paramètre **Chiffrer les données de l’application** n'est **pas** certifiée FIPS 140-2.


  ## <a name="data-transfer-exemptions"></a>Exemptions au transfert de données

  La stratégie de protection des applications Intune peut autoriser le transfert de données à destination et à partir d’applications et de services de plateforme exemptés. Par exemple, pour que le texte affiché à l’écran d’un appareil mobile puisse être lu à voix haute, toutes les applications compatibles avec Intune sur Android doivent pouvoir transférer des données à destination et à partir de l’application Synthèse vocale de Google. Cette liste, qui est susceptible d’être modifiée, reflète les services et les applications considérés comme utiles pour sécuriser la productivité.

  ### <a name="full-exemptions"></a>Exemptions totales

  Ces applications et services prennent entièrement en charge le transfert de données à destination et à partir des applications gérées par Intune.

  |Nom de l’application ou du service | Description |
  | ------ | ---- |
  | com.android.phone | Application de téléphone native
  | com.android.vending | Google Play Store |
  | com.android.documentsui | Sélecteur de documents Android|
  | com.google.android.webview | [WebView](https://developer.android.com/reference/android/webkit/WebView.html), nécessaire pour de nombreuses applications, notamment Outlook. |
  | com.android.webview |[WebView](https://developer.android.com/reference/android/webkit/WebView.html), nécessaire pour de nombreuses applications, notamment Outlook.|
  | com.google.android.tts | Synthèse vocale de Google |
  | com.android.providers.settings | Paramètres système Android |
  | com.azure.authenticator | Application Azure Authenticator, nécessaire pour l’authentification dans de nombreux scénarios. |
  | com.microsoft.windowsintune.companyportal | Portail d'entreprise Intune|

  ### <a name="conditional-exemptions"></a>Exemptions conditionnelles
  Ces applications et services prennent en charge le transfert de données à destination et à partir d’applications gérées par Intune sous certaines conditions.

  |Nom de l’application ou du service | Description | Condition d’exemption|
  | ------ | ---- | --- |
  | com.android.chrome | Navigateur Google Chrome | Chrome est utilisé pour certains composants WebView sur Android 7.0+ et n’est jamais masqué. Toutefois, le flux de données à destination et à partir de l’application est toujours limité.
  | com.skype.raider | Skype | L’application Skype n’est autorisée que pour certaines actions aboutissant à un appel téléphonique. |
  | com.android.providers.media | Fournisseur de contenu multimédia Android | Le fournisseur de contenu multimédia est uniquement autorisé pour l’action de sélection de la sonnerie. |
  | com.google.android.gms ; com.google.android.gsf | Packages Google Play Services | Ces packages sont autorisés pour les actions Google Cloud Messaging, comme les notifications push. |



##  <a name="access-settings"></a>Paramètres d’accès

| Paramètre | Procédure d'utilisation | Valeur(s) par défaut |
|------|------|------|
| **Exiger un code confidentiel d’accès** | Choisissez **Oui** afin d'exiger un code confidentiel pour utiliser cette application. L’utilisateur est invité à définir ce code lors de la première exécution de l’application dans un contexte professionnel ou scolaire. Valeur par défaut = **Oui**.<br><br> Configurez les paramètres suivants pour le niveau de sécurité du code confidentiel : <ul><li>**Nombre de tentatives avant réinitialisation du code confidentiel**: spécifiez le nombre de fois qu'un utilisateur doit saisir correctement son code confidentiel avant de devoir le réinitialiser. Valeur par défaut = **5**.</li><li> **Autoriser un code confidentiel simple :** choisissez **Oui** pour autoriser les utilisateurs à utiliser des séquences de code confidentiel simples telles que 1234 ou 1111. Choisissez **Non** pour empêcher l’utilisation de séquences simples. Valeur par défaut = **Oui**. </li><li> **Longueur du code confidentiel** : spécifiez le nombre minimal de chiffres d’une séquence de code confidentiel. Valeur par défaut = **4**. </li><li> **Autoriser une empreinte digitale à la place du code confidentiel (Android 6.0 et ultérieur)** : choisissez **Oui** pour autoriser l'utilisateur à se servir de [l'authentification par empreinte digitale](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) à la place d’un code confidentiel pour accéder à l’application. Valeur par défaut = **Oui**.</li></ul> Sur les appareils Android, vous pouvez laisser l’utilisateur prouver son identité à l’aide de [l’authentification par empreinte digitale Android](https://developer.android.com/about/versions/marshmallow/android-6.0.html#fingerprint-authentication) au lieu d’un code confidentiel. Quand l’utilisateur tente d'utiliser l’application à l'aide de son compte professionnel ou scolaire, il est invité à s’identifier par empreinte digitale au lieu d’entrer un code confidentiel. </li></ul>| Exiger un code confidentiel : Oui <br><br> Tentatives de réinitialisation du code confidentiel : 5 <br><br> Autoriser un code confidentiel : Oui <br><br> Longueur du code confidentiel : 4 <br><br> Autoriser l'empreinte digitale : Oui |
| **Exiger des informations d'identification d'entreprise pour l'accès** | Choisissez **Oui** pour obliger l’utilisateur à se connecter avec son compte professionnel ou scolaire au lieu d’entrer un code confidentiel pour accéder à l’application. Si vous affectez la valeur **Oui** à ce paramètre, il se substitue à l’obligation de recourir à un code confidentiel ou à un ID tactile.  | Non |
| **Bloquer l’exécution des applications gérées sur les appareils jailbreakés ou rootés** |Choisissez **Oui** pour empêcher l'exécution de cette application sur les appareils jailbreakés ou rootés. L’utilisateur peut encore utiliser cette application pour des tâches personnelles, mais il doit utiliser un autre appareil pour accéder aux données professionnelles ou scolaires dans cette application. | Oui |
| **Revérifier les exigences d'accès après (minutes)** | Configurez les paramètres suivants : <ul><li>**Délai** : il s’agit du nombre de minutes qui s’écoulent avant que les conditions d’accès (définies plus haut dans la stratégie) ne soient revérifiées. Par exemple, un administrateur active un code confidentiel dans la stratégie, un utilisateur ouvre une application GAM et doit entrer un code confidentiel. Quand ce paramètre est employé, l’utilisateur n’a pas à entrer un code confidentiel pour aucune application GAM pendant encore **30 minutes** (valeur par défaut).</li><li>**Période de grâce hors connexion** : il s’agit du nombre de minutes pendant lesquelles les applications GAM peuvent être exécutées hors connexion ; spécifiez la durée (en minutes) au bout de laquelle les conditions d’accès à l’application sont revérifiées. Valeur par défaut = **720** minutes (12 heures). Après l’expiration de cette période, l’application nécessite une authentification utilisateur auprès d’AAD pour poursuivre son exécution.</li></ul>| Délai d'expiration : 30 <br><br> Hors connexion : 720 |
| **Intervalle en mode hors connexion avant la réinitialisation des données d’application (en jours)** | Après ce nombre de jours (défini par l’administrateur) d’exécution en mode hors connexion, l’application elle-même procède à une réinitialisation sélective. Cette réinitialisation sélective est identique à celle qui peut être lancée par l’administrateur dans le flux de travail de réinitialisation GAM. <br><br> | 90 jours |
| **Bloquer la capture d'écran et l'Assistant Android (Android 6.0 et ultérieur)** | Sélectionnez **Oui** pour bloquer les fonctionnalités de capture d’écran et d’**Assistant Android** de l’appareil lors de l’utilisation de cette application. Si vous choisissez **Oui**, l’image d’aperçu du sélecteur d’application sera floue lors de l’utilisation de cette application avec un compte professionnel ou scolaire. | Non |
| **Désactiver le code PIN de l’application quand le code PIN de l’appareil est géré** | Choisissez **Oui** pour désactiver le code PIN de l’application lorsqu’un verrouillage d’appareil est détecté sur un appareil inscrit. | Non |

