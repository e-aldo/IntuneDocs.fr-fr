---
title: Inscrire des appareils | Microsoft Intune
description: "La gestion des appareils mobiles utilise l’inscription pour gérer les appareils et leur autoriser l’accès aux ressources."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f28cce75626df1115283dc98547adcb97ee1cb4
ms.openlocfilehash: d880123a9b4d4afd74e9941ce0590f5dae554667


---

# <a name="enroll-devices-for-management-in-intune"></a>Inscrire des appareils pour la gestion dans Intune
Vous pouvez inscrire des appareils, y compris des PC Windows, pour utiliser la gestion des appareils mobiles avec Microsoft Intune. Cette rubrique décrit différentes façons d’inscrire des appareils mobiles dans la gestion Intune. La façon dont vous inscrivez vos appareils dépend du type d’appareil, de son propriétaire et du niveau de gestion souhaité. L’inscription BYOD (« Bring your own device ») permet aux utilisateurs d’inscrire leurs téléphones, tablettes ou PC personnels. L’inscription COD (« Corporate-owned device ») permet de gérer des appareils d’entreprise en utilisant des fonctionnalités telles que la réinitialisation à distance, le partage d’appareils ou l’affinité utilisateur.

Si vous utilisez [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) (soit localement, soit hébergé dans le cloud), vous pouvez choisir la gestion Intune simple sans inscription. Vous pouvez également gérer des PC Windows à l’aide du [logiciel client Intune](#manage-windows-pcs-with-intune).

## <a name="overview-of-device-enrollment-methods"></a>Présentation des méthodes d’inscription des appareils

Le tableau suivant présente les méthodes d’inscription Intune, ainsi que les fonctionnalités prises en charge et les exigences de chaque méthode. Les fonctionnalités et les exigences sont décrites ci-dessous.

- **Réinitialisation** : indique si l’appareil doit être réinitialisé pour que les utilisateurs puissent inscrire l’appareil. Le terme « réinitialiser » implique une réinitialisation des paramètres d’usine de l’appareil, laquelle supprime toutes les données. Pour plus d’informations, consultez [Retirer des appareils](retire-devices-from-microsoft-intune-management.md).
- **Affinité** : associe les appareils à des utilisateurs. Fonctionnalité nécessaire pour la gestion des applications mobiles (GAM) et l’accès conditionnel aux données d’entreprise. Pour plus d’informations, consultez [Affinité utilisateur](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices).
- **Verrouillage** : empêche les utilisateurs de retirer leur appareil de la gestion. Les appareils iOS nécessitent le mode de verrouillage Supervisé. Pour plus d’informations, consultez [Verrouillage à distance](retire-devices-from-microsoft-intune-management.md#block-access-a-device).

**Méthodes d’inscription iOS**

| **Méthode** |  **Réinitialisation nécessaire ?** |    **Affinité**    |   **Verrouiller** | **Détails** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |   Non | [Plus d’informations](prerequisites-for-enrollment.md#set-up-device-management)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|   Non |Non |Non  | [Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Oui |   Facultatif |  Facultatif|[Plus d’informations](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Oui |   Facultatif |  Non| [Plus d’informations](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Non |    Non  | Non|[Plus d’informations](ios-direct-enrollment-in-microsoft-intune.md)|

**Méthodes d’inscription de Windows**

| **Méthode** |  **Réinitialisation nécessaire ?** |    **Affinité**    |   **Verrouiller** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Oui|   Oui |   Non | [Plus d’informations](prerequisites-for-enrollment.md#set-up-device-management)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|   Non |Non |Non  |[Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Méthodes d’inscription d’Android**

| **Méthode** |  **Réinitialisation nécessaire ?** |    **Affinité**    |   **Verrouiller** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |   Non | [Plus d’informations](prerequisites-for-enrollment.md#set-up-device-management)|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|   Non |Non |Non  |[Plus d’informations](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

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
  - Inscription verrouillée
  - Accès conditionnel
  - Détection de jailbreak
  - Gestion des applications mobiles

En savoir plus sur le programme [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
Les appareils d’entreprise connectés par USB sont préparés à l’aide d’une stratégie Intune. Pour l’inscription de l’Assistant Configuration, l’administrateur crée cette stratégie Intune et l’exporte vers Apple Configurator. L’administrateur doit inscrire manuellement chaque appareil. Les utilisateurs reçoivent leur appareil et exécutent l’Assistant Configuration pour inscrire leur appareil. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  - Accès conditionnel
  - Détection de jailbreak
  - Gestion des applications mobiles

En savoir plus sur l’[inscription de l’Assistant Configuration avec Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
Pour l’inscription directe, l’administrateur crée une stratégie Intune et l’exporte vers Apple Configurator. Les appareils d’entreprise connectés par USB sont inscrits directement et aucune réinitialisation aux paramètres d’usine n’est nécessaire. L’administrateur doit inscrire manuellement chaque appareil. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ou la gestion des applications mobiles. En savoir plus sur l’[inscription directe avec Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud.

Pour plus d’informations, consultez [Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Gestion des PC Windows avec Intune  
Vous pouvez également utiliser Microsoft Intune pour gérer des PC Windows avec le logiciel client Intune. Les PC gérés avec le client Intune peuvent :

 - Fournir un inventaire logiciel et matériel
 - Installer des applications de bureau (par exemple des fichiers .exe et .msi)
 - Gérer les paramètres de pare-feu

Les PC gérés avec le logiciel client Intune ne peuvent pas être entièrement réinitialisés, bien que la réinitialisation sélective soit disponible. Les PC gérés avec le logiciel client Intune ne peuvent pas utiliser de nombreuses fonctionnalités de gestion Intune telles que l’accès conditionnel, les paramètres VPN et Wi-Fi, ou le déploiement de certificats et de configurations de messagerie.

Pour plus d’informations, consultez [Gestion des ordinateurs Windows avec Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Plateformes d’appareil prises en charge

Intune peut gérer les plateformes d’appareils suivantes :

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Étapes suivantes
- [Prérequis pour l’inscription d’appareils](prerequisites-for-enrollment.md)
- [Gérer les appareils d’entreprise](manage-corporate-owned-devices.md)
- [Ordinateurs et appareils mobiles pris en charge](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Nov16_HO3-->


