---
title: "Protéger l’accès aux réseaux avec Cisco ISE | Microsoft Docs"
description: "Utilisez Cisco ISE avec Intune pour que les appareils soient inscrits auprès d’Intune et conformes aux stratégies avant d’accéder aux infrastructures Wi-Fi et VPN contrôlées par Cisco ISE."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9f34d54710f0ec662eecec85f7fa041061132a0d
ms.openlocfilehash: 8ef24e4d413662012f091c1be318d1d274e16439


---

# <a name="using-cisco-ise-with-microsoft-intune"></a>Utilisation de Cisco ISE avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

L’intégration d’Intune à Cisco ISE (Identity Services Engine) vous permet de créer des stratégies réseau dans votre environnement ISE faisant appel à l’état de conformité et à l’inscription d’appareils Intune. Vous pouvez utiliser ces stratégies pour vous assurer que l’accès à votre réseau d’entreprise est limité aux appareils gérés par Intune et conformes aux stratégies Intune.

## <a name="configuration-steps"></a>Étapes de configuration

Pour activer cette intégration, aucune configuration particulière n’est nécessaire dans votre client Intune. Vous devrez fournir des autorisations à votre serveur Cisco ISE pour accéder à votre client Intune. Une fois cette opération effectuée, le reste de la configuration a lieu sur votre serveur Cisco ISE. Cet article indique comment fournir à votre serveur ISE des autorisations d’accès à votre client Intune.

### <a name="step-1-manage-the-certificates"></a>Étape 1 : Gérer les certificats
Exportez le certificat à partir de la console Azure Active Directory (Azure AD) et importez-le dans le magasin Certificats approuvés de la console ISE :

#### <a name="internet-explorer-11"></a>Internet Explorer 11


   a. Exécutez Internet Explorer comme administrateur, puis connectez-vous à la console Azure AD.

   b. Choisissez l’icône en forme de verrou dans la barre d’adresse, puis **Afficher les certificats**.

   c. Sous l’onglet **Détails** des propriétés des certificats, choisissez **Copier dans un fichier**.

   d. Dans la page **Assistant Exportation de certificat**, choisissez **Suivant**.

   e. Dans la page **Format du fichier d’exportation**, laissez la valeur par défaut, **X.509 binaire encodé DER (*.cer)**, puis choisissez **Suivant**.  

   f. Dans la page **Fichier à exporter**, choisissez **Parcourir** pour choisir l’emplacement auquel enregistrer le fichier, puis fournissez un nom de fichier. Concrètement, cette opération consiste en fait à nommer le fichier dans lequel le certificat exporté sera enregistré. Choisissez **Suivant** &gt; **Terminer**.

   g. À partir de la console ISE, importez le certificat Intune (le fichier exporté) dans le magasin **Trusted Certificates** (Certificats approuvés).

#### <a name="safari"></a>Safari

 a. Connectez-vous à la console Azure AD.

b. Cliquez sur l’icône en forme de verrou &gt;  **Plus d’informations**.

   c. Choisissez **Afficher le certificat** &gt; **Détails**.

   d. Choisissez le certificat, puis **Exporter**. 

   e. À partir de la console ISE, importez le certificat Intune (le fichier exporté) dans le magasin **Trusted Certificates** (Certificats approuvés).

> [!IMPORTANT]
>
> Vérifiez la date d’expiration du certificat, car vous devrez en exporter et en importer un nouveau quand celui-ci arrivera à expiration.


### <a name="obtain-a-self-signed-cert-from-ise"></a>Obtenir un certificat auto-signé à partir d’ISE 

1.  Dans la console ISE, accédez à **Administration** > **Certificates** > **System Certificates** > **Generate Self Signed Certificate** (Générer un certificat auto-signé).  
2.       Exportez le certificat auto-signé.
3. Dans un éditeur de texte, modifiez le certificat exporté :

 - Supprimez ** -----BEGIN CERTIFICATE-----**.
 - Supprimez ** -----END CERTIFICATE-----**.
 
Vérifiez que tout le texte contient sur une seule ligne.


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a>Étape 2 : Créer une application pour ISE dans votre client Azure AD
1. Dans la console Azure AD, choisissez **Applications** > **Ajouter une application** > **Ajouter une application développée par mon organisation**.
2. Spécifiez un nom et une URL pour l’application. L’URL peut correspondre au site web de votre entreprise.
3. Téléchargez le manifeste d’application (fichier JSON).
4. Modifiez le fichier manifeste JSON. Pour le paramètre **keyCredentials**, fournissez le texte du certificat modifié à l’étape 1.
5. Enregistrez le fichier sans modifier son nom.
6. Fournissez à votre application des autorisations à Microsoft Graph et à l’API Microsoft Intune.

 a. Pour Microsoft Graph, choisissez ce qui suit :
    - **Autorisations d’application** : Lire des données d’annuaire
    - **Autorisations déléguées** :
        - Accéder aux données utilisateur à tout moment
        - Connecter les utilisateurs

 b. Pour l’API Microsoft Intune, dans **Autorisations d’application**, choisissez **Get device state and compliance from Intune** (Obtenir l’état et la conformité de l’appareil à partir d’Intune).

7. Choisissez **Points de terminaison** et copiez les valeurs suivantes, que vous utiliserez pour configurer les paramètres ISE :

|Valeur dans le portail Azure AD|Champ correspondant dans le portail ISE|
|-------------------|---------------------------------|
|Point de terminaison de l’API Microsoft Azure AD Graph|Auto Discovery URL (URL de découverte automatique)|
|Point de terminaison de jeton OAuth 2.0|Token Issuing URL (URL émettrice de jeton)|
|Mettre à jour votre code avec votre ID client|ID client|

