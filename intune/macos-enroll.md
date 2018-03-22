---
title: Configurer l’inscription des appareils macOS
titlesuffix: Microsoft Intune
description: Découvrez comment configurer l’inscription des appareils macOS dans Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c1fb846dc65ee14315edf7b9ba15e0e24998a3a2
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="set-up-enrollment-for-macos-devices-in-intune"></a>Configurer l’inscription des appareils macOS dans Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune vous permet de gérer les appareils Mac OS. Pour activer la gestion des appareils, vos utilisateurs doivent inscrire leurs appareils en accédant au [site web Portail d’entreprise](http://portal.manage.microsoft.com), puis en suivant les invites. Une fois que les appareils Mac OS sont gérés, vous pouvez [créer des paramètres personnalisés pour les appareils Mac OS](custom-settings-macos.md). D’autres fonctionnalités seront bientôt disponibles.

## <a name="prerequisites"></a>Prérequis

Avant de configurer l’inscription des appareils macOS, effectuez les prérequis suivants :

- [Configurer des domaines](custom-domain-name-configure.md)
- [Configurer l’autorité MDM](mdm-authority-set.md)
- [Créer des groupes](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurer le portail d’entreprise](company-portal-app.md)
- Attribuer des licences utilisateur dans le [portail Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenir un certificat Push MDM Apple](apple-mdm-push-certificate-get.md)

## <a name="user-owned-ios-devices-byod"></a>Appareils iOS de l’utilisateur (BYOD)

Vous pouvez laisser les utilisateurs inscrire leurs appareils personnels pour la gestion Intune, approche communément appelée « BYOD » (Bring Your Own Device). Une fois que vous avez répondu aux prérequis et affecté des licences aux utilisateurs, ces derniers peuvent télécharger l’application Portail d’entreprise macOS à partir de l’App Store et suivre les instructions d’inscription dans l’application.

## <a name="company-owned-ios-devices"></a>Appareils d’entreprise iOS
Pour les organisations qui achètent des appareils pour leurs utilisateurs, Intune prend en charge l’inscription des appareils macOS d’entreprise avec un compte du [gestionnaire d’inscription d’appareil](device-enrollment-manager-enroll.md).

## <a name="set-up-macos-enrollment"></a>Configurer l’inscription macOS

Par défaut, Intune autorise déjà l’inscription des appareils Mac OS.

Pour empêcher l’inscription des appareils Mac OS, consultez [Définir des restrictions de type d’appareil](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise

Indiquez à vos utilisateurs finaux d’accéder au [site web Portail d’entreprise](https://portal.manage.microsoft.com) et de suivre les invites pour inscrire leurs appareils. Vous pouvez également leur envoyer un lien vers les étapes d’inscription en ligne : [Inscrire votre appareil Mac OS dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :

- [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](end-user-educate.md)
- [Utiliser un appareil macOS avec Intune](/intune-user-help/using-your-macos-device-with-intune)

## <a name="enroll-virtual-macos-machines-for-testing"></a>Inscrire des machines virtuelles macOS à des fins de test

> [!NOTE]
> Les machines virtuelles macOS sont uniquement prises en charge à des fins de test. Vous ne devez pas utiliser des machines virtuelles macOS en tant qu’appareils de production pour vos utilisateurs finaux. 

Vous pouvez inscrire des machines virtuelles macOS à des fins de test à l’aide de Parallels Desktop ou de VMware Fusion. 

Pour Parallels Desktop, vous avez besoin de définir le type de matériel et le numéro de série des machines virtuelles pour qu’Intune puisse les reconnaître. Suivez les instructions de Parallels pour [définir le type de matériel](http://kb.parallels.com/123594) et le [numéro de série](http://kb.parallels.com/123455) afin de configurer les paramètres nécessaires au test. Nous vous recommandons de faire correspondre le type de matériel de l’appareil qui exécute les machines virtuelles à celui des machines virtuelles que vous créez. Vous pouvez trouver ce type de matériel dans le **menu Pomme** > **À propos de ce Mac** > **Rapport système** > **Identifiant du modèle**. 

Pour VMware Fusion, vous devez [modifier le fichier .vmx](https://kb.vmware.com/s/article/1014782) pour définir le modèle matériel et le numéro de série de la machine virtuelle. Nous vous recommandons de faire correspondre le type de matériel de l’appareil qui exécute les machines virtuelles à celui des machines virtuelles que vous créez. Vous pouvez trouver ce type de matériel dans le **menu Pomme** > **À propos de ce Mac** > **Rapport système** > **Identifiant du modèle**. 
