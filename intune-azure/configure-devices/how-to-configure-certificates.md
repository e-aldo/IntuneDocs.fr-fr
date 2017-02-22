---
title: "Guide pratique pour la configuration de certificats avec Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment utiliser Intune pour créer et attribuer des certificats qui vous aident à sécuriser les connexions Wi-Fi, VPN et autres."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f05e0018fb202ab5774e935c3f59855e4aa2e75
ms.openlocfilehash: a0183f2a170ed458b19c7688b20ee5ba5c2c696e


---

# <a name="how-to-configure-certificates-with-intune-azure-preview"></a>Guide pratique pour la configuration de certificats avec la version préliminaire d’Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Quand vous donnez un accès à des utilisateurs aux ressources d’entreprise par le biais de profils VPN, Wi-Fi ou de messagerie, vous pouvez sécuriser cet accès à l’aide d’un certificat installé sur chaque appareil de l’utilisateur. Le flux de travail de haut niveau est le suivant :

1. Assurez-vous de disposer d’une infrastructure de certificat appropriée. Vous pouvez utiliser des [certificats SCEP](configure-certificate-infrastructure-for-scep.md) et des [certificats PKCS](configure-certificate-infrastructure-for-pfx.md).
2. Installez un certificat racine ou un certificat intermédiaire d’une autorité de certification sur chaque appareil pour qu’il reconnaisse la légitimité de votre autorité de certification. Pour ce faire, créez et attribuez un **profil de certificat approuvé**. Quand vous attribuez ce profil, les appareils que vous gérez avec Intune demandent et reçoivent le certificat racine. Vous devez créer un profil distinct pour chaque plateforme. Les profils de certificat approuvés sont disponibles pour ces plateformes :
    - iOS 8.0 et versions ultérieures
    - macOS 10.9 et versions ultérieures
    - Android 4.0 et versions ultérieures<!--Android for Work --->
    - Windows 8.1 et versions ultérieures
    - Windows Phone 8.1 et versions ultérieures
    - Windows 10 et versions ultérieures
3. Créez des profils de certificat pour que les appareils demandent l’utilisation d’un certificat à des fins d’authentification pour l’accès au VPN, au Wi-Fi et aux e-mails. Vous pouvez créer et déployer un profil de certificat **PKCS** ou un profil de certificat **SCEP** pour les appareils exécutant ces plateformes :
    - iOS 8.0 et versions ultérieures
    - Android 4.0 et versions ultérieures
    - Android for Work
    - Windows 10 (Desktop et Mobile) et versions ultérieures

    Vous pouvez seulement utiliser un profil de certificat SCEP avec ces plateformes :

-   macOS 10.9 et versions ultérieures
-   Windows Phone 8.1 et versions ultérieures

Vous devez créer un profil distinct pour chaque plateforme d’appareil. Quand vous créez le profil, associez-le au profil de certificat racine approuvé que vous avez déjà créé.

### <a name="further-considerations"></a>Autres considérations

- Si vous n’avez pas d’autorité de certification d’entreprise, vous devez en créer une.
- Si vous décidez, en fonction de vos plateformes d’appareils, d’utiliser le profil SCEP (Simplified Certificate Enrollment Protocol), vous devez également configurer un serveur NDES (Network Device Enrollment Service).
- Si vous envisagez d’utiliser des profils SCEP ou PKCS, vous devez télécharger et configurer Microsoft Intune Certificate Connector.

## <a name="before-you-start"></a>Avant de commencer


### <a name="if-you-want-to-use-scep-certificates"></a>Si vous souhaitez utiliser des certificats SCEP

Exécutez la configuration requise dans [l’infrastructure de certificats pour SCEP](/intune-azure/configure-devices/configure-certificate-infrastructure-for-scep).

### <a name="if-you-want-to-use-pkcs-certificates"></a>Si vous souhaitez utiliser des certificats PKCS

Exécutez la configuration requise dans [l’infrastructure de certificats pour PKCS](/intune-azure/configure-devices/configure-certificate-infrastructure-for-pfx).

## <a name="task-1-export-the-trusted-root-ca-certificate"></a>Tâche 1 : Exporter le certificat d’autorité de certification racine approuvée
Exportez le certificat d’autorité de certification racine approuvée sous la forme d’un fichier **.cer** à partir de l’autorité de certification émettrice ou d’un appareil qui approuve votre autorité de certification émettrice. N’exportez pas la clé privée.

Vous importerez ce certificat quand vous configurerez un profil de certificat approuvé.