### <a name="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a>Étape 4 : Charger le certificat auto-signé de l’ISE dans l’application ISE que vous avez créée dans Azure AD
1.     Récupérez l’empreinte numérique et la valeur de certificat codée en base64 d’un fichier de certificat public X509 (.cer). Cet exemple utilise PowerShell :
   
      
      $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()
 
    Stockez les valeurs de $base64Thumbprint, $base64Value et $keyid à utiliser à l’étape suivante.
2.       Chargez le certificat depuis le fichier manifeste. Connectez-vous au [Portail de gestion Azure](https://manage.windowsazure.com)
2.      Dans le composant logiciel enfichable Azure AD, recherchez l’application que vous souhaitez configurer avec un certificat X.509.
3.      Téléchargez le fichier manifeste d’application. 
5.      Remplacez la propriété “KeyCredentials”: [], vide par le code JSON suivant.  Le type complexe KeyCredentials est documenté dans [Entity and complex type reference](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType) (Informations de référence sur les entités et les types complexes).

 
    “keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2. 
     ], 
 
Exemple :
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      Enregistrez la modification dans le fichier manifeste d’application.
7.      Chargez le fichier manifeste d’application modifié via le portail de gestion Azure.
8.      (Facultatif) Rechargez le manifeste pour vérifier que votre certificat X.509 figure bien dans l’application.

>[!NOTE]
>
> Comme KeyCredentials est une collection, vous pouvez charger plusieurs certificats X.509 pour les scénarios de substitution, ou supprimer des certificats dans des scénarios de compromission.


### <a name="step-4-configure-ise-settings"></a>Étape 5 : Configurer les paramètres ISE
Dans la console d’administration ISE, fournissez ces valeurs de paramètre :
  - **Server Type** (Type de serveur) : Mobile Device Manager
  - **Authentication type** (Type d’authentification) : OAuth – Client Credentials (OAuth – Informations d’identification du client)
  - **Auto Discovery** (Découverte automatique) : Yes (Oui)
  - **Auto Discovery URL** (URL de découverte automatique) : *entrez la valeur provenant de l’étape 1.*
  - **Client ID** (ID client) : *entrez la valeur provenant de l’étape 1.*
  - **Token Issuing URL** (URL émettrice de jeton) : *entrez la valeur provenant de l’étape 1.*



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a>Informations partagées entre votre client Intune et votre serveur Cisco ISE
Ce tableau répertorie les informations partagées entre votre client Intune et votre serveur Cisco ISE pour les appareils gérés par Intune.

|Propriété|  Description|
|---------------|------------------------------------------------------------|
|complianceState|La chaîne vrai ou faux indique si l’appareil est conforme ou non.|
|isManaged|La chaîne vrai ou faux indique si le client est géré par Intune ou non.|
|macAddress|Adresse MAC de l’appareil.|
|serialNumber|Numéro de série de l’appareil. Concerne uniquement les appareils iOS.|
|imei|Le numéro IMEI (15 chiffres décimaux : 14 chiffres plus un chiffre de vérification) ou IMEISV (16 chiffres) inclut des informations sur l’origine, le modèle et le numéro de série de l’appareil. La structure de ce numéro est définie dans la spécification 3GPP TS 23.003. Cela concerne uniquement les appareils dotés de cartes SIM.|
|udid|Identificateur unique de l’appareil (séquence de 40 lettres et chiffres). Il est propre aux appareils iOS.|
|meid|Identificateur d’équipement mobile (nombre global unique identifiant un élément physique de l’équipement de station mobile CDMA). Le format du nombre est défini par le rapport 3GPP2 S. R0048. Toutefois, en pratique il ressemble à un numéro IMEI, mais avec des chiffres hexadécimaux. Un identificateur MEID occupe 56 bits (14 caractères hexadécimaux). Il se compose de trois champs, dont un code régional de 8 bits, un code fabricant de 24 bits et un numéro de série de 24 bits attribué par le fabricant.|
|osVersion|Version du système d’exploitation de l’appareil.
|model|Modèle de l'appareil.
|manufacturer|Fabricant de l'appareil.
|azureDeviceId|ID de l’appareil une fois joint à l’espace de travail avec Azure AD. Il s’agit d’un GUID vide pour les appareils qui ne sont pas joints.|
|lastContactTimeUtc|Date et heure du dernier enregistrement de l’appareil auprès du service de gestion Intune.


## <a name="user-experience"></a>Expérience utilisateur

Quand un utilisateur tente d’accéder à des ressources à l’aide d’un appareil non inscrit, il reçoit une invite d’inscription, comme illustré ci-dessous :

![Exemple d’invite d’inscription](../media/cisco-ise-user-iphone.png)

Quand un utilisateur choisit de s’inscrire, il est redirigé vers le processus d’inscription Intune. L’expérience utilisateur de l’inscription pour Intune est décrite dans les rubriques suivantes :

- [Inscrire un appareil Android dans Intune](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [Inscrire un appareil iOS dans Intune](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Inscrire un appareil Mac OS X dans Intune](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Inscrire un appareil Windows dans Intune](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Vous pouvez également [télécharger un ensemble d’instructions d’inscription](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) et l’adapter pour vos utilisateurs.


### <a name="see-also"></a>Voir aussi

[Cisco Identity Services Engine Administrator Guide, Release 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Jan17_HO1-->


