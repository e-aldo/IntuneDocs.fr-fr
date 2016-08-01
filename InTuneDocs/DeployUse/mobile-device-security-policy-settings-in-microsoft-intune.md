---
title: "Paramètres de stratégie de sécurité des appareils mobiles | Microsoft Intune"
description: "Utilisez Intune pour configurer une grande variété de paramètres que vous pouvez déployer sur les appareils gérés de votre organisation."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 648cc02b47682a58195ee927560763818b6d32ac


---

# Paramètres de stratégie de sécurité des appareils mobiles dans Microsoft Intune
> [!IMPORTANT]
> Microsoft Intune offre désormais des stratégies de configuration distinctes pour chaque plateforme d’appareil. Elles contiennent les paramètres les plus récents que vous pouvez utiliser. Vous pouvez continuer à utiliser la stratégie de sécurité des appareils mobiles et tous les déploiements existants continueront de fonctionner. Toutefois, vous devez planifier la migration vers les nouvelles stratégies de configuration dès que possible, car la stratégie de sécurité des appareils mobiles sera bientôt supprimée.

Utilisez des stratégies de sécurité des appareils mobiles Intune pour configurer une grande variété de paramètres que vous pouvez déployer sur les appareils gérés de votre organisation. Ces paramètres peuvent être utilisés pour contrôler les fonctionnalités et la sécurité de vos appareils.

Vous pouvez créer et déployer des stratégies de sécurité des appareils mobiles pour les types d'appareils suivants :

-   Appareils Windows RT 8.1 et Windows 8.1 inscrits

-   Windows RT

-   Windows Phone 8 et Windows Phone 8.1

-   iOS

-   Android et Samsung KNOX

> [!NOTE]
> Certains paramètres ne sont pas applicables à certains appareils. Consultez le tableau ci-dessous pour obtenir une liste complète des paramètres que vous pouvez configurer.

## Paramètres de sécurité

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Non|Non|Oui|Oui|Oui|
|**Type de mot de passe requis**<br /><br />(spécifie le type de mot de passe requis, par exemple, numérique uniquement ou alphanumérique)|Oui|Oui|Oui|Oui|Non|
|**Type de mot de passe requis - Nombre minimum de jeux de caractères**<br /><br />Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe). Toutefois, pour les appareils iOS, il spécifie le nombre de caractères de symbole devant être inclus dans le mot de passe)|Oui|Oui|Oui|Oui|Non|
|**Longueur minimale du mot de passe**|Oui|Oui|Oui|Oui|Oui|
|**Autoriser les mots de passe simples**<br /><br />Exemples de mots de passe simples : « 0000 » et « 1234 ».|Non|Non|Oui|Oui|Non|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Oui|Oui|Oui|Oui|Oui|
|**Minutes d’inactivité avant arrêt de l’écran**<sup>1</sup>|Oui|Oui|Oui|Oui|Oui|
|**Expiration du mot de passe (jours)**|Oui|Oui|Oui|Oui|Oui|
|**Mémoriser l'historique des mots de passe**|Oui|Oui|Oui|Oui|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Oui|Oui|Oui|Oui|Oui|
|**Qualité du mot de passe**|Non|Non|Non|Non|Oui|
|**Autoriser un mot de passe image et un code confidentiel**|Oui|Oui|Non|Non|Non|
|**Minutes d'inactivité avant demande du mot de passe**|Non|Non|Non|Oui|Non|
|**Autoriser le déverrouillage par empreinte digitale**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
Pour les appareils iOS, quand vous configurez les paramètres **Minutes d’inactivité avant arrêt de l’écran** et **Minutes d’inactivité avant demande du mot de passe**, ils sont appliqués de manière séquentielle. Par exemple, si vous affectez aux deux paramètres la valeur **5** minutes, l'écran s'éteint automatiquement après 5 minutes, et l'appareil se verrouille après 5 minutes de plus. Toutefois, si l'utilisateur désactive manuellement l'écran, le second paramètre est immédiatement appliqué. Dans le même exemple, une fois que l'utilisateur a désactivé l'écran, l'appareil se verrouille 5 minutes plus tard.

Quand vous déployez une stratégie de longueur de mot de passe sur des appareils qui exécutent Windows RT, les utilisateurs sont obligés de réinitialiser leur mot de passe, même si leur mot de passe actuel est conforme aux exigences de la stratégie.

