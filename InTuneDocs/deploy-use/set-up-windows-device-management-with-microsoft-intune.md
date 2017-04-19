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
ms.sourcegitcommit: 771aed4e1c57171183b9a9ea7d9e0f702dc1859c
ms.openlocfilehash: f6014c5500b05762d123b2285ef859d67382e402
ms.lasthandoff: 04/06/2017


---

# <a name="set-up-windows-device-management"></a>Configurer la gestion des appareils Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pour configurer l’inscription pour les appareils Windows, utilisez l’une des méthodes suivantes :

- [**Inscription automatique de Windows 10 avec Azure Active Directory Premium**](#set-up-windows-10-and-windows-10-mobile-automatic-enrollment-with-azure-active-directory-premium)
 -  Cette méthode est disponible uniquement pour les appareils Windows 10.
 -  Vous devez disposer d’Azure Active Directory Premium pour utiliser cette méthode.
 -  Si vous choisissez de ne pas activer l’inscription automatique, utilisez la méthode d’inscription pour Windows 8.1 et Windows Phone 8.1.

- [**Inscription sans inscription automatique d’Azure AD Premium**](#enable-windows-enrollment-without-azure-ad-premium)
 - Vous devez utiliser cette méthode pour inscrire des appareils Windows 8.1 et Windows Phone 8.1.
 - Vous pouvez utiliser cette méthode pour les appareils Windows 8.1 et versions ultérieures si vous ne souhaitez pas utiliser Azure Active Directory (AD) Premium.

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Activer l’inscription de Windows sans inscription automatique
Vous pouvez permettre aux utilisateurs d’installer et d’inscrire leurs appareils sans passer par l’inscription automatique Azure AD Premium. Une fois que vous avez attribué une licence à un compte d’utilisateur, celui-ci peut ajouter ce compte à un appareil Windows et donner son accord pour l’inscription de l’appareil à la gestion. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans entrer un nom de serveur.

**Étape 1 : Créer des enregistrements CNAME** (facultatif)<br>
Créez des enregistrements de ressources CNAME DNS pour le domaine de votre entreprise. Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com.

Bien que la création d’entrées DNS CNAME soit facultative, les enregistrements CNAME facilitent l’inscription pour les utilisateurs. Si aucun enregistrement CNAME d’inscription n’est trouvé, les utilisateurs sont invités à taper le nom du serveur de gestion des appareils mobiles (enrollment.manage.microsoft.com).

S'il existe plusieurs domaines vérifiés, créez un enregistrement CNAME pour chaque domaine. Ces enregistrements doivent contenir les informations suivantes :

Les enregistrements de ressources CNAME doivent avoir les informations suivantes :

|TYPE|Nom d'hôte|Pointe vers|TTL|
|--------|-------------|-------------|-------|
|CNAME|enterpriseenrollment.domaine_entreprise.com|EnterpriseEnrollment-s.manage.microsoft.com |1 heure|
|CNAME|EnterpriseRegistration.domaine_entreprise.com|EnterpriseRegistration.windows.net|1 heure|

`EnterpriseEnrollment-s.manage.microsoft.com` : prend en charge une redirection vers le service Intune avec reconnaissance du domaine à partir du nom de domaine de l’e-mail.

Si votre entreprise utilise plusieurs domaines pour les informations d’identification de l’utilisateur, créez des enregistrements CNAME pour chaque domaine.

Par exemple, si le site web de votre entreprise est contoso.com, vous devez créer un enregistrement CNAME dans DNS qui redirige EnterpriseEnrollment.contoso.com vers EnterpriseEnrollment-s.manage.microsoft.com. La propagation des modifications DNS peut prendre jusqu’à 72 heures. Vous ne pouvez pas vérifier la modification DNS dans Intune tant que l’enregistrement DNS ne s’est pas propagé.

**Étape 2 : Vérifier les enregistrements CNAME** (facultatif)<br>
Dans la [console d’administration Intune](http://manage.microsoft.com), cliquez sur **Admin** &gt; **Gestion des appareils mobiles** &gt; **Windows**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Indiquer aux utilisateurs comment inscrire des appareils Windows
Informez vos utilisateurs sur la manière d’inscrire leurs appareils Windows et sur les principes de gestion des appareils.
Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-windows). Vous pouvez également diriger les utilisateurs vers la rubrique [Que voit mon administrateur informatique quand j’inscris mon appareil ?](https://docs.microsoft.com/intune/enduser/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Pour plus d’informations sur les tâches de l’utilisateur final, consultez [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune).

### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription d’appareils dans Microsoft Intune](prerequisites-for-enrollment.md)

