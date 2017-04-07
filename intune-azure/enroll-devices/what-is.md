---
title: "Qu’est-ce que l’inscription des appareils Microsoft Intune ?"
titleSuffix: Intune Azure preview
description: "Version préliminaire d&quot;Intune Azure : en savoir plus sur l’inscription pour les appareils iOS, Android et Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 671d862c8d9a98e02f33d96cf6ceba712e740dec
ms.openlocfilehash: 6127604afb01a9482eadc3d03b566304e2acdd21
ms.lasthandoff: 03/17/2017


---

# <a name="what-is-device-enrollment"></a>Qu’est-ce que l’inscription d’appareils ?
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Cette rubrique décrit l’inscription et répertorie différentes façons d’inscrire des appareils mobiles dans la gestion Intune.

Vous inscrivez des appareils, notamment des PC Windows, dans Intune afin de pouvoir gérer ces appareils. Nous appelons cette fonctionnalité « gestion des appareils mobiles (MDM) » dans la documentation Intune . Lorsque les appareils sont inscrits en tant qu’appareils mobiles (et non comme PC), ils se voient remettre un certificat MDM, que les appareils utilisent ensuite pour communiquer avec le service Intune.

La façon dont vous inscrivez vos appareils dépend du type d’appareil, de son propriétaire et du niveau de gestion souhaité. L’inscription BYOD (« Bring your own device ») permet aux utilisateurs d’inscrire leurs téléphones, tablettes ou PC personnels. Vous pouvez gérer l’inscription des appareils d’entreprise (COD) de plusieurs façons : inscription automatique, appareils partagés ou inscription pré-autorisée.

Si vous utilisez Exchange ActiveSync (soit localement, soit hébergé dans le cloud), vous pouvez choisir la gestion Intune simple sans inscription (plus d’informations prochainement). Vous pouvez gérer les PC Windows en tant qu’appareils mobiles, ce qui est la méthode recommandée décrite ci-après. Vous pouvez également gérer les PC à l’aide du [logiciel client Intune](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune).


## <a name="overview-of-device-enrollment-methods"></a>Présentation des méthodes d’inscription des appareils

Le tableau suivant présente les méthodes d’inscription Intune, ainsi que les fonctionnalités prises en charge et les exigences de chaque méthode. Les fonctionnalités et les exigences sont décrites ci-dessous. Les termes suivants sont utilisés dans le tableau :

