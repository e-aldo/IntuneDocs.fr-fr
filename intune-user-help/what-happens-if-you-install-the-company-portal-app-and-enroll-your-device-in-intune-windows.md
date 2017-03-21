---
title: "Installation de l’application Portail d’entreprise pour Windows | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d65e3452-5bbf-4d26-a06e-401ddcc47f39
searchScope:
- User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: 0e6b7ae1794ff0857dfb203eb3c67d7ba494bd8e
ms.openlocfilehash: bde2ccc0c170a85e926357d54fcf4ffe6ee50fd9
ms.lasthandoff: 02/21/2017


---


# <a name="what-happens-if-you-install-the-company-portal-app-and-enroll-your-windows-device-in-intune"></a>Que se passe-t-il si vous installez l’application Portail d’entreprise et inscrivez votre appareil Windows dans Intune ?

Quand vous installez l’application Portail d’entreprise et que vous l’utilisez pour inscrire un appareil Windows ou Windows Phone, vous permettez à l’administrateur informatique de gérer votre appareil pour sécuriser les données de votre entreprise ou établissement scolaire. Cette rubrique décrit ce qui se passe pour les appareils antérieurs à Windows 10. Pour les appareils Windows 10, consultez la [rubrique connexe](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows10.md).

## <a name="what-happens-to-all-windows-devices-after-enrollment"></a>Que se passe-t-il pour tous les appareils Windows après l’inscription ?
Quand votre appareil Windows ou Windows Phone est inscrit dans Intune, vous pouvez :

-   accéder au réseau de l’entreprise, à votre messagerie et à vos fichiers de travail ;

-   obtenir des applications d’entreprise à partir du site web du portail d’entreprise ; (__Remarque__ : Pour Windows 7 et Windows Vista, vous ne pouvez obtenir des applications d’entreprise qu’à partir du site web du portail d’entreprise.)

-   configurer automatiquement votre compte e-mail d’entreprise ou scolaire ;

-   réinitialiser les paramètres de votre téléphone en cas de perte ou de vol.

Quand vous inscrivez votre appareil, vous autorisez l’administrateur informatique à effectuer les opérations suivantes :

-   Réinitialiser votre appareil aux réglages par défaut d’origine. Ceci est utile si l'appareil est perdu ou volé.

-   Supprimer uniquement les fichiers relatifs à l’entreprise et les applications professionnelles. *Vos données et paramètres personnels ne sont pas supprimés.*

-   Votre administrateur informatique peut voir les logiciels installés sur l’appareil, dont les logiciels que vous avez installés personnellement.

-   Définir les exigences pour votre appareil, comme vous obliger à avoir un mot de passe ou un code confidentiel sur l’appareil pour protéger les données d’entreprise. Votre administrateur informatique peut également limiter le nombre de tentatives de saisie d’un mot de passe et bloquer l’appareil si vous dépassez le nombre maximal autorisé.

-   Vous obliger à chiffrer les données sur votre appareil pour mieux protéger les données d’entreprise si l’appareil est perdu ou volé.

-   Vous êtes obligé d'accepter les conditions générales.

-   Vous empêcher de prendre des photos de données d’entreprise.

## <a name="what-happens-to-all-windows-pcs-after-enrollment"></a>Que se passe-t-il pour tous les ordinateurs Windows après l’inscription ?

-  Certains logiciels seront installés sur votre ordinateur pour permettre à votre administrateur informatique de gérer l’ordinateur et à vous d’accéder aux ressources d’entreprise telles que des applications et des informations de support. Votre administrateur informatique peut automatiquement mettre à jour ces logiciels.

-  Intune Endpoint Protection peut être installé sur votre ordinateur. Ce logiciel recherche les virus et programmes malveillants.

-  Votre administrateur informatique peut collecter ou supprimer des données du disque dur de votre ordinateur.

-  Votre administrateur informatique peut installer des applications et des mises à jour sur votre ordinateur.

## <a name="what-happens-every-eight-hours-after-device-enrollment"></a>Que se passe-t-il toutes les huit heures après l’inscription d’appareils ?

Environ toutes les huit heures, les appareils inscrits vont :

-   télécharger toute mise à jour d’une application ou d’une stratégie rendue disponible par votre administrateur informatique ;

-   envoyer toute mise à jour de l'inventaire matériel ;

-   envoyer toute mise à jour de l'inventaire d'applications de la société.

Si vous avez des questions, contactez votre administrateur informatique. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](http://portal.manage.microsoft.com).
