---
title: "Que sont les profils d’appareil dans Microsoft Intune ? | Préversion Intune Azure | Microsoft Docs"
description: "Préversion Intune Azure : Découvrez plus d’informations sur les profils d’appareil Intune et comment ils peuvent vous aider à gérer et protéger les appareils de votre entreprise."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: a5f6ad4dd5339b31a6a1fd549a3b29b0ff258a5b
ms.lasthandoff: 02/16/2017


---

# <a name="what-are-microsoft-intune-device-profiles"></a>Que sont les profils d’appareil Microsoft Intune ?

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Utilisez la charge de travail **Configurer des appareils** de Microsoft Intune pour gérer les paramètres et fonctionnalités sur tous les appareils que vous gérez. Vous utiliserez généralement cette charge de travail pour créer des profils d’appareil qui vous permettent de gérer et contrôler tout un ensemble de fonctions et fonctionnalités différentes sur les appareils que vous gérez.

Lorsque vous ouvrez cette charge de travail, vous verrez les options suivantes :

- **Vue d’ensemble** : cette page vous donne des informations d’état et des rapports qui vous aident à surveiller les configurations d’appareil que vous avez affectées aux utilisateurs et appareils.
- **Gérer les profils** : cette section vous permet d’accéder à la création de profils de configuration d’appareil. Vous trouverez ci-dessous une liste de tous les types de profils que vous pouvez créer.
- **Configurer l’autorité de certification** : ce flux de travail présente les étapes requises pour configurer des certificats. Vous devez effectuer cette opération si vous souhaitez utiliser des profils de certificat Intune.

## <a name="getting-started"></a>Mise en route

Le flux de travail pour la création de profils d’appareil est identique pour tous les profils. Lisez [Guide pratique pour créer des profils de configuration d’appareil Microsoft Intune](/intune-azure/configure-devices/how-to-create-device-profiles) pour plus d’informations sur la création de profils. Pour des informations spécifiques sur la création de paramètres pour chaque type de profil, lisez la suite.

Vous pouvez gérer les fonctionnalités suivantes sur vos appareils :

## <a name="device-restrictions"></a>Limites des appareils
Les restrictions d’appareil vous permettent de contrôler un large éventail de paramètres et fonctionnalités que vous gérez sur diverses catégories, dont la sécurité, le navigateur, le matériel et les paramètres de partage de données. Par exemple, vous pouvez créer un profil de restriction d’appareil qui empêche les utilisateurs d’appareils iOS d’accéder à l’appareil photo.
Pour plus d’informations, consultez [Guide pratique pour configurer des paramètres de restriction d’appareil](how-to-configure-device-restrictions.md) Prend en charge : Android, iOS, Mac OS, Windows 10 et Windows 10 Collaboration.

## <a name="email"></a>Courrier électronique
Les profils de messagerie vous permettent de créer, déployer et contrôler les paramètres de messagerie Exchange ActiveSync sur les appareils que vous gérez. En déployant ces paramètres, vous assurez la cohérence, réduisez les appels au support technique et permettez aux utilisateurs finaux d’accéder à la messagerie d’entreprise sur leurs appareils personnels sans aucune autre configuration de leur part.
Pour plus d’informations, consultez [Guide pratique pour configurer des paramètres de messagerie](how-to-configure-email-settings.md) Prend en charge : Android, iOS et Windows Phone 8.1 et Windows 10.

## <a name="wi-fi"></a>Wi-Fi
Utilisez les profils Wi-Fi pour déployer les paramètres de réseau sans fil des utilisateurs et des appareils de votre organisation. Quand vous déployez un profil Wi-Fi, vos utilisateurs ont accès à votre Wi-Fi d’entreprise sans avoir à le configurer eux-mêmes.
Pour plus d’informations, consultez [Guide pratique pour configurer des paramètres Wi-Fi](how-to-configure-wi-fi-settings.md) Prend en charge : Android, iOS, Mac OS et Windows 8.1 (importation uniquement).

## <a name="vpn"></a>VPN
Les réseaux privés virtuels (ou VPN) donnent à vos utilisateurs un accès distant sécurisé à votre réseau d’entreprise. Les appareils utilisent un profil de connexion VPN pour établir une connexion avec le serveur VPN. Utilisez les profils VPN pour déployer des paramètres VPN sur les utilisateurs et appareils de votre organisation, afin qu’ils puissent se connecter au réseau facilement et en toute sécurité.
Pour plus d'informations, consultez [Guide pratique pour configurer des paramètres VPN](how-to-configure-vpn-settings.md).
Prend en charge : Android, iOS, Mac OS, Windows Phone 8.1, Windows 8.1 et Windows 10.

## <a name="certificates"></a>Certificats
Ce type de profil permet de configurer des certificats de confiance, SCEP et PKCS qui peuvent être affectés aux appareils et utilisés pour authentifier le Wi-Fi, le VPN, et les profils de messagerie.
Pour plus d’informations, consultez [Guide pratique pour configurer des certificats](how-to-configure-certificates.md) Prend en charge : Android, iOS et Windows Phone 8.1, Windows 8.1 et Windows 10.

## <a name="edition-upgrade"></a>Mise à niveau d’édition
Ce type de profil vous permet de mettre automatiquement à jour les appareils qui exécutent certaines versions de Windows 10 vers une version plus récente. Pour plus d’informations, consultez [Guide pratique pour configurer des mises à niveau Windows 10](how-to-configure-windows-10-edition-upgrade.md) Prend en charge : Windows 10 uniquement.

## <a name="windows-information-protection"></a>Protection des informations Windows
L’ensemble de fonctionnalités Protection des informations Windows vous permet de vous protéger contre toute fuite de données sans avoir à interférer avec l’expérience de l’employé. Il permet également de protéger les données et les applications d’entreprise contre des fuites accidentelles de données sur les appareils d’entreprise et les appareils personnels que les employés amènent sur leur lieu de travail, sans que cela entraîne nécessairement une modification de votre environnement ou d’autres applications.
Pour plus d’informations, consultez [Guide pratique pour configurer la Protection des informations Windows](how-to-configure-windows-information-protection.md) Prend en charge : Windows 10 uniquement.

## <a name="custom"></a>Personnalisé
Les paramètres personnalisés vous permettent d’affecter des paramètres d'appareil qui ne sont pas intégrés à Intune. Par exemple, sur les appareils Android, vous pouvez spécifier des valeurs d’OMA-URI qui configurent l’appareil. Pour les appareils iOS, vous pouvez importer un fichier de configuration que vous avez créé dans l’outil Apple Configurator.
Pour plus d’informations, consultez [Guide pratique pour configurer des paramètres personnalisés](how-to-configure-custom-settings.md) Prend en charge : Android, iOS, Mac OS et Windows Phone 8.1.

