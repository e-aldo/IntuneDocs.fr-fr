---
title: "Inclure des applications iOS dans un wrapper avec l’outil de création de package de restrictions d’application Intune | Microsoft Intune"
description: "Cette rubrique explique comment inclure des applications iOS dans un wrapper sans changer leur code. Préparez les applications afin d’appliquer des stratégies de gestion des applications mobiles."
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99ab0369-5115-4dc8-83ea-db7239b0de97
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b25c7d7063ce586bb1cd960534f3e2ed57f6aec4
ms.openlocfilehash: f70a32cf7db4d46f15cdef85e111a8857a1a0215


---

# <a name="prepare-ios-apps-for-mobile-application-management-with-the-intune-app-wrapping-tool"></a>Préparer des applications iOS pour la gestion des applications mobiles avec l'outil de création de package de restrictions d'application Intune

Utilisez l’outil Microsoft Intune App Wrapping Tool for iOS pour changer le comportement des applications iOS internes en limitant les fonctionnalités de l’application sans modifier le code de l’application proprement dit.

L’outil est une application en ligne de commande macOS qui crée un wrapper autour d’une application. Une fois qu’une application est traitée, vous pouvez modifier sa fonctionnalité à l’aide de [stratégies de gestion des applications mobiles](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) Intune que vous configurez.

Pour télécharger l’outil, consultez [Microsoft Intune App Wrapping Tool for iOS](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) (Outil de création de package de restrictions d’application Microsoft Intune pour iOS).



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Remplir les prérequis pour l’utilisation de l’outil de création de package de restrictions d’application
Consultez [Skype for Business Online: Enable your tenant for modern authentication](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) (Skype Entreprise Online : activer votre client pour l’authentification moderne) pour en savoir plus sur les prérequis et sur la façon de les définir.

