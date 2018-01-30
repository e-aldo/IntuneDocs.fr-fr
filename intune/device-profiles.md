---
title: "Que sont les profils d’appareil dans Microsoft Intune ?"
titlesuffix: Azure portal
description: "Découvrez plus d’informations sur les profils d’appareil Intune et comment ils peuvent vous aider à gérer et protéger les appareils de votre entreprise."
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0c745f9f745802e0de7a58e3dd7570c0e363ab5d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Que sont les profils d’appareil Microsoft Intune ?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Utilisez la charge de travail **Configuration de l’appareil** Microsoft Intune pour gérer les paramètres et fonctionnalités sur tous les appareils que vous gérez. Vous utilisez généralement cette charge de travail pour créer des profils d’appareil qui vous permettent de gérer et de contrôler tout un ensemble de fonctions et fonctionnalités différentes sur les appareils.

Quand vous ouvrez cette charge de travail, les options suivantes sont disponibles :

- **Vue d’ensemble** : cette page vous donne des informations d’état et des rapports qui vous aident à surveiller les configurations d’appareil que vous avez affectées aux utilisateurs et appareils.
- **Gérer les profils** : cette section vous permet de créer des profils de configuration d’appareil. Vous trouverez une liste de tous les types de profils que vous pouvez créer plus loin dans cette rubrique.
- **Configurer l’autorité de certification** : ce flux de travail présente les étapes nécessaires pour configurer des profils de certificats Intune.

## <a name="getting-started"></a>Prise en main

Le flux de travail pour la création de profils d’appareil est identique pour tous les profils. Pour plus d’informations, lisez le [Guide pratique pour créer des profils de configuration d’appareil Microsoft Intune](device-profile-create.md). Pour des informations spécifiques sur la création de paramètres pour chaque type de profil, lisez la suite.

Vous pouvez gérer les fonctionnalités suivantes sur vos appareils :

## <a name="device-features"></a>Fonctionnalités de l’appareil

Les fonctionnalités de l’appareil vous permettent de contrôler les fonctionnalités iOS et MacOS comme AirPrint, les notifications et les configurations d’appareils partagés.
Pour plus d’informations, consultez [Configuration des paramètres de fonctionnalité de l’appareil](device-features-configure.md) Prend en charge : iOS et MacOS.

## <a name="device-restrictions"></a>Restrictions d’appareil
Les restrictions d’appareil vous permettent de contrôler de nombreux paramètres sur les appareils que vous gérez, dans des catégories telles que la sécurité, le matériel et le partage de données. Par exemple, vous pouvez créer un profil de restriction de l’appareil qui empêche les utilisateurs d’appareils iOS d’accéder à l’appareil photo.
Pour plus d’informations, consultez le [Guide pratique pour configurer des paramètres de restriction d’appareil](device-restrictions-configure.md) Prend en charge : Android, iOS, Mac OS, Windows 10 et Windows 10 Collaboration.

## <a name="email"></a>E-mail
Les profils de messagerie vous permettent de créer, d’affecter et de surveiller les paramètres de messagerie Exchange ActiveSync sur les appareils que vous gérez. Les profils de messagerie aident à garantir la cohérence, réduisent les appels au support technique et permettent aux utilisateurs finaux d’accéder à la messagerie d’entreprise sur leurs appareils personnels sans aucune autre configuration de leur part.
Pour plus d’informations, consultez le [Guide pratique pour configurer des paramètres de messagerie](email-settings-configure.md) Prend en charge : Android, iOS, Windows Phone 8.1 et Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Utilisez les profils Wi-Fi pour affecter les paramètres de réseau sans fil aux utilisateurs et appareils de votre organisation. Quand vous affectez un profil Wi-Fi, vos utilisateurs ont accès à votre Wi-Fi d’entreprise sans avoir à le configurer eux-mêmes.
Pour plus d’informations, consultez le [Guide pratique pour configurer des paramètres Wi-Fi](wi-fi-settings-configure.md) Prend en charge : Android, iOS, Mac OS et Windows 8.1 (importation uniquement).

## <a name="vpn"></a>VPN
Les réseaux privés virtuels (ou VPN) donnent à vos utilisateurs un accès distant sécurisé à votre réseau d’entreprise. Les appareils utilisent un profil de connexion VPN pour établir une connexion avec le serveur VPN. Affectez des profils VPN aux utilisateurs et aux appareils de votre organisation pour qu’ils puissent se connecter au réseau facilement et en toute sécurité.
Pour plus d'informations, consultez [Guide pratique pour configurer des paramètres VPN](vpn-settings-configure.md).
Prend en charge : Android, iOS, Mac OS, Windows Phone 8.1, Windows 8.1 et Windows 10.

## <a name="education"></a>Éducation
Vous permet de configurer les options pour l’application Windows Take a Test. Lorsque vous configurez ces options, aucune autre application ne peut s’exécuter sur l’appareil tant que le test n’est pas terminé.
Pour en savoir plus, voir [Configuration des paramètres d’éducation](education-settings-configure.md)

## <a name="certificates"></a>Certificats
Ce type de profil permet de configurer des certificats de confiance, SCEP et PKCS qui peuvent être affectés aux appareils et utilisés pour authentifier le Wi-Fi, le VPN, et les profils de messagerie.
Pour plus d’informations, consultez le [Guide pratique pour configurer des certificats](certificates-configure.md) Prend en charge : Android, iOS et Windows Phone 8.1, Windows 8.1 et Windows 10.

## <a name="edition-upgrade"></a>Mise à niveau d’édition
Ce type de profil vous permet de mettre à niveau automatiquement les appareils qui exécutent des versions de Windows 10 vers une édition plus récente.
Pour plus d’informations, consultez le [Guide pratique de configuration des mises à niveau Windows 10](edition-upgrade-configure-windows-10.md) Prend en charge : Windows 10 uniquement.

## <a name="endpoint-protection"></a>Endpoint Protection
Ce type de profil vous permet de configurer les paramètres de BitLocker et de Windows Defender pour les appareils Windows 10.
Pour plus d’informations, consultez [Paramètres Endpoint Protection pour Windows 10](endpoint-protection-windows-10.md) Prend en charge : Windows 10 uniquement.

## <a name="windows-information-protection"></a>Protection des informations Windows
L’ensemble de fonctionnalités Protection des informations Windows vous permet de vous protéger contre toute fuite de données sans avoir à interférer avec l’expérience de l’employé. Il permet également de protéger les données et les applications d’entreprise contre des fuites accidentelles de données sur les appareils d’entreprise et les appareils personnels que les employés amènent sur leur lieu de travail, sans que cela entraîne nécessairement une modification de votre environnement ou d’autres applications.
Pour plus d’informations, consultez [Guide pratique pour configurer la Protection des informations Windows](windows-information-protection-configure.md) Prend en charge : Windows 10 uniquement.

## <a name="custom"></a>Personnalisé
Les paramètres personnalisés vous permettent d’affecter des paramètres d'appareil qui ne sont pas intégrés à Intune. Par exemple, sur les appareils Android, vous pouvez spécifier des valeurs d’OMA-URI qui configurent l’appareil. Pour les appareils iOS, vous pouvez importer un fichier de configuration que vous avez créé dans l’outil Apple Configurator.
Pour plus d’informations, consultez le [Guide pratique pour configurer des paramètres personnalisés](custom-settings-configure.md) Prend en charge : Android, iOS, Mac OS et Windows Phone 8.1.

## <a name="next-steps"></a>Étapes suivantes
Choisissez l’un des types de profils dans la liste pour commencer à configurer des appareils.
