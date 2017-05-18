---
title: "Paramètres de la stratégie Windows | Microsoft Docs"
description: "Utilisez la stratégie de configuration générale Windows (Windows 8.1 et versions ultérieures) Intune pour configurer les paramètres des appareils Windows 8 et Windows 8.1 inscrits."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 53ac1c31cf2a2054080e43716b30c50c73961759
ms.lasthandoff: 12/10/2016


---

# <a name="windows-policy-settings-in-microsoft-intune"></a>Paramètres de la stratégie Windows dans Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Utilisez la stratégie de **configuration générale Windows (Windows 8.1 et versions ultérieures) Microsoft Intune** pour configurer les paramètres suivants des appareils Windows 8, Windows 8.1 et Windows RT 8.1 inscrits :

## <a name="applicability-settings"></a>Paramètres d’applicabilité

|Nom du paramètre|Détails|
|----------------|----------------------------------|
|**Appliquer toutes les configurations à Windows 10**|Permet aux paramètres de cette stratégie d’être appliqués aux appareils Windows 10 en plus des appareils Windows 8 et Windows 8.1.|

## <a name="security-settings"></a>Paramètres de sécurité

|Nom du paramètre|Détails|
|----------------|------|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple alphanumérique ou numérique uniquement.|
|**Type de mot de passe requis - Nombre minimum de jeux de caractères**|Spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe. Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Toutefois, pour les appareils iOS, ce paramètre spécifie le nombre de symboles devant être inclus dans le mot de passe.|
|**Longueur minimale du mot de passe**|Configure la longueur minimale requise (en caractères) pour le mot de passe.|
|**Nombre d’échecs de connexion répétée autorisé avant réinitialisation de l’appareil**|Réinitialise l’appareil si le nombre d’échecs de tentative spécifié est atteint.|
|**Minutes d’inactivité avant arrêt de l’écran**|Spécifie le nombre de minutes pendant lesquelles un appareil doit être inactif avant qu’un mot de passe soit nécessaire pour le déverrouiller.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant de devoir modifier le mot de passe de l’appareil.|
|**Mémoriser l’historique des mots de passe**|Spécifie si l’utilisateur peut configurer des mots de passe précédemment utilisés.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.|
|**Autoriser un mot de passe image et un code confidentiel**|Permet l’utilisation d’un mot de passe image et d’un code confidentiel. Un mot de passe image permet à l’utilisateur de se connecter en effectuant des gestes sur une image. Un code confidentiel permet aux utilisateurs de se connecter rapidement à l’aide d’un code à quatre chiffres.|

## <a name="encryption-settings"></a>Paramètres de chiffrement

|Nom du paramètre|Détails|
|----------------|-----|
|**Exiger le chiffrement sur l’appareil mobile**<sup>1</sup>|Exige que les fichiers soient chiffrés sur le périphérique.|
<sup>1</sup> Informations supplémentaires pour les appareils qui exécutent Windows 8.1

