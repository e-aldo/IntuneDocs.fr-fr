---
title: "Inclure des applications Android dans un wrapper avec l’outil de création de package de restrictions d’application | Microsoft Docs"
description: "Cet article explique comment inclure des applications Android dans un wrapper sans changer le code. Préparez les applications afin d’appliquer des stratégies de gestion des applications mobiles."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: a89c2b26daf2b3b4da57e0c190f772e078681bee
ms.lasthandoff: 04/14/2017


---

# <a name="prepare-android-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Préparer des applications Android pour la gestion des applications mobiles avec l'outil de création de package de restrictions d'application

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez l’outil de création de package de restrictions d’application Microsoft Intune pour Android pour changer le comportement de vos applications Android internes en limitant les fonctionnalités de l’application sans modifier le code de l’application proprement dit.

L’outil est une application en ligne de commande Windows qui s’exécute dans PowerShell et crée un wrapper autour de votre application Android. Une fois l’application encapsulée, vous pouvez modifier sa fonctionnalité en configurant des [stratégies de gestion des applications mobiles](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) dans Intune.


Avant d’exécuter l’outil, passez en revue les [considérations en matière de sécurité pour l’exécution de l’outil de création de package de restrictions d’application](#security-considerations-for-running-the-app-wrapping-tool). Pour télécharger l’outil, accédez à la page [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) (Outil de création de package de restrictions d’application Microsoft Intune pour Android) sur GitHub.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Remplir les prérequis pour l’utilisation de l’outil de création de package de restrictions d’application

-   Vous devez exécuter l’outil de création de package de restrictions d’application sur un ordinateur Windows exécutant Windows 7 ou version ultérieure.

-   Votre application d’entrée doit être un package d’application Android valide avec l’extension de fichier .apk et :

    -   elle ne doit pas être chiffrée ;
    -   elle ne doit pas avoir déjà été encapsulée par l’outil de création de package de restrictions d’application Intune ;
    -   elle doit être écrite pour Android 4.0 ou version ultérieure.

-   L’application doit être développée par ou pour votre entreprise. Vous ne pouvez pas utiliser cet outil sur des applications téléchargées à partir de Google Play Store.

-   Pour exécuter l’outil de création de package de restrictions d’application, vous devez installer la dernière version de [Java Runtime Environment](http://java.com/download/) et vous assurer que la variable de chemin d’accès de Java a pour valeur C:\ProgramData\Oracle\Java\javapath dans vos variables d’environnement Windows. Pour plus d’informations, consultez la [documentation Java](http://java.com/download/help/).

    > [!NOTE]
    > Dans certains cas, la version 32 bits de Java peut occasionner des problèmes de mémoire. Nous vous conseillons d’installer la version 64 bits.

- Android nécessite que tous les packages d’application (.apk) soient signés. Recourez à l’utilitaire Java keytool pour générer les informations d’identification nécessaires pour signer l’application de sortie encapsulée. Par exemple, la commande suivante utilise l’exécutable Java keytool.exe pour générer des clés qui peuvent être utilisées par l’outil de création de package de restrictions d’application pour signer l’application de sortie encapsulée.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    Cet exemple génère une paire de clés (une clé publique et une clé privée associée de 2 048 bits) à l’aide de l’algorithme RSA. Elle encapsule ensuite la clé publique dans un certificat auto-signé X.509 v3, qui est stocké en tant que chaîne de certificats à élément unique. Cette chaîne de certificat et la clé privée sont stockées dans une nouvelle entrée de magasin de clés nommée « mykeystorefile » et identifiée par l’alias « mykeyalias ». L’entrée de magasin de clés est valide pendant 50 000 jours.

    La commande vous invite à fournir des mots de passe pour le magasin de clés et la clé. Utilisez des mots de passe sécurisés, mais notez-les, car ils sont nécessaires pour exécuter l’outil de création de package de restrictions d’application.

    Pour obtenir une documentation détaillée sur Java, consultez [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) et le [magasin de clés](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) Java sur le site web de la documentation Oracle.

## <a name="install-the-app-wrapping-tool"></a>installer l'outil de création de package de restrictions d'application

1.  À partir du [dépôt GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), téléchargez le fichier d’installation InstallAWT.exe de l’outil de création de package de restrictions d’application Intune pour Android sur un ordinateur Windows. Ouvrez le fichier d’installation.

2.  Acceptez le contrat de licence, puis terminez l’installation.

Notez le dossier dans lequel vous avez installé l'outil. L’emplacement par défaut est : C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>exécuter l'outil de création de package de restrictions d'application

1.  Sur l’ordinateur Windows où vous avez installé l’outil de création de package de restrictions d’application, ouvrez une fenêtre PowerShell en mode administrateur.

2.  À partir du dossier où vous avez installé l’outil, importez le module PowerShell de l’outil de création de package de restrictions d’application :

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Exécutez l’outil à l’aide de la commande **invoke-AppWrappingTool**, dont la syntaxe est la suivante :
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 Le tableau suivant décrit les propriétés de la commande **invoke-AppWrappingTool** :

|Propriété|Informations|Exemple|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Chemin d'accès de l'application Android source (.apk).| |
|**-OutputPath**&lt;String&gt;|Chemin d’accès à l’application Android de sortie. S'il s'agit du même chemin de répertoire qu'InputPath, la création de package échoue.| |
|**-KeyStorePath**&lt;String&gt;|Chemin d’accès au fichier de magasin de clés qui détient la paire de clés publique/privée pour la signature.|Par défaut, les fichiers de magasin de clés sont stockés dans « C:\Program Files (x86)\Java\jreX.X.X_XX\bin ». |
|**-KeyStorePassword**&lt;SecureString&gt;|Mot de passe utilisé pour déchiffrer le magasin de clés. Android requiert la signature de tous les packages d’applications (.apk). Recourez à l’utilitaire Java keytool pour générer le mot de passe du magasin de clés (KeyStorePassword). Vous pouvez en savoir plus sur le [magasin de clés](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) Java ici.| |
|**-KeyAlias**&lt;String&gt;|Nom de la clé à utiliser pour la signature.| |
|**-KeyPassword**&lt;SecureString&gt;|Mot de passe utilisé pour déchiffrer la clé privée qui sera utilisée pour la signature.| |
|**-SigAlg**&lt;SecureString&gt;| (Facultatif) Nom de l’algorithme de signature à utiliser pour la signature. L’algorithme doit être compatible avec la clé privée.|Exemples : SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Facultatif) La commande prend en charge les paramètres PowerShell communs tels que verbose et debug. |


- Pour obtenir la liste des paramètres communs, consultez le [Centre de scripts Microsoft](https://technet.microsoft.com/library/hh847884.aspx).

- Pour afficher des informations détaillées sur l’utilisation de l’outil, entrez la commande suivante :

    ```
    Help Invoke-AppWrappingTool
    ```

**Exemple :**

Importez le module PowerShell.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Exécutez l’outil de création de package de restrictions d’application sur l’application native HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Vous êtes ensuite invité à entrer des valeurs pour **KeyStorePassword** et **KeyPassword**. Entrez les informations d’identification que vous avez utilisées pour créer le fichier de magasin de clés.

L’application encapsulée et un fichier journal sont générés et enregistrés dans le chemin de sortie spécifié.

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Considérations en matière de sécurité lors de l’exécution de l’outil de création de package de restrictions d’application
Pour empêcher l'usurpation d'identité, la divulgation d'informations et les attaques par élévation de privilège, procédez comme suit :

-   Vérifiez que l’application métier d’entrée, l’application de sortie et le magasin de clés Java se trouvent sur le même ordinateur Windows que celui sur lequel l’outil de création de package de restrictions d’application est en cours d’exécution.

-   Importez l’application de sortie dans la console Intune sur l’ordinateur où l’outil est en cours d’exécution. Pour plus d’informations sur l’utilitaire Java keytool, consultez [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Si l’application de sortie et l’outil se trouvent sur un chemin d’accès UNC (Universal Naming Convention) et que vous n’exécutez pas l’outil et les fichiers d’entrée sur le même ordinateur, sécurisez l’environnement en utilisant la [sécurité du protocole Internet (IPsec)](http://wikipedia.org/wiki/IPsec) ou la [signature SMB (Server Message Block)](https://support.microsoft.com/kb/887429).

-   Vérifiez que l’application provient d’une source approuvée.

-   Sécurisez le répertoire de sortie qui a l’application encapsulée. Envisagez d'utiliser un répertoire au niveau utilisateur pour la sortie.

### <a name="see-also"></a>Voir aussi
- [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [Utiliser le SDK pour activer des applications pour la gestion des applications mobiles](use-the-sdk-to-enable-apps-for-mobile-application-management.md)

