---
title: "Télécharger la stratégie de configuration d’application iOS Skycure | Microsoft Docs"
description: "Téléchargez la stratégie de configuration d’applications iOS Skycure à utiliser avec l’application iOS Skycure déployée sur les utilisateurs finaux."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d211b876-4d3a-473c-999f-843c0a16cd22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: a8e46960a5d469093052148eb457140b3c235d3a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="download-skycure-ios-app-configuration-policy"></a>Télécharger la stratégie de configuration d’applications iOS Skycure

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

##<a name="before-you-begin"></a>Avant de commencer

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

2.  Cliquez sur le lien **Integration setup files** et enregistrez le fichier \*.zip généré. Le fichier .zip contient le fichier **skycure\_configuration.plist**, qui sera utilisé pour créer des stratégies de configuration d’applications iOS dans la console classique Intune.

![Fichiers d’installation de l’intégration Skycure](../media/mtp/skycure-ios-app-2.png)

## <a name="next-steps"></a>Étapes suivantes

[Ajouter des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