-   Pour appliquer le chiffrement à des appareils exécutant Windows 8.1, vous devez installer la [Mise à jour du client MDM pour Windows publiée en décembre 2014](http://support.microsoft.com/kb/3013816) sur chaque appareil.

-   Si vous activez ce paramètre pour les appareils Windows 8.1, tous les utilisateurs de l’appareil doivent disposer d’un compte Microsoft.

-   Pour que le chiffrement fonctionne, l'appareil doit répondre aux conditions de certification matérielle de la spécification [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) de Microsoft.

-   Quand vous appliquez le chiffrement à un appareil, vous pouvez uniquement obtenir la clé de récupération à partir du compte Microsoft de l’utilisateur, accessible à partir de son compte OneDrive. Vous ne pouvez pas récupérer cette clé au nom d'un utilisateur.

## <a name="malware-settings"></a>Paramètres anti-programme malveillant

|Nom du paramètre|Détails|
|----------------|-----|
|**Exiger un pare-feu réseau**|Nécessite l’activation du Pare-feu Windows.|
|**Activer SmartScreen**|Nécessite l’utilisation de Windows SmartScreen.|

## <a name="system-settings"></a>Paramètres système

|Nom du paramètre|Détails|
|----------------|-------|
|**Exiger les mises à jour automatiques**|Active le paramètre de mises à jour automatiques sur les appareils.|
|**Exiger les mises à jour automatiques – Classification minimale des mises à jour à installer automatiquement**|Choisit la classification des mises à jour à installer automatiquement :<br /><br />-   **Importantes** : installe toutes les mises à jour classifiées comme importantes.<br />-   **Recommandées** : installe toutes les mises à jour classées comme importantes ou recommandées.|
|**Contrôle de compte d'utilisateur**|Nécessite l’utilisation du contrôle de compte d’utilisateur (UAC) sur les appareils.|
|**Autoriser la soumission des données de diagnostic**|Autorise l’appareil à soumettre des informations de diagnostic à Microsoft.|


## <a name="cloud-settings--documents-and-data"></a>Paramètres du cloud - documents et données

|Nom du paramètre|Détails|
|----------------|------|
|**URL des dossiers de travail**|Définit l’URL du dossier de travail pour autoriser la synchronisation des documents entre les appareils.|

## <a name="email-settings"></a>Paramètres de messagerie

|Nom du paramètre|Détails|
|----------------|-----|
|**Rendre le compte Microsoft facultatif dans l’application Windows Mail**|Autorise l’accès à l’application Windows Mail sans compte Microsoft.|

## <a name="application-settings---browser"></a>Paramètres de l'application - navigateur

|Nom du paramètre|Détails|
|----------------|-----|
|**Autoriser le remplissage automatique**|Permet aux utilisateurs de modifier les paramètres de saisie semi-automatique dans le navigateur.|
|**Autoriser le bloqueur de fenêtres publicitaires**|Active ou désactive le bloqueur de fenêtres publicitaires du navigateur.|
|**Autoriser les plug-ins**|Permet aux utilisateurs d’ajouter des plug-ins à Internet Explorer.|
|**Autoriser les scripts actifs**|Permet au navigateur d’exécuter des scripts, tels que des scripts ActiveX.|
|**Autoriser l’avertissement de fraudes**|Active ou désactive les avertissements pour les sites web potentiellement frauduleux.|
|**Autoriser les sites intranet avec entrée à mot unique**|Permet l’utilisation d’un mot unique pour diriger Internet Explorer vers un site web, tel que Bing.|
|**Autoriser la détection automatique des réseaux intranet**|Facilite la configuration de la sécurité des sites intranet dans Internet Explorer.|
|**Niveau de sécurité pour Internet**|Définit le niveau de sécurité d’Internet Explorer pour les sites Internet.|
|**Niveau de sécurité pour intranet**|Définit le niveau de sécurité d’Internet Explorer pour les sites intranet.|
|**Niveau de sécurité pour les sites de confiance**|Configure le niveau de sécurité pour la zone Sites de confiance.|
|**Niveau de sécurité pour les sites sensibles**|Configure le niveau de sécurité pour la zone Sites sensibles.|
|**Envoyer un en-tête Do Not Track**|Envoie un en-tête Do Not Track aux sites visités dans Internet Explorer.|
|**Autoriser l’accès au menu Mode entreprise**|Permet aux utilisateurs d'accéder aux options du menu Mode entreprise à partir d'Internet Explorer.<br>Si vous sélectionnez ce paramètre, vous pouvez également spécifier un **Emplacement du rapport de journalisation**, qui contient une URL vers un rapport affichant les sites web pour lesquels les utilisateurs ont activé l’accès en Mode entreprise.|
|**Emplacement de la liste des sites en mode entreprise**|Spécifie l’emplacement de la liste des sites web qui utilisent le Mode entreprise quand il est actif.|

## <a name="device-capabilities-settings---cellular"></a>Paramètres des fonctionnalités de l'appareil - cellulaire

|Nom du paramètre|Détails|
|----------------|----|
|**Autoriser l’itinérance des données**|Autorise l’itinérance des données quand l’appareil se trouve sur un réseau de téléphonie mobile.|



### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

