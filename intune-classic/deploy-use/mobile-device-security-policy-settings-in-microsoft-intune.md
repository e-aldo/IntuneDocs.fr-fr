---
title: "Paramètres de stratégie de sécurité des appareils mobiles | Microsoft Docs"
description: "Utilisez Intune pour configurer une grande variété de paramètres que vous pouvez déployer sur les appareils gérés de votre organisation."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 755cf7d87d7145c55eb5fe583748bd98d34e8fb1
ms.lasthandoff: 12/10/2016



---

# <a name="mobile-device-security-policy-settings-in-microsoft-intune"></a>Paramètres de stratégie de sécurité des appareils mobiles dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

> [!IMPORTANT]
> Microsoft Intune propose désormais des stratégies de configuration distinctes pour chaque plateforme d’appareil. Ces stratégies contiennent les paramètres les plus récents que vous pouvez utiliser. Vous pouvez continuer à utiliser la stratégie de sécurité des appareils mobiles, tous les déploiements existants continueront de fonctionner. Toutefois, vous devez planifier la migration vers les nouvelles stratégies de configuration dès que possible, car la stratégie de sécurité des appareils mobiles sera bientôt supprimée.

Vous pouvez utiliser des stratégies de sécurité des appareils mobiles Intune pour configurer une grande variété de paramètres que vous pouvez déployer sur les appareils gérés de votre organisation. Ces paramètres servent à contrôler les fonctionnalités et la sécurité de vos appareils.

Vous pouvez créer et déployer des stratégies de sécurité des appareils mobiles pour les types d'appareils suivants :

-   Appareils Windows RT 8.1 et Windows 8.1 inscrits

-   Windows RT

-   Windows Phone 8 et Windows Phone 8.1

-   iOS

-   Android et Samsung KNOX Standard

> [!NOTE]
> Certains paramètres ne sont pas applicables à certains appareils. Consultez le tableau ci-dessous pour obtenir une liste complète des paramètres configurables.
> À compter d’octobre 2016, Microsoft Intune ne prend plus en charge les applications du portail d’entreprise Windows 8. Microsoft Intune ne prend également plus en charge les plateformes Windows Phone 8 et WinRT. Ainsi, vous ne pouvez plus inscrire ni mettre à jour des appareils Windows Phone 8 ou WinRT. Néanmoins, vous pouvez continuer à gérer les appareils Windows Phone 8, WinRT et Windows 8 déjà inscrits. Mettez à jour les appareils Windows Phone 8 et Windows 8 vers Windows Phone 8.1 et Windows 8.1, et utilisez les applications Portail d’entreprise Windows 8.1 et Windows Phone 8.1 correspondantes pour continuer à distribuer des applications sur ces appareils sans interruption.

## <a name="security-settings"></a>Paramètres de sécurité

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Non|Non|Oui|Oui|Oui|
|**Type de mot de passe requis**<br /><br />Ce paramètre spécifie le type de mot de passe exigé, par exemple numérique uniquement ou alphanumérique.|Oui|Oui|Oui|Oui|Non|
|**Type de mot de passe requis - Nombre minimum de jeux de caractères**<br /><br />Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe. Toutefois, pour les appareils iOS, il spécifie le nombre de caractères de symbole devant être inclus dans le mot de passe.|Oui|Oui|Oui|Oui|Non|
|**Longueur minimale du mot de passe**|Oui|Oui|Oui|Oui|Oui|
|**Autoriser les mots de passe simples**<br /><br />Exemples de mots de passe simples : « 0000 » et « 1234 ».|Non|Non|Oui|Oui|Non|
|**Nombre d’échecs de connexion répétée autorisé avant réinitialisation de l’appareil**|Oui|Oui|Oui|Oui|Oui|
|**Minutes d’inactivité avant arrêt de l’écran**<sup>1</sup>|Oui|Oui|Oui|Oui|Oui|
|**Expiration du mot de passe (jours)**|Oui|Oui|Oui|Oui|Oui|
|**Mémoriser l’historique des mots de passe**|Oui|Oui|Oui|Oui|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Oui|Oui|Oui|Oui|Oui|
|**Qualité du mot de passe**|Non|Non|Non|Non|Oui|
|**Autoriser un mot de passe image et un code confidentiel**|Oui|Oui|Non|Non|Non|
|**Minutes d’inactivité avant demande du mot de passe**|Non|Non|Non|Oui|Non|
|**Autoriser le déverrouillage par empreinte digitale**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
<sup>1</sup> Pour les appareils iOS, quand vous configurez les paramètres **Minutes d’inactivité avant arrêt de l’écran** et **Minutes d’inactivité avant demande du mot de passe**, ceux-ci sont appliqués de manière séquentielle. Par exemple, si vous affectez aux deux paramètres la valeur **5** minutes, l'écran s'éteint automatiquement après 5 minutes, et l'appareil se verrouille après 5 minutes de plus. Toutefois, si l'utilisateur désactive manuellement l'écran, le second paramètre est immédiatement appliqué. Dans le même exemple, une fois que l'utilisateur a désactivé l'écran, l'appareil se verrouille 5 minutes plus tard.

