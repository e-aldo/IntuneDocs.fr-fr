---
title: Paramètres de messagerie Microsoft Intune pour les appareils iOS
titleSuffix: ''
description: Découvrez les paramètres Microsoft Intune que vous pouvez utiliser pour configurer les paramètres de messagerie sur des appareils exécutant iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0912ec4fdc77b51903b4febd54f9d16972b867a8
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-ios"></a>Paramètres de profil de messagerie dans Microsoft Intune pour les appareils exécutant iOS 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cet article répertorie les paramètres de profil de messagerie que vous pouvez configurer pour vos appareils exécutant iOS.

## <a name="email-settings"></a>Paramètres de messagerie

- **Serveur de messagerie** : le nom d’hôte de votre serveur Exchange.
- **Nom du compte** : spécifiez le nom complet du compte de messagerie, tel qu’il apparaît aux utilisateurs sur leurs appareils.
- **Attribut de nom d’utilisateur d’AAD** : il s’agit de l’attribut dans Active Directory (AD) ou Azure AD, qui est utilisé pour générer le nom d’utilisateur de ce profil de messagerie. Sélectionnez **Adresse SMTP principale**, comme **user1@contoso.com** ou **Nom d’utilisateur principal**, comme **user1** ou **user1@contoso.com**.
- **Attribut d’adresse de messagerie d’AAD** : la façon dont l’adresse de messagerie de l’utilisateur est générée sur chaque appareil. Sélectionnez **Adresse SMTP principale** pour utiliser l’adresse SMTP principale pour vous connecter à Exchange ou **Nom d’utilisateur principal** pour utiliser le nom principal complet comme adresse de messagerie.
- **Méthode d’authentification** : sélectionnez **Nom d’utilisateur et mot de passe** ou **Certificats** comme méthode d’authentification utilisée par le profil de messagerie (**Remarque** : Azure Multi-Factor Authentication n’est pas pris en charge).
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment et qui sert à authentifier la connexion Exchange.
- **SSL** : utilisez la communication SSL (Secure Sockets Layer) pour envoyer et recevoir des e-mails, et communiquer avec le serveur Exchange.
- **S/MIME** : envoyez des e-mails en utilisant la signature S/MIME.
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment et qui sert à authentifier la connexion Exchange.
    - Si vous choisissez un certificat SCEP, vérifiez qu’un certificat PFX (Personal Information Exchange) valide est installé sur l’appareil.
- **Nombre d’e-mails à synchroniser** : sélectionnez le nombre de jours de courrier électronique à synchroniser ou sélectionnez **Illimité** pour synchroniser tous les messages disponibles.
- **Autoriser le déplacement des messages vers d’autres comptes de messagerie** : cette option permet aux utilisateurs de déplacer les e-mails entre les différents comptes configurés sur l’appareil.
- **Autoriser l’envoi de courrier électronique à partir d’applications tierces** : autorisez l’utilisateur à sélectionner ce profil en tant que compte par défaut pour l’envoi d’e-mails et autorisez les applications tierces à ouvrir les e-mails dans l’application de messagerie native, par exemple pour y joindre des fichiers.
- **Synchroniser les adresses de messagerie récemment utilisées** : cette option permet aux utilisateurs de synchroniser la liste des adresses de messagerie qui ont été récemment utilisées sur l’appareil.
