---
title: "Inclure des applications Android dans un wrapper avec l’outil de création de package de restrictions d’application | Microsoft Intune"
description: "Cette rubrique explique comment inclure des applications Android dans un wrapper sans modifier le code. Préparez les applications afin d’appliquer des stratégies de gestion des applications mobiles."
keywords: 
author: karthikaraman
manager: arob98
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2038ed6219a94dc4285891d71ce00fd51310f3e3
ms.openlocfilehash: 15d0877f799c89e2a8af65c416c0e914f898641f


---

# Préparer des applications Android pour la gestion des applications mobiles avec l'outil de création de package de restrictions d'application
Utilisez l'**outil de création de package de restrictions d'application Microsoft Intune pour Android** pour modifier le comportement de vos applications Android internes dans le but de configurer les fonctionnalités de l'application sans modifier le code de l'application proprement dit.

L'outil est une application de ligne de commande Windows qui s'exécute dans PowerShell et crée un « wrapper » autour de votre application. Une fois l'application traitée, vous pouvez modifier sa fonctionnalité à l'aide de [stratégies de gestion des applications mobiles](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) que vous configurez.

Si votre application utilise l’Azure Active Directory Authentication Library (ADAL), vous devez effectuer les étapes décrites dans [Comment inclure dans un wrapper des applications qui utilisent la bibliothèque Azure Active Directory Library](#how-to-wrap-apps-that-use-the-azure-active-directory-library) avant d'inclure votre application dans un wrapper. Si vous ne savez pas si votre application utilise cette bibliothèque, contactez le développeur de l'application.

Avant d'exécuter l'outil, passez en revue les [considérations en matière de sécurité pour l'exécution de l'outil de création de package de restrictions d'application](#security-considerations-for-running-the-app-wrapping-tool). Pour télécharger l’outil, consultez [Outil de création de package de restrictions d’application Microsoft Intune pour Android](https://www.microsoft.com/download/details.aspx?id=47267).

## Étape 1 : remplir les conditions préalables requises pour l’utilisation de l’outil de création de package de restrictions d’application

-   Vous devez exécuter l'outil de création de package de restrictions d'application sur un ordinateur Windows exécutant Windows 7 ou version ultérieure.

-   Votre application d'entrée doit être un package d'application Android valide avec l'extension de fichier **.apk** et :

    -   elle ne doit pas être chiffrée ;

    -   elle ne doit pas avoir déjà été encapsulée par l'outil de création de package de restrictions d'application ;

    -   elle doit être écrite pour Android 4.0 ou version ultérieure.

-   L'application doit être développée par ou pour votre entreprise. Vous ne pouvez pas utiliser cet outil pour traiter des applications téléchargées depuis la boutique Google Play.

-   Pour exécuter l'outil de création de package de restrictions d'application, vous devez installer la dernière version de [Java Runtime Environment](http://java.com/download/) et vous assurer que la variable de chemin d'accès de Java a pour valeur **C:\ProgramData\Oracle\Java\javapath** dans vos variables d'environnement Windows. Pour plus d'informations, consultez votre [documentation Java](http://java.com/download/help/).

    > [!NOTE]
    > Dans certains cas, la version 32 bits de Java peut occasionner des problèmes de mémoire. Nous vous recommandons d'installer plutôt la version 64 bits.

## Étape 2: installer l’outil de création de package de restrictions d’application

1.  À partir du Centre de téléchargement Microsoft, téléchargez le fichier d'installation de l'outil de création de package de restrictions d'application sur un ordinateur Windows, puis ouvrez-le.

2.  Acceptez le contrat de licence, puis terminez l'installation.

Notez le dossier dans lequel vous avez installé l'outil. L’emplacement par défaut est : **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Étape 3 : exécuter l’outil de création de package de restrictions d’application

1.  Sur l’ordinateur Windows où vous avez installé l’outil de création de package de restrictions d’application, ouvrez une fenêtre PowerShell en mode administrateur.

2.  À partir du dossier où vous avez installé l'outil, importez le module PowerShell de l'outil de création de package de restrictions d'application :

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Exécutez l'outil en utilisant la commande **invoke-AppWrappingTool** avec les paramètres suivants. Les paramètres dits « facultatifs » s'adressent aux applications qui utilisent Azure Active Directory Library (ADAL). Pour plus d’informations, consultez [Comment inclure dans un wrapper des applications qui utilisent la bibliothèque Azure Active Directory Library](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

|Paramètre|Plus d'informations|Exemples|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Chemin d'accès de l'application Android source (.apk).| |
|**-OutputPath**&lt;String&gt;|Chemin d'accès à l'application Android de « sortie ». S'il s'agit du même chemin de répertoire qu'InputPath, la création de package échoue.| |
|**-KeyStorePath**&lt;String&gt;|Chemin d'accès au fichier de magasin de clés qui contient la paire de clés publique/privée pour la signature.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Mot de passe utilisé pour déchiffrer le magasin de clés. Android requiert la signature de tous les packages d’applications (.apk). Utilisez Keytool Java pour générer le KeyStorePassword comme indiqué dans l’exemple. En savoir plus sur le [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;String&gt;|Nom de la clé à utiliser pour la signature.| |
|**-KeyPassword**&lt;SecureString&gt;|Mot de passe utilisé pour déchiffrer la clé privée qui sera utilisée pour la signature.| |
|**-SigAlg**&lt;SecureString&gt;|Nom de l’algorithme de signature à utiliser pour la signature. L’algorithme doit être compatible avec la clé privée.|Exemples : SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|ID client Azure Active Directory de l'application d'entrée (facultatif).| |
|**-AuthorityURI**&lt;Uri&gt;|URI d'autorité Azure Active Directory de l'application d'entrée (facultatif).| |
|**-SkipBroker**&lt;Boolean&gt;|Indique si l'application d'entrée prend en charge l'authentification unique répartie à l'échelle de l'appareil (facultatif). |**True** : l'application d'entrée ne prend pas en charge l'authentification unique répartie à l'échelle de l'appareil. Utilisez le paramètre NonBrokerRedirectURI. **False** : l'application d'entrée prend en charge l'authentification unique répartie à l'échelle de l'appareil.|
|**-NonBrokerRedirectURI**&lt;URI&gt;|URI de redirection Azure Active Directory à utiliser si SkipBroker a la valeur true (facultatif).|  |


**&lt;CommonParameters&gt;**
 (facultatif : prend en charge les paramètres PowerShell communs tels que verbose, debug, etc.)

- Pour obtenir la liste des paramètres communs, consultez le [Centre de scripts Microsoft](https://technet.microsoft.com/library/hh847884.aspx).

- Pour afficher l'aide de l'outil, entrez la commande suivante :

    ```
    Help Invoke-AppWrappingTool
    ```
- Pour plus d’informations sur l’intégration d’Azure Active Directory (AAD), consultez la page [Comment inclure dans un wrapper des applications qui utilisent l’Azure Active Directory Library](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Exemple :**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

Vous êtes ensuite invité à entrer des valeurs pour **KeyStorePassword** et **KeyPassword**.

L'application encapsulée est générée et enregistrée dans le chemin de sortie spécifié avec un fichier journal.

## Considérations en matière de sécurité lors de l'exécution de l'outil de création de package de restrictions d'application
Pour empêcher l'usurpation d'identité, la divulgation d'informations et les attaques par élévation de privilège, procédez comme suit :

-   Vérifiez que l'application métier d'entrée, l'application de sortie et le KeyStore Java figurent sur le même ordinateur sur lequel l'outil de création de package de restrictions d'application est exécuté.

-   Importez l'application de sortie dans la console Intune sur l’ordinateur sur lequel l'outil est exécuté. Consultez [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) pour plus d’informations sur Keytool Java.

-   Si l'application de sortie et l'outil se trouvent sur un chemin d'accès UNC (Universal Naming Convention) et que vous n'exécutez pas l'outil et les fichiers d'entrée sur le même ordinateur, sécurisez l'environnement en utilisant la [sécurité du protocole Internet (IPsec)](http://en.wikipedia.org/wiki/IPsec) ou la [signature SMB (Server Message Block)](https://support.microsoft.com/en-us/kb/887429).

-   Vérifiez que l'application provient d'une source fiable. Cela est particulièrement vrai si vous utilisez Azure Active Directory (AAD), car ce service peut autoriser l'application à accéder au jeton AAD pendant l'exécution.

-   Sécurisez le répertoire de sortie contenant l'application encapsulée. Envisagez d'utiliser un répertoire au niveau utilisateur pour la sortie.

## Comment inclure dans un wrapper des applications qui utilisent l’Azure Active Directory Library
Si votre application utilise la bibliothèque ADAL, vous devez effectuer ces étapes avant d'inclure votre application dans un wrapper.

### Étape 1 : vérifier que vous remplissez les conditions requises pour la bibliothèque ADAL
Pour les applications qui utilisent la bibliothèque ADAL, les conditions suivantes doivent être remplies :

-   L'application doit intégrer une version de la bibliothèque ADAL supérieure ou égale à la version 1.0.2.

-   Les développeurs doivent accorder à leur application l’accès à la ressource Gestion des applications mobiles Intune, comme décrit à [l’étape 3 : configurer l’accès à la gestion des applications mobiles dans AAD](#step-3-configure-access-to-mobile-app-management-in-aad).

### Étape 2 : déterminer les identificateurs dont vous avez besoin pour l’inscription de l’application
À la prochaine étape, vous inscrirez vos applications (qui utilisent la bibliothèque ADAL avec Azure Active Directory (AAD)) via le portail de gestion Azure pour obtenir les identificateurs uniques répertoriés dans le tableau suivant. Vous communiquerez ensuite ces identificateurs au développeur au moment d'intégrer la bibliothèque ADAL à l'application.

|Identificateur|Plus d'informations|Valeur par défaut|
|--------------|--------------------|-----------------|
|**ID client**|Identificateur GUID unique généré pour l'application après avoir été inscrite auprès d'AAD.<br /><br />Si vous connaissez l'ID client de l'application, spécifiez cette valeur. Sinon, utilisez la valeur par défaut.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**URI d'autorité**|Valeur d'URI (Uniform Resource Identifier) d'autorité pour les objets AAD (par exemple, les utilisateurs et les groupes).<br /><br />Le paramètre AuthorityURI est facultatif pour l'outil de création de package de restrictions d'application. Si vous n'utilisez pas le paramètre, l'URI par défaut est utilisé.||
|**SkipBroker**|Valeur indiquant si le portail d'entreprise sera utilisé comme service Broker.<br /><br />**True** : le portail d'entreprise ne sera pas utilisé pour l'authentification ADAL.<br /><br />**False** : le portail d'entreprise sera utilisé pour l'authentification ADAL. Le portail d'entreprise utilise l'utilisateur inscrit à des fins d'authentification unique.||
|**URI de redirection non broker**|URI de connexion à utiliser quand la bibliothèque ADAL n'utilise pas l'application broker (portail d'entreprise Intune).|urn:ietf:wg:oauth:2.0:oob|
|**ID de ressource**|Pointeur vers les ressources AAD de l'application.||

### Étape 3 : configurer l’accès à la gestion des applications mobiles dans AAD
Avant de pouvoir utiliser les valeurs d'inscription AAD d'une application dans l'outil de création de package de restrictions d'application, le développeur doit accorder à l'application l'accès à la ressource de gestion des applications mobiles Intune en procédant comme suit :

1.  Se connecter à un compte AAD existant dans le portail de gestion Azure.

2.  Choisissez l’**inscription d’application métier existante**.

3.  Dans la section de **configurer** , choisir **Configurer l'accès aux API web dans d'autres applications**.

4.  Dans la première liste déroulante de la section **Autorisations pour d’autres applications**, choisissez **Gestion des applications mobiles Intune**.

Vous pouvez maintenant utiliser l'ID client de l'application dans l'outil de création de package de restrictions d'application. Vous trouverez l’ID client dans le portail de gestion Azure Active Directory, comme décrit dans le tableau de l’[Étape 2 : déterminer les identificateurs dont vous avez besoin pour l’inscription de l’application](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app).

### Étape 4 : utiliser les valeurs d’identificateur AAD dans l’outil de création de package de restrictions d’application
Dans l'outil de création de package de restrictions d'application, entrez les valeurs d'identificateur que vous avez obtenues durant le processus d'inscription en tant que propriétés de ligne de commande. Vous devez spécifier dans l'ordre toutes les valeurs figurant dans le tableau pour permettre aux utilisateurs finaux d'authentifier correctement l'application. Si vous ne spécifiez pas de valeurs, les valeurs par défaut sont utilisées.

|Identificateur|Paramètre|
|--------------|-------------|
|ID client|ClientID|
|URI d'autorité|Authority-URI|
|SkipBroker|SkipBroker|
|URI de redirection non broker|NonBrokerRedirectURI|
|ID de ressource|ResourceID|
Gardez à l'esprit les points suivants au moment d'inclure votre application dans un wrapper :

-   Pour vérifier que l’authentification a réussi, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] extrait le jeton AAD associé à l’ID de ressource de gestion des applications mobiles. Cependant, le jeton n'est pas utilisé dans les appels qui vérifieraient à leur tour la validité du jeton. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lit uniquement le nom d'utilisateur principal (UPN) de l'utilisateur connecté pour déterminer l'accès de l'application. Le jeton AAD n'est utilisé pour aucun autre appel de service.

-   Vous pouvez éviter les invites de connexion en double si vous fournissez l'ID client et l'URI d'autorité de votre application cliente. Vous devez inscrire l'ID client pour lui permettre d'accéder à l'ID de ressource MAM [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] publié dans le tableau de bord AAD. Si vous n'inscrivez pas l'ID client, les utilisateurs obtiennent un échec de connexion pendant l'exécution de l'application.


### Voir aussi
- [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Utiliser le Kit de développement logiciel (SDK) pour activer des applications pour la gestion des applications mobiles](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


