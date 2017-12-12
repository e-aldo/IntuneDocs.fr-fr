---
title: "Utiliser des applications gérées sur votre appareil iOS | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8c3d9285408f2cfa394ed31ec36fcaea47306eb5
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2017
---
# <a name="use-managed-apps-on-your-ios-device"></a>Utiliser des applications gérées sur votre appareil iOS

Les applications gérées sont des applications que le support technique de votre entreprise peut configurer pour protéger les données d’entreprise auxquelles vous pouvez accéder dans cette application. Quand vous accédez à des données d’entreprise dans une application gérée sur votre appareil iOS, l’application peut ne pas fonctionner exactement comme prévu. Par exemple, vous ne pouvez pas copier et coller des données d’entreprise protégées, ou vous ne pouvez pas enregistrer ces données à certains emplacements.

Différentes applications gérées peuvent aussi fonctionner ensemble sur votre appareil pour vous permettre d’effectuer vos tâches quotidiennes tout en protégeant les données d’entreprise. Par exemple, si vous ouvrez un fichier de l’entreprise dans une application gérée et qu’une autre application gérée est nécessaire pour afficher ce fichier, l’application gérée qui vous permet d’afficher le fichier s’ouvre automatiquement. Si une application obligatoire n’est pas disponible, certaines actions, comme l’ouverture d’un document ou l’accès à un lien web à partir d’un document géré, peuvent ne pas être disponibles.

Quand vous accédez à des données d’entreprise dans une application gérée, un message semblable à celui ci-dessous s’affiche, qui vous indique que l’application que vous ouvrez est gérée.

![managed-apps-message-ios](./media/managed-apps-message.png)

### <a name="how-do-i-get-managed-apps"></a>Comment obtenir des applications gérées ?
Vous obtenez des applications gérées de deux façons différentes :

-   Quand votre appareil est inscrit dans Microsoft Intune, vous installez l’application à partir de votre application Portail d’entreprise ou du site web du portail d’entreprise, ou bien le support technique de votre entreprise peut l’installer sur votre appareil. Pour en savoir plus sur l’inscription, consultez [Inscrire un appareil iOS dans Intune](enroll-your-device-in-intune-ios.md) ou [Inscrire votre appareil macOS dans Intune](enroll-your-device-in-intune-macos.md).

-   Vous installez une application à partir de l’App Store, puis vous vous connectez avec votre compte d’utilisateur d’entreprise qui est géré par Intune.

Le support technique de votre entreprise peut parfois acheter plusieurs licences pour une application que vous installez. Si vous voyez un message vous demandant d’accepter le contrat Programme d’achat en volume (VPP) Apple, ceci est tout à fait normal, et vous pouvez accepter le contrat. Si vous ne l’acceptez pas, vous ne pouvez pas installer l’application.

### <a name="what-can-my-company-support-manage-in-an-app"></a>Que peut gérer le support technique de mon entreprise dans une application ?
Voici quelques exemples d’options que le support technique de votre entreprise peut gérer dans une application et qui peuvent affecter vos interactions avec les données d’entreprise sur votre appareil :

-   Accès à des sites Web spécifiques

-   Transferts de données entre les applications

-   Enregistrement de fichiers

-   Opérations de copier et coller

-   Conditions d'accès de code confidentiel

-   Votre connexion à l’aide d’informations d’identification d’entreprise

-   Possibilité de sauvegarder dans le cloud

-   Possibilité de prendre des captures d’écran

-   Cryptage des données

Pour plus d’informations sur les applications gérées sur votre appareil, contactez le support technique de votre entreprise. Pour obtenir ses coordonnées, consultez le [site web du Portail d’entreprise](https://portal.manage.microsoft.com#HelpDeskDialog).
