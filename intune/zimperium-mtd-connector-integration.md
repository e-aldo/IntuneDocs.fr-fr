---
title: "Intégrer Zimperium à Intune"
titleSuffix: Intune on Azure
description: "Intégrer Intune à Zimperium"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-zimperium-with-intune"></a>Intégrer Zimperium à Intune

Vous devez suivre les étapes ci-dessous pour intégrer la solution Zimperium Mobile Threat Defense à Intune.

## <a name="before-you-begin"></a>Avant de commencer

> [!NOTE]
> Les étapes suivantes doivent être exécutées dans la [console Zimperium MTD](https://staging2-console.zimperium.com).

Avant d’entamer le processus d’intégration de Zimperium à Intune, veillez à disposer des éléments suivants :

-   Abonnement Microsoft Intune

-   Informations d’identification d’administrateur Azure Active Directory pour accorder les autorisations suivantes :

    -   Connexion et lecture de profil utilisateur

    -   Accès à l’annuaire en tant qu’utilisateur connecté

    -   Lecture des données de l’annuaire

    -   Envoi des informations d’appareil à Intune

-   Informations d’identification d’administrateur pour accéder à la console Zimperium MTD.

### <a name="zimperium-app-authorization"></a>Autorisation de l’application Zimperium

Le processus d’autorisation de l’application Zimperium est constitué des étapes suivantes :

-   Autoriser le service Zimperium à communiquer à Intune des informations relatives à l’état d’intégrité des appareils.

-   Synchroniser Zimperium avec l’appartenance au groupe d’inscriptions Azure AD pour remplir sa base de données d’appareils.

-   Autoriser la console d’administration Zimperium à utiliser l’authentification unique (SSO) Azure AD.

-   Autoriser l’application Zimperium à se connecter en utilisant l’authentification unique Azure AD.

## <a name="to-set-up-zimperium-integration"></a>Pour configurer l’intégration de Zimperium

1.  Accédez à la [console Zimperium MTD](https://staging2-console.zimperium.com) et connectez-vous avec vos informations d’identification.

2.  Choisissez **Management** (Administration) dans le menu de gauche.

3.  Choisissez l’onglet **MDM settings** (Paramètres MDM).

4.  Choisissez **Add MDM** (Ajouter MDM), puis sélectionnez **Microsoft Intune** dans la liste **MDM provider** (Fournisseur MDM).

5.  Après avoir défini Microsoft Intune comme service MDM, la fenêtre **Microsoft Intune Configuration** (Configuration de Microsoft Intune) s’affiche. Choisissez **Ajouter Azure Active Directory** pour chaque option : applications **Zimperium zConsole**, **zIPS iOS et Android** pour autoriser Zimperium à communiquer avec Intune et Azure AD via l’authentification unique Azure AD.

    > [!IMPORTANT]
    > Vous devez ajouter les applications zConsole Zimperium, zIPS iOS et Android pour terminer le processus d’intégration à Intune.

6.  Choisissez **Accepter** pour autoriser l’application Zimperium à communiquer avec Intune et Azure Active Directory.

7.  Une fois que vous avez ajouté les applications **Zimperium zConsole** et **zIPS iOS et Android** à Azure AD, vous devez ajouter les groupes de sécurité Azure AD afin que Zimperium puisse synchroniser le groupe de sécurité Azure AD avec son service.

8.  Choisissez **Terminer** pour enregistrer la configuration et démarrer la première synchronisation de groupe de sécurité Azure AD.

## <a name="next-steps"></a>Étapes suivantes

-   [Configurer les applications Zimperium](mtd-apps-ios-app-configuration-policy-add-assign.md)
