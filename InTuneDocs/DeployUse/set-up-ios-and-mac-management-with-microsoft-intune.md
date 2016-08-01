---
title: Configurer la gestion iOS et Mac | Microsoft Intune
description: "Activez la gestion des appareils mobiles pour les appareils iOS, notamment iPad et iPhone, ainsi que les appareils Mac OS X avec Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 8a41c4c4f0ab4b4864fe366a2852046693b6baee


---

# Configurer la gestion des appareils iOS et Mac
Utilisez la gestion des appareils mobiles Intune des iPad, iPhone et autres appareils Mac OS X et gérez l’accès à la messagerie et aux applications de l’entreprise. Intune requiert un certificat APNS (Apple Push Notification Service) pour gérer les appareils iOS et Mac. Une fois le certificat ajouté à Intune, les utilisateurs peuvent installer l’application Portail d’entreprise pour inscrire leurs appareils, ou l’administrateur peut configurer la [gestion des appareils iOS d’entreprise](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

1.  **Configurer Intune**<br>
    Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2.  **Obtenir une demande de signature de certificat**<br>
    En tant qu’administrateur, ouvrez la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **iOS et Mac OS X** &gt; **Télécharger un certificat APNs**, puis cliquez sur **Télécharger la demande de certificat APNs**. Enregistrez localement le fichier de demande de signature de certificat (.csr). Le fichier .csr est utilisé pour demander un certificat de relation d'approbation à partir du portail Apple Push Certificates.

    ![Boîte de dialogue Télécharger un certificat APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  **Obtenir un certificat des services de notification Push Apple**<br>
    Accédez au [portail Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) et connectez-vous avec votre ID Apple d’entreprise pour créer le certificat APNs à l’aide du fichier .csr. Après avoir cliqué sur **Télécharger** sur le portail de certificat push d’Apple, vous recevrez un fichier .json qui ne peut pas être utilisé pour APNs. Terminez le téléchargement, revenez au portail de certificats push Apple pour obtenir des **Certificats pour serveurs tiers** et cliquez sur **Télécharger**.

    Téléchargez le certificat APNs (.pem) et enregistrez le fichier localement. Cet ID Apple doit être utilisé ultérieurement pour renouveler votre certificat APNs.

4.  **Ajouter le certificat APNs à Intune**<br>
    Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), accédez à **Administration** &gt; **Gestion des appareils mobiles** &gt; **iOS et Mac OS X** &gt; **Télécharger un certificat APNs**, puis cliquez sur **Télécharger le certificat APNs**. **Accédez** au fichier de certificat (.pem) et cliquez sur **Ouvrir** , puis entrez votre **ID Apple**. Avec le certificat APNs, Intune peut inscrire et gérer des appareils iOS en envoyant la stratégie aux appareils mobiles inscrits.

5.  **Indiquer aux utilisateurs comment accéder aux ressources d’entreprise avec le portail d’entreprise**<br>
    Vos utilisateurs doivent savoir comment inscrire leurs appareils et connaître les principes de la gestion d'appareils. [Ce qu'il faut dire à vos utilisateurs finaux concernant l'utilisation de Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)

Si votre entreprise ou organisation achète des appareils iOS pour les utilisateurs, ils peuvent également être inscrits pour être gérés en tant qu’[appareils iOS appartenant à l’entreprise](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).

### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


