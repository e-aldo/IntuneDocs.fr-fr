---
title: "Paramètres de restriction d’appareil Intune pour Android for Work | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Version préliminaire d&quot;Intune Azure : découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 857522ef4931407accf98b2a2ad97334278c138f
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Android for Work dans Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

## <a name="work-profile-settings"></a>Paramètres de profil professionnel
-     **Partage des données entre les profils professionnels et personnels** : utilisez ce paramètre pour indiquer si les applications associées au profil professionnel peuvent ou non partager des données avec des applications du profil personnel. Choisissez parmi :
    - **Default sharing restrictions** (Restrictions de partage par défaut) : comportement de partage par défaut de l’appareil, qui varie selon la version d’Android en cours d’exécution. Par défaut, le partage du profil personnel vers le profil professionnel est autorisé. Le partage entre le profil professionnel et le profil personnel est aussi bloqué par défaut. Ce paramètre empêche les fuites de données du profil professionnel vers le profil personnel. Google ne fournit aucun moyen de bloquer les données qui transitent entre le profil personnel et le profil professionnel sur les appareils exécutant des versions antérieures à 6.0.  
    - **Les applications du profil professionnel peuvent gérer une demande de partage provenant d’un profil personnel** : utilisez cette option pour activer la fonctionnalité Android intégrée qui autorise le partage entre le profil personnel et le profil professionnel. Lorsque cette option est activée, une demande de partage initiée à partir d’une application du profil personnel permet d’activer le partage avec les applications associées au profil professionnel. Il s’agit du comportement par défaut pour les appareils Android exécutant des versions antérieures à 6.0.
    - **Apps in personal profile can handle sharing request from work profile** (Les applications du profil personnel peuvent gérer une demande de partage provenant d’un profil professionnel) : permet le partage dans les deux sens au-delà de la limite du profil professionnel. Lorsque vous sélectionnez ce paramètre, les applications du profil de travail peuvent partager des données avec des applications non gérées du profil personnel.  Utilisez ce paramètre avec précaution car il autorise le transfert des données gérées dans le profil professionnel vers le côté non géré de l’appareil.


-     **Notifications du profil professionnel quand l'appareil est verrouillé** : permet de déterminer si les applications du profil professionnel peuvent afficher des notifications à l’écran lorsque l’appareil est verrouillé.
-     **Autorisations des applications par défaut** : définit la stratégie d’autorisation par défaut pour toutes les applications du profil professionnel. À partir d’Android 6, certaines autorisations requises par les applications sont demandées à l’utilisateur final au moment de l’exécution. Ce paramètre de stratégie vous permet de décider comment ou si les utilisateurs sont invités à accorder des autorisations pour les applications du profil professionnel.
Par exemple, vous pouvez transmettre au profil professionnel une application qui nécessite un accès à l’emplacement. Habituellement, cette application affiche une boîte de dialogue demandant à l’utilisateur s’il souhaite autoriser l’application à accéder à l’emplacement. L’utilisateur peut alors approuver ou refuser cette autorisation. Cette stratégie vous permet de décider si toutes les autorisations doivent être accordées automatiquement sans invite, refusées automatiquement sans invite ou déterminées par l’utilisateur. Choisissez parmi :
    -     **Paramètre par défaut de l’appareil**
    -     **Demander**
    -     **Accorder automatiquement**
    -     **Refuser automatiquement**

## <a name="password"></a>Mot de passe

- **Longueur minimale du mot de passe** : entrez le nombre minimal de caractères devant figurer dans le mot de passe des utilisateurs (**4**-**14**)
- **Nombre maximal de minutes d’inactivité avant le verrouillage de l'appareil** : sélectionnez le délai de verrouillage automatique d’un appareil inactif.
- **Nombre d’échecs de connexion avant réinitialisation de l’appareil** : entrez le nombre de saisies possibles d’un mot de passe incorrect avant que toutes les données de l’appareil soient supprimées.
- **Expiration du mot de passe (jours)** : entrez le nombre de jours avant que l’utilisateur ne doive modifier le mot de passe de l’appareil (**1**-**255**).
- **Type de mot de passe requis** : sélectionnez le type de mot de passe qui doit être défini sur l’appareil. Choisissez parmi :
    - **Paramètre par défaut de l’appareil**
    - **Sécurité biométrique faible**
    - **Obligatoire**
    - **Au moins numérique**
    - **Chiffres complexes** (les chiffres répétés ou consécutifs tels que « 1111 » ou « 1234 » ne sont pas autorisés)
    - **Au moins alphabétique**
    - **Au moins alphanumérique**
    - **Au moins alphanumérique avec des symboles**
- **Empêcher la réutilisation des mots de passe précédents** : entrez le nombre de nouveaux mots de passe devant être utilisés avant de pouvoir réutiliser un ancien mot de passe (**1**-**24**).
- **Déverrouillage par empreinte digitale** : empêche les utilisateurs d’utiliser le lecteur d’empreintes digitales de l’appareil pour le déverrouiller.
- **Smart Lock et autres agents de confiance** : vous permet de contrôler la fonctionnalité Smart Lock sur les appareils compatibles. Cette fonctionnalité du téléphone, parfois appelée agent de confiance, vous permet de désactiver ou de contourner le mot de passe de l’écran de verrouillage de l’appareil si celui-ci se trouve dans un emplacement fiable (par exemple, quand il est connecté à un appareil Bluetooth spécifique ou qu’il se trouve à proximité d’une balise NFC). Vous pouvez utiliser ce paramètre pour empêcher les utilisateurs de configurer Smart Lock.

## <a name="custom-policy-settings"></a>Paramètres de la stratégie personnalisée
Utilisez la **stratégie de configuration personnalisée Android for Work** de Microsoft Intune pour affecter les paramètres OMA-URI qui peuvent être utilisés pour contrôler les fonctionnalités sur les appareils Android for Work. Il s'agit de paramètres standard qui sont utilisés par de nombreux fabricants d'appareils mobiles pour contrôler les fonctionnalités des appareils.

Cette fonctionnalité est conçue pour vous permettre d’affecter les paramètres Android qui ne sont pas configurables avec des stratégies Intune.
Intune prend en charge un nombre limité de stratégies personnalisées Android à l’heure actuelle. Consultez les exemples de cette rubrique pour savoir quelles stratégies vous pouvez configurer.

### <a name="general-settings"></a>Paramètres généraux :

|Nom du paramètre|Détails|
    |----------------|--------------------|
    |**Nom** |Entrez un nom unique pour la stratégie personnalisée Android pour pouvoir l’identifier dans la console Intune.|
    |**Description** |Fournissez une description générale de la stratégie personnalisée Android et d'autres informations pertinentes pour mieux la localiser.|

### <a name="oma-uri-settings"></a>Paramètres OMA-URI

  |Nom du paramètre|Détails|
  |--------|--------------------|
  |**Nom** |Affectez un nom unique au paramètre OMA-URI pour vous aider à l'identifier dans la liste des paramètres.|
  |**Description** |Entrez une description générale du paramètre et d'autres informations pertinentes pour faciliter sa localisation.|
    |**OMA-URI (sensible à la casse)** |Spécifiez l'identificateur OMA-URI pour lequel vous souhaitez fournir un paramètre.|
  |**Type de données** |Sélectionnez le type de données pour lequel vous allez spécifier ce paramètre OMA-URI. Choisissez **Chaîne, Chaîne (XML), Date et heure, Entier, Virgule flottante** ou **Booléen**.|
  |**Valeur** |Spécifiez la valeur à associer à l’identificateur OMA-URI spécifié précédemment.|

