---
title: Configurer Skycure pour utiliser Azure Active Directory Single Sign On | Microsoft Docs
description: Configurer Skycure pour utiliser Azure Active Directory Single Sign On (SSO)
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: bf4cf8441a0ff53abf3f7830f0cdd955a4317fb0
ms.contentlocale: fr-fr
ms.lasthandoff: 05/23/2017


---

# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Configurer Skycure pour utiliser Azure Active Directory Single Sign On (SSO)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure AD SSO est utilisée lorsque vous intégrez Intune à Skycure. Voici les principaux avantages :

-   Les **administrateurs** peuvent utiliser les mêmes informations d’identification sans avoir à les saisir chaque fois qu’ils ouvrent et ferment une session à partir des portails Microsoft (Intune, Azure) et de la console de gestion Skycure.

-   **Les utilisateurs finaux** peuvent utiliser les mêmes informations d’identification Azure AD sans avoir à les saisir chaque fois qu’ils ouvrent et ferment une session à partir des applications Skycure.

Voici les étapes permettant d’intégrer Skycure à Azure Active Directory Single Sign On (SSO).

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>Pour récupérer l’ID du locataire Azure Active Directory

Vous devez récupérer l’ID du locataire Azure AD.

1.  Accédez au [portail Azure](https://portal.azure.com/) et connectez-vous à l’aide de vos informations d’identification.

2.  Dans le **tableau de bord,** choisissez **Azure Active Directory**.

![Tableau de bord Azure AD](../media/mtp/skycure-sso-1.png)

1.  Le panneau **Azure Active Directory** s’ouvre, choisissez **Propriétés**.

![Panneau Propriétés Azure AD](../media/mtp/skycure-sso-2.png)

1.  Cliquez sur l’**icône Copier** sous **ID du répertoire locataire** dans le panneau **Propriétés Azure Active Directory**.

> Collez la valeur d’ID de répertoire copiée dans un fichier texte afin de pouvoir l’utiliser ultérieurement. La valeur d’ID de répertoire sera requise plus tard dans le processus d’intégration de Skycure et Intune.

![Tableau de bord Azure AD](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Autoriser Skycure à communiquer avec Azure Active Directory

1.  Entrez l’URL ci-dessous dans votre navigateur. Au lieu de **DIRECTORY_ID**, entrez votre ID de locataire Active Directory Azure copié précédemment dans le fichier texte.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Vous devez vous connecter à l’aide de vos informations d’identification Azure Active Directory. Cliquez sur **Accepter** pour continuer.

![Page de connexion Azure AD Directory](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Créer un groupe de sécurité Azure AD pour Skycure (facultatif)

Vous pouvez créer un groupe d’utilisateur dédié qui contient des utilisateurs exécutant Skycure (par exemple, les utilisateurs Skycure). Cela peut être utile lors de l’analyse de l’activité Skycure via les rapports.

-   En savoir plus sur la [création d’un groupe et l’ajout de membres dans Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Vous pouvez également utiliser un groupe de sécurité Azure AD existant.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Configurer le compte Azure AD pour intégrer Intune à Skycure

1.  Dans la [console de gestion Skycure](https://aad.skycure.com/), entrez l’ID du locataire Active Directory Azure précédemment enregistré dans le fichier texte.

![Camp ID du locataire Azure AD dans la console de gestion Skycure](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> Skycure vérifie si l’ID du locataire Azure AD existe en interrogeant Azure AD. Si Skycure détecte cet ID, l’administrateur peut procéder à l’étape suivante : la configuration de base.

## <a name="next-steps"></a>Étapes suivantes

[Télécharger la stratégie de configuration d’application iOS Skycure](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

