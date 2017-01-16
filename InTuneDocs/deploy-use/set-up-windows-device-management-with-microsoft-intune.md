---
title: Configurer la gestion des appareils Windows avec Microsoft Intune | Microsoft Docs
description: "Activez la gestion des appareils mobiles pour les ordinateurs Windows, y compris les appareils Windows 10 avec Microsoft Intune."
keywords: 
author: staciebarker
manager: stabar
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 31d58d9973cca4023186731a5411c9c9e830e32a
ms.openlocfilehash: e24251a066349e23beb94b75a66c5710ba7e41f1


---

# <a name="set-up-windows-device-management"></a>Configurer la gestion des appareils Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

En tant qu’administrateur Intune, vous pouvez activer l’inscription et la gestion des PC Windows de deux manières :

- **[Inscription automatique auprès d’Azure Active Directory](#azure-active-directory-enrollment)** - Les utilisateurs Windows 10 et Windows 10 Mobile inscrivent leurs appareils en y ajoutant un compte professionnel ou scolaire.

- **[Inscription par le biais du portail d’entreprise](#set-up-company-portal-app-enrollment)** - Les utilisateurs Windows 8.1 et versions ultérieures inscrivent leurs appareils en téléchargeant et installant l’application Portail d’entreprise, puis en entrant les informations d’identification de leur compte professionnel ou scolaire dans l’application.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-company-portal-app-enrollment"></a>Configurer l’inscription par le biais de l’application Portail d’entreprise
Vous pouvez permettre aux utilisateurs d’installer et d’inscrire leurs appareils à l’aide de l’application Portail d’entreprise Intune. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans entrer un nom de serveur.

1. **Configurer Intune**<br>
Si ce n’est déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) sur **Microsoft Intune**, puis en configurant la gestion des appareils mobiles.

2. **Créer des enregistrements CNAME** (facultatif)<br>Créez des enregistrements de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers enterpriseenrollment.manage.microsoft.com.

    Si vous avez un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers manage.microsoft.com. Nous vous recommandons donc de le remplacer par un CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers enterpriseenrollment-s.manage.microsoft.com. Cette modification est recommandée, car le point de terminaison manage.microsoft.com est désapprouvé pour les inscriptions dans une version ultérieure.

    Les enregistrements de ressources CNAME doivent avoir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 heure|

  `EnterpriseEnrollment-s.manage.microsoft.com` : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’e-mail.

  `EnterpriseRegistration.windows.net` : prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

  Si votre entreprise utilise plusieurs domaines pour les informations d’identification de l’utilisateur, créez des enregistrements CNAME pour chaque domaine.

  Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

3.  **Vérifier un enregistrement CNAME**<br>Dans la [console d’administration Intune](http://manage.microsoft.com), cliquez sur **Admin** &gt; **Gestion des appareils mobiles** &gt; **Windows**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

4.  **Étapes facultatives**<br>L’étape **Ajouter des clés de déploiement (sideloading)** n’est pas nécessaire pour Windows 10. L’étape **Télécharger un certificat de signature de code** est uniquement nécessaire si vous voulez distribuer des applications métier non disponibles depuis le Windows Store à des appareils.

6.  **Informez vos utilisateurs sur la manière d’inscrire leurs appareils et sur les principes de gestion des appareils.**

    Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows).

    Pour plus d’informations sur les tâches de l’utilisateur final, consultez [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune).


### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription d’appareils dans Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Dec16_HO3-->


