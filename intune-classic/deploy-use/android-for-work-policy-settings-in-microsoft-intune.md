---
title: Paramètres de stratégie Android for Work
description: Créez des stratégies qui contrôlent les paramètres et fonctionnalités sur les appareils Android for Work que vous gérez avec Intune.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 02/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 89c0e09a34a734ccfe704b9a89971544e9a25e86
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Paramètres de stratégie Android for Work dans Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune fournit un certain nombre de paramètres généraux intégrés que vous pouvez configurer sur les [appareils Android for Work](android-for-work.md).

## <a name="general-configuration-policy"></a>Stratégie de configuration générale

Utilisez la **stratégie de configuration générale Android for Work** d’Intune pour configurer les paramètres de profil professionnel et de sécurité pour votre appareil Android for Work.

Si le paramètre que vous recherchez n’est pas mentionné dans cette rubrique, vous pourrez peut-être le créer à l’aide d’une stratégie personnalisée Android qui vous permet d’utiliser des paramètres OMA-URI pour contrôler l’appareil. Pour plus d’informations, accédez à la section [Paramètres de stratégie personnalisée](#custom-policy-settings) plus loin dans cette rubrique.

> [!TIP]
> Les appareils sont chiffrés automatiquement quand vous configurez un profil professionnel. Vous ne pouvez pas changer ce paramètre.

### <a name="password-settings"></a>Paramètres de mot de passe

|Nom du paramètre|Détails|
|----------------|-|
|**Exiger un mot de passe pour déverrouiller des appareils mobiles**|Spécifie si un mot de passe est requis sur les appareils gérés. Choisissez parmi :<br><br>- **Complexe** : exige au moins une lettre, un chiffre et un symbole<br>- **Alphanumérique** : exige au moins un chiffre et un caractère alphabétique<br>- **Alphabétique** : exige au moins des lettres ou des symboles<br>- **Au moins avec des chiffres complexes** : exige des caractères numériques qui ne sont pas consécutifs ou répétés<br>- **Numérique**<br><br>Si ce paramètre n’est pas activé, aucune exigence de complexité n’est appliquée.|
|**Longueur minimale du mot de passe**|Spécifie le nombre minimal de caractères ou chiffres figurant dans le mot de passe.|
|**Minutes d’inactivité avant verrouillage de l’appareil**|Spécifie le nombre de minutes sans activité utilisateur avant verrouillage automatique de l’appareil.|
|**Autoriser Smart Lock et d’autres agents de confiance**<br>(Android 6 et versions ultérieures)|Permet de contrôler la fonctionnalité Smart Lock sur les appareils Android compatibles. Cette fonctionnalité du téléphone, parfois appelée agent de confiance, vous permet de désactiver ou de contourner le mot de passe de l’écran de verrouillage de l’appareil si celui-ci se trouve dans un emplacement fiable (par exemple, quand il est connecté à un appareil Bluetooth spécifique ou qu’il se trouve à proximité d’une balise NFC). Vous pouvez utiliser ce paramètre pour empêcher les utilisateurs de configurer Smart Lock.|
|**Nombre d’échecs de connexion répétée avant suppression du profil professionnel**|Spécifie le nombre d’échecs de connexion autorisé avant suppression du profil professionnel sur l’appareil. Cette option n’effectue pas de réinitialisation complète de l’appareil.|
|**Mémoriser l’historique des mots de passe**|Empêche la réutilisation des mots de passe déjà utilisés.|
|**Mémoriser l'historique des mots de passe** - **Empêcher la réutilisation des mots de passe précédents**|Spécifie le nombre de mots de passe déjà utilisés à mémoriser.|
|**Expiration du mot de passe (jours)**|Spécifie le nombre de jours avant de devoir modifier le mot de passe de l’appareil.|
|**Autoriser le déverrouillage par empreinte digitale**<br>(Android 6 et versions ultérieures)|Vous permet d’utiliser une empreinte digitale pour déverrouiller les appareils dotés de cette fonctionnalité.|


### <a name="work-profile-settings"></a>Paramètres de profil professionnel

|Nom du paramètre|Détails|
|----------------|-|
|**Autoriser le partage de données entre profils professionnels et personnels**|Permet aux applications dans le profil professionnel de partager des données avec les applications dans le profil personnel des utilisateurs. Choisissez parmi :<br><br>- **Empêcher tout partage en dehors des limites**<br>- **Les applications du profil professionnel peuvent gérer une demande de partage venant d’un profil personnel**<br>- **Aucune restriction de partage**|
|**Masquer les notifications du profil professionnel quand l’appareil est verrouillé**<br>(Android 6 et versions ultérieures)|Contrôler s’il faut afficher des notifications du profil professionnel quand l’appareil est verrouillé.|
|**Définir une stratégie d’autorisation d’application par défaut**<br>(Android 6 et versions ultérieures)|Définit la stratégie d’autorisation par défaut pour toutes les applications dans le profil professionnel. À partir d’Android 6, certaines autorisations requises par les applications sont demandées à l’utilisateur final au moment de l’exécution.  Ce paramètre de stratégie permet au service informatique de décider comment ou si les utilisateurs sont invités à accorder des autorisations pour les applications dans le profil professionnel. <br/><br/>Par exemple, le service informatique peut transmettre au profil professionnel une application qui nécessite un accès à l’emplacement.  Habituellement, cette application affiche une boîte de dialogue demandant à l’utilisateur s’il souhaite autoriser l’application à accéder à l’emplacement. L’utilisateur peut alors approuver ou refuser cette autorisation.  Cette stratégie permet au service informatique de décider si toutes les autorisations doivent être accordées automatiquement sans invite, refusées automatiquement sans invite ou déterminées par l’utilisateur.|


## <a name="custom-policy-settings"></a>Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée Android for Work** de Microsoft Intune pour déployer les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android for Work. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre de déployer les paramètres Android qui ne sont pas configurables avec des stratégies Intune.
Intune prend en charge un nombre limité de stratégies personnalisées Android à l’heure actuelle. Consultez les exemples de cette rubrique pour savoir quelles stratégies vous pouvez configurer.

### <a name="general-settings"></a>Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom**|Entrez un nom unique pour la stratégie personnalisée Android pour pouvoir l’identifier dans la console Intune.|
    |**Description**|Fournissez une description générale de la stratégie personnalisée Android et d'autres informations pertinentes pour mieux la localiser.|

### <a name="oma-uri-settings"></a>Paramètres OMA-URI

   |Nom du paramètre|Détails|
    |--------|--------------------|
    |**Nom du paramètre**|Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.|
    |**Description du paramètre**|Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.|
    |**Type de données**|Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne, Chaîne (XML), Date et heure, Entier, Virgule flottante** ou **Booléen**.|
    |**OMA-URI (sensible à la casse)**|Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.|
    |**Valeur**|Spécifiez la valeur à associer à l’identificateur OMA-URI spécifié précédemment.|

### <a name="examples"></a>Exemples

- [Création d’un profil Wi-Fi avec une clé prépartagée](pre-shared-key-wi-fi-profile.md)
- [Utiliser une stratégie personnalisée pour créer un profil VPN par application pour les appareils Android](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>Voir aussi
[Gérer des paramètres et des fonctionnalités sur vos appareils avec des stratégies Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
