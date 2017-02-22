---
title: "Inscrire des appareils Android dans Intune | Version préliminaire d’Intune Azure | Microsoft Docs"
description: "Version préliminaire d’Intune Azure : découvrez comment inscrire des appareils Android dans la version préliminaire d’Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/16/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 990062ecf03a117dad74eb71e3f40abb79f22be6
ms.openlocfilehash: edd6303f3bb05dfff758cbb7d4bd08e21f083998


---

# <a name="enroll-android-devices"></a>Inscrire des appareils Android

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

En tant qu’administrateur Intune, vous pouvez activer la gestion des appareils Android, notamment les appareils Samsung Knox Standard, à partir du portail d’entreprise. Les utilisateurs peuvent alors inscrire leurs appareils à l’aide de l’application Portail d’entreprise disponible sur Google Play.

## <a name="prerequisite"></a>Composant requis

Vous devez définir l’autorité MDM sur **Microsoft Intune** pour préparer la gestion des appareils mobiles. Consultez la page [Configurer l’autorité MDM](set-mdm-authority.md) pour obtenir des instructions. Cet élément ne se définit qu’une seule fois, lorsque vous configurez pour la première fois Intune pour la gestion des appareils mobiles, donc vous l’avez peut-être déjà défini. 

## <a name="set-up-android-enrollment"></a>Configurer l’inscription Android

Par défaut, Intune est configuré pour autoriser l’inscription des appareils Android et Samsung Knox Standard. 

Pour afficher le paramètre permettant d’autoriser ou de bloquer l’inscription d’appareils Android, accédez au panneau Intune dans le portail Azure, puis choisissez **Inscription** > **Restrictions d’inscription**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise

Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Android dans Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-android). Le processus d’inscription indique aux utilisateurs ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent voir ou ne peuvent pas voir sur leurs appareils.

Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :

- [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Utilisation de votre appareil Android avec Intune](https://docs.microsoft.com/intune/enduser/using-your-android-device-with-intune)


<!--HONumber=Feb17_HO1-->