|Condition requise|Plus d'informations|
|---------------|--------------------------------|
|Système d’exploitation et boîte à outils pris en charge|Vous devez exécuter l’outil de création de package de restrictions d’application sur un ordinateur macOS exécutant la version X 10.8.5 ou ultérieure et sur lequel est installé l’ensemble d’outils XCode version 5 ou ultérieure.|
|Certificat de signature et profil de configuration|Vous devez disposer d’un certificat de signature Apple et d’un profil de configuration. Consultez votre [documentation pour développeurs Apple](https://developer.apple.com/).|
|Traitement d’une application avec l’outil de création de package de restrictions d’application|Elle doit être développée et signée par votre entreprise ou par un éditeur de logiciels indépendant (ISV). Vous ne pouvez pas utiliser cet outil pour traiter des applications de l'Apple Store. Les applications doivent être écrites pour iOS version 8.0 ou ultérieure. Elles doivent être également au format PIE (Position Independent Executable). Pour plus d’informations sur le format PIE, consultez votre documentation pour développeurs Apple. Enfin, l’application doit avoir l’extension **.app** ou **.ipa**.|
|Applications que l’outil ne peut pas traiter|Applications chiffrées, applications non signées et applications avec des attributs de fichiers étendus.|
|Définition de droits pour votre application|Avant d’encapsuler l’application, vous devez définir des droits qui confèrent à l’application des autorisations et des fonctionnalités supplémentaires qui vont au-delà de celles qui sont généralement accordées. Consultez [Définition des droits de l’application](#setting-app-entitlements) pour obtenir des instructions.|

## <a name="install-the-app-wrapping-tool"></a>installer l'outil de création de package de restrictions d'application

1.  Téléchargez les fichiers de l’outil de création de package de restrictions d’application à partir du dépôt de l’[outil de création de package de restrictions d’application pour iOS hébergé sur GitHub](https://github.com/msintuneappsdk/intune-app-wrapping-tool-ios) sur un ordinateur macOS.

2.  Double-cliquez sur **Microsoft Intune App Wrapping Tool for iOS.dmg**. Une fenêtre présentant le Contrat de licence utilisateur final (CLUF) s’affiche. Lisez attentivement le document.

3. Choisissez **J’accepte** pour accepter le CLUF, qui monte le package sur votre ordinateur.

4.  Ouvrez IntuneMAMPackager et enregistrez les fichiers dans un dossier local de votre ordinateur macOS. Vous êtes maintenant prêt à exécuter l’outil de création de package de restrictions d’application.

## <a name="run-the-app-wrapping-tool"></a>Exécuter l'outil de création de package de restrictions d'application
* Ouvrez un terminal et accédez au dossier où vous avez enregistré les fichiers de l’outil de création de package de restrictions d’application. L’outil exécutable se nomme IntuneMAMPackager et se trouve dans IntuneMAMPackager/Contents/MacOS. Exécutez la commande suivante :

    ```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> -p /<path to provisioning profile> -c <SHA1 hash of the certificate> [-b [<output app build string>]] [-v] [-e] [-x /<array of extension provisioning profile paths>]

    ```

    > [!NOTE]
    > Certains paramètres sont facultatifs, comme indiqué dans le tableau suivant.

    **Exemple :** l’exemple de commande suivant exécute l’outil de création de package de restrictions d’application sur l’application MyApp.ipa. Un profil de configuration et le hachage SHA-1 sont spécifiés. L’application traitée (MyApp_Wrapped.ipa) est créée et stockée dans votre dossier Bureau.

    ```
    ./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager -i ~/Desktop/MyApp.ipa -o ~/Desktop/MyApp_Wrapped.ipa -p ~/Desktop/My_Provisioning_Profile_.mobileprovision -c 12A3BC45D67EF8901A2B3CDEF4ABC5D6E7890FAB  -v true
    ```
    Vous pouvez utiliser les propriétés de ligne de commande suivantes avec l’outil de création de package de restrictions d’application :

|Propriété|Comment l’utiliser|
|---------------|--------------------------------|
|**-i**|`<Path of the input native iOS application file>`. Le nom de fichier doit se terminer par .app ou .ipa. |
|**-o**|`<Path of the wrapped output application>` |
|**-p**|`<Path of your provisioning profile for iOS apps>`|
|**-c**|`<SHA1 hash of the signing certificate>`|
|**-h**|Affiche des informations détaillées sur l’utilisation des propriétés de ligne de commande disponibles pour l’outil de création de package de restrictions d’application.|
|**-v**|(Facultatif) Affiche les messages détaillés sur la console.|
|**-e**| (Facultatif) Utilisez cet indicateur pour que l’outil de création de package de restrictions d’application supprime les droits manquants pendant le traitement de l’application. Pour plus d’informations, consultez Définition des droits de l’application.|
|**-xe**| (Facultatif) Imprime des informations sur les extensions iOS dans l’application et les droits qui sont nécessaires pour les utiliser. Pour plus d’informations, consultez Définition des droits de l’application. |
|**-x**| (Facultatif) `<An array of paths to extension provisioning profiles>`. À utiliser si votre application a besoin d’extension des profils d’approvisionnement d’extension.|
|**-f**|(Facultatif) `<Path to a plist file specifying arguments.>` Utilisez cet indicateur devant le fichier [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) si vous choisissez d’utiliser le modèle plist pour spécifier le reste des propriétés IntuneMAMPackager telles que -i, -o et -p. Consultez Utiliser un fichier plist pour les arguments d’entrée. |
|**-b**|(Facultatif) Utilisez -b sans argument si vous voulez que l’application de sortie encapsulée ait la même version d’ensemble (bundle) que l’application d’entrée (non recommandé). <br/><br/> Utilisez `-b <custom bundle version>` si vous voulez que l’application encapsulée ait une valeur CFBundleVersion personnalisée. Si vous choisissez de spécifier une valeur CFBundleVersion personnalisée, pensez à incrémenter la valeur CFBundleVersion de l’application native sur le composant le moins significatif, par exemple, 1.0.0 -> 1.0.1. |

### <a name="use-a-plist-to-input-arguments"></a>Utiliser un fichier plist pour les arguments d’entrée
Placer tous les arguments de commande dans un fichier [plist](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/PropertyLists/Introduction/Introduction.html) constitue un moyen simple d’exécuter l’outil de création de package de restrictions d’application. Plist est un format de fichier similaire à XML que vous pouvez utiliser pour vos arguments de ligne de commande à l’aide d’une interface de formulaire.

Dans le dossier IntuneMAMPackager/contenu/MacOS, ouvrez `Parameters.plist` (un modèle plist vide) à l’aide d’un éditeur de texte ou Xcode. Entrez vos arguments pour les clés suivantes :

| Clé plist |  Valeur par défaut| Remarques |
|------------------|--------------|-----|
| Chemin du package d’application d’entrée  |empty| Identique à -i|
| Chemin du package d’application de sortie |empty| Identique à -o|
| Chemin du profil d’approvisionnement |empty| Identique à -p|
| Hachage du certificat SHA-1 |empty| Identique à -c|
| Mode détaillé activé |false| Identique à -v|
| Supprimer les droits manquants | false| Identique à -c|
| Empêcher la build par défaut |false | Équivaut à utiliser -b sans arguments|
|Générer le remplacement de chaîne | empty| Valeur CFBundleVersion personnalisée de l’application de sortie encapsulée |
|Chemins des profils d’approvisionnement d’extension | empty| Tableau de profils d’approvisionnement d’extension pour l’application.


Exécutez la commande IntuneMAMPackager avec le fichier plist comme unique argument :

```
./IntuneMAMPackager –f Parameters.plist
```

* Une fois le traitement terminé, le message « The application was successfully wrapped » s’affiche.

    Si une erreur se produit, consultez [Messages d'erreur](prepare-ios-apps-for-mobile-application-management-with-the-microsoft-intune-app-wrapping-tool.md#error-messages) pour obtenir de l'aide.

*   L'application encapsulée est enregistrée dans le dossier de sortie spécifié précédemment. Vous pouvez maintenant charger l’application sur [wit_nextref](../includes/wit_nextref_md.md) et l’associer à une stratégie de gestion des applications mobiles.

    > [!IMPORTANT]
    > Lors du chargement d’une application encapsulée, vous pouvez tenter de mettre à jour une version antérieure de l’application si telle version (encapsulée ou native) a déjà été déployée pour Intune. Si vous rencontrez une erreur, chargez l’application comme nouvelle application et supprimez l’ancienne version.

    Vous pouvez maintenant déployer l’application sur vos groupes [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Elle s’exécutera sur l’appareil selon les restrictions d’applications que vous spécifiez.

## <a name="error-messages-and-log-files"></a>Messages d’erreur et fichiers journaux
Aidez-vous des informations suivantes pour résoudre les problèmes que vous rencontrez avec l’outil de création de package de restrictions d’application.

### <a name="error-messages"></a>Messages d'erreur
Si l’outil de création de package de restrictions d’application échoue, l’un des messages d’erreur suivants s’affiche dans la console :

|Message d'erreur|Plus d'informations|
|-----------------|--------------------|
|Vous devez spécifier un profil de configuration iOS valide.|Votre profil de configuration n'est peut-être pas valide. Vérifiez que vous avez les autorisations appropriées pour les appareils et que votre profil cible correctement le développement ou la distribution. Votre profil de configuration a peut être aussi expiré.|
|Spécifiez un nom d'application d'entrée valide.|Assurez-vous que le nom de l'application d'entrée spécifié est correct.|
|Spécifiez un chemin d'accès valide vers l'application de sortie.|Assurez-vous que le chemin d'accès à l'application de sortie que vous avez spécifié existe et est correct.|
|Spécifiez un profil de configuration d'entrée valide.|Vérifiez que vous avez fourni un nom et une extension de profil de configuration valides. Votre profil de configuration n’a peut-être pas les droits nécessaires, ou vous n’avez peut-être pas inclus l’option de ligne de commande –p.|
|L'application d'entrée spécifiée est introuvable. Spécifiez un nom et un chemin d'accès d'application d'entrée valides.|Assurez-vous que le chemin d'accès à l'application d'entrée est valide et qu'il existe. Assurez-vous que l'application d'entrée existe à cet emplacement.|
|Le fichier de profil de configuration d'entrée spécifié est introuvable. Spécifiez un fichier de profil de configuration d'entrée valide.|Assurez-vous que le chemin d'accès au fichier de configuration d'entrée est valide et que le fichier spécifié existe.|
|Le dossier d'application de sortie spécifié est introuvable. Spécifiez un chemin d'accès valide vers l'application de sortie.|Assurez-vous que le chemin de sortie spécifié est valide et qu'il existe.|
|L’application de sortie n’a pas une extension **.ipa**.|Seules les applications avec les extensions **.app** et **.ipa** sont acceptées par l’outil de création de package de restrictions d’application. Assurez-vous que votre fichier de sortie a une extension valide.|
|Un certificat de signature non valide a été spécifié. Spécifiez un certificat de signature Apple valide.|Assurez-vous d'avoir téléchargé le certificat de signature correct à partir du portail de développement Apple. Votre certificat a peut-être expiré, ou une clé publique ou privée est peut-être manquante. Si votre profil de configuration et votre certificat Apple peuvent être utilisés pour signer correctement une application dans Xcode, cela signifie qu’ils sont valides pour l’outil de création de package de restrictions d’application.|
|L'application d'entrée spécifiée n'est pas valide. Spécifiez une application valide.|Assurez-vous que votre application iOS est valide et qu'elle a été compilée sous forme de fichier .app ou .ipa.|
|L'application d'entrée spécifiée est chiffrée. Spécifiez une application non chiffrée valide.|L’outil de création de package de restrictions d’application ne gère pas les applications chiffrées. Fournissez une application non chiffrée.|
|L'application d'entrée spécifiée n'est pas au format PIE (Position Independent Executable). Spécifiez une application valide au format PIE.|Vous pouvez charger les applications PIE (Position Independent Executable) à une adresse mémoire aléatoire au moment de l’exécution. Cela peut offrir certains avantages en termes de sécurité. Pour plus d’informations sur les avantages en termes de sécurité, consultez votre documentation pour développeurs Apple.|
|L'application d'entrée spécifiée a déjà été encapsulée. Spécifiez une application non encapsulée valide.|Vous ne pouvez pas traiter une application qui a déjà été traitée par l'outil. Si vous souhaitez retraiter une application, exécutez l'outil à l'aide de la version d'origine de l'application.|
|L'application d'entrée spécifiée n'est pas signée. Spécifiez une application signée valide.|L'outil de création de package de restrictions d'application nécessite que les applications soient signées. Consultez votre documentation pour développeurs pour savoir comment signer une application encapsulée.|
|L'application d'entrée spécifiée doit être au format .ipa ou .app.|Seules les extensions .app et .ipa sont acceptées par l'outil de création de package de restrictions d'application. Assurez-vous que votre fichier d'entrée a une extension valide et qu'il a été compilé sous forme de fichier .app ou .ipa.|
|L'application d'entrée spécifiée a déjà été encapsulée et est à la dernière version de modèle de stratégie.|L’outil de création de package de restrictions d’application ne peut pas ré-encapsuler une application encapsulée existante avec la dernière version du modèle de stratégie.|
|AVERTISSEMENT : vous n’avez pas spécifié de hachage de certificat SHA1. Assurez-vous que votre application encapsulée est signée avant le déploiement.|Veillez à spécifier un hachage SHA1 valide à la suite de l’indicateur de ligne de commande –c. |

### <a name="log-files-for-the-app-wrapping-tool"></a>Fichiers journaux de l’outil de création de package de restrictions d’application
Les applications qui ont été encapsulées à l’aide de l’outil de création de package de restrictions d’application génèrent des journaux qui sont écrits dans la console de l’appareil iOS client. Ces informations sont utiles quand vous rencontrez des problèmes avec l’application et que vous devez déterminer si le problème est lié à l’outil de création de package de restrictions d’application. Pour récupérer ces informations, procédez comme suit :

1.  Reproduisez le problème en exécutant l'application.

2.  Recueillez la sortie de console en suivant les instructions d'Apple pour le [débogage des applications iOS déployées](https://developer.apple.com/library/ios/qa/qa1747/_index.html).

3.  Filtrez les journaux enregistrés pour la sortie de Restrictions d'application en entrant le script suivant dans la console :

    ```
    grep “IntuneAppRestrictions” <text file containing console output> > <required filtered log file name>
    ```
    Vous pouvez envoyer les journaux filtrés à Microsoft.

    > [!NOTE]
    > Dans le fichier journal, l'élément « build version » représente le numéro de build de Xcode.

    Les applications encapsulées offrent également aux utilisateurs la possibilité d'envoyer les journaux directement à partir de l'appareil par courrier électronique, après un blocage de l'application. Les utilisateurs peuvent vous envoyer les journaux pour que vous les examiniez et le transmettiez à Microsoft si nécessaire.


### <a name="certificate-provisioning-profile-and-authentication-requirements"></a>Exigences concernant le certificat, le profil de configuration et l’authentification

L’outil de création de package de restrictions d’application présente des conditions qui doivent être remplies pour pouvoir bénéficier de toutes les fonctionnalités.

|Condition requise|Détails|
|---------------|-----------|
|Profil de configuration|Vérifiez que le profil d’approvisionnement est valide avant de l’inclure. L’outil de création de package de restrictions d’application ne vérifie pas si le profil d’approvisionnement a expiré pendant le traitement d’une application iOS. Si vous spécifiez un profil de configuration ayant expiré, l’outil de création de package de restrictions d’application inclut le profil de configuration ayant expiré, et vous ne découvrez le problème qu’une fois que l’installation de l’application a échoué sur un appareil iOS.|
|Certificat|Vérifiez que le certificat est valide avant de le spécifier. L’outil ne vérifie pas si un certificat a expiré lors du traitement des applications iOS. Si vous fournissez le hachage d'un certificat ayant expiré, l'outil traitera et signera l'application, mais l'installation sur les appareils échouera.<br /><br />Vérifiez que le certificat fourni pour signer l’application empaquetée a une correspondance dans le profil d’approvisionnement. L’outil ne vérifie pas si le profil d’approvisionnement a une correspondance avec le certificat fourni pour signer l’application encapsulée.|
|Authentification|Pour que le chiffrement fonctionne, un code confidentiel doit être défini pour l’appareil. Sur les appareils sur lesquels vous avez déployé une application encapsulée, une pression sur la barre d’état sur l’appareil nécessite que l’utilisateur se réauthentifie auprès de [wit_nextref](../includes/wit_nextref_md.md). La stratégie par défaut dans une application encapsulée est l’*authentification lors du redémarrage*. iOS gère toutes les notifications externes (telles qu’un appel téléphonique) en quittant l’application, puis en la redémarrant.


## <a name="setting-app-entitlements"></a>Définition des droits de l’application
Avant d’encapsuler votre application, vous pouvez lui accorder des *droits* dans le but de lui octroyer des autorisations et des fonctionnalités supplémentaires qui vont au-delà de ce qu’une application peut généralement faire. Un *fichier de droits* est utilisé pendant la signature du code pour spécifier des autorisations spéciales dans votre application (par exemple, l’accès à un trousseau partagé). Des services d’application spécifiques appelés *capabilities* (fonctionnalités) sont activés dans Xcode pendant le développement de l’application. Une fois activées, les fonctionnalités apparaissent dans votre fichier de droits. Pour plus d’informations sur les droits et les fonctionnalités, consultez [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) (Ajout de fonctionnalités) dans la bibliothèque du développeur iOS. Pour obtenir la liste complète des fonctionnalités prises en charge, consultez [Supported capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/SupportedCapabilities/SupportedCapabilities.html) (Fonctionnalités prises en charge).

### <a name="supported-capabilities-for-the-app-wrapping-tool-for-ios"></a>Fonctionnalités prises en charge pour App Wrapping Tool for iOS

|Fonctionnalité|Description|Recommandation|
|--------------|---------------|------------------------|
|Groupes d’applications|Utilisez des groupes d’applications pour autoriser plusieurs applications à accéder à des conteneurs partagés et autoriser une communication interprocessus supplémentaire entre les applications.<br /><br />Pour activer les groupes d’applications, ouvrez le volet **Capabilities** (Fonctionnalités), puis cliquez sur **ON** (Activer) dans **App Groups** (Groupes d’applications). Vous pouvez ajouter des groupes d’applications en ou sélectionner des existants.|Quand vous utilisez App Groups, utilisez la notation DNS inverse :<br /><br />*group.com.companyName.AppGroup*|
|Modes d’arrière-plan|L’activation des modes d’arrière-plan permet à votre application iOS de continuer à s’exécuter en arrière-plan.||
|Protection des données|Data Protection (protection des données) ajoute un niveau de sécurité aux fichiers stockés sur le disque par votre application iOS. Data Protection utilise le matériel de chiffrement intégré présent sur certains appareils pour stocker les fichiers dans un format chiffré sur disque. Votre application doit être configurée pour utiliser Data Protection.||
|Achat dans l’application|L’achat dans l’application incorpore un store directement dans votre application. Vous pouvez vous y connecter et traiter les paiements de l’utilisateur en toute sécurité. Vous pouvez utiliser l’achat dans l’application pour récupérer les paiements en contrepartie de fonctionnalités améliorées ou de contenu supplémentaire que votre application peut exploiter.||
|Partage de trousseau|Le partage de trousseau permet à votre application de partager des mots de passe dans le trousseau avec les autres applications développées par votre équipe.|Quand vous utilisez le partage de trousseau, utilisez la notation DNS inverse :<br /><br />*com.companyName.KeychainGroup*|
|Personal VPN|Activez Personal VPN (VPN personnel) pour permettre à votre application de créer et contrôler une configuration VPN système personnalisée à l’aide de l’infrastructure Network Extension.||
|Notifications push|Le service de notification Push Apple (APN) permet à une application qui ne s’exécute pas au premier plan de notifier l’utilisateur que des informations sont à sa disposition.|Pour que les notifications Push fonctionnent, vous devez utiliser un profil de configuration spécifique à l’application.<br /><br />Suivez la procédure décrite dans la [documentation pour développeurs Apple](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html).|
|Configuration d’accessoire sans fil|L’activation de la configuration d’accessoire sans fil a pour effet d’ajouter le framework External Accessory à votre projet et permet à votre application de configurer les accessoires Wi-Fi MFi.||

### <a name="steps-to-enable-entitlements"></a>Étapes d’activation des droits

1.  Activez les fonctionnalités dans votre application :

    1.  Dans Xcode, accédez à la cible de votre application, puis cliquez sur **Capabilities** (Fonctionnalités).

    2.  Activez les fonctionnalités appropriées. Pour obtenir des informations détaillées sur chaque fonctionnalité et pour savoir comment déterminer les valeurs correctes, consultez [Adding Capabilities](https://developer.apple.com/library/ios/documentation/IDEs/Conceptual/AppDistributionGuide/AddingCapabilities/AddingCapabilities.html) dans la bibliothèque du développeur iOS.

    3.  Notez les ID que vous avez créés pendant le processus.

    4.  Générer et signez votre application à encapsuler.

2.  Activez les droits dans votre profil de configuration :

    1.  Connectez-vous à l’Apple Developer Member Center.

    2.  Créez un profil de configuration pour votre application. Pour obtenir des instructions, consultez la page [How to Obtain the Prerequisites for the Intune App Wrapping Tool for iOS](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/25/how-to-obtain-the-prerequisites-for-the-intune-app-wrapping-tool-for-ios/) (Comment obtenir la configuration requise pour Intune App Wrapping Tool for iOS).

    3.  Dans votre profil de configuration, activez les mêmes droits que ceux que vous avez dans votre application. Vous devez fournir les mêmes ID que ceux que vous avez spécifiés pendant le développement de votre application.

    4.  Terminez l’Assistant de configuration de profil, puis téléchargez votre fichier.

3.  Assurez-vous que vous avez rempli toutes les conditions préalables, puis encapsulez l’application.

### <a name="troubleshooting-common-errors-with-entitlements"></a>Résolution des erreurs courantes liées aux droits
Si App Wrapping Tool for iOS affiche une erreur de droit, essayez d’exécuter les étapes de dépannage suivantes.

|Problème|Cause|Résolution|
|---------|---------|--------------|
|Impossible d’analyser les droits générés à partir de l’application d’entrée.|L’outil de création de package de restrictions d’application ne peut pas lire le fichier de droits qui a été extrait de l’application. Le fichier de droits est peut être incorrect.|Examinez le fichier de droits de votre application. Les instructions suivantes expliquent comment effectuer cette opération. Au moment d’inspecter le fichier de droits, assurez-vous que la syntaxe est correcte. Le fichier doit être au format XML.|
|Il manque des droits dans le profil de configuration (les droits manquants sont répertoriés). Recréez le package de l’application avec un profil de configuration qui contienne ces droits.|Il y a une incohérence entre les droits activés dans le profil de configuration et les fonctionnalités activées dans l’application. Cette incohérence vaut aussi pour les ID associés à des fonctionnalités particulières (telles que les groupes d’applications et l’accès à un trousseau).|En règle générale, vous pouvez créer un nouveau profil de configuration qui active les mêmes fonctionnalités que l’application. Quand les ID du profil et de l’application ne correspondent pas, l’outil de création de package de restrictions d’application remplace les ID, dans la mesure du possible. Si vous obtenez encore cette erreur après avoir créé un profil de configuration, vous pouvez essayer de supprimer les droits de l’application à l’aide du paramètre –e (voir la section Utilisation du paramètre –e pour supprimer les droits d’accès).|

### <a name="finding-the-existing-entitlements-of-a-signed-app"></a>Recherche des droits existants d’une application signée
Pour examiner les droits existants d’une application signée et le profil de configuration :

1.  Recherchez le fichier .ipa et remplacez son extension par .zip.

2.  Développez le fichier .zip. Un dossier Payload contenant votre ensemble .app est alors généré.

3.  Utilisez l’outil codesign pour vérifier les droits de l’ensemble .app, où `YourApp.app` correspond au nom réel de votre ensemble .app :

    ```
    $ codesign -d --entitlements :- "Payload/YourApp.app"
    ```

4.  Utilisez l’outil de sécurité pour vérifier les droits du profil de configuration incorporé de l’application, où `YourApp.app` correspond au nom réel de votre ensemble .app.

    ```
    $ security -D -i "Payload/YourApp.app/embedded.mobileprovision"
    ```

### <a name="remove-entitlements-from-an-app-by-using-the-e-parameter"></a>Supprimer les droits d’accès d’une application à l’aide du paramètre –e
Cette commande supprime toutes les fonctionnalités activées dans l’application qui ne figurent pas dans le fichier de droits. Si vous supprimez des fonctionnalités qui sont utilisées par l’application, elle risque de se bloquer. Vous pourriez par exemple supprimer des fonctionnalités manquantes dans une application générée par un fournisseur qui dispose de toutes les fonctionnalités par défaut.

```
./IntuneMAMPackager/Contents/MacOS/IntuneMAMPackager –i /<path of input app>/<app filename> -o /<path to output folder>/<app filename> –p /<path to provisioning profile> –c <SHA1 hash of the certificate> -e
```

## <a name="security-and-privacy-for-the-app-wrapping-tool"></a>Sécurité et confidentialité pour l’outil de création de package de restrictions d’application
Respectez les bonnes pratiques de sécurité et de confidentialité suivantes quand vous utilisez l’outil de création de package de restrictions d’application.

-   Le certificat de signature, le profil d’approvisionnement et l’application métier que vous spécifiez doivent se trouver sur le même ordinateur macOS que celui que vous utilisez pour exécuter l’outil de création de package de restrictions d’application. Si les fichiers se trouvent sur un chemin UNC, vérifiez qu’ils sont accessibles à partir de l’ordinateur macOS. Le chemin d'accès doit être sécurisé via la signature SMB ou la sécurité IPsec.

    L’application encapsulée importée dans la console [wit_nextref](../includes/wit_nextref_md.md) doit se trouver sur le même ordinateur que celui sur lequel vous exécutez l’outil. Si le fichier se trouve dans un chemin UNC, vérifiez qu’il est accessible sur l’ordinateur qui exécute la console [wit_nextref](../includes/wit_nextref_md.md). Le chemin d'accès doit être sécurisé via la signature SMB ou la sécurité IPsec.

-   L’environnement où l’outil de création de package de restrictions d’application est téléchargé à partir du site du dépôt GitHub doit être sécurisé par le biais de la signature SMB ou la sécurité IPsec.

-   L’application que vous traitez doit provenir d’une source digne de confiance pour garantir la protection contre les attaques.

-   Vérifiez que le dossier de sortie que vous spécifiez dans l’outil de création de package de restrictions d’application est sécurisé, en particulier s’il s’agit d’un dossier distant.

-   Les applications iOS qui incluent une boîte de dialogue de chargement de fichier peuvent permettre aux utilisateurs de contourner les restrictions relatives aux opérations couper, copier et coller appliquées à l’application. Par exemple, un utilisateur peut utiliser la boîte de dialogue de téléchargement de fichier pour télécharger une capture d'écran des données de l'application.

-   Quand vous analysez le dossier de documents sur votre appareil depuis une application encapsulée, vous risquez de voir un dossier nommé .msftintuneapplauncher. Si vous modifiez ou supprimez ce fichier, cela peut affecter le bon fonctionnement des applications restreintes.

### <a name="see-also"></a>Voir aussi
- [Décider comment préparer les applications pour la gestion des applications mobiles avec Microsoft Intune](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)</br>
- [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)</br>
- [Utiliser le Kit de développement logiciel (SDK) pour activer des applications pour la gestion des applications mobiles](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Nov16_HO1-->