## <a name="task-2-create-trusted-certificate-profiles"></a>Tâche 2 : Créer des profils de certificat approuvés
Vous devez créer un profil de certificat approuvé pour pouvoir créer un profil de certificat SCEP ou PKCS. Il faut un profil de certificat approuvé et un profil SCEP ou PKCS pour chaque plateforme d’appareil.

### <a name="to-create-a-trusted-certificate-profile"></a>Pour créer un profil de certificat approuvé

1. Connectez-vous au portail Azure.
2. Choisissez **Plus de services** > **Autres** > **Intune**.
3. Dans le panneau **Intune**, choisissez **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de certificat approuvé.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat approuvé. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres de restriction de l’appareil :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Certificat approuvé**.
7. Accédez au certificat que vous avez enregistré dans la Tâche 1, puis cliquez sur **OK**.
8. Pour les appareils Windows 8.1 et Windows 10 uniquement, sélectionnez le **Magasin de destination** pour le certificat approuvé à partir de :
    - **Boutique de certificats de l’ordinateur - Racine**
    - **Boutique de certificats de l’ordinateur - Intermédiaire**
    - **Boutique de certificats de l’utilisateur - Intermédiaire**
8. Lorsque vous avez terminé, cliquez sur **OK**, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.
Si vous souhaitez continuer et attribuer ce profil à des groupes, consultez [Guide pratique pour l’attribution de profils d’appareils](how-to-assign-device-profiles.md).


> [!Note]
> Les appareils Android affichent une notification indiquant qu’un tiers a installé un certificat approuvé.

## <a name="task-3-create-scep-or-pkcs-certificate-profiles"></a>Tâche 3 : Créer des profils de certificat SCEP ou PKCS
Après avoir créé un profil de certificat approuvé, créez des profils de certificat SCEP ou PKCS pour chaque plateforme que vous voulez utiliser. Quand vous créez un profil de certificat SCEP, vous devez spécifier un profil de certificat approuvé pour cette même plateforme. Cette opération lie les deux profils de certificat, mais vous devez quand même attribuer chaque profil séparément.

### <a name="to-create-an-scep-certificate-profile"></a>Pour créer un profil de certificat SCEP

1. Dans le portail Azure, sélectionnez la charge de travail **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau des profils, sélectionnez **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de certificat SCEP.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat SCEP. Actuellement, vous pouvez choisir l’une des plateformes suivantes pour les paramètres de restriction de l’appareil :
    - **Android**
    - **iOS**
    - **MacOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 et versions ultérieures**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Certificat SCEP**.
