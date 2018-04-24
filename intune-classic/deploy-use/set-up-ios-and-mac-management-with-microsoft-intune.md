---
title: Configurer la gestion iOS et MAC
description: Activez la gestion des appareils mobiles pour les appareils iOS, notamment iPad et iPhone, ainsi que les appareils Mac OS X avec Microsoft Intune.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 280efe7e7a5a1616ebab9abce7b7a5d78e321e7c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-ios-and-mac-device-management"></a>Configurer la gestion des appareils iOS et Mac

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune permet la gestion des appareils mobiles (MDM) pour les appareils iPad, iPhone et Mac OS, et permet aux utilisateurs d’accéder à la messagerie et aux applications de l’entreprise. Intune requiert un certificat APNS (Apple Push Notification Service) pour gérer les appareils iOS et Mac. Une fois le certificat ajouté à Intune, les utilisateurs peuvent installer l’application Portail d’entreprise pour inscrire leurs appareils, ou l’administrateur peut configurer la [gestion des appareils iOS d’entreprise](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Configurer Intune**<br>
    Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](prerequisites-for-enrollment.md#step-2-set-mdm-authority) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2.  **Obtenir une demande de signature de certificat**<br>
    En tant qu’administrateur, ouvrez la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **iOS et Mac OS X** &gt; **Télécharger un certificat APNs**, puis choisissez **Télécharger la demande de certificat APNs**. Enregistrez localement le fichier de demande de signature de certificat (.csr). Le fichier .csr est utilisé pour demander un certificat de relation d'approbation à partir du portail Apple Push Certificates.

    ![Boîte de dialogue Télécharger un certificat APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Obtenir un certificat du service Apple Push Notification**<br>
    Accédez au [portail Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) et connectez-vous avec votre ID Apple d’entreprise pour créer le certificat APNs à l’aide du fichier .csr. Après avoir choisi **Télécharger** sur le portail de certificat push d’Apple, vous recevrez un fichier .json qui ne peut pas être utilisé pour APNs. Terminez le téléchargement, revenez au portail de certificats push Apple pour obtenir des **Certificats pour serveurs tiers**, puis choisissez **Télécharger**.

    Téléchargez le certificat APNs (.pem) et enregistrez le fichier localement.

    > [!NOTE]
    > Chaque année, vous devez renouveler (et non remplacer) ce certificat APNs. Utilisez le même ID Apple pour vous connecter au portail Push Certificate d’Apple et renouveler le certificat, suivez les instructions figurant dans cette rubrique pour télécharger le certificat, puis chargez-le dans Intune.

4.  **Ajouter le certificat APNs à Intune**<br>
    Dans la [console d’administration Microsoft Intune](https://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **iOS et Mac OS X** &gt; **Télécharger un certificat APNs**, puis choisissez **Télécharger le certificat APNs**. Accédez au fichier de certificat (.pem), choisissez **Ouvrir**, puis entrez votre **ID Apple**. Avec le certificat APNs, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits.

5.  **Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise.**

    Pour obtenir des instructions sur l’inscription des utilisateurs finaux, consultez [Inscrire votre appareil iOS dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) et [Inscrire votre appareil Mac OS dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos). Le processus d’inscription indique aux utilisateurs ce qu’ils peuvent attendre, et ce que les administrateurs informatiques peuvent voir ou ne peuvent pas voir sur leurs appareils.

    Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :
    - [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](/intune/end-user-educate)
    - [Conseils destinés aux utilisateurs finaux pour les appareils iOS et Mac](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

Si votre entreprise ou organisation achète des appareils iOS pour les utilisateurs, ils peuvent également être inscrits pour être gérés en tant qu’[appareils iOS appartenant à l’entreprise](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription d’appareils auprès de Microsoft Intune](prerequisites-for-enrollment.md)
