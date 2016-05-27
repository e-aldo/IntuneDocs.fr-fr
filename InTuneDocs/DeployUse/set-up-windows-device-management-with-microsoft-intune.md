---
# required metadata

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

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Configurer la gestion des appareils Windows
Avec Intune, vous pouvez activer l’inscription d’appareils iOS personnels (dits « BYOD ») pour permettre aux ordinateurs Windows d’accéder à la messagerie et aux applications d’entreprise. Utilisé avec Azure Active Directory, il permet également, de manière rapide et sans intervention, de gérer de nouveaux appareils Windows 10, qui peuvent alors accéder aux ressources d’entreprise sans avoir à créer une nouvelle image de l’ordinateur. Une fois inscrits, les utilisateurs peuvent se connecter et leurs appareils peuvent être ciblés par la stratégie, les applications et les paramètres à l’aide de la console d’administration Intune. Vous pouvez également [Configurer la gestion de Windows Phone avec Microsoft Intune](set-up-windows-phone-management-with-microsoft-intune.md) ou [gérer des ordinateurs avec le logiciel client Intune](manage-windows-pcs-with-microsoft-intune.md) en utilisant le client Intune.

La création d’un enregistrement CNAME DNS permet aux utilisateurs de se connecter et de s’inscrire à Intune sans saisir un nom de serveur.

### Configurer la gestion des appareils Windows

  1.  Créez un enregistrement de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. S’il existe plusieurs domaines vérifiés, créez un enregistrement CNAME pour chaque domaine. Ces enregistrements doivent contenir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 heure|

    DNS record changes might take up to 72 hours to propagate. You cannot verify the DNS change in Intune until the DNS record propagates.

    **EnterpriseEnrollment-s.manage.microsoft.com** – Supports a redirect to the Intune service with domain recognition from the email’s domain name

    **EnterpriseRegistration.windows.net** – Supports Windows 8.1 and Windows 10 Mobile devices that will register with Azure Active Directory using their work or school account

  2.  Dans la [console d’administration Intune](http://manage.microsoft.com), cliquez sur **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows**.
  ![Boîte de dialogue Gestion des appareils Windows](../media/enroll-intune-winenr.png)
  3.  Tapez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis cliquez sur **Auto-détection de test**.

### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