7. Dans le panneau **Certificat SCEP**, configurez les paramètres suivants :
    - **Période de validité du certificat** : si vous avez exécuté la commande **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** sur l’autorité de certification émettrice, ce qui autorise une période de validité personnalisée, vous pouvez spécifier le temps restant avant l’expiration du certificat.<br>Vous pouvez spécifier une valeur inférieure à la période de validité du modèle de certificat spécifié, mais pas une valeur supérieure. Par exemple, si la période de validité du certificat dans le modèle de certificat est de&2; ans, vous pouvez spécifier une valeur de&1; an mais pas une valeur de&5; ans. La valeur doit également être inférieure à la période de validité restante du certificat de l’autorité de certification émettrice. 
    - **Fournisseur de stockage de clés** (Windows Phone 8.1, Windows 8.1, Windows 10) : spécifiez l’emplacement de stockage de la clé du certificat. Choisissez l'une des valeurs suivantes :
        - **Inscrire auprès du fournisseur de stockage de clés (KSP) du module de plateforme sécurisée (TPM) s’il est présent ; sinon, inscrire auprès du fournisseur de stockage de clés du logiciel**
        - **Inscrire auprès du fournisseur de stockage de clés (KSP) du module de plateforme sécurisée (TPM), sinon mettre en échec**
        - **Inscrire auprès de Passport, sinon mettre en échec (Windows 10 et versions ultérieures)**
        - **Inscrire auprès du fournisseur de stockage de clés du logiciel**
    - **Format du nom de l’objet** : dans la liste, sélectionnez comment Intune crée automatiquement le nom de l’objet dans la demande de certificat. Si le certificat est pour un utilisateur, vous pouvez également inclure l'adresse de messagerie de cet utilisateur dans le nom de l'objet. Choisissez parmi :
        - **Non configuré**
        - **Nom commun**
        - **Nom commun (adresse e-mail incluse)**
        - **Nom commun comme adresse e-mail**
    - **Autre nom de l’objet** : spécifiez comment Intune crée automatiquement les valeurs pour l’autre nom de l’objet dans la demande de certificat. Par exemple, si vous avez sélectionné un type de certificat utilisateur, vous pouvez inclure le nom d'utilisateur principal (UPN) dans l'autre nom de l'objet. Si le certificat client est utilisé pour l'authentification sur un serveur de stratégie réseau, l'autre nom de l'objet doit être défini sur le nom d'utilisateur principal. 
    - **Utilisation de la clé** : spécifiez les options d’utilisation de la clé pour le certificat. Vous pouvez choisir parmi les options suivantes : 
        - **Chiffrage de clés** : autorisez l’échange de clés uniquement quand la clé est chiffrée. 
        - **Signature numérique** : autorisez l’échange de clés uniquement quand une signature numérique contribue à protéger la clé. 
    - **Taille de la clé (bits)** : sélectionnez le nombre de bits qui seront contenus dans la clé. 
    - **Algorithme de hachage** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) : sélectionnez l’un des types d’algorithme de hachage disponibles avec ce certificat. Permet de sélectionner le niveau le plus élevé de sécurité pris en charge par les appareils se connectant. 
    - **Certificat racine** : choisissez un profil de certificat d’autorité de certification racine que vous avez précédemment configuré et attribué à l’utilisateur ou à l’appareil. Ce certificat d'autorité de certification doit être le certificat racine de l'autorité de certification qui émet le certificat que vous configurez dans ce profil de certificat. 
    - **Utilisation de la clé étendue** : choisissez **Ajouter** pour ajouter des valeurs pour le rôle prévu du certificat. Dans la plupart des cas, le certificat demande une **Authentification client** afin que l'utilisateur ou l'appareil puisse être authentifié sur un serveur. Toutefois, vous pouvez ajouter d'autres utilisations de la clé en fonction de vos besoins. 
    - **Paramètres d’inscription**
        - **Seuil de renouvellement (%)** : spécifiez le pourcentage de durée de vie restante du certificat avant que l’appareil ne demande le renouvellement du certificat.
        - **URL du serveur SCEP** : spécifiez une ou plusieurs URL pour les serveurs NDES qui délivreront les certificats via SCEP. 
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

Suivez les instructions de la page de configuration de profil pour configurer les paramètres de profil de certificat SCEP.
>[!Note]
> Pour les appareils iOS seulement : sous Format du nom de l’objet, sélectionnez Personnalisé pour entrer un format de nom d’objet personnalisé.
> Les deux variables actuellement prises en charge pour le format personnalisé sont **Nom courant (cn)** et **Message électronique (e)**. En combinant ces variables avec des chaînes statiques, vous pouvez créer un format de nom d’objet personnalisé tel que celui-ci : **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Dans cet exemple, vous avez créé un format de nom d’objet qui, en plus des variables CN et E, utilise des chaînes pour les valeurs Organizational Unit (Unité organisationnelle), Organization (Organisation), Location (Emplacement), State (État) et Country (Pays). [Cette rubrique](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) illustre la fonction **CertStrToName** et ses chaînes prises en charge.


### <a name="to-create-a-pkcs-certificate-profile"></a>Pour créer un profil de certificat PKCS

Dans le portail Azure, sélectionnez la charge de travail **Configurer des appareils**.
2. Dans le panneau **Configuration de l’appareil**, choisissez **Gérer** > **Profils**.
3. Dans le panneau de profils, cliquez sur **Créer un profil**.
4. Dans le panneau **Créer un profil**, entrez un **Nom** et une **Description** pour le profil de certificat PKCS.
5. Dans la liste déroulante **Plateforme**, sélectionnez la plateforme d’appareil pour ce certificat PKCS :
    - **Android**
    - **iOS**
    - **Windows 10 et versions ultérieures**
