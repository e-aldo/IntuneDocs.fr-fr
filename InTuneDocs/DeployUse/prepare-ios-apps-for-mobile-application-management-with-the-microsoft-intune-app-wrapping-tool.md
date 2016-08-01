---
title: "Inclure des applications iOS dans un wrapper avec l’outil de création de package de restrictions d’application | Microsoft Intune"
description: "Cette rubrique explique comment inclure des applications iOS dans un wrapper sans modifier leur code. Préparez les applications afin d’appliquer des stratégies de gestion des applications mobiles."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19a5b8f8260bace2bbe3626da3df281306f53024
ms.openlocfilehash: ebd68513da55b8bb1715d2c82636abf791cae1ff


---

# Préparer des applications iOS pour la gestion des applications mobiles avec l'outil de création de package de restrictions d'application Intune
Utilisez l’outil **Microsoft Intune App Wrapping Tool for iOS** pour modifier le comportement des applications iOS internes en limitant les fonctionnalités de l’application sans modifier le code de l’application proprement dit.

L'outil est une application de ligne de commande Mac OS qui crée un « wrapper » autour d'une application. Une fois une application traitée, vous pouvez modifier sa fonctionnalité à l'aide de [stratégies de gestion des applications mobiles](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) que vous configurez.

Pour télécharger l’outil, consultez [Microsoft Intune App Wrapping Tool for iOS](http://www.microsoft.com/en-us/download/details.aspx?id=45218).

## Étape 1 : remplir les conditions préalables requises pour l’utilisation de l’outil de création de package de restrictions d’application

|Condition requise|Plus d'informations|
|---------------|--------------------------------|
|Système d’exploitation et boîte à outils pris en charge|Vous devez exécuter l'outil de création de package de restrictions d'application sur un ordinateur Mac OS X 10.8.5 ou version ultérieure sur lequel est installé la version 5 ou ultérieure de la boîte à outils XCode.|
|Certificat de signature et profil de configuration|Vous devez disposer d’un certificat de signature Apple et d’un profil de configuration. Consultez votre [documentation pour développeurs Apple](https://developer.apple.com/).|
|Traitement d’une application avec l’outil de création de package de restrictions d’application|Elle doit être développée et signée par votre entreprise ou par un éditeur de logiciels indépendant (ISV). Vous ne pouvez pas utiliser cet outil pour traiter des applications de l'Apple Store. Les applications doivent être écrites pour iOS version 7.0 ou ultérieure. Elles doivent être également au format PIE (Position Independent Executable). Pour plus d'informations sur le format PIE, consultez votre documentation pour développeurs Apple. Enfin, l’application doit avoir l'extension **.app**ou **.ipa** .|
|Applications que l’outil de création de package de restrictions d’application ne peut pas traiter|Applications chiffrées, applications non signées et applications avec des attributs de fichiers étendus.|
|Applications qui utilisent la bibliothèque ADAL (Azure Active Directory Library)|Si votre application utilise la bibliothèque ADAL, elle doit intégrer une version de la bibliothèque ADAL supérieure ou égale à la version 1.0.2 et le développeur doit accorder à leur application l’accès à la ressource de gestion des applications mobiles Intune.<br /><br />Consultez la rubrique [Informations pour les applications utilisant la bibliothèque Azure Active Directory](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#information-for-apps-that-use-the-azure-active-directory-library) dans cet article pour plus d’informations sur l’utilisation de la bibliothèque ADAL|
|Définition de droits pour votre application|Avant d’encapsuler l’application, vous devez définir des droits qui confèrent à l’application des autorisations et des fonctionnalités supplémentaires qui vont au-delà de celles qui sont généralement accordées. Consultez [Définition des droits de l’application](#setting-app-entitlements) pour obtenir des instructions.|

## Étape 2: installer l’outil de création de package de restrictions d’application

1.  À partir de la page **Microsoft Intune App Wrapping Tool for iOS** du [Centre de téléchargement Microsoft](https://www.microsoft.com/download/details.aspx?id=45218), téléchargez le fichier d'installation de l'outil de création de package de restrictions d'application sur un ordinateur Mac.

2.  Sur l’ordinateur Mac, double-cliquez sur le fichier d’installation **Microsoft Intune App Wrapping Tool for iOS.dmg**.

3.  Choisissez **J'accepte** pour accepter le contrat de licence utilisateur final (CLUF). Le programme d'installation est monté et affiché sur l'ordinateur Mac.

4.  Ouvrez le programme d’installation et copiez les fichiers affichés dans un nouveau dossier sur l’ordinateur Mac. Vous pouvez maintenant déconnecter le lecteur du programme d’installation monté.

    Vous êtes maintenant prêt à exécuter l'outil de création de package de restrictions d'application.

## Étape 3 : exécuter l’outil de création de package de restrictions d’application

1.  Sur l'ordinateur Mac, ouvrez une fenêtre de terminal et accédez au dossier où vous avez enregistré les fichiers. Étant donné que le fichier exécutable se trouve dans le package, vous devez exécuter la commande qui suit :
```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -a <client ID of input app> -r <reply URI of input app> -v true
```
    > [!NOTE]
    > Some parameters are optional as shown in the table below.

    **Example:** The following example command runs the app wrapping tool on an app named **MyApp.ipa**. A provisioning profile and SHA-1 hash are specified. The processed app is created and stored in the **/users/myadmin/Documents** on the Mac computer.

    ```
    /users/myadmin/Downloads/IntuneMAMPackager.app/Contents/MacOS/IntuneMAMPackager -i /users/myadmin/Downloads/MyApp.ipa -o /users/myadmin/Documents/MyApp_Wrapped.ipa -p /users/myadmin/Downloads/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB –a 20e1cd0d-268e-4308-9583-02ae97dd353e –r https://contoso/ -v true
    ```
    You can use the following command line properties with the app wrapping tool:

|Propriété|Plus d'informations|
  |------------|--------------------|
  |**-h**|Affiche les propriétés de ligne de commande disponibles pour l'outil de création de package de restrictions d'application.|
  |**-i**|Spécifie le chemin d'accès et le nom de fichier de l'application d'entrée.|
  |**-o**|Spécifie le chemin d'accès où enregistrer l'application traitée.|
  |**-p**|Spécifie le chemin d'accès à votre profil de configuration pour les applications iOS.|
  |**-c**|Spécifie le hachage SHA1 du certificat de signature.|
  |**-a**|ID de client de l'application d'entrée (au format GUID), si elle utilise les bibliothèques Azure Active Directory (facultatif).|
  |**-r**|URI de redirection de l'application d'entrée, si elle utilise les bibliothèques Azure Active Directory (facultatif).|
  |**-v**|Afficher des messages détaillés sur la console (facultatif).|

2. Une fois le traitement terminé, le message **The application was successfully wrapped** est affiché.

    Si une erreur se produit, consultez [Messages d'erreur](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) pour obtenir de l'aide.

3.  L'application encapsulée est enregistrée dans le dossier de sortie spécifié précédemment. Vous pouvez maintenant télécharger l'application dans [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] et l'associer à une stratégie de gestion des applications mobiles.

    > [!IMPORTANT]
    > Vous devez télécharger l'application comme nouvelle application. Vous ne pouvez pas mettre à jour une version plus ancienne et non encapsulée de l'application.

    Vous pouvez maintenant déployer l’application dans vos groupes [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Elle s’exécutera désormais sur l’appareil selon les restrictions d’applications que vous spécifiez.

## Messages d’erreur et fichiers journaux
Aidez-vous des informations suivantes pour résoudre les problèmes que vous rencontrez avec l’outil de création de package de restrictions d’application.

### Messages d'erreur
Si l'outil de création de package de restrictions d'application échoue, l'un des messages d'erreur suivants s'affiche :

|Message d'erreur|Plus d'informations|
|-----------------|--------------------|
|Vous devez spécifier un profil de configuration iOS valide.|Votre profil de configuration n'est peut-être pas valide. Vérifiez que vous avez les autorisations appropriées pour les appareils et que votre profil cible correctement le développement ou la distribution. Votre profil de configuration a peut être aussi expiré.|
|Spécifiez un nom d'application d'entrée valide.|Assurez-vous que le nom de l'application d'entrée spécifié est correct.|
|Spécifiez un chemin d'accès valide vers l'application de sortie.|Assurez-vous que le chemin d'accès à l'application de sortie que vous avez spécifié existe et est correct.|
|Spécifiez un profil de configuration d'entrée valide.|Vérifiez que vous avez fourni un nom et une extension de profil de configuration valides. Votre profil de configuration n'a peut-être pas les droits nécessaires ou vous n'avez peut-être pas inclus l'option de ligne de commande **– p**.|
|L'application d'entrée spécifiée est introuvable. Spécifiez un nom et un chemin d'accès d'application d'entrée valides.|Assurez-vous que le chemin d'accès à l'application d'entrée est valide et qu'il existe. Assurez-vous que l'application d'entrée existe à cet emplacement.|
|Le fichier de profil de configuration d'entrée spécifié est introuvable. Spécifiez un fichier de profil de configuration d'entrée valide.|Assurez-vous que le chemin d'accès au fichier de configuration d'entrée est valide et que le fichier spécifié existe.|
|Le dossier d'application de sortie spécifié est introuvable. Spécifiez un chemin d'accès valide vers l'application de sortie.|Assurez-vous que le chemin de sortie spécifié est valide et qu'il existe.|
|L'application de sortie n'a pas une extension .ipa.|Seules les applications avec les extensions **.app** et **.ipa** sont acceptées par l'outil de création de package de restrictions d'application. Assurez-vous que votre fichier de sortie a une extension valide.|
|Un certificat de signature non valide a été spécifié. Spécifiez un certificat de signature Apple valide.|Assurez-vous d'avoir téléchargé le certificat de signature correct à partir du portail de développement Apple. Votre certificat a peut-être expiré. Si votre profil de configuration et votre certificat Apple peuvent être utilisés pour signer correctement une application dans Xcode, cela signifie qu'ils sont valides pour l'outil de création de package de restrictions d'application.|
|L'application d'entrée spécifiée n'est pas valide. Spécifiez une application valide.|Assurez-vous que votre application iOS est valide et qu'elle a été compilée sous forme de fichier .app ou .ipa.|
|L'application d'entrée spécifiée est chiffrée. Spécifiez une application non chiffrée valide.|L'outil de création de package de restrictions d'application ne gère pas les applications chiffrées. Spécifiez une application non chiffrée.|
|L'application d'entrée spécifiée n'est pas au format PIE (Position Independent Executable). Spécifiez une application valide au format PIE.|Les applications PIE (Position Independent Executable) peuvent être chargées à une adresse mémoire aléatoire lors de l'exécution, ce qui peut offrir certains avantages en termes de sécurité. Pour plus d'informations, consultez votre documentation pour développeurs Apple.|
|L'application d'entrée spécifiée a déjà été encapsulée. Spécifiez une application non encapsulée valide.|Vous ne pouvez pas traiter une application qui a déjà été traitée par l'outil. Si vous souhaitez retraiter une application, exécutez l'outil à l'aide de la version d'origine de l'application.|
|L'application d'entrée spécifiée n'est pas signée. Spécifiez une application signée valide.|L'outil de création de package de restrictions d'application nécessite que les applications soient signées. Consultez votre documentation pour développeurs pour savoir comment signer une application encapsulée.|
|L'application d'entrée spécifiée doit être au format .ipa ou .app.|Seules les extensions .app et .ipa sont acceptées par l'outil de création de package de restrictions d'application. Assurez-vous que votre fichier d'entrée a une extension valide et qu'il a été compilé sous forme de fichier .app ou .ipa.|
|L'application d'entrée spécifiée a déjà été encapsulée et est à la dernière version de modèle de stratégie.|L'outil de création de package de restrictions d'application ne peut pas ré-encapsuler une application encapsulée existante avec la dernière version du modèle de stratégie.|
|L'ID client Azure Active Directory donné n'est pas un GUID correctement formé. Veuillez spécifier un ID de client valide.|Lors de l'utilisation du paramètre Client ID, vérifiez que vous avez fourni un ID client valide au format GUID.|
|L'URI de réponse Azure Active Directory donné n'est pas un URI correctement formé. Veuillez spécifier un URI de réponse valide.|Lors de l'utilisation de la propriété de ligne de commande d'URI de réponse, vérifiez que vous avez fourni un URI de réponse valide.|
|AVERTISSEMENT : vous n’avez pas spécifié de hachage de certificat SHA1. Assurez-vous que votre application encapsulée est signée avant le déploiement.|Veillez à spécifier un hachage SHA valide (à l'aide de la propriété de ligne de commande **– c** ).|

### Fichiers journaux de l'outil de création de package de restrictions d'application
Les applications qui ont été encapsulées à l'aide de l'outil de création de package de restrictions d'application génèrent des journaux qui sont écrits dans la console de l'appareil iOS client. Ces informations sont utiles dans les situations où vous rencontrez des problèmes avec l'application et vous devez identifier si le problème est lié à l'outil de création de package de restrictions d'application. Pour récupérer ces informations, procédez comme suit :

1.  Reproduisez le problème en exécutant l'application.

2.  Recueillez la sortie de console en suivant les instructions d'Apple pour le [débogage des applications iOS déployées](https://developer.apple.com/library/ios/qa/qa1747/_index.html).

3.  Filtrez les journaux enregistrés pour la sortie de Restrictions d'application en entrant le script suivant dans la console :

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Vous pouvez envoyer les journaux filtrés à Microsoft.

    > [!NOTE]
    > Dans le fichier journal, l'élément « build version » représente le numéro de build de Xcode.

    Les applications encapsulées offrent également aux utilisateurs la possibilité d'envoyer les journaux directement à partir de l'appareil par courrier électronique, après un blocage de l'application. Les utilisateurs peuvent vous envoyer le journal pour que vous l'examiniez et le transmettiez à Microsoft si nécessaire.

## Informations pour les applications utilisant la bibliothèque Azure Active Directory
Les informations contenues dans cette section concernent uniquement les applications qui utilisent la bibliothèque ADAL. Si vous ne savez pas si votre application utilise cette bibliothèque, contactez le développeur de l'application.

L'application doit intégrer une version de la bibliothèque ADAL supérieure ou égale à la version 1.0.2.

Pour les applications qui utilisent la bibliothèque ADAL, les conditions suivantes doivent être remplies :

-   L'application doit intégrer une version de la bibliothèque ADAL supérieure ou égale à la version 1.0.2.

-   Les développeurs doivent accorder à leur application l’accès à la ressource Gestion des applications mobiles Intune, comme décrit dans [Étapes à suivre pour les applications qui utilisent la bibliothèque ADAL](#steps-to-follow-for-apps-that-use-adal).

### Vue d’ensemble des identificateurs que vous devez obtenir
Les applications qui utilisent la bibliothèque ADAL doivent être inscrites via le portail de gestion Azure pour obtenir deux identificateurs uniques :

|Identificateur|Plus d'informations|Valeur par défaut|
|--------------|--------------------|-----------------|
|**Client ID**|Un identificateur GUID unique est généré pour chaque application après son inscription auprès d'Azure Active Directory.<br /><br />Si vous connaissez l’ID client spécifique de l’application, vous pouvez spécifier cette valeur. Sinon, la valeur par défaut doit être utilisée.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Redirect URI**|Valeur d'URI que les développeurs peuvent fournir lors de l'inscription de leur application auprès d'Azure Active Directory pour s'assurer que les jetons d'authentification sont retournés spécifiquement à ce point de terminaison.<br /><br />L'URI de redirection est un paramètre facultatif pour l'outil de création de package de restrictions d'application. Si vous ne le spécifiez pas, un URI par défaut est utilisé.|urn:ietf:wg:oauth:2.0:oob|


### Étapes à suivre pour les applications qui utilisent la bibliothèque ADAL

1.  Consultez la [Vue d’ensemble des identificateurs que vous devez obtenir](#overview-of-identifiers-you-need-to-get) pour identifier les valeurs que vous devez obtenir.

2.  Configurez l’accès à la gestion des applications mobiles dans Azure Active Directory en procédant comme suit :

    1. Connectez-vous à un compte Azure Active Directory existant dans le portail de gestion Azure.

    2.  Cliquez sur **Inscription d'application métier existante** dans Azure Active Directory.

    3.  Dans la section de configuration, choisissez **Configurez l'accès aux API web dans d'autres applications**.

    4.  Dans la section **Autorisations pour d’autres applications**, choisissez **Gestion des applications mobiles Intune** dans la première liste déroulante.

        Vous pouvez maintenant utiliser l’ID client de l’application dans l’outil de création de package de restrictions d’application. Vous trouverez l’ID client de l’application dans le portail de gestion Azure Active Directory, comme décrit dans la section [Vue d’ensemble des identificateurs que vous devez obtenir](#overview-of-identifiers-you-need-to-get).

3.  Utilisez les valeurs de **Client-ID** (en utilisant la propriété **–a**) et **Redirect-URI** comme propriétés de ligne de commande dans l’outil de création de package de restrictions d’application. Si vous n’avez pas ces valeurs, les valeurs par défaut sont utilisées. Vous devez spécifier les deux valeurs, sinon l’utilisateur final ne pourra pas s’authentifier auprès de l’application traitée.

### Exigences concernant le certificat, le profil de configuration et l’authentification

|Exigence|Détails|
|---------------|-----------|
|Profil de configuration|**Vérifiez que le profil de configuration est valide avant de l’inclure** - L'outil de création de package de restrictions d'application ne vérifie pas si le profil de configuration a expiré lors du traitement d'une application iOS. Si vous spécifiez un profil de configuration ayant expiré, l’outil de création de package de restrictions d’application inclut le profil de configuration ayant expiré, et vous ne découvrez le problème qu’une fois que l’installation de l’application a échoué sur un appareil iOS.|
|Certificat|**Assurez-vous que le certificat est valide avant de le spécifier** - L'outil ne vérifie pas si un certificat a expiré lors du traitement d’applications iOS. Si vous fournissez le hachage d'un certificat ayant expiré, l'outil traitera et signera l'application, mais l'installation sur les appareils échouera.<br /><br />**Assurez-vous que le certificat fourni pour signer l'application empaquetée a une correspondance dans le profil de configuration** - L'outil ne vérifie pas si le profil de configuration a une correspondance pour le certificat fourni pour signer l'application encapsulée.|
|Authentification|Pour que le chiffrement fonctionne, un code confidentiel doit être défini pour l'appareil. Sur les appareils sur lesquels vous avez déployé une application encapsulée, une pression sur la barre d'état sur l'appareil exigera de l'utilisateur qu'il se réauthentifie auprès de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. La stratégie par défaut dans une application encapsulée est l’*authentification lors du redémarrage*. iOS gère toutes les notifications externes (par exemple, un appel téléphonique) en quittant l’application, puis en la redémarrant.<br /><br />Pour les applications encapsulées, le premier utilisateur qui se connecte à une application encapsulée du même éditeur est mis en cache. Après cela, seul cet utilisateur est autorisé à accéder à l'application. Pour réinitialiser l'utilisateur, l'appareil doit être désinscrit puis réinscrit.|

### Résolution des problèmes et notes techniques concernant la bibliothèque ADAL

-   Si aucune ressource ADAL n'est trouvée, l'outil inclut la bibliothèque dynamique ADAL. L'outil recherche la bibliothèque ADAL nommée **ADALiOS.bundle** dans le dossier racine.

-   L'outil ne recherche pas de binaires ADAL (le cas échéant) dans l'application. Si l'application est liée à une version obsolète, des erreurs d'exécution peuvent se produire pendant la connexion si des stratégies d'authentification sont activées.

-   [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] extrait le jeton AAD dans l'ID de ressource MAM [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] pour l'authentification. Cependant, le jeton n’est pas utilisé dans les appels qui vérifieraient à leur tour la validité du jeton. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] lit uniquement le nom d’utilisateur principal (UPN) de l’utilisateur connecté pour déterminer l’accès de l’application. Le jeton AAD n'est utilisé pour aucun autre appel de service.

-   Les jetons d'authentification sont partagés entre les applications du même éditeur, car ils sont stockés dans un trousseau partagé. Si vous souhaitez isoler une application spécifique, vous devez utiliser un certificat de signature et un profil de configuration différents pour cette application.

-   Vous pouvez éviter les invites de connexion en double si vous fournissez l'ID client et l'URI de redirection de votre application cliente. Cet ID client doit être inscrit pour accéder à l'ID de ressource MAM [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] publiée dans le tableau de bord AAD. Si ce n'est pas le cas, un échec de connexion se produit lors de l'exécution de l'application.

## Définition des droits de l’application
Avant d’encapsuler votre application, vous pouvez lui accorder des **droits** dans le but de lui octroyer des autorisations et des fonctionnalités supplémentaires qui vont au-delà de ce qu’une application peut généralement faire.  Un **fichier de droits** est utilisé pendant la signature du code pour spécifier des autorisations spéciales dans votre application (par exemple, l’accès à un trousseau partagé). Des services d’application spécifiques appelés **capabilities** (fonctionnalités) sont activés dans Xcode pendant le développement de l’application. Une fois activées, les fonctionnalités apparaissent dans votre fichier de droits. Pour plus d’informations sur les droits et les fonctionnalités, consultez [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Ajout de fonctionnalités) dans la bibliothèque du développeur iOS. Pour obtenir la liste complète des fonctionnalités prises en charge, consultez [Supported capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) (Fonctionnalités prises en charge).

### Fonctionnalités prises en charge pour App Wrapping Tool for iOS

|Fonctionnalité|Description|Recommandation|
|--------------|---------------|------------------------|
|App Groups|App Groups (groupes d’applications) permet d’autoriser plusieurs applications à accéder à des conteneurs partagés et d’autoriser une communication interprocessus supplémentaire entre les applications.<br /><br />Pour activer App Groups, ouvrez le volet **Capabilities**, puis cliquez sur le commutateur **ON** dans la section **App Groups**. Vous pouvez ajouter des groupes d’applications en ou sélectionner des existants.|Quand vous utilisez App Groups, utilisez la notation DNS inverse :<br /><br />*group.com.companyName.AppGroup*|
|Background Modes|L'activation de Background Modes (modes d’arrière-plan) permet à votre application iOS de continer à s’exécuter en arrière-plan.||
|Data Protection|Data Protection (protection des données) ajoute un niveau de sécurité aux fichiers stockés sur le disque par votre application iOS. Data Protection utilise le matériel de chiffrement intégré présent sur certains appareils pour stocker les fichiers dans un format chiffré sur disque. Votre application doit être configurée pour utiliser Data Protection.||
|In-App Purchase|In-App Purchase (achat dans l’application) incorpore un store directement dans votre application. Vous pouvez vous y connecter et traiter les paiements de l’utilisateur en toute sécurité. Vous pouvez utiliser In-App Purchase pour récupérer les paiements en contrepartie de fonctionnalités améliorées ou de contenu supplémentaire que votre application peut exploiter.||
|Keychain Sharing|L’activation de Keychain Sharing (partage de trousseau) permet à votre application de partager des mots de passe dans le trousseau avec les autres applications développées par votre équipe.|Quand vous utilisez Keychain Sharing, utilisez la notation DNS inverse :<br /><br />*com.companyName.KeychainGroup*|
|Personal VPN|Activez Personal VPN (VPN personnel) pour permettre à votre application de créer et contrôler une configuration VPN système personnalisée à l’aide de l’infrastructure Network Extension.||
|Push Notifications|Le service de notification Push Apple (APN) permet à une application qui ne s’exécute pas au premier plan de notifier l’utilisateur que des informations sont à sa disposition.|Pour que les notifications Push fonctionnent, vous devez utiliser un profil de configuration spécifique à l’application.<br /><br />Suivez la procédure décrite dans la [documentation pour développeurs Apple](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Wireless Accessory Configuration|L’activation de Wireless Accessory Configuration (configuration d’accessoire sans fil) a pour effet d’ajouter l’infrastructure External Accessory à votre projet et permet à votre application de configurer les accessoires Wi-Fi MFi.||

### Étapes d’activation des droits

1.  Activez les fonctionnalités dans votre application :

    1.  Dans Xcode, accédez à la cible de votre application, puis cliquez sur le volet **Capabilities**.

    2.  Activez les fonctionnalités appropriées. Pour obtenir des informations détaillées sur chaque fonctionnalité et pour savoir comment déterminer les valeurs correctes, consultez [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) dans la bibliothèque du développeur iOS.

    3.  Notez les ID que vous avez créés pendant le processus.

    4.  Générer et signez votre application à encapsuler.

2.  Activez les droits dans votre profil de configuration :

    1.  Connectez-vous à l’Apple Developer Member Center.

    2.  Créez un profil de configuration pour votre application. Pour obtenir des instructions, consultez la page [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Comment obtenir la configuration requise pour Intune App Wrapping Tool for iOS).

    3.  Dans votre profil de configuration, activez les mêmes droits que ceux que vous avez dans votre application. Vous devez fournir les mêmes ID que ceux que vous avez spécifiés pendant le développement de votre application.

    4.  Complétez l’Assistant de configuration de profil, puis téléchargez votre fichier.

3.  Assurez-vous que vous avez rempli toutes les conditions préalables, puis encapsulez l’application.

### Résolution des erreurs courantes liées aux droits
Si App Wrapping Tool for iOS affiche une erreur de droit, essayez d’exécuter les étapes de dépannage suivantes.

|Problème|Cause|Résolution|
|---------|---------|--------------|
|Impossible d’analyser les droits générés à partir de l’application d’entrée.|L’outil de création de package de restrictions d’application ne peut pas lire le fichier de droits qui a été extrait de l’application. Le fichier de droits est peut être incorrect.|Examinez le fichier de droits de votre application. Pour ce faire, suivez les instructions détaillées ci-dessous. Au moment d’inspecter le fichier de droits, assurez-vous que la syntaxe est correcte. Le fichier doit être au format XML.|
|Il manque des droits dans le profil de configuration (les droits manquants sont répertoriés). Recréez le package de l’application avec un profil de configuration qui contienne ces droits.|Il y a une incohérence entre les droits activés dans le profil de configuration et les fonctionnalités activées dans l’application. Cette incohérence vaut aussi pour les ID associés à des fonctionnalités particulières (par exemple, App Groups, Keychain Access, etc.).|En règle générale, vous pouvez créer un nouveau profil de configuration qui active les mêmes fonctionnalités que l’application. Quand les ID du profil et de l’application ne correspondent pas, l’outil de création de package de restrictions d’application remplace les ID, dans la mesure du possible. Si vous obtenez encore cette erreur après avoir créé un profil de configuration, vous pouvez essayer de supprimer les droits de l’application à l’aide du paramètre **–e** (voir la section « Utilisation du paramètre –e pour supprimer les droits d’accès » ci-dessous).|

### Recherche des droits existants d’une application signée
Pour examiner les droits existants d’une application signée et le profil de configuration :

1.  Recherchez le fichier .ipa et remplacez son extension par .zip.

2.  Développez le fichier .zip. Un dossier Payload contenant votre ensemble .app est alors généré.

3.  Utilisez l’outil codesign pour vérifier les droits de l’ensemble .app comme suit :

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```
    `YourApp.app` correspondant au nom effectif de votre ensemble .app.

4.  Utilisez l’outil de sécurité pour vérifier les droits du profil de configuration incorporé de l’application :

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```
    `YourApp.app` correspondant au nom effectif de votre ensemble .app.

### Utilisation du paramètre –e pour supprimer les droits d’accès d’une application
Cette commande supprime toutes les fonctionnalités activées dans l’application qui ne figurent pas dans le fichier de droits. Si vous supprimez des fonctionnalités qui sont utilisées par l’application, elle risque de se bloquer. Vous pourriez par exemple supprimer des fonctionnalités manquantes si vous avez une application générée par un fournisseur qui dispose de toutes les fonctionnalités par défaut.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## Sécurité et confidentialité pour l'outil de création de package de restrictions d'application
Respectez les meilleures pratiques de sécurité et de confidentialité suivantes lors de l'utilisation de l'outil de création de package de restrictions d'application.

-   Le certificat de signature, le profil de configuration et l'application métier que vous spécifiez doivent se trouver sur le même ordinateur Mac que celui que vous utilisez pour exécuter l'outil de création de package de restrictions d'application. Si les fichiers se trouvent sur un chemin UNC, assurez-vous qu'ils sont accessibles à partir de l'ordinateur Mac. Le chemin d'accès doit être sécurisé via la signature SMB ou la sécurité IPsec.

    L'application encapsulée importée dans la console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] doit se trouver sur le même ordinateur que celui sur lequel vous exécutez l'outil. Si le fichier se trouve dans un chemin UNC, assurez-vous qu'il est accessible sur l'ordinateur qui exécute la console [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Le chemin d'accès doit être sécurisé via la signature SMB ou la sécurité IPsec.

-   L'environnement où l'outil de création de package de restrictions d'application est téléchargé à partir du site du Centre de téléchargement Microsoft doit être sécurisé via la signature SMB ou la sécurité IPsec.

-   L'application que vous traitez doit provenir d'une source digne de confiance, pour garantir la protection contre les attaques.

-   Assurez-vous que le dossier de sortie que vous spécifiez dans l'outil de création de package de restrictions d'application est sécurisé, en particulier s'il s'agit d'un dossier distant.

-   Les applications iOS qui incluent une boîte de dialogue de téléchargement de fichier peuvent permettre aux utilisateurs de contourner les restrictions relatives aux opérations couper, copier et coller appliquées à l'application. Par exemple, un utilisateur peut utiliser la boîte de dialogue de téléchargement de fichier pour télécharger une capture d'écran des données de l'application.

-   Quand les utilisateurs analysent le dossier de documents sur leur appareil depuis une application encapsulée, ils risquent de voir un dossier nommé **.msftintuneapplauncher**. Si ce dossier est modifié ou supprimé, cela peut affecter le bon fonctionnement des applications restreintes.

### Voir aussi
- [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Utiliser le Kit de développement logiciel (SDK) pour activer des applications pour la gestion des applications mobiles](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO4-->


