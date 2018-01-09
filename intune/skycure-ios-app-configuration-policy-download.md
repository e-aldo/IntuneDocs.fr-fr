---
title: "Télécharger la stratégie de configuration d’application iOS Skycure à utiliser avec Intune"
titlesuffix: Azure portal
description: "Téléchargez la stratégie de configuration d’application iOS Skycure à utiliser avec Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cbf26b44725f1fa08fbc6766f0560fe91d63d6ca
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/30/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Télécharger la stratégie de configuration d’applications iOS Skycure

## <a name="before-you-begin"></a>Avant de commencer

Vous devez vous connecter à la console de gestion Skycure pour effectuer les étapes suivantes.

> [!TIP] 
> Si vous utilisez Microsoft Internet Explorer 11 ou Edge, vous devrez peut-être ouvrir la console de gestion Skycure en mode privé.

## <a name="to-download-the-ios-app-configuration-policy"></a>Pour télécharger la stratégie de configuration d’applications iOS

1.  Accédez à la [console de gestion Skycure](https://aad.skycure.com).

2.  Entrez vos **informations d’identification d’administrateur Skycure**, puis cliquez sur **Continuer**.

    ![Connexion à la console de gestion Skycure](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Le nom d’utilisateur de l’administrateur Skycure est un compte de messagerie qui doit être un compte d’utilisateur valide dans Azure Active Directory Skycure, sinon la connexion échouera. Skycure utilise Azure Active Directory pour authentifier le nom d’utilisateur de l’administrateur à l’aide d’une authentification unique Single Sign On (SSO).

3.  Accédez à **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choisissez **Microsoft Intune**, puis enregistrez votre sélection.

4.  Cliquez sur le lien **Integration setup files** et enregistrez le fichier \*.zip généré. Le fichier .zip contient le fichier **skycure\_configuration.plist**, qui sera utilisé pour créer des stratégies de configuration d’applications iOS dans le portail classique Intune.

![Fichiers d’installation de l’intégration Skycure](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Étapes suivantes

[Ajouter et affecter des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS](mtd-apps-ios-app-configuration-policy-add-assign.md)
