---
title: Configurer la gestion de Windows 10 Mobile et Windows Phone avec Microsoft Intune | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c5d1b53f09ce2f475cd934e36ddb19d019737431
ms.openlocfilehash: e67a5be851b68d87a4cdda871824cf0ecb14579e


---


# Configurer la gestion de Windows 10 Mobile et Windows Phone avec Microsoft Intune
Avant de pouvoir gérer des appareils mobiles Windows 10 ou Windows Phone avec Microsoft Intune, ceux-ci doivent être en mesure de communiquer avec Intune. Pour simplifier cela, vous pouvez créer un enregistrement DNS pour que les utilisateurs n’aient pas à entrer l’adresse du serveur. La procédure ci-dessous décrit comment simplifier l’inscription pour les utilisateurs.  

Dans la plupart des cas, les utilisateurs peuvent installer l’application Portail d’entreprise à partir de Windows Store. Si vous gérez des appareils Windows Phone 8.0 ou si vous devez déployer le Portail d’entreprise sur des appareils Windows Phone, vous devez également télécharger et signer l’application Portail d’entreprise. Consultez [Configurer la gestion de Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md).

1.  **Configurer Intune** Si vous ne l’avez pas encore fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2.  **Définir un alias DNS pour l'adresse du serveur d'inscription** (facultatif)

    La création d’un alias DNS (type d’enregistrement CNAME) simplifie l’inscription des appareils pour les utilisateurs. Si vous ne créez pas un alias DNS, les utilisateurs doivent

  1.  Créez des enregistrements de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers manage.microsoft.com. S’il existe plusieurs domaines vérifiés, créez un enregistrement CNAME pour chaque domaine. Ces enregistrements doivent contenir les informations suivantes :

      |TYPE|Nom d'hôte|Pointe vers|TTL|
      |--------|-------------|-------------|-------|
      |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
      |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 heure|

      La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

      **EnterpriseEnrollment-s.manage.microsoft.com** : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’adresse de messagerie.

      **EnterpriseRegistration.windows.net** : prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

    2.  Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), cliquez sur **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows Phone**.

      ![Boîte de dialogue Configurer la gestion des appareils mobiles pour Windows](../media/windows-device-enrollment.png)

    3.  Tapez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis cliquez sur **Auto-détection de test**.



Aucun travail supplémentaire n’est requis sauf si vous déployez le Portail d’entreprise sur les appareils.  Les étapes 2 et 3 dans la console d’administration peuvent être ignorées en toute sécurité.



<!--HONumber=Jun16_HO4-->


