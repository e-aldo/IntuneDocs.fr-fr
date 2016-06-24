---
# required metadata

title: Paramètres de la stratégie Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Paramètres de la stratégie Windows dans Microsoft Intune
Utilisez la **stratégie de configuration générale Windows (Windows 8.1 et versions ultérieures)** Microsoft Intune pour configurer les paramètres des appareils Windows 8 et Windows 8.1 inscrits :

## Paramètres d’applicabilité

|Nom du paramètre|Détails|
|----------------|----------------------------------|
|**Appliquer toutes les configurations à Windows 10**|Permet aux paramètres de cette stratégie d’être appliqués aux appareils Windows 10 en plus des appareils Windows 8 et Windows 8.1.|

## Paramètres de sécurité

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Type de mot de passe requis**|Spécifie le type de mot de passe requis, par exemple, numérique uniquement ou alphanumérique.|Oui|Oui|
|**Type de mot de passe requis - Nombre minimum de jeux de caractères**|Il existe quatre jeux de caractères : lettres minuscules, lettres majuscules, symboles et chiffres. Ce paramètre spécifie le nombre de jeux de caractères différents devant être inclus dans le mot de passe. Toutefois, pour les appareils iOS, il spécifie le nombre de caractères de symbole devant être inclus dans le mot de passe.|Oui|Oui|
|**Longueur minimale du mot de passe**<sup>1</sup>|Configure la longueur minimale requise (en caractères) pour le mot de passe sur les appareils.|Oui|Oui|
|**Nombre d'échecs de connexion répétée autorisé avant réinitialisation de l'appareil**|Réinitialise le périphérique si la connexion échoue ce nombre de fois.|Oui|Oui|
|**Minutes d'inactivité avant arrêt de l'écran**|Choisissez le nombre de minutes pendant lesquelles un appareil doit être inactif avant qu’un mot de passe soit requis pour le déverrouiller.| Oui|Oui|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant de devoir modifier le mot de passe de l’appareil.|Oui|Oui|
|**Mémoriser l'historique des mots de passe**|Spécifie si l’utilisateur peut configurer des mots de passe précédemment utilisés.|Oui|Oui|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe précédemment utilisés conservés par l’appareil.|Oui|Oui|
|**Autoriser un mot de passe image et un code confidentiel**|Autorise l'utilisation d'un mot de passe image et d’un code confidentiel sur l’appareil. Un mot de passe image permet à l'utilisateur de se connecter en effectuant des gestes sur une image. Un code confidentiel permet aux utilisateurs de se connecter rapidement à l’aide d’un code à 4 chiffres.|Oui|Oui|
<sup>1</sup> Quand vous déployez une stratégie de longueur de mot de passe sur des appareils qui exécutent Windows RT, les utilisateurs sont obligés de réinitialiser leur mot de passe, même si leur mot de passe actuel est conforme aux exigences de la stratégie.

## Paramètres de chiffrement

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Exiger le chiffrement sur l’appareil mobile**<sup>1</sup>|Exige que les fichiers soient chiffrés sur le périphérique.<br>Pour les appareils Windows Phone 8, affectez la valeur **Oui**.|Oui|Non|
<sup>1</sup> Informations supplémentaires pour les appareils qui exécutent Windows 8.1

