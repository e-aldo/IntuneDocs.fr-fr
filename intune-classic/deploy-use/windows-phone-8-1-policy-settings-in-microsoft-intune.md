---
title: "Paramètres de stratégie Windows Phone 8.1"
description: "Intune fournit un éventail de paramètres généraux intégrés que vous pouvez configurer sur les appareils Windows Phone 8.1. En outre, vous pouvez spécifier des valeurs OMA-URI pour créer des paramètres personnalisés qui ne sont pas disponibles à partir d’Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b496acfa2a596f016142b73b8fc99d1f763c35e0
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie Windows Phone 8.1 dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune fournit un éventail de paramètres généraux intégrés que vous pouvez configurer sur les appareils Windows Phone 8.1. Vous pouvez aussi spécifier des valeurs OMA-URI (Open Mobile Alliance Uniform Resource Identifier) pour créer des paramètres personnalisés qui ne sont pas disponibles à partir d’Intune.

## <a name="general-configuration-settings"></a>Paramètres de configuration généraux

Utilisez la **stratégie de configuration générale Windows Phone (Windows Phone 8.1 et versions ultérieures)** Microsoft Intune pour configurer les paramètres suivants des appareils Windows Phone 8.1 :

-   **Paramètres de sécurité des appareils mobiles** : choisissez des paramètres dans une liste de paramètres prédéfinis qui vous permettent de contrôler diverses fonctions et fonctionnalités sur l'appareil.

-   **Applications conformes et non conformes** : spécifiez une liste d’applications conformes ou non conformes dans votre entreprise. Les appareils Windows Phone peuvent bloquer ou autoriser l’installation de ces applications.

### <a name="applicability-settings"></a>Paramètres d’applicabilité

|Nom du paramètre|Détails|
|----------------|----------------------------------|
|**Appliquer toutes les configurations à Windows 10**|Permet aux paramètres de cette stratégie d’être appliqués aux appareils Windows 10 en plus des appareils Windows Phone 8.1.|

### <a name="password-settings"></a>Paramètres de mot de passe

|Nom du paramètre|Détails|
|----------------|------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Spécifie si les utilisateurs doivent saisir un mot de passe pour accéder à leurs appareils.|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple alphanumérique ou numérique uniquement.|
|**Type de mot de passe requis - Nombre minimum de jeux de caractères**|Spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe. Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Toutefois, pour les appareils iOS, ce paramètre spécifie le nombre de symboles devant être inclus dans le mot de passe.|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères devant figurer dans le mot de passe.|
|**Autoriser les mots de passe simples**|Indique que les mots de passe simples tels que « 0000 » et « 1234 » peuvent être utilisés.|
|**Nombre d’échecs de connexion répétée autorisé avant réinitialisation de l’appareil**|Spécifie le nombre de saisies possibles d’un mot de passe incorrect avant que l’appareil soit réinitialisé.|
|**Minutes d’inactivité avant arrêt de l’écran**|Indique la durée pendant laquelle l’appareil doit rester inactif avant que l’écran se verrouille automatiquement.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant de devoir modifier le mot de passe de l’appareil.|Oui|Oui|
|**Mémoriser l’historique des mots de passe**|Indique si les mots de passe précédemment utilisés sont mémorisés pour empêcher l'utilisateur de les réutiliser.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés mémorisés.|

### <a name="encryption-settings"></a>Paramètres de chiffrement

|Nom du paramètre|Détails|
|----------------|------|
|**Exiger le chiffrement sur l'appareil mobile**|Exige que les données sur les appareils mobiles pris en charge soient chiffrées.|

### <a name="system-settings"></a>Paramètres système

|Nom du paramètre|Détails|
|----------------|-----|
|**Autoriser la capture d’écran**|Permet à l'utilisateur de capturer le contenu de l'écran en tant qu'image.|
|**Autoriser la soumission des données de diagnostic**|Autorise l’appareil à soumettre des informations de diagnostic à Microsoft.|

### <a name="cloud-settings--accounts-and-synchronization"></a>Paramètres du cloud - comptes et synchronisation

|Nom du paramètre|Détails|
|----------------|------|
|**Autoriser le compte Microsoft**|Autorise la liaison d’un compte Microsoft à l’appareil.|

### <a name="email-settings"></a>Paramètres de messagerie

|Nom du paramètre|Détails|
|----------------|-----|
|**Autoriser les comptes de messagerie personnalisés**|Autorise l’appareil à se connecter à des comptes de messagerie non Microsoft.|

### <a name="application-settings---browser"></a>Paramètres de l'application - navigateur

|Nom du paramètre|Détails|
|----------------|-----|
|**Autoriser le navigateur web**|Autorise ou bloque le navigateur web intégré sur les appareils.|

### <a name="application-settings---apps"></a>Paramètres de l'application - applications

|Nom du paramètre|Détails|
|----------------|-----|
|**Autoriser la boutique d’applications**|Permet aux utilisateurs de se connecter à l'App Store depuis l'appareil.|

### <a name="device-capabilities-settings---hardware"></a>Paramètres des fonctionnalités de l'appareil - matériel

