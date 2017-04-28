---
title: Inscrire des appareils | Microsoft Docs
description: "La gestion des appareils mobiles utilise l’inscription pour gérer les appareils et leur autoriser l’accès aux ressources."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 2a35387cdc2ebeb3c83fa043a8b2c6583fccdbc9
ms.lasthandoff: 04/24/2017


---

# <a name="enroll-devices-for-management-in-intune"></a>Inscrire des appareils pour la gestion dans Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous pouvez inscrire des appareils, y compris des PC Windows, pour utiliser la gestion des appareils mobiles avec Microsoft Intune. Cette rubrique décrit différentes façons d’inscrire des appareils mobiles dans la gestion Intune. La façon dont vous inscrivez vos appareils dépend du type d’appareil, de son propriétaire et du niveau de gestion souhaité. L’inscription BYOD (« Bring your own device ») permet aux utilisateurs d’inscrire leurs téléphones, tablettes ou PC personnels. Vous pouvez gérer l’inscription des appareils d’entreprise (COD) de plusieurs façons : inscription automatique, appareils partagés ou inscription pré-autorisée.

Si vous utilisez [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) (soit localement, soit hébergé dans le cloud), vous pouvez choisir la gestion Intune simple sans inscription. Vous pouvez également gérer des PC Windows à l’aide du [logiciel client Intune](#manage-windows-pcs-with-intune).

Par défaut, les appareils de toutes les plateformes peuvent être inscrits dans Intune. Pour bloquer l’inscription des appareils, connectez-vous au [portail d’administration Microsoft Intune](https://manage.microsoft.com) avec vos informations d’identification d’administrateur. Choisissez **Admin** > **Gestion des appareils mobiles** > **Règles d’inscription**, puis décochez les cases appropriées pour les plateformes que vous souhaitez bloquer.

## <a name="overview-of-device-enrollment-methods"></a>Présentation des méthodes d’inscription des appareils

Le tableau suivant présente les méthodes d’inscription Intune, ainsi que les fonctionnalités prises en charge et les exigences de chaque méthode. Les fonctionnalités et les exigences sont décrites ci-dessous.

- **Réinitialisation** : indique si l’appareil doit être réinitialisé pour que les utilisateurs puissent inscrire l’appareil. Le terme « réinitialiser » implique une réinitialisation des paramètres d’usine de l’appareil, laquelle supprime toutes les données. Pour plus d’informations, consultez [Retirer des appareils](retire-devices-from-microsoft-intune-management.md).
- **Affinité** : associe les appareils à des utilisateurs. Fonctionnalité nécessaire pour la gestion des applications mobiles (GAM) et l’accès conditionnel aux données d’entreprise. Pour plus d’informations, consultez [Affinité utilisateur](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices).
- **Verrou** : indique si les utilisateurs ne sont pas autorisés à désinscrire leurs appareils à l’aide des menus du système d’exploitation natif. Les utilisateurs peuvent désinscrire leurs appareils sur toutes les plateformes à l’aide de l’application Portail d’entreprise.

**Méthodes d’inscription iOS**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | [Plus d’informations](prerequisites-for-enrollment.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    | [Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|    Oui |    Facultatif |    Facultatif|[Plus d’informations](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**|    Oui |    Facultatif |    Non| [Plus d’informations](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**|    Non |    Non    | Non|[Plus d’informations](ios-direct-enrollment-in-microsoft-intune.md)|

**Méthodes d’inscription de Windows**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | [Plus d’informations](prerequisites-for-enrollment.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    |[Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Méthodes d’inscription d’Android**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | [Plus d’informations](prerequisites-for-enrollment.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    |[Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Méthodes d’inscription Android for Work**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | [Plus d’informations](prerequisites-for-enrollment.md)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    |[Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Méthodes d’inscription macOS**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | [Plus d’informations](prerequisites-for-enrollment.md)|


Pour répondre à une série de questions qui vous aideront à déterminer la méthode appropriée, consultez [Choisir comment inscrire des appareils](/intune/get-started/choose-how-to-enroll-devices1).

## <a name="byod"></a>BYOD
Les utilisateurs d’appareils personnels installent l’application Portail d’entreprise et inscrivent leurs propres appareils. Ils peuvent ensuite se connecter au réseau d’entreprise et rejoindre le domaine ou Azure Active Directory. Pour la plupart des plateformes, vous devez activer l’inscription BYOD pour de nombreux scénarios d’appareil d’entreprise. Pour plus d’informations, voir [Conditions préalables à la gestion d’appareils mobiles dans Intune](prerequisites-for-enrollment.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Appareils d’entreprise
Vous pouvez gérer les appareils d’entreprise (COD, Corporate-Owned Devices) à l’aide de la console Intune. Vous pouvez inscrire les appareils iOS directement par le biais des outils fournis par Apple. Tous les types d’appareils peuvent être inscrits par un administrateur ou un gestionnaire à l’aide du Gestionnaire d’inscription d’appareil. Les appareils dotés d’un numéro IMEI peuvent également être identifiés et référencés comme appartenant à l’entreprise pour activer des scénarios COD.

Pour plus d’informations, consultez [Inscrire les appareils d’entreprise](manage-corporate-owned-devices.md).

### <a name="dem"></a>Gestionnaire d’inscription d’appareil
Le gestionnaire d’inscription d’appareil est un compte Intune spécial permettant d’inscrire et de gérer plusieurs appareils d’entreprise. Les responsables peuvent installer le Portail d’entreprise et inscrire de nombreux appareils sans utilisateur. En savoir plus sur le [gestionnaire d’inscription d’appareil](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Le programme d’inscription d’appareils Apple (ou DEP) vous permet de créer et déployer une stratégie « à distance » sur des appareils iOS achetés et gérés avec DEP. L’appareil est inscrit quand l’utilisateur le démarre pour la première fois et exécute l’Assistant d’installation iOS. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  -    Inscription verrouillée
  -    Mode plein écran et autres configurations et restrictions avancées

En savoir plus sur le programme [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
Les administrateurs utilisent Apple Configurator, via un port USB, pour préparer manuellement chaque appareil d’entreprise à l’inscription à l’aide de l’Assistant Configuration. Ils créent un profil d’inscription et l’exportent vers Apple Configurator. Lorsque les utilisateurs reçoivent leurs appareils, ils sont invités à exécuter l’Assistant Configuration pour inscrire leurs appareils. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  -    Inscription verrouillée
  -    Mode plein écran et autres configurations et restrictions avancées

En savoir plus sur l’[inscription de l’Assistant Configuration avec Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
Pour les inscriptions directes, l’administrateur doit inscrire manuellement chaque appareil en créant une stratégie d’inscription et en l’exportant vers Apple Configurator. Les appareils d’entreprise connectés par USB sont inscrits directement et aucune réinitialisation aux paramètres d’usine n’est nécessaire. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ou la gestion des applications mobiles.  En savoir plus sur l’[inscription directe avec Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud. Pour plus d’informations, consultez [Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Gestion des PC Windows avec Intune  
Vous pouvez également utiliser Microsoft Intune pour gérer des PC Windows avec le logiciel client Intune. Les PC gérés avec le client Intune peuvent :

 - Fournir un inventaire logiciel et matériel
 - Installer des applications de bureau (par exemple des fichiers .exe et .msi)
 - Gérer les paramètres de pare-feu

Les PC gérés avec le logiciel client Intune ne peuvent pas être entièrement réinitialisés, bien que la réinitialisation sélective soit disponible. Les PC gérés avec le logiciel client Intune ne peuvent pas utiliser de nombreuses fonctionnalités de gestion Intune telles que l’accès conditionnel, les paramètres VPN et Wi-Fi, ou le déploiement de certificats et de configurations de messagerie. Pour plus d’informations, consultez [Gestion des ordinateurs Windows avec Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Plateformes d’appareil prises en charge

Intune peut gérer les plateformes d’appareils suivantes :

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Étapes suivantes
- [Prérequis pour l’inscription d’appareils](prerequisites-for-enrollment.md)
- [Gérer les appareils d’entreprise](manage-corporate-owned-devices.md)
- [Ordinateurs et appareils mobiles pris en charge](../get-started/supported-mobile-devices-and-computers.md)

