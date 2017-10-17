---
title: "Protéger des appareils avec Microsoft Intune"
description: "Découvrez certaines méthodes permettant à Intune de vous aider à protéger vos appareils contre les accès non autorisés et d’autres menaces."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c866f2a8eebdb2f6c07314b745f65c06e3469e4e
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/10/2017
---
# <a name="protect-devices-with-microsoft-intune"></a>Protéger des appareils avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune offre un ensemble complet de fonctionnalités qui vous permettent de protéger les appareils que vous gérez et les données stockées sur ces appareils. Lisez cette rubrique pour apprendre l’essentiel de ces fonctionnalités et découvrir comment procéder pour en savoir plus.

## <a name="general-ways-to-protect-all-devices"></a>Généralités sur la protection de tous les appareils

### <a name="device-configuration"></a>Configuration des appareils
Les [stratégies de configuration](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) Intune vous permettent de protéger et de configurer des appareils en contrôlant une multitude de paramètres et de fonctionnalités. Exemple :
- Vous pouvez limiter l’utilisation des fonctionnalités matérielles sur l’appareil, comme l’appareil photo ou le Bluetooth.
- Vous pouvez configurer les applications conformes et non conformes. Vous êtes averti si une application non conforme est installée (et certaines plateformes peuvent même bloquer l’installation).

### <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Réinitialiser les codes secrets quand les utilisateurs ne peuvent plus accéder à leur appareil
Sachant que la première mesure à prendre pour protéger les données de l’entreprise sur les appareils mobiles est d’exiger un code secret pour utiliser l’appareil, vous êtes parfois amené à [réinitialiser un code secret](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou à aider un employé à le faire en supprimant le code secret ou en définissant un code secret temporaire à distance. Vous pouvez également [Verrouiller un appareil à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) en cas de perte ou de vol.

### <a name="retire-devices-and-remove-data"></a>Mettre des appareils hors service et supprimer des données
Quand un appareil doit être [retiré de la gestion Intune](retire-devices-from-microsoft-intune-management.md) (par exemple, quand un utilisateur quitte l’entreprise ou quand l’appareil est perdu ou volé), vous voulez très probablement supprimer les données qu’il contient. Intune propose tout un éventail de méthodes pour veiller à ce que vos données d’entreprise restent sécurisées.

### <a name="require-devices-to-be-compliant"></a>Exiger la conformité des appareils
Intune comprend des [stratégies de conformité des appareils](introduction-to-device-compliance-policies-in-microsoft-intune.md) qui vous permettent d’évaluer (et dans certains cas corriger) des appareils qui ne sont pas conformes aux règles que vous spécifiez. Par exemple, vous pouvez déterminer si des appareils iOS sont jailbreakés, si des appareils sont chiffrés ou si des appareils Windows 10 sont signalés comme étant intègres par le service d’attestation d’intégrité.

### <a name="protect-apps-and-the-data-they-use"></a>Protéger les applications et les données qu’elles utilisent
Intune vous propose tout un éventail de fonctionnalités pour vous permettre de protéger les applications et leurs données. Par exemple, les stratégies de gestion des applications mobiles (GAM) peuvent empêcher des données d’être sauvegardées à partir d’une application protégée, limiter la copie et le collage vers d’autres applications, exiger un code confidentiel pour accéder à une application, etc. Pour plus d’informations sur la protection des applications, consultez [Protéger les applications et les données avec Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md).

### <a name="add-an-additional-layer-of-protection-to-devices"></a>Ajouter une couche supplémentaire de protection sur des appareils
L’[authentification multifacteur (MFA)](multi-factor-authentication-azure-active-directory.md) est un moyen plus sûr d’authentifier les utilisateurs d’appareils sur le réseau.  Avec MFA, les utilisateurs doivent confirmer leur identité au-delà du nom d’utilisateur et du mot de passe, via un appel téléphonique ou un message texte.

## <a name="further-capabilities-for-windows-devices"></a>Fonctions supplémentaires pour les appareils Windows

### <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Contrôler les paramètres Windows Hello Entreprise sur des appareils Windows
Intune vous permet d’intégrer [Windows Hello Entreprise](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (anciennement Microsoft Passport) et de disposer ainsi d’une autre méthode de connexion pour Windows 10 et versions ultérieures utilisant Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

## <a name="further-capabilities-for-ios-devices"></a>Fonctions supplémentaires pour les appareils iOS

### <a name="bypass-activation-lock-on-ios-devices"></a>Contourner le verrou d’activation sur les appareils iOS
Le verrou d’activation est une fonctionnalité qui permet de protéger les appareils des utilisateurs en demandant la saisie de leur ID Apple et de leur mot de passe avant d’effacer ou de réactiver l’appareil. Toutefois, cela peut engendrer des problèmes, par exemple, si l’utilisateur quitte l’entreprise sans supprimer le verrou. [Le contournement du verrou d’activation iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) peut vous aider en supprimant le verrou des appareils iOS supervisés pour vous permettre de les réaffecter ou de les effacer.



## <a name="protect-windows-pcs-managed-with-the-intune-client"></a>Protéger les PC Windows gérés avec le client Intune
Intune continue à prendre en charge les stratégies de sécurité pour les PC Windows non inscrits mais gérés avec le logiciel client pour ordinateur Intune. Pour savoir comment ces stratégies peuvent vous aider à sécuriser vos PC Windows, consultez [Utilisation de stratégies pour vous aider à protéger les PC Windows qui exécutent le logiciel client Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).