|Nom du paramètre|Détails|
|----------------|-----|
|**Autoriser l’appareil photo**|Autorise ou bloque l’appareil photo de l’appareil.|
|**Autoriser le stockage amovible**|Autorise l’appareil à utiliser du stockage amovible, tel qu’une carte SD.|
|**Autoriser le Wi-Fi**|Active ou désactive la fonctionnalité Wi-Fi de l'appareil.|
|**Autoriser la connexion Wi-Fi**|Autorise l’utilisation de la connexion Wi-Fi sur l’appareil.|
|**Autoriser la connexion automatique aux points d’accès Wi-Fi gratuits**|Autorise l’appareil à se connecter automatiquement aux points d’accès Wi-Fi gratuits et à accepter automatiquement les termes et conditions de la connexion.|
|**Autoriser l’indication des points d’accès Wi-Fi**|Envoie des informations concernant les connexions Wi-Fi pour aider l’utilisateur à détecter les connexions proches.|
|**Autoriser la géolocalisation**|Permet à l’appareil d’utiliser les informations d’emplacement.|
|**Autoriser NFC**|Autorise les opérations qui utilisent la communication en champ proche.|
|**Autoriser Bluetooth**|Active ou désactive la fonctionnalité Bluetooth de l’appareil.|

### <a name="device-capabilities-settings---features"></a>Paramètres des fonctionnalités de l'appareil - fonctionnalités

|Nom du paramètre|Détails|
|----------------|----|
|**Autoriser la fonction copier-coller**|Autorise la fonction copier-coller sur les appareils.|

### <a name="settings-for-allowed-and-blocked-apps"></a>Paramètres des applications autorisées et bloquées
Dans la **Liste des applications autorisées et bloquées**, spécifiez une liste des applications que vous souhaitez autoriser ou bloquer en utilisant les informations suivantes :

> [!NOTE]
> Une stratégie ne peut contenir qu’une liste d’applications autorisées ou bloquées. Vous ne pouvez pas spécifier les deux dans la même stratégie.

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Bloquer l'ouverture des applications répertoriées sur l'appareil**|Répertorie les applications qui ne sont pas gérées par Intune et que les utilisateurs ne sont pas autorisés à installer et à exécuter.|
|**Autoriser les appareils à installer uniquement les applications répertoriées**|Répertorie les applications que les utilisateurs sont autorisés à installer. Les utilisateurs ne peuvent pas installer d'autres applications. Les applications qui sont gérées par Intune sont autorisées automatiquement.|
|**Ajouter**|Ajoute une application à la liste sélectionnée. Spécifiez un nom de votre choix, l’URL de l’application dans le magasin d’applications et l’éditeur de l’application (facultatif). Pour obtenir de l’aide, consultez Comment spécifier des URL de magasins d’applications plus loin dans cette rubrique.
|**Importer des applications**|Importe une liste d’applications que vous avez spécifiée dans un fichier de valeurs séparées par des virgules. Utilisez le format, le nom de l’application, l’éditeur et l’URL de l’application dans le fichier.|
|**Éditer**|Vous permet de modifier le nom, l’éditeur et l’URL de l’application sélectionnée.|
|**Supprimer**|Supprime l'application sélectionnée dans la liste.|
> [!IMPORTANT]
> Si vous spécifiez une liste d’applications autorisées pour les appareils Windows Phone 8.1, vous devez ajouter l’application Portail d’entreprise à cette liste, ou elle sera bloquée.


### <a name="reference-information-for-allowed-and-blocked-apps"></a>Informations de référence pour les applications autorisées et bloquées

#### <a name="how-to-specify-urls-to-app-stores"></a>Comment spécifier des URL de magasins d'applications
Pour insérer une URL d’application dans la liste des applications autorisées ou bloquées, utilisez le format suivant :

Dans la page [Applications+Jeux Windows Phone](http://www.windowsphone.com/store/overview), recherchez l’application à utiliser.

Ouvrez la page de l'application, puis copiez l'URL dans le Presse-papiers. Vous pouvez maintenant utiliser cette URL dans la liste des applications autorisées ou bloquées.

**Exemple :** recherchez l'application Skype dans le Store. L’URL que vous utilisez est **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## <a name="custom-policy-settings"></a>Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée Windows Phone** de Microsoft Intune pour déployer les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les **Appareils Windows Phone 8.1**. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité vous permet de déployer les paramètres Windows Phone qui ne sont pas configurables avec une stratégie de configuration générale Intune. Pour obtenir des informations sur les paramètres que vous pouvez configurer avec ces stratégies, consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Pour obtenir de l’aide sur la création de paramètres OMA-URI pour les appareils Windows Phone, consultez la [documentation du protocole MDM Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx).

### <a name="general-settings"></a>Paramètres généraux :

|Nom du paramètre|Détails|
|----------------|--------------------|
|**Nom**|Entrez un nom unique pour la stratégie afin de vous aider à l’identifier dans la console Intune.|
|**Description**|Entrez une description générale de la stratégie et d'autres informations pertinentes pour faciliter sa localisation.|

### <a name="oma-uri-settings"></a>Paramètres OMA-URI

Dans la section **Paramètres OMA-URI**, cliquez sur **Ajouter** pour ajouter un paramètre. Vous pouvez également modifier ou supprimer un paramètre existant.

Dans la boîte de dialogue **Ajouter ou modifier un paramètre OMA-URI**, spécifiez les informations suivantes :

|Nom du paramètre|Détails|
    |--------|--------------------|
    |**Nom du paramètre**|Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.|
    |**Description du paramètre**|Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.|
    |**Type de données**|Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez parmi :<br /><br />-   **Chaîne**<br />-   **Chaîne (XML)**<br />-   **Date et heure**<br />-   **Entier**<br />-   **Virgule flottante**<br />-   **Booléen**|
    |**OMA-URI (sensible à la casse)**|Spécifiez l’identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.|
    |**Valeur**|Spécifiez la valeur à associer à l’identificateur OMA-URI spécifié précédemment.|

### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
