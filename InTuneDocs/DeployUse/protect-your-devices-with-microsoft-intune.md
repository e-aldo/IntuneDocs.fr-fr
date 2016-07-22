---
title: "Protéger des appareils | Microsoft Intune"
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
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c52448ab454a764be922319fb930a85a86c3996e
ms.openlocfilehash: c8f833593e6a4606b0dd56373d4dc016c7ea0924


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

## Contourner le verrou d’activation sur les appareils iOS
Le verrou d’activation est une fonctionnalité qu permet de protéger les appareils des utilisateurs en demandant la saisie de leur ID Apple et de leur mot de passe avant d’effacer ou de réactiver l’appareil. Toutefois, cela peut engendrer des problèmes, par exemple, si l’utilisateur quitte l’entreprise sans supprimer le verrou. [Le contournement du verrou d’activation iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) peut vous aider en supprimant le verrou des appareils iOS supervisés pour vous permettre de les réaffecter ou de les effacer.

## Protéger les PC Windows gérés avec le client Intune
Intune continue à prendre en charge les stratégies de sécurité pour les PC Windows non inscrits mais gérés avec le logiciel client pour ordinateur Intune. Pour savoir comment ces stratégies peuvent vous aider à sécuriser vos PC Windows, consultez [Utilisation de stratégies pour vous aider à protéger les PC Windows qui exécutent le logiciel client Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Jun16_HO4-->


