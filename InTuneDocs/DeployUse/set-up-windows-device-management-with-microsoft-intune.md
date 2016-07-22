---
title: Configurer la gestion des appareils Windows avec Microsoft Intune | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6951ccdb0e37489217ef939f0cbf6fc1133a6d3c
ms.openlocfilehash: c18445385e8361cf01948b583f08e992658a8762


---

# Configurer la gestion des appareils Windows
Avec Intune, vous pouvez activer l’inscription d’appareils personnels (dits « BYOD ») pour permettre aux ordinateurs Windows d’accéder à la messagerie et aux applications d’entreprise. Utilisé avec Azure Active Directory, il permet également, de manière rapide et sans intervention, de gérer de nouveaux appareils Windows 10, qui peuvent alors accéder aux ressources d’entreprise sans avoir à créer une nouvelle image de l’ordinateur. Une fois inscrits, les utilisateurs peuvent se connecter et leurs appareils peuvent être ciblés par la stratégie, les applications et les paramètres à l’aide de la console d’administration Intune. Vous pouvez également [Configurer la gestion de Windows Phone avec Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) ou [gérer des ordinateurs avec le logiciel client Intune](manage-windows-pcs-with-microsoft-intune.md) en utilisant le client Intune.

La création d’un enregistrement CNAME DNS permet aux utilisateurs de se connecter et de s’inscrire à Intune sans saisir un nom de serveur.

### Configurer la gestion des appareils Windows

  1.  Créez un enregistrement de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. S’il existe plusieurs domaines vérifiés, créez un enregistrement CNAME pour chaque domaine. Ces enregistrements doivent contenir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 heure|

    La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

    **EnterpriseEnrollment-s.manage.microsoft.com** : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’adresse de messagerie.

    **EnterpriseRegistration.windows.net** : prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

  2.  Dans la [console d’administration Intune](http://manage.microsoft.com), cliquez sur **Administration**&gt; **Gestion des appareils mobiles**&gt; **Windows**.
  ![Boîte de dialogue Gestion des appareils Windows](../media/enroll-intune-winenr.png)
  3.  Tapez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis cliquez sur **Auto-détection de test**.

### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