Quand vous déployez une stratégie de longueur de mot de passe sur des appareils qui exécutent Windows RT, les utilisateurs sont obligés de réinitialiser leur mot de passe, même si leur mot de passe actuel est conforme aux exigences de la stratégie.

## <a name="encryption-settings"></a>Paramètres de chiffrement

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger le chiffrement sur l’appareil mobile**<sup>1</sup><br /><br />Pour les appareils Windows Phone 8, affectez la valeur **Oui**.<br /><br />Pour activer le chiffrement sur les appareils iOS, activez le paramètre **Exiger un mot de passe pour déverrouiller des appareils mobiles**.|Oui|Non|Oui|Non|Oui|
|**Exiger le chiffrement sur les cartes de stockage**<br /><br />Ce paramètre s’applique aux appareils gérés également par Exchange ActiveSync.|Non applicable|Non applicable|Non applicable <br />Les données des applications et données associées sont chiffrées automatiquement.|Non applicable|Oui|
<sup>1</sup>Voici des informations supplémentaires pour les appareils qui exécutent Windows 8.1 :

-   Pour appliquer le chiffrement à des appareils exécutant Windows 8.1, vous devez installer la [Mise à jour du client MDM pour Windows publiée en décembre 2014](http://support.microsoft.com/kb/3013816) sur chaque appareil.

-   Si vous activez ce paramètre pour les appareils Windows 8.1, tous les utilisateurs de l’appareil doivent disposer d’un compte Microsoft.

-   Pour que le chiffrement fonctionne, l'appareil doit répondre aux conditions de certification matérielle de la spécification [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) de Microsoft.

-   Quand vous appliquez le chiffrement à un appareil, vous pouvez uniquement obtenir la clé de récupération à partir du compte Microsoft de l’utilisateur, accessible à partir de son compte OneDrive. Vous ne pouvez pas récupérer cette clé au nom d'un utilisateur.

## <a name="malware-settings"></a>Paramètres anti-programme malveillant

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger un pare-feu réseau**|Oui|Non|Non|Non|Non|
|**Activer SmartScreen**|Oui|Non|Non|Non|Non|

## <a name="system-settings"></a>Paramètres système

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Exiger les mises à jour automatiques**|Oui|Non|Non|Non|Non|
|**Exiger les mises à jour automatiques – Classification minimale des mises à jour à installer automatiquement**<br /><br />Choisissez la classification des mises à jour à installer automatiquement :<br /><br />- **Important**. Installe toutes les mises à jour classifiées comme importantes.<br /><br />- **Recommandé**. Installe toutes les mises à jour classées comme importantes ou recommandées.|Oui|Non|Non|Non|Non|
|**Autoriser la capture d’écran**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser le centre de contrôle sur l’écran verrouillé**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser l’affichage des notifications sur l’écran verrouillé**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser l’affichage du mode Aujourd’hui sur l’écran verrouillé**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Contrôle de compte d'utilisateur**|Oui|Non|Non|Non|Non|
|**Autoriser la soumission des données de diagnostic**|Oui|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser les certificats TLS non autorisés**|Non|Non|Non|Oui|Non|
|**Autoriser le logiciel de portefeuille personnel lors du verrouillage**|Non|Non|Non|Oui|Non|
|**Autoriser la réinitialisation aux paramètres d’usine**|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|


## <a name="cloud-settings--documents-and-data"></a>Paramètres du cloud - documents et données

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser la sauvegarde dans iCloud**|Non|Non|Non|Oui|Non|
|**Autoriser la synchronisation des documents dans iCloud**|Non|Non|Non|Oui|Non|
|**Autoriser la synchronisation du flux de photos dans iCloud**|Non|Non|Non|Oui|Non|
|**Exiger la sauvegarde chiffrée**|Non|Non|Non|Oui|Non|
|**URL des dossiers de travail**<br /><br />Ce paramètre définit l’URL du dossier de travail pour autoriser la synchronisation des documents entre les appareils.|Oui|Non|Non|Non|Non|
|**Autoriser la sauvegarde Google**|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|

## <a name="cloud-settings--accounts-and-synchronization"></a>Paramètres du cloud - comptes et synchronisation

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser le compte Microsoft**|Non|Non|Windows Phone 8.1 uniquement|Non|Non|
|**Autoriser la synchronisation automatique de compte Google**|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|

## <a name="email-settings"></a>Paramètres de messagerie

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser les utilisateurs à télécharger des pièces jointes de messages électroniques**<sup>1</sup>|Non applicable|Non applicable|Non applicable|Non applicable|Non applicable|
|**Période de synchronisation des messages électroniques** <br /><br />Ce paramètre s’applique aux appareils gérés également par Exchange ActiveSync.|Non applicable|Non applicable|Non applicable|Non applicable|Non applicable|
|**Autoriser les appareils mobiles qui ne prennent pas entièrement en charge ces paramètres à se synchroniser avec Exchange (Exchange ActiveSync)** <br /><br />Ce paramètre s’applique aux appareils gérés également par Exchange ActiveSync.|Non applicable|Non applicable|Non applicable|Non applicable|Non applicable|
|**Rendre le compte Microsoft facultatif dans l’application Windows Mail**|Oui|Non|Non|Non|Non|
|**Autoriser les comptes de messagerie personnalisés**|Non|Non|Windows Phone 8.1 uniquement|Non|Non|

## <a name="application-settings---browser"></a>Paramètres de l'application - navigateur

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser le navigateur web**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser le remplissage automatique**|Oui|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser le bloqueur de fenêtres publicitaires**|Oui|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser les cookies**|Non|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser les plug-ins**|Oui|Non|Non|Non|Non|
|**Autoriser les scripts actifs**|Oui|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser l’avertissement de fraudes**|Oui|Non|Non|Oui|Non|
|**Autoriser les sites intranet avec entrée à mot unique**<br /><br />Ce paramètre autorise l’utilisation d’un mot unique pour diriger Internet Explorer vers un site web, par exemple « Bing ».)|Oui|Non|Non|Non|Non|
|**Autoriser la détection automatique des réseaux intranet**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour Internet**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour intranet**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour les sites de confiance**|Oui|Non|Non|Non|Non|
|**Niveau de sécurité pour les sites sensibles**|Oui|Non|Non|Non|Non|
|**Envoyer un en-tête Do Not Track**|Oui|Non|Non|Non|Non|
|**Autoriser l’accès au menu Mode entreprise**|Oui|Non|Non|Non|Non|
|**Emplacement de la liste des sites en mode entreprise**|Oui|Non|Non|Non|Non|

