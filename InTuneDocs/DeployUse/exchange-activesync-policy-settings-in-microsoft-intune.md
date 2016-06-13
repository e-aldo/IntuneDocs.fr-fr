---
# required metadata

title: Paramètres de la stratégie Exchange ActiveSync | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie Exchange ActiveSync dans Microsoft Intune
Utilisez la stratégie **Exchange ActiveSync** de Microsoft Intune pour configurer les paramètres qui vous permettent de contrôler diverses fonctions et fonctionnalités sur les appareils gérés par Exchange ActiveSync.


## Paramètres de mot de passe

|Nom du paramètre|Détails
|----------------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Indique si les appareils doivent être verrouillés à l’aide d’un mot de passe.<br>(ne s’applique pas aux appareils exécutant Windows RT)|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple numérique uniquement ou alphanumérique|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères requis dans le mot de passe de l’appareil.|
|**Autoriser les mots de passe simples**|Exemples de mots de passe simples : « 0000 » et « 1234 ».|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Autoriser ce nombre de tentatives de saisie d’un mot de passe correct avant réinitialisation de l’appareil.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours au bout duquel le mot de passe de l’appareil doit être modifié.
|**Mémoriser l'historique des mots de passe**|Indique s’il faut interdire l’utilisation des mots de passe utilisés précédemment.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Indique le nombre de mots de passe précédemment utilisés qui ne peuvent pas être réutilisés.|
|**Minutes d'inactivité avant demande du mot de passe**|Indique la durée pendant laquelle l’appareil doit être inactif avant que l’écran se verrouille.

## Paramètres de chiffrement

|Nom du paramètre|Détails|
|----------------|
|**Exiger le chiffrement sur l’appareil mobile**<sup>1</sup>|Exige que les données sur l’appareil soit chiffrées quand cela est pris en charge.<br>Pour les appareils Windows Phone 8, affectez la valeur **Oui**.<br /><br />Pour activer le chiffrement sur les appareils iOS, activez le paramètre **Exiger un mot de passe pour déverrouiller des appareils mobiles**.|
|**Exiger le chiffrement sur les cartes de stockage**|Exige que les données stockées sur un stockage externe tel qu’une carte SD soient chiffrées (sur les appareils pris en charge).
<sup>1</sup> Informations supplémentaires pour les appareils qui exécutent Windows 8.1

-   Pour appliquer le chiffrement à des appareils exécutant Windows 8.1, vous devez installer la [Mise à jour du client MDM pour Windows publiée en décembre 2014](http://support.microsoft.com/kb/3013816) sur chaque appareil.

-   Si vous activez ce paramètre pour les appareils Windows 8.1, tous les utilisateurs de l'appareil doivent disposer d'un compte Microsoft.

-   Pour que le chiffrement fonctionne, l'appareil doit répondre aux conditions de certification matérielle de la spécification [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) de Microsoft.

-   Quand vous appliquez le chiffrement à un appareil, vous pouvez uniquement obtenir la clé de récupération à partir du compte Microsoft de l'utilisateur auquel vous devez accéder à partir de son compte OneDrive. Vous ne pouvez pas récupérer cette clé au nom d'un utilisateur.

## Paramètres de messagerie

|Nom du paramètre|Détails
|----------------|
|**Autoriser les utilisateurs à télécharger des pièces jointes de messages électroniques**|Spécifie si les pièces jointes peuvent être téléchargées sur l’appareil.|
|**Période de synchronisation des messages électroniques**|Sélectionnez le nombre de jours de courrier électronique reçu qui seront synchronisés avec l’appareil.
|**Autoriser les appareils mobiles qui ne prennent pas entièrement en charge ces paramètres Exchange ActiveSync à se synchroniser avec Exchange**|Spécifie s’il faut autoriser l’accès à Exchange sur les appareils qui ne prennent pas en charge un ou plusieurs paramètres Exchange ActiveSync.

## Paramètres du navigateur

|Nom du paramètre|Détails
|----------------|-
|**Autoriser le navigateur web**|Spécifie si le navigateur web de l’appareil peut être utilisé.<br>(non disponible pour Windows RT ou Windows Phone)

## Paramètres matériels

|Nom du paramètre|Détails
|----------------|
|**Autoriser l'appareil photo**|Spécifie si l’appareil photo de l’appareil peut être utilisé.<br>(non disponible pour Windows RT ou Windows Phone)



### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO1-->


