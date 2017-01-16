---
title: "Configurer la gestion de Windows 10 Mobile et Windows Phone | Microsoft Docs"
description: "Activez la gestion des appareils mobiles pour les appareils Windows 10 Mobile ou Windows Phone avec Microsoft Intune."
keywords: 
author: staciebarker
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5615051-2dd1-453b-9872-d3fdcefb2cb8
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: d58b2d57ec99add7bbc372584f0ecc430830530a


---


# <a name="set-up-windows-phone-and-windows-10-mobile-management-with-microsoft-intune"></a>Configurer la gestion de Windows 10 Mobile et Windows Phone avec Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

En tant qu’administrateur Intune, vous pouvez activer l’inscription et la gestion des appareils Windows 10 Mobile et Windows Phone de deux manières :

- **[Inscription automatique auprès d’Azure Active Directory](#azure-active-directory-enrollment)** - Les utilisateurs Windows 10 et Windows 10 Mobile inscrivent leurs appareils en y ajoutant un compte professionnel ou scolaire.
- **[Inscription par le biais du portail d’entreprise](#company-portal-app-enrollment)** - Les utilisateurs Windows Phone 8.1 et versions ultérieures inscrivent leurs appareils en téléchargeant et installant l’application Portail d’entreprise, puis en entrant les informations d’identification de leur compte professionnel ou scolaire dans l’application.


[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="company-portal-app-enrollment"></a>Inscription par le biais de l’application Portail d’entreprise
Vous pouvez permettre aux utilisateurs d’installer et d’inscrire leurs appareils à l’aide de l’application Portail d’entreprise Intune. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans entrer un nom de serveur.

1.  **Configurer Intune**<br>Si ce n’est déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) sur **Microsoft Intune**, puis en configurant la gestion des appareils mobiles.

2.  **Créer des enregistrements CNAME** (facultatif)<br>Créez des enregistrements de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com.

    Bien que la création d’entrées DNS CNAME soit facultative, les enregistrements CNAME facilitent l’inscription pour les utilisateurs. Si aucun enregistrement CNAME d’inscription n’est trouvé, les utilisateurs sont invités à entrer manuellement le nom du serveur de gestion des appareils mobiles (https://manage.microsoft.com).

    Si vous avez un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers manage.microsoft.com. Nous vous recommandons donc de le remplacer par un CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers enterpriseenrollment-s.manage.microsoft.com. Cette modification est recommandée, car le point de terminaison manage.microsoft.com est désapprouvé pour les inscriptions dans une version ultérieure.

    S'il existe plusieurs domaines vérifiés, créez un enregistrement CNAME pour chaque domaine. Ces enregistrements doivent contenir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 heure|

  `EnterpriseEnrollment-s.manage.microsoft.com` : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’e-mail.

  `EnterpriseRegistration.windows.net` : prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

  Si votre entreprise utilise plusieurs domaines pour les informations d’identification de l’utilisateur, créez des enregistrements CNAME pour chaque domaine.

  Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

3.  **Vérifier un enregistrement CNAME**<br>Dans la [console d’administration Microsoft Intune](http://manage.microsoft.com), choisissez **Administration** &gt; **Gestion des appareils mobiles** &gt; **Windows Phone**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

    ![Boîte de dialogue Configurer la gestion des appareils mobiles pour Windows](../media/windows-phone-enrollment.png)

4.  **Étapes facultatives**<br>L’étape **Ajouter des clés de déploiement (sideloading)** n’est pas nécessaire pour Windows 10. L’étape de **chargement de certificat de signature de code** est uniquement nécessaire si vous voulez distribuer des applications métier non disponibles depuis le Windows Store pour des appareils.

5.  **Indiquez à vos utilisateurs comment inscrire leurs appareils de manière à ce qu’ils puissent accéder aux ressources de l’entreprise.**

    Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](../enduser/enroll-your-device-in-intune-windows.md). Vos utilisateurs peuvent également se référer à [Que peut voir votre administrateur informatique lorsque vous inscrivez votre appareil dans Intune ?](../enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).

    Pour plus d’informations sur les autres tâches de l’utilisateur final, consultez les articles suivants :
    - [Ce qu’il faut dire à vos utilisateurs finaux concernant l’utilisation de Microsoft Intune](what-to-tell-your-end-users-about-using-microsoft-intune.md)
    - [Conseils destinés aux utilisateurs relatifs aux appareils Windows](../enduser/using-your-windows-device-with-intune.md)

Aucun travail supplémentaire n’est requis sauf si vous déployez le Portail d’entreprise sur les appareils.  Les étapes 2 et 3 dans la console d’administration peuvent être ignorées en toute sécurité.



<!--HONumber=Dec16_HO2-->