- **Réinitialisation** : indique si l’appareil doit être réinitialisé pour que les utilisateurs puissent inscrire l’appareil. Le terme « réinitialiser » implique une réinitialisation des paramètres d’usine de l’appareil, laquelle supprime toutes les données. Pour plus d’informations, consultez [Utilisation de la réinitialisation complète ou sélective sur les appareils](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Affinité** : associe les appareils à des utilisateurs. Fonctionnalité nécessaire pour la gestion des applications mobiles (GAM) et l’accès conditionnel aux données d’entreprise. Pour plus d’informations, consultez [Affinité utilisateur](enroll-ios-devices-using-device-enrollment-program.md).
- **Verrou**: indique que les utilisateurs ne peuvent pas désinscrire leurs appareils de la gestion. Les utilisateurs peuvent désinscrire leurs appareils sur toutes les plateformes à l’aide de l’application Portail d’entreprise. Ils ne peuvent pas utiliser les menus du système d’exploitation natif pour les désinscrire.


**Méthodes d’inscription iOS**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | Plus d’informations seront bientôt disponibles|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    | [Plus d’informations](enroll-ios-devices-using-device-enrollment-program.md)|
|**[DEP](#dep)**|    Oui |    Facultatif |    Facultatif|[Plus d’informations](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**|    Oui |    Facultatif |    Non| [Plus d’informations](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**|    Non |    Non    | Non|[Plus d’informations](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|



**Méthodes d’inscription de Windows**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non |    Oui |    Non | Plus d’informations seront bientôt disponibles|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    |[Plus d’informations](enroll-devices-using-device-enrollment-manager.md)|

**Méthodes d’inscription d’Android**

| **Méthode** |    **Réinitialisation nécessaire ?** |    **Affinité**    |    **Verrouillage** | **Détails**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Non|    Oui |    Non | Plus d’informations seront bientôt disponibles|
|**[GESTIONNAIRE D’INSCRIPTION D’APPAREIL](#dem)**|    Non |Non |Non    |[Plus d’informations](enroll-ios-devices-using-device-enrollment-program.md)|


## <a name="byod"></a>BYOD
Les utilisateurs d’appareils personnels installent l’application Portail d’entreprise et inscrivent leurs propres appareils. Ils peuvent ensuite se connecter au réseau d’entreprise et rejoindre le domaine ou Azure Active Directory. Pour la plupart des plateformes, vous devez activer l’inscription BYOD pour de nombreux scénarios d’appareil d’entreprise. Vous pouvez bloquer l’inscription d’appareils personnels iOS et Android. Consultez la page [Définir des restrictions de type d’appareil](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions) pour obtenir des instructions.

## <a name="corporate-owned-devices"></a>Appareils d’entreprise
Vous pouvez gérer les appareils d’entreprise (COD, Corporate-Owned Devices) à l’aide du portail Azure. Vous pouvez inscrire les appareils iOS directement par le biais des outils fournis par Apple. Tous les types d’appareils peuvent être inscrits par un administrateur ou un gestionnaire à l’aide du Gestionnaire d’inscription d’appareil. Les appareils dotés d’un numéro IMEI peuvent également être identifiés et référencés comme appartenant à l’entreprise pour activer des scénarios COD.

### <a name="dem"></a>Gestionnaire d’inscription d’appareil
Le gestionnaire d’inscription d’appareil est un compte d’utilisateur spécial permettant d’inscrire et de gérer plusieurs appareils d’entreprise. Les responsables peuvent installer le Portail d’entreprise et inscrire de nombreux appareils sans utilisateur. En savoir plus sur le [gestionnaire d’inscription d’appareil](enroll-devices-using-device-enrollment-manager.md). ([Retour au tableau](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Le programme d’inscription d’appareils Apple (ou DEP) vous permet de créer et déployer une stratégie « à distance » sur des appareils iOS achetés et gérés avec DEP. L’appareil est inscrit quand l’utilisateur le démarre pour la première fois et exécute l’Assistant d’installation iOS. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :

  -    Inscription verrouillée
  -    Mode plein écran et autres configurations et restrictions avancées

Pour en savoir plus sur l’inscription d’appareils iOS, consultez :

- [Choisir comment inscrire des appareils iOS](choose-ios-enrollment-method.md)
- [Inscrire des appareils iOS à l’aide du programme d’inscription d’appareils](enroll-ios-devices-using-device-enrollment-program.md)
- [Retour au tableau ci-dessus](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
Les administrateurs utilisent Apple Configurator, via un port USB, pour préparer manuellement chaque appareil d’entreprise à l’inscription à l’aide de l’Assistant Configuration. Ils créent un profil d’inscription et l’exportent vers Apple Configurator. Lorsque les utilisateurs reçoivent leurs appareils, ils sont invités à exécuter l’Assistant Configuration pour inscrire leurs appareils. Cette méthode prend en charge le mode **iOS supervisé** qui permet à son tour ce qui suit :
  -    Inscription verrouillée
  -    Mode plein écran et autres configurations et restrictions avancées

Pour en savoir plus sur l’inscription d’appareils iOS, consultez :

- [Choisir la méthode d’inscription des appareils iOS](choose-ios-enrollment-method.md)
- [Inscrire des appareils iOS avec Configurator et l’Assistant Configuration](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)

### <a name="usb-direct"></a>USB-Direct
Pour les inscriptions directes, l’administrateur doit inscrire manuellement chaque appareil en créant une stratégie d’inscription et en l’exportant vers Apple Configurator. Les appareils d’entreprise connectés par USB sont inscrits directement et aucune réinitialisation aux paramètres d’usine n’est nécessaire. Les appareils sont gérés comme des appareils sans utilisateur. Ils ne sont pas verrouillés ni supervisés et ne peuvent pas prendre en charge l’accès conditionnel, la détection de jailbreak ou la gestion des applications mobiles.

Pour en savoir plus sur l’inscription d’appareils iOS, consultez :

- [Choisir la méthode d’inscription des appareils iOS](choose-ios-enrollment-method.md)
- [Inscrire des appareils iOS avec Apple Configurator et l’inscription directe](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Gestion des appareils mobiles à l’aide d’Exchange ActiveSync et d’Intune
Les appareils mobiles qui ne sont pas inscrits mais qui se connectent à Exchange ActiveSync (EAS) peuvent être gérés par Intune à l’aide de la stratégie de gestion des appareils mobiles EAS. Intune utilise un connecteur Exchange pour communiquer avec EAS, localement ou hébergé dans le cloud. Plus d’informations seront bientôt disponibles.


## <a name="windows-pc-management-with-intune"></a>Gestion des PC Windows avec Intune  
Vous pouvez également utiliser Microsoft Intune pour gérer des PC Windows avec le logiciel client Intune. Les PC gérés avec le client Intune peuvent :

 - Fournir un inventaire logiciel et matériel
 - Installer des applications de bureau (par exemple des fichiers .exe et .msi)
 - Gérer les paramètres de pare-feu

Les PC gérés avec le logiciel client Intune ne peuvent pas être entièrement réinitialisés, bien que la réinitialisation sélective soit disponible. Les PC gérés avec le logiciel client Intune ne peuvent pas utiliser de nombreuses fonctionnalités de gestion Intune telles que l’accès conditionnel, les paramètres VPN et Wi-Fi, ou le déploiement de certificats et de configurations de messagerie. Plus d’informations seront bientôt disponibles.

## <a name="supported-device-platforms-and-browsers"></a>Plateformes et navigateurs d’appareil pris en charge

Consultez [Appareils et navigateurs pris en charge pour Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Nettoyage de l’appareil mobile après expiration du certificat MDM

Le certificat MDM est renouvelé automatiquement lorsque les appareils mobiles communiquent avec le service Intune. Si des appareils mobiles (non PC) sont réinitialisés ou ne parviennent pas à communiquer avec le service Intune pendant un certain temps, le certificat MDM n’est pas renouvelé. L’appareil est supprimé du portail Azure 180 jours après l’expiration du certificat MDM.

