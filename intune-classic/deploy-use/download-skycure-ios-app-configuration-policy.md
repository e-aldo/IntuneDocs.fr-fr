---
title: Télécharger la stratégie de configuration d’applications iOS Skycure
description: Téléchargez la stratégie de configuration d’applications iOS Skycure à utiliser avec l’application iOS Skycure déployée sur les utilisateurs finaux.
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f3cf3b2b18eeadf6779b7a8e96d75e569e6e3be
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Télécharger la stratégie de configuration d’applications iOS Skycure

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Avant de commencer

Vous devez vous connecter à la console de gestion Skycure pour effectuer les étapes suivantes.

> [!TIP] 
> Si vous utilisez Microsoft Internet Explorer 11 ou Edge, vous devrez peut-être ouvrir la console de gestion Skycure en mode privé.

## <a name="to-download-the-ios-app-configuration-policy"></a>Pour télécharger la stratégie de configuration d’applications iOS

1.  Accédez à la [console de gestion Skycure](https://aad.skycure.com).

2.  Entrez vos **informations d’identification d’administrateur Skycure**, puis cliquez sur **Continuer**.

    ![Connexion à la console de gestion Skycure](../media/mtp/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Le nom d’utilisateur de l’administrateur Skycure est un compte de messagerie qui doit être un compte d’utilisateur valide dans Azure Active Directory Skycure, sinon la connexion échouera. Skycure utilise Azure Active Directory pour authentifier le nom d’utilisateur de l’administrateur à l’aide d’une authentification unique Single Sign On (SSO).

3.  Accédez à **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choisissez **Microsoft Intune**, puis enregistrez votre sélection.

2.  Cliquez sur le lien **Integration setup files** et enregistrez le fichier \*.zip généré. Le fichier .zip contient le fichier **skycure\_configuration.plist**, qui sera utilisé pour créer des stratégies de configuration d’applications iOS dans le portail classique Intune.

![Fichiers d’installation de l’intégration Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Étapes suivantes

[Ajouter des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)
