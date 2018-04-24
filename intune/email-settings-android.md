---
title: Paramètres de messagerie Microsoft Intune pour les appareils exécutant Android et Android for Work
titleSuffix: ''
description: Découvrez les paramètres Microsoft Intune que vous pouvez utiliser pour configurer les paramètres de messagerie sur des appareils exécutant Android et Android for Work.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 10bea7ace3fe03db66fa6f8a83a94679dfdc071c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="email-profile-settings-in-microsoft-intune-for-devices-running-android-and-android-for-work"></a>Paramètres de profil de messagerie dans Microsoft Intune pour les appareils exécutant Android et Android for Work

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Cet article affiche les paramètres de profil de messagerie que vous pouvez configurer pour vos appareils exécutant Android.

En tant qu’administrateur Intune, vous pouvez créer et affecter des paramètres de messagerie aux appareils Android suivants :
- [Android Samsung Knox Standard](#android-samsung-knox-standard-email-settings)
- [Android for Work](#android-for-work-email-settings)

## <a name="android-samsung-knox-standard-email-settings"></a>Paramètres de messagerie Android Samsung Knox Standard
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
