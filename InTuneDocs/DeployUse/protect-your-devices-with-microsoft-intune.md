---
# required metadata

title: Protéger des appareils avec Microsoft Intune | Microsoft Intune
description:
keywords:
author: Robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Protéger des appareils avec Microsoft Intune
Une fois vos appareils gérés par Intune, vous devez vous assurer qu’ils sont protégés contre les accès non autorisés et d’autres menaces. Voici quelques-unes des fonctionnalités d’Intune qui aident à atteindre ces objectifs.

> [!TIP]
> Cette rubrique ne contient pas tous les moyens par lesquels Intune peut aider à sécuriser vos appareils. Par exemple, vous pouvez utiliser des stratégies Intune pour configurer de nombreux paramètres de sécurité pour vos appareils, notamment les mots de passe, les paramètres de chiffrement et les fonctionnalités matérielles telles que l’appareil photo et le Bluetooth. Consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) pour en savoir plus sur ces paramètres.

## Réinitialiser les codes secrets quand les utilisateurs ne peuvent plus accéder à leur appareil
Sachant que la première mesure à prendre pour protéger les données de l’entreprise sur les appareils mobiles est d’exiger un code secret pour utiliser l’appareil, vous êtes parfois amené à [réinitialiser un code secret](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou à aider un employé à le faire en supprimant le code secret ou en définissant un code secret temporaire à distance. Vous pouvez également [Verrouiller un appareil à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) en cas de perte ou de vol.

## Ajouter une couche supplémentaire de protection sur des appareils Windows
L’[authentification multifacteur (MFA)](protect-windows-devices-with-multi-factor-authentication.md) est un moyen plus sûr d’authentifier les utilisateurs d’appareils Windows et Windows Phone sur le réseau.  Avec elle, les utilisateurs doivent confirmer leur identité au-delà du nom d'utilisateur et du mot de passe, via un appel téléphonique ou un message texte.

## Contrôler les paramètres de Microsoft Passport sur les appareils Windows
Intune vous permet d’intégrer [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) et de disposer ainsi d’une autre méthode de connexion pour Windows 10 et versions ultérieures utilisant Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

## Protéger les PC Windows gérés avec le client Intune
Intune continue à prendre en charge les stratégies de sécurité pour les PC Windows non inscrits mais gérés avec le logiciel client pour ordinateur Intune. Pour savoir comment ces stratégies peuvent vous aider à sécuriser vos PC Windows, consultez [Utiliser des stratégies pour protéger les PC Windows équipés du logiciel client Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).


<!--HONumber=May16_HO1-->


