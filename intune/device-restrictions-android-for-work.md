---
title: "Paramètres de restriction d’appareil Intune pour Android for Work"
titleSuffix: Intune on Azure
description: "Découvrez les paramètres Intune qui vous permettent de contrôler les paramètres et fonctionnalités des appareils Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 361777884187937632b2af02d7a7f15f0574193f
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/12/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Paramètres de restriction des appareils Android for Work dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Paramètres de profil professionnel
- **Partage des données entre les profils professionnels et personnels** : utilisez ce paramètre pour indiquer si les applications associées au profil professionnel peuvent ou non partager avec des applications du profil personnel. Ce paramètre contrôle les actions de partage dans les applications (par exemple, l’option **Patager...** dans l’application de navigateur Chrome) et ne s’applique pas au comportement copier/coller du Presse-papiers. Contrairement aux [paramètres de stratégie de protection des applications](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune), les paramètres de restriction d’appareil sont gérés à partir du portail Intune et utilisent le profil de travail Android for Work pour isoler les applications gérées. Choisissez parmi :
    - **Default sharing restrictions** (Restrictions de partage par défaut) : comportement de partage par défaut de l’appareil, qui varie selon la version d’Android en cours d’exécution. Par défaut, le partage du profil personnel vers le profil professionnel est autorisé. Le partage du le profil professionnel vers le profil personnel est aussi bloqué par défaut. Ce paramètre empêche les partages de données du profil professionnel vers le profil personnel. Google ne fournit aucun moyen de bloquer le partage du profil personnel vers le profil professionnel sur les appareils exécutant des versions antérieures à 6.0.   
    - **Les applications du profil professionnel peuvent gérer une demande de partage provenant d’un profil personnel** : utilisez cette option pour activer la fonctionnalité Android intégrée qui autorise le partage entre le profil personnel et le profil professionnel. Lorsque cette option est activée, une demande de partage à partir d’une application du profil personnel peut partager avec les applications associées au profil professionnel. Il s’agit du comportement par défaut pour les appareils Android exécutant des versions antérieures à 6.0.
    - **Autoriser le partage en dehors des limites** : permet le partage dans les deux sens au-delà de la limite du profil professionnel. Lorsque vous sélectionnez ce paramètre, les applications du profil de travail peuvent partager des données avec des applications sans badge du profil personnel. Utilisez ce paramètre avec précaution car il autorise le partage des applications gérées dans le profil professionnel vers des applications sur le côté non géré de l’appareil.

-   **Notifications du profil professionnel quand l'appareil est verrouillé** : permet de déterminer si les applications du profil professionnel peuvent afficher des données dans des notifications lorsque l’appareil est verrouillé.
-   **Autorisations des applications par défaut** : définit la stratégie d’autorisation par défaut pour toutes les applications du profil professionnel. À compter d’Android 6, l’utilisateur est invité à accorder certaines autorisations requises par les applications lorsque l’application est lancée. Ce paramètre de stratégie vous permet de décider si les utilisateurs sont invités à accorder des autorisations pour toutes les applications du profil professionnel. Par exemple, vous pouvez affecter au profil professionnel une application qui nécessite un accès à l’emplacement. Normalement, cette application invite l’utilisateur à approuver ou refuser l’accès à l’emplacement pour l’application. Cette stratégie vous permet de décider si toutes les autorisations doivent être accordées automatiquement sans invite, refusées automatiquement sans invite ou déterminées par l’utilisateur. Choisissez parmi :
    -   **Paramètre par défaut de l’appareil**
    -   **Demander**
    -   **Accorder automatiquement**
    -   **Refuser automatiquement**

    L’état de l’octroi des autorisations peut être défini plus précisément pour des applications spécifiques en définissant une stratégie de configuration d’application pour une application individuelle (sous **Applications mobiles** > **Stratégies de configuration des applications**).

### <a name="work-profile-password"></a>Mot de passe de profil professionnel
- **Exiger le mot de passe du profil de travail** - (Android 7.0 et versions ultérieures avec le profil de travail activé) Définissez une stratégie de mot de passe qui s’applique uniquement aux applications dans le profil de travail. Par défaut, l’utilisateur final peut utiliser les deux codes PIN définis séparément, ou il peut choisir de combiner les deux codes PIN définis dans le plus sécurisé des deux.
- **Longueur minimale du mot de passe** : entrez le nombre minimal de caractères devant figurer dans le mot de passe des utilisateurs (**4**-**16**)
- **Nombre maximal de minutes d’inactivité avant le verrouillage de l’appareil** : sélectionnez le délai de verrouillage du profil professionnel. L’utilisateur doit ensuite entrer ses informations d’identification pour rétablir l’accès.
- **Nombre d’échecs de connexion avant réinitialisation de l’appareil** : entrez le nombre de saisies possibles d’un mot de passe incorrect avant que le profil de travail soit supprimé.
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
- **Smart Lock et autres agents de confiance** : vous permet de contrôler la fonctionnalité Smart Lock sur les appareils compatibles. Cette fonctionnalité du téléphone, parfois appelée agent de confiance, vous permet de désactiver ou de contourner le mot de passe du profil de travail si celui-ci se trouve dans un emplacement fiable (par exemple, quand il est connecté à un appareil Bluetooth spécifique ou qu’il se trouve à proximité d’une balise NFC). Vous pouvez utiliser ce paramètre pour empêcher les utilisateurs de configurer Smart Lock.

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

## <a name="next-steps"></a>Étapes suivantes

Aidez-vous des informations contenues dans la rubrique [Guide pratique pour configurer des paramètres de restriction d’appareils](device-restrictions-configure.md) pour enregistrer et affecter le profil à des utilisateurs et appareils.
