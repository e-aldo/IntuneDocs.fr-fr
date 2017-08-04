---
title: "Configurer la gestion des périphériques Windows avec Microsoft Intune"
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
ms.openlocfilehash: 9066414bcef1ba312db64aef077db8f8bfbbdb44
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/03/2017
---
# <a name="set-up-windows-device-management"></a>Configurer la gestion des appareils Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Cette rubrique aide les administrateurs informatiques à simplifier l’inscription de Windows pour leurs utilisateurs.  Les appareils Windows peuvent être inscrits sans aucune étape supplémentaire, mais vous pouvez faciliter l’inscription pour les utilisateurs.

Deux facteurs déterminent la manière dont vous pouvez simplifier l’inscription des appareils Windows :
- **Utilisez-vous Azure Active Directory Premium ?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) est inclus avec Enterprise Mobility + Security et d’autres plans de licence.
- **Quelles versions des clients Windows allez-vous inscrire ?** <br>Les appareils Windows 10 peuvent s’inscrire automatiquement quand vous ajoutez un compte professionnel ou scolaire. L’inscription des versions antérieures doit s’effectuer à l’aide de l’application Portail d’entreprise.

||**Azure AD Premium**|**Autre AD** |
|----------|---------------|---------------|  
|**Windows 10**|[Inscription automatique](#enable-windows-10-automatic-enrollment) |[Inscription d’utilisateur](#enable-windows-enrollment-without-automatic-enrollment)|
|**Versions précédentes de Windows**|[Inscription d’utilisateur](#enable-windows-enrollment-without-automatic-enrollment)|[Inscription d’utilisateur](#enable-windows-enrollment-without-automatic-enrollment)|

[!INCLUDE[AAD-enrollment](../includes/win10-automatic-enrollment-aad.md)]

## <a name="enable-windows-enrollment-without-automatic-enrollment"></a>Activer l’inscription de Windows sans inscription automatique
Vous pouvez permettre aux utilisateurs d’inscrire leurs appareils sans passer par l’inscription automatique Azure AD Premium. Une fois que vous affectez des licences, les utilisateurs peuvent s’inscrire après avoir ajouté leur compte professionnel sur leurs appareils personnels ou après avoir connecté leurs appareils d’entreprise à votre compte Azure AD. La création d’un alias DNS (type d’enregistrement CNAME) simplifie l’inscription des appareils pour les utilisateurs. Si vous créez des enregistrements de ressources CNAME DNS, les utilisateurs se connectent et s’inscrivent à Intune sans avoir à entrer le nom du serveur Intune.

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
Dans la [console d’administration Intune](https://manage.microsoft.com), cliquez sur **Admin** &gt; **Gestion des appareils mobiles** &gt; **Windows**. Entrez l’URL du domaine vérifié du site web de l’entreprise dans la zone **Spécifiez un nom de domaine vérifié**, puis choisissez **Auto-détection de test**.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Indiquer aux utilisateurs comment inscrire des appareils Windows
Informez vos utilisateurs sur la manière d’inscrire leurs appareils Windows et sur les principes de gestion des appareils.
Pour obtenir des instructions d’inscription pour l’utilisateur final, consultez [Inscrire un appareil Windows dans Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Vous pouvez également diriger les utilisateurs vers la rubrique [Que voit mon administrateur informatique quand j’inscris mon appareil ?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows).

Pour plus d’informations sur les tâches de l’utilisateur final, consultez [Ressources concernant l’expérience utilisateur final avec Microsoft Intune](/intune/end-user-educate).

### <a name="see-also"></a>Voir aussi
[Prérequis pour l’inscription d’appareils dans Microsoft Intune](prerequisites-for-enrollment.md)
