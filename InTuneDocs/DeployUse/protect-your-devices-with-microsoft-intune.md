---
title: "Protéger des appareils | Microsoft Intune"
description: "Découvrez certaines méthodes permettant à Intune de vous aider à protéger vos appareils contre les accès non autorisés et d’autres menaces."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c999a852b68762002ac94269e27ecbf46c8f9999
ms.openlocfilehash: 3318590eaedc6f0e96fb463dc016d5786eeb38fb


---

# Protéger des appareils avec Microsoft Intune
Une fois vos appareils gérés par Intune, vous devez vérifier qu’ils sont protégés contre les accès non autorisés et d’autres menaces. Voici quelques-unes des fonctionnalités d’Intune qui aident à atteindre ces objectifs.

> [!TIP]
> Cette rubrique ne contient pas tous les moyens par lesquels Intune peut aider à sécuriser vos appareils. Par exemple, vous pouvez utiliser des stratégies Intune pour configurer de nombreux paramètres de sécurité pour vos appareils, notamment les mots de passe, les paramètres de chiffrement et les fonctionnalités matérielles telles que l’appareil photo et le Bluetooth. Consultez [Gérer des paramètres et des fonctionnalités sur vos appareils avec Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) pour en savoir plus sur ces paramètres.

## Réinitialiser les codes secrets quand les utilisateurs ne peuvent plus accéder à leur appareil
La première étape de la protection des données d’entreprise sur les appareils mobiles consiste à exiger un code secret pour utiliser l’appareil. Il peut arriver que vous deviez [réinitialiser un code secret](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou aider un employé à le faire, soit en supprimant le code secret, soit en définissant un code secret temporaire à distance. Vous pouvez également [Verrouiller un appareil à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) en cas de perte ou de vol.

## Ajouter une couche supplémentaire de protection sur des appareils Windows
L’[authentification multifacteur (MFA)](protect-windows-devices-with-multi-factor-authentication.md) est un moyen plus sûr d’authentifier les utilisateurs d’appareils Windows et Windows Phone sur le réseau. Avec elle, les utilisateurs doivent confirmer leur identité au-delà du nom d’utilisateur et du mot de passe, via un appel téléphonique ou un message texte.

## Contrôler les paramètres de Microsoft Passport sur les appareils Windows
Intune s’intègre à [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), qui est l’une des méthodes de connexion disponibles pour Windows 10 et ultérieur. Microsoft Passport for Work utilise Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

## Contourner le verrou d’activation sur les appareils iOS
Le verrou d’activation est une fonctionnalité qui permet de protéger les appareils des utilisateurs en demandant la saisie de leur ID Apple et de leur mot de passe avant d’effacer ou de réactiver l’appareil. Toutefois, cela peut engendrer des problèmes, par exemple si l’utilisateur quitte l’entreprise sans supprimer le verrou. [Le contournement du verrou d’activation iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) peut vous aider en supprimant le verrou des appareils iOS supervisés pour vous permettre de les réaffecter ou de les effacer.

## Protéger les PC Windows gérés avec le client Intune
Intune continue à prendre en charge les stratégies de sécurité pour les PC Windows non inscrits mais gérés avec le logiciel client pour ordinateur Intune. Pour savoir comment ces stratégies peuvent vous aider à sécuriser vos PC Windows, consultez [Utilisation de stratégies pour vous aider à protéger les PC Windows qui exécutent le logiciel client Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Aug16_HO2-->


