---
title: "Paramètres de messagerie Intune pour les appareils Android et Android for Work"
titleSuffix: Intune on Azure
description: "Découvrez les paramètres Intune que vous pouvez utiliser pour configurer les connexions à la messagerie sur les appareils Android."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4d3458cc-fcaa-4648-b13f-bf1f0616c1c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c1f80e09241609b420a186011ff8dd059f0dd8df
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="email-profile-settings-for-android--devices-in-microsoft-intune"></a>Paramètres de profil de messagerie pour les appareils Android dans Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

En tant qu’administrateur Intune, vous pouvez créer et affecter des paramètres de messagerie aux appareils Android suivants :
- [Android – Samsung KNOX Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Paramètres de messagerie Android Samsung KNOX Standard
- **Serveur de messagerie** : le nom d’hôte de votre serveur Exchange.
- **Nom du compte** : spécifiez le nom complet du compte de messagerie, tel qu’il apparaît aux utilisateurs sur leurs appareils.
- **Attribut de nom d’utilisateur d’AAD** : il s’agit de l’attribut dans Active Directory (AD) ou Azure AD utilisé pour générer le nom d’utilisateur de ce profil de messagerie. Sélectionnez **Adresse SMTP principale**, comme user1@contoso.com ou **Nom d’utilisateur principal**, comme user1 ou user1@contoso.com.
- **Attribut d’adresse de messagerie d’AAD** : la façon dont l’adresse de messagerie de l’utilisateur est générée sur chaque appareil. Sélectionnez **Adresse SMTP principale** pour utiliser l’adresse SMTP principale pour vous connecter à Exchange ou **Nom d’utilisateur principal** pour utiliser le nom principal complet comme adresse de messagerie.
- **Méthode d’authentification** : sélectionnez **Nom d’utilisateur et mot de passe** ou **Certificats** comme méthode d’authentification utilisée par le profil de messagerie.
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment pour authentifier la connexion Exchange.

### <a name="security-settings"></a>Paramètres de sécurité

- **SSL** : utilisez la communication SSL (Secure Sockets Layer) pour envoyer et recevoir des e-mails, et communiquer avec le serveur Exchange.
- **S/MIME** : envoyez le courrier électronique sortant à l’aide du chiffrement S/MIME.
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment pour authentifier la connexion Exchange.

### <a name="synchronization-settings"></a>Paramètres de synchronisation

- **Nombre d’e-mails à synchroniser** : sélectionnez le nombre de jours de courrier électronique à synchroniser ou sélectionnez **Illimité** pour synchroniser tous les messages disponibles.
- **Planification de la synchronisation** : sélectionnez la planification selon laquelle les appareils vont synchroniser les données à partir du serveur Exchange. Vous pouvez également sélectionner **À mesure que les messages arrivent** pour synchroniser les données quand elles arrivent ou **Manuel** pour que ce soit l’utilisateur de l’appareil qui lance la synchronisation.

### <a name="content-sync-settings"></a>Paramètres de synchronisation du contenu

- **Type de contenu à synchroniser** : sélectionnez les types de contenu à synchroniser avec les appareils :
    - **Contacts**
    - **Calendrier**
    - **Tâches**

## <a name="android-for-work-email-settings"></a>Paramètres de messagerie Android for Work

- **Application de messagerie** - Sélectionnez **Gmail** ou **Nine Work**
- **Serveur de messagerie** : le nom d’hôte de votre serveur Exchange.
- **Attribut de nom d’utilisateur d’AAD** : il s’agit de l’attribut dans Active Directory (AD) ou Azure AD, qui doit être utilisé pour générer le nom d’utilisateur de ce profil de messagerie. Sélectionnez **Adresse SMTP principale**, comme user1@contoso.com ou **Nom d’utilisateur principal**, comme user1 ou user1@contoso.com.
- **Attribut d’adresse de messagerie d’AAD** : la façon dont l’adresse de messagerie de l’utilisateur est générée sur chaque appareil. Sélectionnez le **Nom d’utilisateur principal** pour utiliser le nom principal complet en tant qu’adresse de messagerie ou **nom d’utilisateur**.
- **Méthode d’authentification** : sélectionnez **Nom d’utilisateur et mot de passe** ou **Certificats** comme méthode d’authentification utilisée par le profil de messagerie.
    - Si vous avez sélectionné **Certificats**, sélectionnez un profil de certificat SCEP ou PKCS client que vous avez créé précédemment pour authentifier la connexion Exchange.
- **SSL** : utilisez la communication SSL (Secure Sockets Layer) pour envoyer et recevoir des e-mails, et communiquer avec le serveur Exchange.
- **Nombre d’e-mails à synchroniser** : sélectionnez le nombre de jours de courrier électronique à synchroniser ou sélectionnez **Illimité** pour synchroniser tous les messages disponibles.
- **Type de contenu à synchroniser** (Nine Work uniquement) : sélectionnez les types de contenu à synchroniser avec les appareils :
    - **Contacts**
    - **Calendrier**
    - **Tâches**