## <a name="application-settings---apps"></a>Paramètres de l'application - applications

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser la boutique d’applications**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Demander un mot de passe pour accéder à la boutique d’applications**|Non|Non|Non|Oui|Non|
|**Autoriser les achats dans l’application**|Non|Non|Non|Oui|Non|
|**Autoriser les documents gérés dans d’autres applications non gérées**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser les documents non gérés dans d’autres applications gérées**|Non|Non|Non|iOS 7 et versions ultérieures|Non|
|**Autoriser la vidéoconférence**|Non|Non|Non|Oui|Non|
|**Autoriser le contenu pour adultes dans la boutique multimédia**|Non|Non|Non|Oui|Non|
|**Autoriser l’installation d’applications**|Non|Non|Non|iOS 6 et versions ultérieures|Non|

## <a name="application-settings---gaming"></a>Paramètres de l'application - jeux

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser les amis Game Center**|Non|Non|Non|Oui|Non|
|**Autoriser les jeux multijoueur**|Non|Non|Non|Oui|Non|

## <a name="device-capabilities-settings---hardware"></a>Paramètres des fonctionnalités de l'appareil - matériel

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser l’appareil photo**|Non|Non|Windows Phone 8.1 uniquement|Oui|Oui|
|**Autoriser le stockage amovible**|Non|Non|Oui|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser le Wi-Fi**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser la connexion Wi-Fi**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser la connexion automatique aux points d’accès Wi-Fi gratuits**|Non|Non|Windows Phone 8.1 uniquement|Non|Non|
|**Autoriser l’indication des points d’accès Wi-Fi**<br /><br />Ce paramètre envoie des informations concernant les connexions Wi-Fi pour détecter les connexions proches.|Non|Non|Windows Phone 8.1 uniquement|Non|Non|
|**Autoriser la géolocalisation**<br /><br />Ce paramètre permet à l’appareil d’utiliser les informations d’emplacement.|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser NFC**<br /><br />Ce paramètre autorise les opérations qui utilisent la communication en champ proche.|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser Bluetooth**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser l’extinction**<br>Si ce paramètre est désactivé, le paramètre **Nombre d’échecs de connexion successifs autorisé avant réinitialisation de l’appareil** pour les appareils Samsung KNOX Standard ne fonctionne pas.|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|

## <a name="device-capabilities-settings---cellular"></a>Paramètres des fonctionnalités de l'appareil - cellulaire

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser l’itinérance vocale**|Non|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser l’itinérance des données**|Oui|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser la synchronisation automatique lors de l’itinérance**|Non|Non|Non|Oui|Non|
|**Autoriser les messages SMS/MMS**|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|

## <a name="device-capabilities-settings---features"></a>Paramètres des fonctionnalités de l'appareil - fonctionnalités

|Nom du paramètre|Windows 8.1 et Windows RT 8.1|Windows RT|Windows Phone 8 et Windows Phone 8.1|iOS|Android et Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Autoriser l’assistant vocal**|Non|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser l’assistant vocal quand l’appareil est verrouillé**|Non|Non|Non|Oui|Non|
|**Autoriser la composition vocale**|Non|Non|Non|Oui|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser la fonction copier-coller**|Non|Non|Windows Phone 8.1 uniquement|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser le partage du Presse-papiers entre applications**|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|
|**Autoriser YouTube**|Non|Non|Non|Non|Oui (Samsung KNOX Standard uniquement)|

### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

