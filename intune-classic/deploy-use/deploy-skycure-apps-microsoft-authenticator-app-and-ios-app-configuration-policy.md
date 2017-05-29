---
title: "Déployer des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS | Microsoft Docs"
description: "Déployer des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration iOS dans la console classique Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 19c8ca7bbfe19649585d63ce2c0c96a8f57b3739
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Déployer des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration d’application iOS

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Avant de commencer

-   Les étapes ci-dessous doivent être effectuées dans la [console classique Intune](https://manage.microsoft.com/).

-   Utilisez le même compte Azure AD configuré précédemment dans la console de gestion Skycure, qui doit être le même compte utilisé pour vous connecter à la console classique Intune.

-   Vérifiez que vous êtes familiarisé avec ce processus :

    -   [Déploiement d’une application avec Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Déploiement d’une stratégie de configuration d’application iOS](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Pour déployer des applications Skycure, l’application Microsoft Authenticator et une stratégie de configuration d’application iOS

1.  Dans la console classique Intune, choisissez **Applications** &gt; **Applications** pour afficher la liste des applications que vous pouvez gérer.

2.  Sélectionnez les applications suivantes :

    a.  Microsoft Authenticator

    b.  Application Skycure pour Android

    c.  Application Skycure pour iOS

       ![Toutes les applications de la console classique Intune à déployer](../media/mtp/skycure-deploy-app-1.png)

3.  Choisissez **Gérer les déploiements,** sélectionnez le groupe de sécurité Azure AD qui contient les utilisateurs Skycure, puis cliquez sur **Suivant**.

4.  Sur la page **Action de déploiement** , sélectionnez l’option **installation requise** dans la liste déroulante **Approbation**, puis cliquez sur **Suivant**.

    ![Action de déploiement dans la console classique Intune](../media/mtp/skycure-deploy-app-2.png)

5.  Sur la page **Profil VPN**, sélectionnez l’option **Aucune** dans la liste déroulante **Stratégie VPN**, puis cliquez sur **Suivant**.

6.  Sur la page **Configuration des applications mobiles**, sélectionnez la stratégie de configuration d’application iOS créée précédemment dans la liste déroulante **Stratégie de configuration des applications**, puis cliquez **Terminer**.

    ![Configuration des applications mobiles dans la console classique Intune](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Étapes suivantes

[Configuration de l’intégration de Skycure avec Intune](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

