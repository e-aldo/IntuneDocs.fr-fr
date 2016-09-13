---
title: "Restreindre l’accès aux réseaux avec Cisco ISE | Microsoft Intune"
description: "Utilisez Cisco ISE avec Intune pour que les appareils soient inscrits auprès d’Intune et conformes aux stratégies avant d’accéder aux infrastructures Wi-Fi et VPN contrôlées par Cisco ISE."
keywords: 
author: nbigman
manager: angrobe
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 40194f4359d0889806e080a4855b8e1934b667f9
ms.openlocfilehash: 9d6b7198e3c2e30898a8ec83785c7f3b777eda5f


---

# Utilisation de Cisco ISE avec Microsoft Intune
L’intégration d’Intune à Cisco ISE (Identity Services Engine) vous permet de créer des stratégies réseau dans votre environnement ISE faisant appel à l’état de conformité et à l’inscription d’appareils Intune. Vous pouvez utiliser ces stratégies pour vous assurer que l’accès à votre réseau d’entreprise est limité aux appareils gérés par Intune et conformes aux stratégies Intune.

## Étapes de configuration

Pour activer cette intégration, aucune configuration particulière n’est nécessaire dans votre client Intune. Vous devrez fournir des autorisations à votre serveur Cisco ISE pour accéder à votre client Intune. Une fois cette opération effectuée, le reste de la configuration a lieu sur votre serveur Cisco ISE. Cet article indique comment fournir à votre serveur ISE des autorisations d’accès à votre client Intune.

### Étape 1 : Gérer les certificats
1. Dans la console Azure Active Directory (Azure AD), exportez le certificat.

#### Internet Explorer 11


   a. Exécutez Internet Explorer comme administrateur, puis connectez-vous à la console Azure AD.

   b. Choisissez l’icône en forme de verrou dans la barre d’adresse, puis **Afficher les certificats**.

   c. Sous l’onglet **Détails** des propriétés des certificats, choisissez **Copier dans un fichier**.

   d. Dans la page **Assistant Exportation de certificat**, choisissez **Suivant**.

   e. Dans la page **Format du fichier d’exportation**, laissez la valeur par défaut, **X.509 binaire encodé DER (*.cer)**, puis choisissez **Suivant**.  

   f. Dans la page **Fichier à exporter**, choisissez **Parcourir** pour choisir l’emplacement auquel enregistrer le fichier, puis fournissez un nom de fichier. Concrètement, cette opération consiste en fait à nommer le fichier dans lequel le certificat exporté sera enregistré. Choisissez **Suivant** &gt; **Terminer**.

#### Safari

 a. Connectez-vous à la console Azure AD.

b. Cliquez sur l’icône en forme de verrou &gt;  **Plus d’informations**.

   c. Choisissez **Afficher le certificat** &gt; **Détails**.

   d. Choisissez le certificat, puis **Exporter**.  

> [!IMPORTANT]
>
> Vérifiez la date d’expiration du certificat, car vous devrez en exporter et en importer un nouveau quand celui-ci arrivera à expiration.


2. À partir de la console ISE, importez le certificat Intune (le fichier exporté) dans le magasin **Trusted Certificates** (Certificats approuvés).


### Obtenir un certificat auto-signé à partir d’ISE 

1.  Dans la console ISE, accédez à **Administration** > **Certificates** > **System Certificates** > **Generate Self Signed Certificate** (Générer un certificat auto-signé).  
2.       Exportez le certificat auto-signé.
3. Dans un éditeur de texte, modifiez le certificat exporté : [commentaire] : <> I’d rather not put a period at the end of these two statements, I think it could be confusing.
 - Supprimez ** -----BEGIN CERTIFICATE-----**.
 - Supprimez ** -----END CERTIFICATE-----**.
 
Vérifiez que tout le texte contient sur une seule ligne.


### Étape 2 : Créer une application pour ISE dans votre client Azure AD
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


### Étape 3 : Configurer les paramètres ISE
Dans la console d’administration ISE, fournissez ces valeurs de paramètre :
  - **Server Type** (Type de serveur) : Mobile Device Manager
  - **Authentication type** (Type d’authentification) : OAuth – Client Credentials (OAuth – Informations d’identification du client)
  - **Auto Discovery** (Découverte automatique) : Yes (Oui)
  - **Auto Discovery URL** (URL de découverte automatique) : *entrez la valeur provenant de l’étape 1.*
  - **Client ID** (ID client) : *entrez la valeur provenant de l’étape 1.*
  - **Token Issuing URL** (URL émettrice de jeton) : *entrez la valeur provenant de l’étape 1.*



## Informations partagées entre votre client Intune et votre serveur Cisco ISE
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


## Expérience utilisateur

Quand un utilisateur tente d’accéder à des ressources à l’aide d’un appareil non inscrit, il reçoit une invite d’inscription, comme illustré ci-dessous :

![Exemple d’invite d’inscription](../media/cisco-ise-user-iphone.png)

Quand un utilisateur choisit de s’inscrire, il est redirigé vers le processus d’inscription Intune. L’expérience utilisateur de l’inscription pour Intune est décrite dans les rubriques suivantes :

- [Inscrire un appareil Android dans Intune](/intune/enduser/enroll-your-device-in-Intune-android)</br>
- [Inscrire un appareil iOS dans Intune](/intune/enduser/enroll-your-device-in-intune-ios)</br>
- [Inscrire votre appareil Mac OS X dans Intune](/intune/enduser/enroll-your-device-in-intune-mac-os-x)</br>
- [Inscrire un appareil Windows dans Intune](/intune/enduser/enroll-your-device-in-intune-windows)</br>

Vous pouvez également [télécharger un ensemble d’instructions d’inscription](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) et l’adapter pour vos utilisateurs.


### Voir aussi

[Cisco Identity Services Engine Administrator Guide, Release 2.1 (Guide d’administration de Cisco Identity Services Engine, version 2.1)](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)



<!--HONumber=Sep16_HO1-->