6. Dans la liste déroulante **Type de profil**, choisissez **Certificat PKCS**.
7. Dans le panneau **Certificat PKCS**, configurez les paramètres suivants :
    - **Seuil de renouvellement (%)** : spécifiez le pourcentage de durée de vie restante du certificat avant que l’appareil ne demande le renouvellement du certificat.
    - **Période de validité du certificat** : si vous avez exécuté la commande **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** sur l’autorité de certification émettrice, ce qui autorise une période de validité personnalisée, vous pouvez spécifier le temps restant avant l’expiration du certificat.<br>Vous pouvez spécifier une valeur inférieure à la période de validité du modèle de certificat spécifié, mais pas une valeur supérieure. Par exemple, si la période de validité du certificat dans le modèle de certificat est de&2; ans, vous pouvez spécifier une valeur de&1; an mais pas une valeur de&5; ans. La valeur doit également être inférieure à la période de validité restante du certificat de l’autorité de certification émettrice.
    - **Fournisseur de stockage de clés (KSP)** (Windows 10) -
    - **Autorité de certification** -
    - **Nom de l’autorité de certification** -
    - **Nom du modèle de certificat** : entrez le nom d’un modèle de certificat que doit utiliser le service d’inscription de périphériques réseau conformément à sa configuration et qui a été ajouté à une autorité de certification émettrice.
    Assurez-vous que le nom correspond exactement à l’un des modèles de certificat figurant dans le registre du serveur exécutant le service d’inscription de périphériques réseau. Assurez-vous que vous spécifiez le nom du modèle de certificat et non le nom d'affichage du modèle de certificat. 
    Pour rechercher les noms des modèles de certificats, accédez à la clé suivante : HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP. Les modèles de certificat s'affichent sous la forme des valeurs **EncryptionTemplate**, **GeneralPurposeTemplate**et **SignatureTemplate**. Par défaut, la valeur des trois modèles de certificat est IPSECIntermediateOffline, laquelle correspond au nom d’affichage du modèle **IPSec (requête hors connexion)**. 
    - **Format du nom de l’objet** : dans la liste, sélectionnez comment Intune crée automatiquement le nom de l’objet dans la demande de certificat. Si le certificat est pour un utilisateur, vous pouvez également inclure l'adresse de messagerie de cet utilisateur dans le nom de l'objet. Choisissez parmi :
        - **Non configuré**
        - **Nom commun**
        - **Nom commun (adresse e-mail incluse)**
        - **Nom commun comme adresse e-mail**
    - **Autre nom de l’objet** : spécifiez comment Intune crée automatiquement les valeurs pour l’autre nom de l’objet dans la demande de certificat. Par exemple, si vous avez sélectionné un type de certificat utilisateur, vous pouvez inclure le nom d'utilisateur principal (UPN) dans l'autre nom de l'objet. Si le certificat client est utilisé pour l'authentification sur un serveur de stratégie réseau, l'autre nom de l'objet doit être défini sur le nom d'utilisateur principal.
    - **Utilisation de la clé étendue** (Android) : choisissez **Ajouter** pour ajouter des valeurs pour le rôle prévu du certificat. Dans la plupart des cas, le certificat demande une **Authentification client** afin que l'utilisateur ou l'appareil puisse être authentifié sur un serveur. Toutefois, vous pouvez ajouter d'autres utilisations de la clé en fonction de vos besoins. 
    - **Certificat racine** (Android) : choisissez un profil de certificat d’autorité de certification racine que vous avez précédemment configuré et attribué à l’utilisateur ou à l’appareil. Ce certificat d'autorité de certification doit être le certificat racine de l'autorité de certification qui émet le certificat que vous configurez dans ce profil de certificat.
8. Lorsque vous avez terminé, revenez au panneau **Créer un profil** et appuyez sur **Créer**.

Le profil est créé et s’affiche dans le panneau de la liste des profils.

## <a name="task-4-assign-certificate-profiles"></a>Tâche 4 : Attribuer des profils de certificat

Considérez les éléments suivants avant d’attribuer des profils de certificat aux groupes :

- Quand vous attribuez des profils de certificat aux groupes, le fichier de certificat issu du profil de certificat d’autorité de certification approuvée est installé sur l’appareil. L’appareil utilise le profil de certificat SCEP ou PKCS pour créer une demande de certificat par l’appareil.
- Les profils de certificat s’installent uniquement sur les appareils exécutant la plateforme que vous utilisez quand vous créez le profil.
- Vous pouvez déployer des profils de certificat sur des regroupements d’utilisateurs ou d’appareils.
- Pour publier un certificat sur un appareil rapidement après l’inscription de l’appareil, déployez le profil de certificat sur un groupe d’utilisateurs plutôt que sur un groupe d’appareils. Si vous déployez sur un groupe d’appareils, une inscription complète des appareils est préalablement nécessaire pour qu’ils puissent recevoir des stratégies.
- Même si vous déployez chaque profil séparément, vous devez également déployer l’autorité de certification racine approuvée et le profil SCEP ou PKCS. Dans le cas contraire, la stratégie de certificat SCEP ou PKCS échoue.

## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations générales sur la façon d’attribuer des profils d’appareils, consultez [Guide pratique pour l’attribution de profils d’appareils](how-to-assign-device-profiles.md).



<!--HONumber=Feb17_HO1-->


