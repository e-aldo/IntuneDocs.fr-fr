---
title: Configurer la gestion des appareils Windows avec Microsoft Intune | Microsoft Docs
description: Activez la gestion des appareils mobiles pour les appareils Windows avec Microsoft Intune.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9a18c0fe-9f03-4e84-a4d0-b63821bf5d25
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: f66bc5a26f137f62defef4a83a36b22247be4ec1
ms.lasthandoff: 03/22/2017


---

# <a name="set-up-windows-device-management"></a>Configurer la gestion des appareils Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour configurer l’inscription pour les appareils Windows, utilisez une des méthodes suivantes :

- [**Inscription automatique de Windows 10 et Windows 10 Mobile avec Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Cette méthode s’applique uniquement aux appareils Windows 10 et Windows 10 Mobile.
 -  Vous devez disposer d’Azure Active Directory Premium pour utiliser cette méthode. Sinon, utilisez la méthode d’inscription pour Windows 8.1 et Windows Phone 8.1.
 -  Si vous choisissez de ne pas activer l’inscription automatique, utilisez la méthode d’inscription pour Windows 8.1 et Windows Phone 8.1.


- [**Inscription Windows 8.1 et Windows Phone 8.1 en configurant l’enregistrement CNAME**](#set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname)
 - Vous devez utiliser cette méthode pour inscrire des appareils Windows 8.1 et Windows Phone 8.1.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="set-up-windows-81-and-windows-phone-81-enrollment-by-configuring-cname"></a>Configuration de l’inscription Windows 8.1 et Windows Phone 8.1 en configurant l’enregistrement CNAME
Vous pouvez permettre aux utilisateurs d’installer et d’inscrire leurs appareils à l’aide du Portail d’entreprise Intune. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans entrer un nom de serveur.

### <a name="step-1-set-up-intune"></a>Étape 1 : Configurer Intune

Si ce n’est déjà fait, préparez la gestion des appareils mobiles en [définissant l’autorité de gestion des appareils mobiles (MDM)](prerequisites-for-enrollment.md#step-2-set-mdm-authority) sur **Microsoft Intune**, puis en configurant la gestion des appareils mobiles.

### <a name="step-2-create-cnames-optional"></a>Étape 2 : Créer des enregistrements CNAME (facultatif)

Créez des enregistrements de ressources **CNAME** DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com.


   Bien que la création d’entrées DNS CNAME soit facultative, les enregistrements CNAME facilitent l’inscription pour les utilisateurs. Si aucun enregistrement CNAME d’inscription n’est trouvé, les utilisateurs sont invités à taper le nom du serveur de gestion des appareils mobiles (enrollment.manage.microsoft.com).

   Les enregistrements de ressources CNAME doivent avoir les informations suivantes :

  |TYPE|Nom d'hôte|Pointe vers|TTL|
  |--------|-------------|-------------|-------|
  |CNAME|enterpriseenrollment.domaine_entreprise.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
  |CNAME|EnterpriseRegistration.domaine_entreprise.com|EnterpriseRegistration.windows.net|1 heure|

  `EnterpriseEnrollment-s.manage.microsoft.com` : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’e-mail.

  `EnterpriseRegistration.windows.net` : prend en charge les appareils Windows 8.1 et Windows 10 Mobile qui s’inscrivent auprès d’Azure Active Directory avec leur compte professionnel ou scolaire.

  Si votre entreprise utilise plusieurs domaines pour les informations d’identification de l’utilisateur, créez des enregistrements CNAME pour chaque domaine.

  Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

### <a name="step-3-verify-cname"></a>Étape 3 : Vérifier un enregistrement CNAME

Dans la [console d’administration Intune](http://manage.microsoft.com), cliquez sur **Admin** &gt; **Gestion des appareils mobiles** &gt; **Windows**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

### <a name="step-4-tell-your-users-how-to-enroll-their-devices-and-what-to-expect-after-theyre-brought-into-management"></a>Étape 4 : Dire à vos utilisateurs comment inscrire leurs appareils et quels sont les principes de gestion des appareils.

   Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows).

   Pour plus d’informations sur les tâches de l’utilisateur final, consultez [Guide pratique pour former vos utilisateurs finaux à Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune) et [Conseils destinés aux utilisateurs relatifs aux appareils Windows](https://docs.microsoft.com/intune-user-help/using-your-windows-device-with-intune).

### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription d’appareils dans Microsoft Intune](prerequisites-for-enrollment.md)

