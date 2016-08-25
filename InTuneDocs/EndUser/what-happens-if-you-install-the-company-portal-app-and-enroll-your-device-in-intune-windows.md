---
title: "Que se passe-t-il si vous installez l’application Portail d’entreprise et inscrivez votre appareil Windows dans Intune ? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 7/8/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
ROBOTS: noindex,nofollow
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 618e2abda642c3b9b2e813824dfd4235c9309faa
ms.openlocfilehash: 8b6e9b1bbf2d870b57dfcd7cdefefa2550d07d14


---


# Que se passe-t-il si vous installez l’application Portail d’entreprise et inscrivez votre appareil Windows dans Intune ?

Lorsque vous installez l’application Portail d’entreprise et que vous l’utilisez pour inscrire un appareil Windows ou Windows Phone, vous permettez à votre administrateur de gérer votre appareil pour sécuriser les données de votre entreprise ou de votre établissement scolaire, comme décrit ci-dessous, pour les appareils antérieurs à Windows 10. Pour plus d’informations sur les appareils Windows 10, consultez [cette page](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## Que se passe-t-il pour tous les appareils Windows après l’inscription ?
Lorsque vous inscrivez votre appareil Windows ou Windows Phone dans Intune, vous pouvez :

-   accéder au réseau de l'entreprise, à votre messagerie et à vos fichiers de travail ;

-   obtenir des applications d’entreprise à partir du site web Portail d’entreprise (ce site web est d’ailleurs le seul moyen pour obtenir de telles applications pour Windows 7 et Vista) ;

-   configurer automatiquement votre compte de messagerie professionnelle ou scolaire ;

-   réinitialiser les paramètres de votre téléphone en cas de perte ou de vol.

Quand vous inscrivez votre appareil, vous autorisez votre administrateur à effectuer les opérations suivantes :

-   réinitialiser votre périphérique aux réglages par défaut d'origine. Ceci est utile si l'appareil est perdu ou volé ;

-   supprimer toutes les données relatives à l’entreprise, ainsi que les applications professionnelles qui ont été installées. Vos données et paramètres personnels ne sont pas supprimés.

-   Votre administrateur informatique peut effectuer un inventaire de tous les logiciels installés sur l'ordinateur, y compris les logiciels que vous avez installés personnellement ;

-   vous forcer à avoir un mot de passe ou un code PIN sur l’appareil, ce qui peut le bloquer, ou le réinitialiser selon les paramètres par défaut du fabricant, ce qui peut entraîner la suppression des données en cas de saisies successives de mots de passe incorrects ;

-   forcer le chiffrement de toutes les données sur l’appareil, ce qui permet de protéger les données si l’appareil est perdu ou volé.

-   Vous êtes obligé d'accepter les conditions générales.

-   Votre administrateur informatique peut appliquer des stratégies sur l'ordinateur. Par exemple, vous devrez peut-être définir un mot de passe ou un code PIN sur l'ordinateur, ce qui peut le bloquer, ou bien supprimer toutes les données du disque dur de votre ordinateur en cas de saisies multiples de mots de passe incorrects.

-   Désactiver la carte SD.

## Que se passe-t-il pour tous les ordinateurs Windows après l’inscription ?

-  Certains logiciels seront installés sur votre ordinateur pour permettre à votre administrateur informatique de gérer l'ordinateur et à vous d'obtenir des ressources d'entreprise telles que des applications et des informations de support. Votre administrateur informatique peut automatiquement mettre à jour ce logiciel.

-  Intune Endpoint Protection peut être installé sur votre ordinateur. Il s'agit d'un logiciel qui recherche les virus et programmes malveillants.

-  Votre administrateur informatique peut effectuer un inventaire de tous les logiciels installés sur l'ordinateur, y compris les logiciels que vous avez installés personnellement.

-  Vous devez accepter les conditions générales.

-  Votre administrateur informatique peut collecter ou supprimer des données du disque dur de votre ordinateur. Votre administrateur peut également supprimer l’ensemble du disque dur.

-  Votre administrateur informatique peut installer des applications et des mises à jour sur votre ordinateur.

-  Votre administrateur informatique peut appliquer des stratégies sur l'ordinateur. Par exemple, vous pouvez être amené à définir un mot de passe ou un code PIN sur l’ordinateur, ce qui peut le bloquer, ou bien supprimer toutes les données du disque dur de votre ordinateur en cas de saisies successives de mots de passe incorrects.


## Que se passe-t-il toutes les huit heures après l’inscription d’appareils ?
Environ toutes les huit heures, les appareils inscrits vont :

-   télécharger toute mise à jour d'une application ou d'une stratégie rendue disponible par votre administrateur informatique ;

-   envoyer toute mise à jour de l'inventaire matériel ;

-   envoyer toute mise à jour de l'inventaire d'applications de la société.

Pour connaître les étapes d'inscription, consultez [Inscrire un appareil Windows dans Intune](enroll-your-device-in-intune-windows.md). Pour savoir ce que votre administrateur informatique peut voir sur votre appareil, consultez [Que voit mon administrateur informatique quand j’inscris mon appareil dans Intune ?](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

Si vous avez des questions, contactez votre administrateur informatique. Pour obtenir ses informations de contact, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).

### Voir aussi
[Utilisation de votre appareil Windows avec Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO4-->