## Paramètres de chiffrement

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger le chiffrement sur l’appareil mobile**<sup>1</sup><br /><br />Pour les appareils Windows Phone 8, affectez la valeur **Oui**.<br /><br />Pour activer le chiffrement sur les appareils iOS, activez le paramètre **Exiger un mot de passe pour déverrouiller des appareils mobiles**.|Oui|Non|Oui|Non|Oui|
|**Exiger le chiffrement sur les cartes de stockage**<br /><br />S’applique aux appareils gérés également par Exchange ActiveSync.|Non applicable|Non applicable|Non applicable (chiffrement automatique des applications et données associées)|Non applicable|Oui|
Informations supplémentaires pour les appareils qui exécutent Windows 8.1

-   Pour appliquer le chiffrement à des appareils exécutant Windows 8.1, vous devez installer la [Mise à jour du client MDM pour Windows publiée en décembre 2014](http://support.microsoft.com/kb/3013816) sur chaque appareil.

-   Si vous activez ce paramètre pour les appareils Windows 8.1, tous les utilisateurs de l'appareil doivent disposer d'un compte Microsoft.

-   Pour que le chiffrement fonctionne, l'appareil doit répondre aux conditions de certification matérielle de la spécification [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) de Microsoft.

-   Quand vous appliquez le chiffrement à un appareil, vous pouvez uniquement obtenir la clé de récupération à partir du compte Microsoft de l'utilisateur auquel vous devez accéder à partir de son compte OneDrive. Vous ne pouvez pas récupérer cette clé au nom d'un utilisateur.

## Paramètres anti-programme malveillant

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger un pare-feu réseau**|Oui|Non|Non|Non|Non|
|**Activer SmartScreen**|Oui|Non|Non|Non|Non|

## Paramètres système

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger les mises à jour automatiques**|Oui|Non|Non|Non|Non|
|**Exiger les mises à jour automatiques – Classification minimale des mises à jour à installer automatiquement**<br /><br />Choisissez la classification des mises à jour à installer automatiquement :<br /><br />**Importantes** : installe toutes les mises à jour classifiées comme importantes.<br /><br />**Recommandées** : installe toutes les mises à jour classifiées comme importantes ou recommandées.|Oui|Non|Non|Non|Non|
|**Autoriser la capture d'écran**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser le centre de contrôle sur l'écran verrouillé**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser l'affichage des notifications sur l'écran verrouillé**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser l'affichage du mode Aujourd'hui sur l'écran verrouillé**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Contrôle de compte d'utilisateur**|Oui|Non|Non|Non|Non|
|**Autoriser la soumission des données de diagnostic**|Oui|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser les certificats TLS non autorisés**|Non|Non|Non|Oui|Non|
|**Autoriser le logiciel de portefeuille personnel lors du verrouillage**|Non|Non|Non|Oui|Non|
|**Autoriser la réinitialisation aux paramètres d'usine**|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|


## Paramètres du cloud - documents et données

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser la sauvegarde dans iCloud**|Non|Non|Non|Oui|Non|
|**Autoriser la synchronisation des documents dans iCloud**|Non|Non|Non|Oui|Non|
|**Autoriser la synchronisation du flux de photos dans iCloud**|Non|Non|Non|Oui|Non|
|**Exiger la sauvegarde chiffrée**|Non|Non|Non|Oui|Non|
|**URL des dossiers de travail**<br /><br />(définit l'URL du dossier de travail pour autoriser la synchronisation des documents entre les appareils)|Oui|Non|Non|Non|Non|
|**Autoriser la sauvegarde Google**|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|

## Paramètres du cloud - comptes et synchronisation

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser le compte Microsoft**|Non|Non|Windows Phone 8.1 uniquement|Non|Non|
|**Autoriser la synchronisation automatique de compte Google**|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|

## Paramètres de messagerie

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser les utilisateurs à télécharger des pièces jointes de messages électroniques**<sup>1</sup>|Non applicable|Non applicable|Non applicable|Non applicable|Non applicable|
|**Période de synchronisation des messages électroniques** S’applique aux appareils gérés également par Exchange ActiveSync.|Non applicable|Non applicable|Non applicable|Non applicable|Non applicable|
|**Autoriser les appareils mobiles qui ne prennent pas entièrement en charge ces paramètres pour se synchroniser avec Exchange (Exchange ActiveSync)** S’applique aux appareils gérés également par Exchange ActiveSync.|Non applicable|Non applicable|Non applicable|Non applicable|Non applicable|
|**Rendre le compte Microsoft facultatif dans l'application Windows Mail**|Oui|Non|Non|Non|Non|
|**Autoriser les comptes de messagerie personnalisés**|Non|Non|Windows Phone 8.1 uniquement|Non|Non|

## Paramètres de l'application - navigateur

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser le navigateur web**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser le remplissage automatique**|Oui|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser le bloqueur de fenêtres publicitaires**|Oui|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser les cookies**|Non|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser les plug-ins**|Oui|Non|Non|Non|Non|
|**Autoriser les scripts actifs**|Oui|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser l'avertissement de fraudes**|Oui|Non|Non|Oui|Non|
|**Autoriser les sites intranet avec entrée à mot unique**<br /><br />(permet l'utilisation d'un mot unique pour diriger Internet Explorer vers un site web, tel que « Bing »)|Oui|Non|Non|Non|Non|
|**Autoriser la détection automatique des réseaux intranet**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour Internet**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour intranet**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour les sites de confiance**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour les sites sensibles**|Oui|Non|Non|Non|Non|
|**Envoyer un en-tête Do Not Track**|Oui|Non|Non|Non|Non|
|**Autoriser l'accès au menu Mode entreprise**|Oui|Non|Non|Non|Non|
|**Emplacement de la liste des sites en mode entreprise**|Oui|Non|Non|Non|Non|

## Paramètres de l'application - applications

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser la boutique d'applications**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX uniquement)|
|**Demander un mot de passe pour accéder à la boutique d'applications**|Non|Non|Non|Oui|Non|
|**Autoriser les achats dans l'application**|Non|Non|Non|Oui|Non|
|**Autoriser les documents gérés dans d'autres applications non gérées**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser les documents non gérés dans d'autres applications gérées**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser la vidéoconférence**|Non|Non|Non|Oui|Non|
|**Autoriser le contenu pour adultes dans la boutique multimédia**|Non|Non|Non|Oui|Non|
|**Autoriser l'installation d'applications**|Non|Non|Non|iOS 6 et versions ultérieures|Non|

## Paramètres de l'application - jeux

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser les amis Game Center**|Non|Non|Non|Oui|Non|
|**Autoriser les jeux multijoueur**|Non|Non|Non|Oui|Non|

## Paramètres des fonctionnalités de l'appareil - matériel

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser l'appareil photo**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui|
|**Autoriser le stockage amovible**|Non|Non|Oui|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser le Wi-Fi**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser la connexion Wi-Fi**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser la connexion automatique aux points d'accès Wi-Fi gratuits**|Non|Non|Windows Phone 8.1 uniquement|Non|Non|
|**Autoriser l'indication des points d'accès Wi-Fi**<br /><br />(envoyer des informations concernant les connexions Wi-Fi pour détecter les connexions proches)|Non|Non|Windows Phone 8.1 uniquement|Non|Non|
|**Autoriser la géolocalisation**<br /><br />(permet à l'appareil d'utiliser les informations d'emplacement)|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser NFC**<br /><br />(autorise les opérations qui utilisent la communication en champ proche)|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser Bluetooth**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser l'extinction**<br>Si ce paramètre est désactivé, le paramètre **Nombre d’échecs de connexion répétée autorisé avant réinitialisation de l’appareil** ne fonctionne pas pour les appareils Samsung KNOX.|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|

## Paramètres des fonctionnalités de l'appareil - cellulaire

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser l'itinérance vocale**|Non|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser l'itinérance des données**|Oui|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser la synchronisation automatique lors de l'itinérance**|Non|Non|Non|Oui|Non|
|**Autoriser les messages SMS/MMS**|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|

## Paramètres des fonctionnalités de l'appareil - fonctionnalités

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser l'assistant vocal**|Non|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser l'assistant vocal quand l'appareil est verrouillé**|Non|Non|Non|Oui|Non|
|**Autoriser la composition vocale**|Non|Non|Non|Oui|Oui (Samsung KNOX uniquement)|
|**Autoriser la fonction copier-coller**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser le partage du Presse-papiers entre applications**|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|
|**Autoriser YouTube**|Non|Non|Non|Non|Oui (Samsung KNOX uniquement)|

### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec Microsoft Intune policies.md](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


