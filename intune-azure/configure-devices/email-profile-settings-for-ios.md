---
title: "Paramètres de messagerie Intune pour les appareils iOS | Préversion Intune Azure | Microsoft Docs"
description: "Préversion Intune Azure : Découvrez les paramètres Intune que vous pouvez utiliser pour configurer les connexions à la messagerie sur les appareils iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 186630903a606842406ff1d76115c1fa7d1c962e
ms.lasthandoff: 02/16/2017


---

# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a>Paramètres de profil de messagerie pour les appareils iOS dans Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]



- **Serveur de messagerie** : le nom d’hôte de votre serveur Exchange.
- **Nom du compte** : spécifiez le nom complet du compte de messagerie, tel qu’il apparaîtra aux utilisateurs sur leurs appareils.
- **Attribut de nom d’utilisateur d’AAD** : il s’agit de l’attribut dans Active Directory (AD) ou Azure AD, qui doit être utilisé pour générer le nom d’utilisateur de ce profil de messagerie. Sélectionnez **Adresse SMTP principale**, comme **user1@contoso.com** ou **Nom d’utilisateur principal**, comme **user1** ou **user1@contoso.com**.
- **Attribut d’adresse de messagerie d’AAD** : la façon dont l’adresse de messagerie de l’utilisateur est générée sur chaque appareil. Sélectionnez **Adresse SMTP principale** pour utiliser l’adresse SMTP principale pour vous connecter à Exchange ou **Nom d’utilisateur principal** pour utiliser le nom principal complet comme adresse de messagerie.
- **Méthode d’authentification** : sélectionnez **Nom d’utilisateur et mot de passe** ou **Certificats** comme méthode d’authentification utilisée par le profil de messagerie.
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment qui servira à authentifier la connexion Exchange.
- **SSL** : utilisez la communication SSL (Secure Sockets Layer) pour envoyer et recevoir des e-mails, et communiquer avec le serveur Exchange.
- **S/MIME** : envoyez le courrier électronique sortant à l’aide du chiffrement S/MIME.
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment qui servira à authentifier la connexion Exchange.
- **Nombre d’e-mails à synchroniser** : sélectionnez le nombre de jours de courrier électronique à synchroniser ou sélectionnez **Illimité** pour synchroniser tous les messages disponibles.
- **Autoriser le déplacement des messages vers d’autres comptes de messagerie** : cette option permet aux utilisateurs de déplacer les e-mails entre les différents comptes configurés sur l’appareil.
- **Autoriser l’envoi de courrier électronique à partir d’applications tierces** : autorisez l’utilisateur à sélectionner ce profil en tant que compte par défaut pour l’envoi d’e-mails et autorisez les applications tierces à ouvrir les e-mails dans l’application de messagerie native, par exemple pour y joindre des fichiers.
- **Synchroniser les adresses de messagerie récemment utilisées** : cette option permet aux utilisateurs de synchroniser la liste des adresses de messagerie qui ont été récemment utilisées sur l’appareil.

