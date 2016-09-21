---
title: "Protéger des appareils | Microsoft Intune"
description: "Découvrez certaines méthodes permettant à Intune de vous aider à protéger vos appareils contre les accès non autorisés et d’autres menaces."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3e761ed60fe3df81061023aa31e0545aeeadd316
ms.openlocfilehash: be5051c46e1ef04ea140c9d440720f570edcbd1e


---

# Protéger des appareils avec Microsoft Intune

Microsoft Intune offre un ensemble complet de fonctionnalités qui vous permettent de protéger les appareils que vous gérez et les données stockées sur ces appareils. Lisez cette rubrique pour apprendre l’essentiel de ces fonctionnalités et découvrir comment procéder pour en savoir plus.

## Généralités sur la protection de tous les appareils

### Configuration des appareils
Les [stratégies de configuration](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) Intune vous permettent de protéger et de configurer des appareils en contrôlant une multitude de paramètres et de fonctionnalités. Exemple :
- Vous pouvez limiter l’utilisation des fonctionnalités matérielles sur l’appareil, comme l’appareil photo ou le Bluetooth.
- Vous pouvez configurer les applications conformes et non conformes. Vous êtes averti si une application non conforme est installée (et certaines plateformes peuvent même bloquer l’installation).

### Réinitialiser les codes secrets quand les utilisateurs ne peuvent plus accéder à leur appareil
Sachant que la première mesure à prendre pour protéger les données de l’entreprise sur les appareils mobiles est d’exiger un code secret pour utiliser l’appareil, vous êtes parfois amené à [réinitialiser un code secret](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou à aider un employé à le faire en supprimant le code secret ou en définissant un code secret temporaire à distance. Vous pouvez également [Verrouiller un appareil à distance](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) en cas de perte ou de vol.

### Mettre des appareils hors service et supprimer des données
Quand un appareil doit être [retiré de la gestion Intune](retire-devices-from-microsoft-intune-management) (par exemple, quand un utilisateur quitte l’entreprise ou quand l’appareil est perdu ou volé), vous voulez très probablement supprimer les données qu’il contient. Intune propose tout un éventail de méthodes pour veiller à ce que vos données d’entreprise restent sécurisées.

### Exiger la conformité des appareils
Intune comprend des [stratégies de conformité des appareils](introduction-to-device-compliance-policies-in-microsoft-intune) qui vous permettent d’évaluer (et dans certains cas corriger) des appareils qui ne sont pas conformes aux règles que vous spécifiez. Par exemple, vous pouvez déterminer si des appareils iOS sont jailbreakés, si des appareils sont chiffrés ou si des appareils Windows 10 sont signalés comme étant intègres par le service d’attestation d’intégrité.

### Protéger les applications et les données qu’elles utilisent
Intune vous propose tout un éventail de fonctionnalités pour vous permettre de protéger les applications et leurs données. Par exemple, les stratégies de gestion des applications mobiles (GAM) peuvent empêcher des données d’être sauvegardées à partir d’une application protégée, limiter la copie et le collage vers d’autres applications, exiger un code confidentiel pour accéder à une application, etc. Pour plus d’informations sur la protection des applications, consultez [Protéger les applications et les données avec Microsoft Intune](protect-apps-and-data-with-microsoft-intune).

## Fonctions supplémentaires pour les appareils Windows

### Ajouter une couche supplémentaire de protection sur des appareils Windows
L’[authentification multifacteur (MFA)](protect-windows-devices-with-multi-factor-authentication.md) est un moyen plus sûr d’authentifier les utilisateurs d’appareils Windows et Windows Phone sur le réseau.  Avec MFA, les utilisateurs doivent confirmer leur identité au-delà du nom d’utilisateur et du mot de passe, via un appel téléphonique ou un message texte.

### Contrôler les paramètres Windows Hello Entreprise sur des appareils Windows
Intune vous permet d’intégrer [Windows Hello Entreprise](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (anciennement Microsoft Passport) et de disposer ainsi d’une autre méthode de connexion pour Windows 10 et versions ultérieures utilisant Active Directory ou un compte Azure Active Directory pour remplacer un mot de passe, une carte à puce ou une carte à puce virtuelle.

## Fonctions supplémentaires pour les appareils iOS

### Contourner le verrou d’activation sur les appareils iOS
Le verrou d’activation est une fonctionnalité qui permet de protéger les appareils des utilisateurs en demandant la saisie de leur ID Apple et de leur mot de passe avant d’effacer ou de réactiver l’appareil. Toutefois, cela peut engendrer des problèmes, par exemple, si l’utilisateur quitte l’entreprise sans supprimer le verrou. [Le contournement du verrou d’activation iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) peut vous aider en supprimant le verrou des appareils iOS supervisés pour vous permettre de les réaffecter ou de les effacer.



## Protéger les PC Windows gérés avec le client Intune
Intune continue à prendre en charge les stratégies de sécurité pour les PC Windows non inscrits mais gérés avec le logiciel client pour ordinateur Intune. Pour savoir comment ces stratégies peuvent vous aider à sécuriser vos PC Windows, consultez [Utilisation de stratégies pour vous aider à protéger les PC Windows qui exécutent le logiciel client Intune](policies-to-protect-windows-pcs-in-microsoft-intune.md).



<!--HONumber=Sep16_HO1-->