-   Pour appliquer le chiffrement à des appareils exécutant Windows 8.1, vous devez installer la [Mise à jour du client MDM pour Windows publiée en décembre 2014](http://support.microsoft.com/kb/3013816) sur chaque appareil.

-   Si vous activez ce paramètre pour les appareils Windows 8.1, tous les utilisateurs de l'appareil doivent disposer d'un compte Microsoft.

-   Pour que le chiffrement fonctionne, l'appareil doit répondre aux conditions de certification matérielle de la spécification [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) de Microsoft.

-   Quand vous appliquez le chiffrement à un appareil, vous pouvez uniquement obtenir la clé de récupération à partir du compte Microsoft de l'utilisateur auquel vous devez accéder à partir de son compte OneDrive. Vous ne pouvez pas récupérer cette clé au nom d'un utilisateur.

## Paramètres anti-programme malveillant

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Exiger un pare-feu réseau**|Nécessite l’activation du pare-feu Windows.|Oui|Non|
|**Activer SmartScreen**|Nécessite l'utilisation de Windows SmartScreen sur les appareils.|Oui|Non|

## Paramètres système

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Exiger les mises à jour automatiques**|Activez les mises à jour automatiques sur les appareils.|Oui|Non|
|**Exiger les mises à jour automatiques – Classification minimale des mises à jour à installer automatiquement**|Choisissez la classification des mises à jour à installer automatiquement :<br /><br />-   **Importantes** : installe toutes les mises à jour classifiées comme importantes.<br />-   **Recommandées** : installe toutes les mises à jour classifiées comme importantes ou recommandées.|Oui|Non|
|**Contrôle de compte d'utilisateur**|Nécessite l'utilisation du contrôle de compte d’utilisateur (UAC) sur les appareils.|Oui|Non|
|**Autoriser la soumission des données de diagnostic**|Autoriser l’appareil à soumettre des informations de diagnostic à Microsoft.|Oui|Non|


## Paramètres du cloud - documents et données

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**URL des dossiers de travail**|Définit l'URL du dossier de travail pour autoriser la synchronisation des documents entre les appareils|Oui|Non|

## Paramètres de messagerie

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Rendre le compte Microsoft facultatif dans l'application Windows Mail**|Autorise l'accès à l'application Windows Mail sans compte Microsoft.|Oui|Non|

## Paramètres de l'application - navigateur

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Autoriser le remplissage automatique**|L'utilisateur peut modifier les paramètres de saisie semi-automatique dans le navigateur.|Oui|Non|
|**Autoriser le bloqueur de fenêtres publicitaires**|Active ou désactive le bloqueur de fenêtres publicitaires du navigateur.|Oui|Non|
|**Autoriser les plug-ins**|L'utilisateur peut ajouter des plug-ins à Internet Explorer.|Oui|Non|
|**Autoriser les scripts actifs**|Le navigateur peut exécuter des scripts, tels que les scripts ActiveX.|Oui|Non|
|**Autoriser l'avertissement de fraudes**|Activez ou désactivez les avertissements des sites Web frauduleux potentiels.|Oui|Non|
|**Autoriser les sites intranet avec entrée à mot unique**|Permet l'utilisation d'un mot unique pour diriger Internet Explorer vers un site web, tel que Bing.|Oui|Non|
|**Autoriser la détection automatique des réseaux intranet**|Facilite la configuration de la sécurité des sites intranet dans Internet Explorer.|Oui|Non|
|**Niveau de sécurité pour Internet**|Définir le niveau de sécurité d’Internet Explorer pour les sites Internet.|Oui|Non|
|**Niveau de sécurité pour intranet**|Définir le niveau de sécurité d’Internet Explorer pour les sites intranet.|Oui|Non|
|**Niveau de sécurité pour les sites de confiance**|Configurez le niveau de sécurité pour la zone Sites de confiance.|Oui|Non|
|**Niveau de sécurité pour les sites sensibles**|Configurez le niveau de sécurité pour la zone des sites sensibles.|Oui|Non|
|**Envoyer un en-tête Do Not Track**|Dans Internet Explorer, envoyer un en-tête Do Not Track aux sites visités.|Oui|Non|
|**Autoriser l'accès au menu Mode entreprise**|Permet aux utilisateurs d'accéder aux options du menu Mode entreprise à partir d'Internet Explorer.<br>Si cette option est sélectionnée, vous pouvez également spécifier un **emplacement du rapport de journalisation** qui contient une URL vers un rapport affichant les sites Web pour lesquels les utilisateurs ont activé l'accès en Mode entreprise.|Oui|Non|
|**Emplacement de la liste des sites en mode entreprise**|Spécifiez l'emplacement de la liste des sites web qui utilisent le Mode entreprise quand il est actif.|Oui|Non|

## Paramètres des fonctionnalités de l'appareil - cellulaire

|Nom du paramètre|Détails|Windows 8.1 et Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Autoriser l'itinérance des données**|Autoriser l’itinérance des données quand l’appareil se trouve sur un réseau cellulaire.|Oui|Non|



### Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jun16_HO1-->


