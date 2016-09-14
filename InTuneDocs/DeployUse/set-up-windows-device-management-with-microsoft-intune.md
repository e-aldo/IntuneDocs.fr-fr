---
title: Configurer la gestion des appareils Windows avec Microsoft Intune | Microsoft Intune
description: "Activez la gestion des appareils mobiles pour les ordinateurs Windows, y compris les appareils Windows 10 avec Microsoft Intune."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ebb1648ab13d31a2ba1ab17615814be8dda8a08c
ms.openlocfilehash: 9b063c1e6b1ff5dcab16fce958ede49303284b18


---

# Configurer la gestion des appareils Windows

En tant qu’administrateur Intune, vous pouvez activer l’inscription et la gestion des PC Windows de deux manières :

- **[Inscription automatique auprès d’Azure AD](#azure-active-directory-enrollment)** -Les utilisateurs Windows 10 et Windows 10 Mobile inscrivent leurs appareils en y ajoutant un compte professionnel ou scolaire.
- **[Inscription par le biais du portail d’entreprise](#company-portal-app-enrollment)** - Les appareils Windows 8.1 et versions ultérieures sont inscrits en téléchargeant et installant l’application Portail d’entreprise, puis en entrant les informations d’identification de leur compte professionnel ou scolaire dans l’application.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## Configurer l’inscription par le biais de l’application Portail d’entreprise
Vous pouvez permettre aux utilisateurs d’inscrire leurs appareils en les installant et en les inscrivant avec l’application Portail d’entreprise Intune. La création d’un enregistrement CNAME DNS permet aux utilisateurs de se connecter et de s’inscrire à Intune sans saisir un nom de serveur.

1. **Configurer Intune**<br>
Si vous ne l’avez pas déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles](get-ready-to-enroll-devices-in-microsoft-intune.md#set-mobile-device-management-authority) sur **Microsoft Intune** et en configurant la gestion des appareils mobiles.

2. **Créer des enregistrements CNAME** (facultatif)<br>Créez des enregistrements de ressources DNS **CNAME** pour le domaine de votre entreprise pour simplifier l’inscription. Bien que la création d’entrées DNS CNAME soit facultative, elle facilite l’inscription pour les utilisateurs. Si aucun enregistrement CNAME d’inscription n’est trouvé, les utilisateurs sont invités à entrer manuellement le nom du serveur de gestion des appareils mobiles, `https://manage.microsoft.com`.  Ces enregistrements doivent contenir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 heure|

  `EnterpriseEnrollment-s.manage.microsoft.com` – Prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’adresse de messagerie.

  `EnterpriseRegistration.windows.net` – Prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

  Si votre entreprise utilise plusieurs domaines pour les informations d’identification de l’utilisateur, créez des enregistrements CNAME pour chaque domaine.

  Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

3.  **Vérifier un enregistrement CNAME**<br>Dans la [console d’administration Intune](http://manage.microsoft.com), cliquez sur **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows**. Tapez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis cliquez sur **Auto-détection de test**.

  ![Boîte de dialogue Gestion des appareils Windows](../media/enroll-intune-winenr.png)

4.  **Étapes facultatives**<br>L’étape **Ajouter des clés de déploiement (sideloading)** n’est pas nécessaire pour Windows 10. L’étape **Télécharger un certificat de signature de code** est uniquement nécessaire si vous voulez distribuer des applications métier à des appareils non disponibles depuis le Windows Store. [En savoir plus](set-up-windows-phone-8.0-management-with-microsoft-intune.md)

6.  **Informer les utilisateurs**<br>Vous devez informer vos utilisateurs sur la manière d’inscrire leurs appareils et sur les principes de gestion des appareils :
      - [Ce qu'il faut dire à vos utilisateurs finaux concernant l'utilisation de Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
      - [Conseils destinés aux utilisateurs relatifs aux appareils Windows](../enduser/using-your-windows-device-with-intune.md)

### Voir aussi
[Se préparer à inscrire des appareils dans Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO5-->


