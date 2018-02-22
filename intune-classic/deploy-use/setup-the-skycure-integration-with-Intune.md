---
title: "Configuration de l’intégration de Skycure avec Intune"
description: "Configurez l’intégration de Skycure avec Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93722f66-7641-4a3f-b1fb-3a0a58a36675
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c981d6fb927d29f0d450c5c7571933626897b4f2
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="set-up-the-skycure-integration-with-intune"></a>Configuration de l’intégration de Skycure avec Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Vous devez ajouter des applications Skycure à Azure AD pour disposer de fonctionnalités à authentification unique.

## <a name="before-you-begin"></a>Avant de commencer

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a>Compte Azure AD permettant d’intégrer Intune et Skycure

-   Assurez-vous de disposer du compte Azure AD correctement configuré dans la [console de gestion Skycure](https://aad.skycure.com) avant de démarrer le processus de configuration Skycure de base.

### <a name="full-integration-vs-read-only"></a>Intégration complète et Lecture seule

Skycure prend en charge deux modes d’intégration avec Intune :

-   **Intégration en lecture seule (configuration de base) :** répertorie uniquement les appareils à partir d’Azure Active Directory et les charge dans la console Skycure.
<br>
    -   Si les cases **Report the health and risk of devices to Intune** (Signaler l’intégrité et les risques des appareils à Intune) et **Also report security incidents to Intune** (Signaler également les incidents de sécurité à Intune) ne sont pas cochées dans la console de gestion Skycure, l’intégration s’effectue en lecture seule et par conséquent ne change jamais l’état d’un appareil (conforme ou non conforme) dans Intune.
<br></br>
-   **Intégration complète :** permet à Skycure de signaler les appareils à risques et les détails des incidents de sécurité à Intune, ce qui crée une communication bidirectionnelle entre les deux services de cloud.

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a>Comment les applications Skycure sont-elles utilisées avec Azure AD et Intune ?

-   **Application iOS :** permet aux utilisateurs finaux de se connecter à Azure AD à l’aide d’une application iOS.

-   **Application Android :** permet aux utilisateurs finaux de se connecter à Azure AD à l’aide d’une application Android.

-   **Application de gestion :** application Skycure Azure AD mutualisée qui permet la communication de service à service avec Intune.

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a>Pour configurer l’intégration en lecture seule entre Intune et Skycure

> [!IMPORTANT]
> Les informations d’identification de l’administrateur figurent dans un message électronique qui doit appartenir à un utilisateur valide dans Azure Active Directory Skycure, sinon la connexion échouera. Skycure utilise Azure Active Directory pour authentifier ses administrateurs à l’aide d’une authentification unique Single Sign On (SSO).

1.  Accédez à la [console de gestion Skycure](https://aad.skycure.com).

2.  Entrez vos **informations d’identification d’administrateur Skycure**, puis cliquez sur **Continuer**.

3.  Sélectionnez **Paramètres**, puis choisissez **Installation de base** sous **Intégration à Intune**.

4.  Dans la zone **App iOS**, cliquez sur **Ajouter à Active Directory**.

    ![Application iOS sur la console de gestion Skycure](../media/mtp/skycure-setup-1.png)

5.  Lorsque la page de connexion s’affiche, entrez vos informations d’identification Intune, puis cliquez sur **Accepter**.

    ![Invite de connexion Intune à l’application iOS](../media/mtp/skycure-setup-2.png)

6.  Une fois l’application ajoutée dans Azure AD, vous pouvez voir une indication que l’application a été ajoutée dans Azure AD sur la console de gestion Skycure.

    ![Écran de finalisation de l’application iOS](../media/mtp/skycure-setup-3.png)

> [!NOTE]
> Répétez ce processus pour les applications **Skycure Android** et les applications de **gestion**.

### <a name="add-an-azure-ad-security-group-into-skycure"></a>Ajouter un groupe de sécurité Azure AD dans Skycure

Vous devez ajouter un groupe de sécurité Azure AD qui contient tous les appareils Skycure en cours d’exécution.

1.  Entrez et sélectionnez tous les groupes de sécurité des appareils qui exécutent Skycure, puis cliquez sur **Appliquer les modifications**.

    ![Configurer la console de gestion Skycure du groupe de sécurité](../media/mtp/skycure-setup-4.png)

Skycure synchronise les appareils exécutant le service Mobile Threat Defense avec les groupes de sécurité Azure AD.

![Configuration du groupe de sécurité terminée sur la console de gestion Skycure](../media/mtp/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a>Configurer l’intégration complète entre Intune et Skycure

1.  Accédez à la [console de gestion Skycure](https://aad.skycure.com).

2.  Entrez vos **informations d’identification d’administrateur Skycure**, puis cliquez sur **Continuer**.

3.  Accédez à **Paramètres**, puis choisissez **Intégration complète** sous **Intégration Intune**.

4.  Vérifiez les paramètres suivants :

    a.  Signalez l’intégrité et les risques d’appareil à Intune

    b.  Signalez également les incidents de sécurité à Intune

5.  Cliquez sur **Appliquer les modifications**.

    ![Intégration complète Skycure terminée](../media/mtp/skycure-setup-6.png)

## <a name="next-steps"></a>Étapes suivantes

[Activer Skycure Mobile Threat Defense dans Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)
