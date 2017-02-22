---
title: "Inscrire des appareils macOS dans Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment inscrire des appareils macOS dans la version préliminaire d’Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Inscrire des appareils macOS dans la version préliminaire d’Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

En tant qu’administrateur Intune, vous pouvez gérer les appareils macOS. Par défaut, le portail Azure permet aux utilisateurs d’inscrire leurs appareils macOS. Il vous suffit d’indiquer à vos utilisateurs d’accéder au [site web Portail d’entreprise](http://portal.manage.microsoft.com) et d’inscrire leur appareil macOS. 

## <a name="prerequisites"></a>Conditions préalables

Avant de configurer l’inscription des appareils macOS, effectuez les préparatifs suivants :

- [Configurer des domaines](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Configurer l’autorité MDM](set-mdm-authority.md)
- [Créer des groupes](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurer le portail d’entreprise](/intune-azure/manage-apps/company-portal-app.md)
- Attribuer des licences utilisateur dans le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenir un certificat Push MDM Apple](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Configurer l’inscription macOS

Par défaut, Intune est déjà configuré pour autoriser l’inscription des appareils macOS. 

Pour afficher le paramètre permettant d’autoriser ou de bloquer l’inscription d’appareils macOS, accédez au panneau Intune dans le portail Azure, puis choisissez **Inscription** > **Restrictions d’inscription**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise

Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire votre appareil macOS dans Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). Le processus d’inscription indique aux utilisateurs ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent voir ou ne peuvent pas voir sur leurs appareils.

Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :

- [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Utilisation de votre appareil iOS ou MacOS avec Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


