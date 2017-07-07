---
title: "Ajouter des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS"
description: "Ajouter des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS dans la console classique Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 425b86e92281bb6e3657a6c806be269ccae94311
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/01/2017
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Ajouter des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous devez utiliser Intune pour ajouter et déployer les applications Skycure afin que les utilisateurs finaux puissent recevoir des notifications lorsqu’une menace est identifiée sur leurs appareils mobiles et recevoir des conseils pour contrer les menaces.

En outre, vous avez besoin de [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) pour permettre aux utilisateurs de faire vérifier leur identité par Azure AD, et la stratégie de configuration d’applications iOS qui indique l’application iOS Skycure pour utiliser Intune et Azure AD Single Sign On (SSO). Les utilisateurs n’ont donc pas besoin de saisir le nom d’utilisateur et le mot de passe chaque fois qu’ils se connectent à l’application Skycure.

## <a name="before-you-begin"></a>Avant de commencer

-   Les étapes ci-dessous doivent être effectuées dans la [console classique Intune](https://manage.microsoft.com/).

-   Utilisez le même compte Azure AD configuré précédemment dans la console de gestion Skycure, qui doit être le même compte utilisé pour vous connecter à la console classique Intune.

-   Vous devez disposer du fichier d’intégration Skycure prêt à l’emploi. Il s’agit du fichier .zip téléchargé précédemment à partir de la console de gestion Skycure, qui contient le fichier **skycure\_configuration.plist** avec les paramètres de stratégie de configuration d’applications iOS.

-   Vérifiez que vous êtes familiarisé avec ce processus :

    -   [Ajout d’une application dans Intune](/intune-classic/deploy-use/add-apps).

    -   [Ajout d’une stratégie de configuration d’applications iOS dans Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-the-skycure-app-for-android"></a>Pour ajouter l’application Skycure pour Android

1.  Dans la console classique Intune, choisissez **Applications**&gt;**Ajouter des applications** pour démarrer l’éditeur de logiciel Intune, puis cliquez sur **Suivant**.

2.  Sur la page **Installation du logiciel**, choisissez **Lien externe**, puis collez l[’URL de l’application Skycure pour Android](https://play.google.com/store/apps/details?id=com.skycure.skycure) sous **Spécifiez l’URL**.

    ![Spécifier l’URL dans l’éditeur de logiciel Intune](../media/mtp/skycure-add-apps-1.png)

3.  Sur la page **Description du logiciel**, entrez l**’éditeur**, le **nom** et la **description**, sélectionnez l’option **Affiche comme application proposée et la met en avant dans le portail d'entreprise**, puis cliquez sur **Suivant**.

    ![Description du logiciel dans l’éditeur de logiciel Intune](../media/mtp/skycure-add-apps-2.png)

4.  Cliquez sur **Télécharger**, puis sur **Fermer**.

## <a name="to-add-the-skycure-app-for-ios"></a>Pour ajouter l’application Skycure pour iOS

1.  Dans la console classique Intune, choisissez **Applications**&gt;**Ajouter des applications** pour démarrer l’éditeur de logiciel Intune, puis cliquez sur **Suivant**.

2.  Sur la page **Installation du logiciel**, choisissez **Application iOS gérée à partir de l'App Store**, puis collez l[’URL de l’application Skycure pour iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) sous **Spécifiez l’URL**.

    ![Application iOS gérée dans l’éditeur de logiciel Intune](../media/mtp/skycure-add-apps-3.png)

3.  Sur la page **Description du logiciel**, entrez l**’éditeur**, le **nom** et la **description**, sélectionnez l’option **Affiche comme application proposée et la met en avant dans le portail d'entreprise**, puis cliquez sur **Suivant**.

    ![Options de l’éditeur de logiciel Intune](../media/mtp/skycure-add-apps-4.png)

4.  Sur la page **Configuration requise** , sélectionnez l’option **N'importe lequel** sous **Type d'appareil mobile**, puis cliquez sur **Suivant**.

5.  Cliquez sur **Télécharger**, puis sur **Fermer**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>Pour ajouter l’application Microsoft Authenticator pour iOS

1.  Dans la console classique Intune, choisissez **Applications**&gt;**Ajouter des applications** pour démarrer l’éditeur de logiciel Intune, puis cliquez sur **Suivant**.

2.  Sur la page **Installation du logiciel**, choisissez **Application iOS gérée à partir de l'App Store**, puis collez l[’URL de l’application Microsoft Authenticator pour iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) sous **Spécifiez l’URL**.

    ![Éditeur de logiciel Intune - Application iOS gérée 2](../media/mtp/skycure-add-apps-5.png)

3.  Sur la page **Description du logiciel**, entrez l**’éditeur**, le **nom** et la **description**, sélectionnez l’option **Affiche comme application proposée et la met en avant dans le portail d'entreprise**, puis cliquez sur **Suivant**.

    ![Éditeur de logiciel Intune - Application iOS gérée 3](../media/mtp/skycure-add-apps-6.png)

4.  Sur la page **Configuration requise** , sélectionnez l’option **N'importe lequel** sous **Type d'appareil mobile**, puis cliquez sur **Suivant**.

5.  Cliquez sur **Télécharger**, puis sur **Fermer**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Pour ajouter la stratégie de configuration d’applications iOS Skycure

1.  Dans la console classique Intune, choisissez **Stratégie** &gt; **Vue d’ensemble &gt; Ajouter une stratégie**.

2.  Dans la liste des stratégies, développez **iOS**, choisissez **Stratégie de configuration d'appareils mobiles (iOS 8.0 et ultérieur)**, puis choisissez **Créer une stratégie**.

    ![Stratégie de configuration d’applications iOS](../media/mtp/skycure-add-apps-7.png)

3.  Dans la section **Général** de la page **Créer une stratégie**, fournissez un nom et éventuellement une description de la stratégie de configuration d’applications iOS.

    a.  Ouvrez le fichier **skycure\_configuration.plist** à l’aide d’un éditeur de texte comme le bloc-notes, copiez le contenu et collez-le dans la zone **Stratégie de configuration d’applications mobiles**, choisissez **Valider**, puis **Enregistrer la stratégie**.

       ![Stratégie de configuration d’applications iOS 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Étapes suivantes

[Déployer des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration d’application iOS](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
